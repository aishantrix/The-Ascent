# Day 7 — First Automation Workflow

## Objective
Build and test my first basic automation workflow using n8n.

## Workflow
Manual Trigger → Edit Fields

## Test Data

| Field | Value |
|---|---|
| Name | Rahul |
| Business | Jewellery |
| Service Required | Meta Ads |
| Budget | ₹50,000 |
| Urgency | 7 days |

## What I Built
Created a basic n8n workflow where a manual trigger starts the workflow and passes structured lead data through an Edit Fields node.

## Testing & Failure Experiments

### Test 1 — Missing Budget
Removed the budget value.

**Result:** Budget appeared as `null`.

**Learning:** Missing input values can result in null data and may need validation before further processing.

### Test 2 — Changed Urgency
Changed the urgency from `7 days` to a new value.

**Result:** The output reflected the updated value.

**Learning:** The workflow processes the current input data when executed.

### Test 3 — Renamed Field
Changed `Services Required` to `Service`.

**Result:** The output used the new field name.

**Learning:** Field names are part of the data structure and can affect downstream workflow steps.

## Key Takeaway
A workflow can successfully pass structured data, but changes or missing values can affect downstream processing. Real-world automations therefore require validation and error handling.

## Status
✅ Day 7 Complete
