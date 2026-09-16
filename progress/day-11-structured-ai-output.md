# Day 11 — Structured AI Output

## Objective

Convert the AI lead qualification response from free-form text into predictable structured data that can be consumed by workflow logic.

## Architecture

Manual Trigger
→ Edit Fields (Lead Data)
→ Message a Model
→ Edit Fields (Extract Category)
→ IF (category = Hot)
→ TRUE: Priority Follow-up
→ FALSE: Nurture / Low Priority

## What I Learned

- Structured output follows a defined schema.
- Unstructured output is free-form text and is harder for automation logic to consume reliably.
- Workflow automation needs predictable fields so individual values can be used in conditions.
- `category` is a decision field.
- `confidence` represents the AI's confidence in its classification, not the probability of conversion.
- `missing_information` helps identify incomplete inputs instead of encouraging the AI to assume missing facts.
- AI interprets; workflow logic decides and routes.

## Structured Output Schema

```json
{
  "type": "object",
  "properties": {
    "lead_score": {
      "type": "number"
    },
    "category": {
      "type": "string",
      "enum": ["Hot", "Warm", "Cold", "Human Review"]
    },
    "reason": {
      "type": "string"
    },
    "missing_information": {
      "type": "string"
    },
    "recommended_action": {
      "type": "string"
    },
    "confidence": {
      "type": "string",
      "enum": ["High", "Medium", "Low"]
    }
  },
  "required": [
    "lead_score",
    "category",
    "reason",
    "missing_information",
    "recommended_action",
    "confidence"
  ],
  "additionalProperties": false
}
