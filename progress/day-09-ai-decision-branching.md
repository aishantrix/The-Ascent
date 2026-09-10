# Day 9 — AI Decision Branching Workflow

**Status:** Completed ✅  
**Date:** 7 September 2026

## Objective

Connect AI classification to workflow decision logic so that an AI-generated result can determine what action the automation should take.

## Core Mental Model

> AI interprets → Workflow decides → Action happens

The AI analyzes the lead and produces a classification. The workflow then uses that result to route the lead into the appropriate action path.

---

## Workflow Built

```text
Manual Trigger
      ↓
Edit Fields — Lead Data
      ↓
Message a Model — AI Analysis
      ↓
IF — Decision
   ↙       ↘
TRUE       FALSE
 ↓           ↓
Priority    Nurture /
Follow-up   Low Priority
