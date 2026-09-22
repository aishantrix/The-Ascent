# Day 12 — Human-in-the-Loop & AI Escalation

## Objective

Implement Human-in-the-Loop (HITL) logic in the AI lead qualification workflow and understand when AI should escalate a case to a human.

## Concept

Human-in-the-Loop means designing an AI workflow so that a human can review, approve, override, or handle certain decisions before consequential actions are taken.

AI should not automatically make every business decision because some situations involve incomplete information, ambiguity, risk, context, or human judgment.

## Workflow

Lead
→ AI Model
→ Structured Output
→ Category + Confidence
→ Decision Logic
→ Automated Action OR Human Review

## HITL Rules

Human Review is triggered when:

1. `category = Human Review`
2. `confidence = Low`

The workflow uses OR logic between these conditions.

## Testing

### Test 1 — Human Review category

The AI produced:

- Category: Human Review
- Confidence: Medium

The workflow correctly routed the lead to Human Review.

This demonstrated that explicit Human Review classification can trigger escalation even when confidence is not Low.

### Test 2 — Low confidence

A controlled test temporarily set confidence to Low.

Result:

`confidence = Low → TRUE → Human Review`

This confirmed that the confidence-based HITL condition works independently.

The manually set Low value was restored to the AI-generated confidence expression after testing.

## Debugging

The Human Review condition initially failed because of capitalization:

`Human review` ≠ `Human Review`

The issue was resolved by matching the exact category value.

## Key Learning

AI classification and AI confidence are separate signals.

A robust AI workflow can use either signal to determine when human intervention is required.

The goal is not to automate everything. The goal is to automate appropriate decisions while deliberately escalating ambiguous or uncertain cases.

## Day 12 Architecture

Lead
↓
AI Analysis
↓
Structured Output
├── category
└── confidence
↓
Decision Logic
├── Hot → Priority Follow-up
├── Human Review → Human Review
├── Low confidence → Human Review
└── Other → Nurture / Low Priority

## Status

Completed.
