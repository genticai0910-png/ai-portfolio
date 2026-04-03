# Conversation State Tracker

Track question coverage, detect evasion, and generate inline directives for AI-guided conversations.

## The Problem This Solves

AI phone agents forget what they've already asked. They re-ask questions. They don't notice when a caller is dodging. They can't adapt mid-conversation to resistance patterns. This tracker fixes all three.

## How It Works

```
                    ┌──────────────────┐
  Caller says  ───▶ │  State Tracker    │
  something         │                   │
                    │  ✓ Track answered │
                    │  ✓ Detect evasion │
                    │  ✓ Read emotion   │
                    │  ✓ Pick next Q    │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Inline Directive  │
                    │                   │
                    │ "YOUR NEXT        │
                    │  QUESTION: ..."   │
                    └────────┬─────────┘
                             │
                             ▼
                      Model generates
                      natural response
                      following directive
```

## `state_tracker.py`

```python
"""
Conversation State Tracker
Tracks coverage, evasion, and emotional state across multi-turn conversations.
Generates inline directives for AI-guided dialogue.

MIT License
"""

from dataclasses import dataclass, field
from enum import Enum
from typing import Optional


class QuestionStatus(Enum):
    PENDING = "pending"
    ASKED = "asked"
    ANSWERED = "answered"
    EVADED = "evaded"


class EmotionalState(Enum):
    NEUTRAL = "neutral"
    COOPERATIVE = "cooperative"
    HESITANT = "hesitant"
    FRUSTRATED = "frustrated"
    EMOTIONAL = "emotional"
    HOSTILE = "hostile"


@dataclass
class Question:
    id: str
    text: str
    priority: str  # "core" or "tail"
    status: QuestionStatus = QuestionStatus.PENDING
    ask_count: int = 0
    evasion_count: int = 0
    answer: Optional[str] = None

    @property
    def is_core(self) -> bool:
        return self.priority == "core"

    @property
    def needs_attention(self) -> bool:
        return self.status in (QuestionStatus.PENDING, QuestionStatus.EVADED)


@dataclass
class ConversationState:
    questions: list[Question]
    emotional_state: EmotionalState = EmotionalState.NEUTRAL
    turn_count: int = 0
    evasion_streak: int = 0
    rapport_score: float = 0.5  # 0.0 = hostile, 1.0 = fully cooperative

    @property
    def coverage(self) -> float:
        """Percentage of questions answered."""
        if not self.questions:
            return 0.0
        answered = sum(1 for q in self.questions if q.status == QuestionStatus.ANSWERED)
        return answered / len(self.questions)

    @property
    def core_coverage(self) -> float:
        """Percentage of core questions answered."""
        core = [q for q in self.questions if q.is_core]
        if not core:
            return 0.0
        answered = sum(1 for q in core if q.status == QuestionStatus.ANSWERED)
        return answered / len(core)

    @property
    def pending_core(self) -> list[Question]:
        return [q for q in self.questions if q.is_core and q.needs_attention]

    @property
    def pending_tail(self) -> list[Question]:
        return [q for q in self.questions if not q.is_core and q.needs_attention]


class StateTracker:
    def __init__(self, questions: list[dict]):
        """
        Initialize with a list of question definitions.

        questions: [{"id": "price", "text": "What price are you hoping for?", "priority": "core"}, ...]
        """
        self.state = ConversationState(
            questions=[
                Question(id=q["id"], text=q["text"], priority=q.get("priority", "tail"))
                for q in questions
            ]
        )

    def record_ask(self, question_id: str):
        """Record that a question was asked."""
        q = self._find_question(question_id)
        if q:
            q.status = QuestionStatus.ASKED
            q.ask_count += 1

    def record_answer(self, question_id: str, answer: str):
        """Record that a question was answered."""
        q = self._find_question(question_id)
        if q:
            q.status = QuestionStatus.ANSWERED
            q.answer = answer
            self.state.evasion_streak = 0
            self.state.rapport_score = min(1.0, self.state.rapport_score + 0.05)

    def record_evasion(self, question_id: str):
        """Record that the caller evaded a question."""
        q = self._find_question(question_id)
        if q:
            q.status = QuestionStatus.EVADED
            q.evasion_count += 1
            self.state.evasion_streak += 1
            self.state.rapport_score = max(0.0, self.state.rapport_score - 0.1)

    def update_emotion(self, state: EmotionalState):
        """Update detected emotional state."""
        self.state.emotional_state = state

    def advance_turn(self):
        """Increment turn counter."""
        self.state.turn_count += 1

    def generate_directive(self) -> str:
        """
        Generate an inline directive for the AI model.
        This is the core output — appended to the user's turn
        before the model generates its response.
        """
        state = self.state

        # High evasion → acknowledge and try softer approach
        if state.evasion_streak >= 2:
            next_q = self._pick_next_question(soft=True)
            if next_q:
                return (
                    f"YOUR NEXT QUESTION: The caller has been hesitant. "
                    f"Acknowledge their concern, then gently ask: {next_q.text} "
                    f"Frame it as helping them get the best outcome."
                )

        # Emotional caller → empathize first
        if state.emotional_state in (EmotionalState.EMOTIONAL, EmotionalState.FRUSTRATED):
            next_q = self._pick_next_question(soft=True)
            directive = "YOUR NEXT STEP: The caller is emotional. Validate their feelings first. "
            if next_q:
                directive += f"When ready, transition to: {next_q.text}"
            return directive

        # Hostile → de-escalate
        if state.emotional_state == EmotionalState.HOSTILE:
            return (
                "YOUR NEXT STEP: The caller is hostile. Do NOT push for information. "
                "De-escalate with empathy. If they remain hostile, offer to call back "
                "at a better time."
            )

        # Normal flow → ask next pending question
        next_q = self._pick_next_question()
        if next_q:
            return f"YOUR NEXT QUESTION: {next_q.text}"

        # All questions covered
        if state.core_coverage >= 0.8:
            return (
                "YOUR NEXT STEP: Core questions are covered. "
                "Summarize what you've learned and transition to the value proposition."
            )

        return "YOUR NEXT STEP: Continue the conversation naturally."

    def get_summary(self) -> dict:
        """Return a snapshot of conversation state."""
        return {
            "turn_count": self.state.turn_count,
            "coverage": round(self.state.coverage * 100, 1),
            "core_coverage": round(self.state.core_coverage * 100, 1),
            "emotional_state": self.state.emotional_state.value,
            "evasion_streak": self.state.evasion_streak,
            "rapport_score": round(self.state.rapport_score, 2),
            "questions": {
                q.id: {
                    "status": q.status.value,
                    "ask_count": q.ask_count,
                    "evasion_count": q.evasion_count,
                    "answered": q.answer is not None,
                }
                for q in self.state.questions
            },
        }

    # --- Internal ---

    def _find_question(self, question_id: str) -> Optional[Question]:
        for q in self.state.questions:
            if q.id == question_id:
                return q
        return None

    def _pick_next_question(self, soft: bool = False) -> Optional[Question]:
        """
        Pick the next question to ask.
        Priority: core pending > core evaded > tail pending > tail evaded
        If soft=True, prefer questions that haven't been evaded multiple times.
        """
        candidates = []

        # Core pending first
        candidates.extend(
            sorted(
                [q for q in self.state.pending_core if q.status == QuestionStatus.PENDING],
                key=lambda q: q.ask_count,
            )
        )

        # Core evaded (retry)
        candidates.extend(
            sorted(
                [q for q in self.state.pending_core if q.status == QuestionStatus.EVADED],
                key=lambda q: q.evasion_count,
            )
        )

        # Tail questions
        candidates.extend(
            sorted(
                self.state.pending_tail,
                key=lambda q: (q.evasion_count, q.ask_count),
            )
        )

        if soft:
            # In soft mode, skip questions evaded 2+ times
            candidates = [q for q in candidates if q.evasion_count < 2] or candidates

        return candidates[0] if candidates else None


# --- Demo ---
if __name__ == "__main__":
    # Define qualification questions
    questions = [
        {"id": "price", "text": "What price are you hoping to get?", "priority": "core"},
        {"id": "motivation", "text": "What's driving the decision to sell?", "priority": "core"},
        {"id": "timeline", "text": "What's your ideal timeline?", "priority": "core"},
        {"id": "condition", "text": "How would you describe the property's condition?", "priority": "core"},
        {"id": "agent", "text": "Are you currently working with an agent?", "priority": "core"},
        {"id": "decision_maker", "text": "Is there anyone else involved in the decision?", "priority": "tail"},
    ]

    tracker = StateTracker(questions)

    # Simulate a conversation
    print("Turn 1:", tracker.generate_directive())

    tracker.record_ask("price")
    tracker.record_answer("price", "Around 350k")
    tracker.advance_turn()

    print("Turn 2:", tracker.generate_directive())

    tracker.record_ask("motivation")
    tracker.record_evasion("motivation")  # Caller dodged
    tracker.advance_turn()

    print("Turn 3:", tracker.generate_directive())

    tracker.record_evasion("motivation")  # Dodged again
    tracker.update_emotion(EmotionalState.HESITANT)
    tracker.advance_turn()

    print("Turn 4:", tracker.generate_directive())

    print("\nSummary:", tracker.get_summary())
```

## Why This Matters

Traditional approach: Put all instructions in the system prompt and hope the model remembers them 10 turns later. **It doesn't.**

This approach: The state tracker observes the conversation in real-time and tells the model exactly what to do next. The model only needs to be good at following a single instruction per turn — which even small models do well.

**Result:** Base Qwen 2.5 1.5B (no fine-tuning) achieves 7.2/10 question coverage using inline directives alone.

---

[← Back to Open Source Index](../README.md)
