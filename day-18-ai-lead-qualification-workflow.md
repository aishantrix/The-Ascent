# AI Lead Qualification System

An AI-powered business workflow that evaluates incoming leads, classifies their conversion potential, and automatically records qualification results.

## Problem
Businesses may lose potential customers due to delayed follow-ups and inconsistent lead prioritization.

## Solution
This workflow uses an AI model to assess incoming lead information, generate a structured qualification result, route the lead based on its category, and store the result in Google Sheets.

## Architecture

Manual Trigger → Lead Data → Message a Model → JSON Parsing → Conditional Routing → Status Assignment → Google Sheets

## Input Fields
- Name
- Business
- Business Type
- Service Required
- Budget
- Urgency
- Email

## AI Assessment
The model evaluates lead completeness, service demand, budget suitability, urgency, and purchase intent.

It returns:
- Lead score
- Category
- Reason
- Missing information
- Recommended action
- Confidence

## Lead Categories

| Category | Assigned Status |
|---|---|
| Hot | Priority Follow-up |
| Warm | Nurture |
| Cold | Low Priority |
| Human Review | Pending Manual Review |

Human Review is triggered when the category is Human Review or the model's confidence is Low.

## Technology
- n8n — Workflow automation
- AI language model — Lead assessment
- JavaScript — JSON parsing
- Google Sheets — Lead tracking and records

## Current Implementation Status
- [x] Manual trigger and lead input
- [x] AI qualification prompt
- [x] Structured AI response
- [x] JSON parsing using a Code node
- [x] Conditional routing structure
- [x] Branch-specific status assignment
- [x] Google Sheets integration
- [x] Timestamp mapping
- [ ] Validate all four routes
- [ ] Complete error recovery and failure logging

## Future Improvements
- Duplicate detection
- Automated follow-up notifications
- Conversion tracking
- Qualification accuracy evaluation
- Improved error monitoring

## Project Learning
This project demonstrates how AI, structured outputs, conditional logic, and workflow automation can be combined to solve a practical business problem.

*Note: This README describes the current implementation. Pending features are explicitly marked as incomplete.*
