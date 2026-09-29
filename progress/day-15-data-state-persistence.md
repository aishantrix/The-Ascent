# Day 15 — Data, State & Persistent Lead Records

## Objective

Understand workflow state, persistent storage, and the difference between AI classification and business lifecycle state.

## Key Concepts

- Workflow data exists within an execution unless explicitly stored.
- Persistent storage allows lead information and AI results to be retained.
- AI classification describes what the AI concludes about a lead.
- Business status describes what is happening with the lead operationally.
- These two dimensions should remain separate.

## AI Qualification

- Lead Score
- Category
- Confidence

## Business Lifecycle

- Processed
- Priority Follow-up
- Nurture
- Converted
- Lost

A lead can be Hot + Priority Follow-up or Hot + Converted.

## Implementation

Created a Google Sheet:

AI Lead Status Tracker

Connected it to n8n using:

Google Sheets → Append Row

Stored:

- Lead Name
- Business
- Service Required
- Budget
- Urgency
- Lead Score
- Category
- Confidence
- Status
- Timestamp

## Testing

Tested with a valid lead and confirmed that the row was successfully written to Google Sheets.

The test lead was then manually changed from:

Processed → Priority Follow-up

This demonstrated that AI classification and business lifecycle status represent different dimensions.

## Key Lesson

AI classification is an assessment.

Business status is an evolving operational state.

## Status

Completed
