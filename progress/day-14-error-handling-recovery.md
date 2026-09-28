# Day 14 — Workflow Error Handling & Recovery

## Objective

Build a reliable fallback mechanism so that AI/API failures do not result in lost leads.

## Core Concept

Automation failure does not mean lead failure.

A failed AI step should preserve the lead and route it to a recoverable human-review path.

## Architecture

Lead Input
↓
Validation
↓
AI Model
├── SUCCESS → Structured Output → Decision → Action
└── ERROR → Google Sheets → Human Recovery

## Fallback System

Google Sheets was used as the fallback storage mechanism.

The failure log stores:

- Lead Name
- Phone Number
- Email
- Business Type
- Service Required
- Budget
- Urgency
- Failure Reason
- Timestamp

Phone and email remain blank when those fields are not available in the current lead input.

## n8n Implementation

Configured the AI node to:

`Continue using error output`

Connected the AI Error output to:

`Google Sheets → Append Row`

A dedicated spreadsheet named:

`AI Lead Failure Log`

was created.

## Testing

### Test 1 — Controlled AI Failure

A temporary invalid expression was added to the AI prompt.

Result:

`Validation → AI Model → ERROR → Google Sheets`

The failed lead was successfully appended to the failure log.

### Test 2 — Normal Recovery

The intentional error was removed and the original AI prompt was restored.

Result:

`Validation → AI Model → Structured Output → Decision → TRUE → Priority Follow-up`

The normal workflow continued successfully.

## Important Debugging Lesson

Removing missing lead information does not necessarily test AI error handling.

For example, removing Budget triggered the validation/human-review path before the AI node.

To test error recovery, the AI node itself must fail.

## Key Takeaways

- AI workflows need explicit failure paths.
- Failed leads should never silently disappear.
- Error branches can preserve business data for later human review.
- Validation failures and AI execution failures are different types of failure.
- A production-ready workflow needs both successful execution and recoverability.

## Status

Completed.
