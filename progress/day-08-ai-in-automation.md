# Day 8 — AI Inside an Automation Workflow

## Objective

Learn how to integrate an AI model into an automation workflow so that structured lead data can be interpreted and classified.

## Workflow

Manual Trigger
→ Edit Fields
→ Message a Model
→ AI Qualification Output

## Sample Lead

- Name: Rahul
- Business: Jewellery
- Service Required: Meta Ads
- Budget: ₹50,000
- Urgency: 7 days

## AI Task

The AI was instructed to analyze:

- Budget
- Urgency
- Service required
- Completeness of information

The AI was asked to produce:

1. Lead Score
2. Category
3. Why
4. Missing Information
5. Recommended Action
6. Confidence

## Testing

The workflow was tested with:

1. Missing budget
2. Very low budget
3. Unknown urgency
4. Missing service requirement

## Observations

- The AI was able to interpret the lead information and classify the lead.
- Changes in the input affected the AI's output.
- Missing information should not be invented by the AI.
- AI interpretation and business decision rules should be treated as separate concepts.
- The current AI response is returned as text rather than separate structured fields.

## Key Learning

Day 7 focused on moving data through an automation workflow.

Day 8 added AI to the workflow so that the data could be interpreted and transformed into a useful qualification result.

## Architecture

Structured Data
→ AI Interpretation
→ Qualification Output

## Status

Completed
