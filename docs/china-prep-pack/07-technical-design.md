# Technical Design

## Purpose
This document describes how the MVP should be implemented from a systems point of view.

The goal is not to over-engineer the first version.
The goal is to build a reliable, structured, fast-to-iterate product.

---

# 1. Technical strategy

The MVP should follow a simple principle:

**structure first, generation second**

That means:
- use structured traveler input
- filter and rank content using rules
- assemble an output pack from content assets
- use AI only for summary wording and user-facing narrative

This reduces hallucination risk and makes the system easier to debug.

---

# 2. High-level system modules

The MVP can be divided into six modules.

## Module 1: Frontend
Responsible for:
- landing page
- onboarding form
- results page
- save/export flow

## Module 2: Form handler
Responsible for:
- receiving user inputs
- validating required fields
- normalizing traveler profile data

## Module 3: Rule engine
Responsible for:
- filtering relevant tasks
- adjusting priorities
- selecting communication cards
- selecting risk templates
- determining arrival-day blocks

## Module 4: Content store
Responsible for:
- task library
- card library
- risk templates
- arrival blocks
- prompt templates

## Module 5: AI generation layer
Responsible for:
- personalized summary wording
- stitched risk explanation
- arrival-day narrative tone

## Module 6: Export layer
Responsible for:
- saveable results page
- printable or PDF output

---

# 3. Suggested stack

A practical first stack could be:

## Frontend
- Next.js
- React
- Tailwind CSS

## Backend
- Next.js API routes or lightweight Node service

## Content storage
- JSON files in repository for MVP

## AI layer
- LLM API for summary generation

## Optional later additions
- database for generated packs
- analytics layer
- payment integration

The important point is that the first version can work without a heavy backend.

---

# 4. Data model

## 4.1 UserProfile

Suggested fields:
- nationality
- language
- first_time_in_china
- trip_length_days
- cities
- travel_party
- chinese_level
- tech_comfort
- dietary_restrictions
- religion_needs
- primary_concerns

### Example shape
```json
{
  "nationality": "US",
  "language": "en",
  "first_time_in_china": true,
  "trip_length_days": 10,
  "cities": ["Beijing", "Shanghai", "Chengdu"],
  "travel_party": "solo",
  "chinese_level": "none",
  "tech_comfort": "high",
  "dietary_restrictions": [],
  "religion_needs": [],
  "primary_concerns": ["payments", "transport", "language"]
}
```

---

## 4.2 PrepTask

Suggested fields:
- id
- category
- title
- priority_default
- recommended_timing
- why_it_matters
- risk_if_missing
- fallback_option
- conditions

### Example shape
```json
{
  "id": "T001",
  "category": "transport",
  "title": "Save your hotel address in Chinese",
  "priority_default": "critical",
  "recommended_timing": "1 day before departure",
  "why_it_matters": "This is one of the most useful tools for first arrival.",
  "risk_if_missing": "Miscommunication with drivers or helpers.",
  "fallback_option": "Screenshot the booking page.",
  "conditions": {
    "chinese_level": ["none", "basic"]
  }
}
```

---

## 4.3 CommunicationCard

Suggested fields:
- card_id
- scenario
- title
- english_text
- chinese_text
- notes
- conditions

---

## 4.4 OutputPack

Suggested fields:
- profile_summary
- top_risks
- critical_tasks
- important_tasks
- optional_tasks
- arrival_guide
- communication_cards
- warnings

---

# 5. Content repository structure

Suggested repository layout:

```text
/content
  /tasks
    prep-tasks.json
  /cards
    communication-cards.json
  /risk-templates
    risks.json
  /arrival-blocks
    arrival-guide-blocks.json
  /prompts
    summary-prompt.md
    risk-summary-prompt.md
```

This allows content updates without changing application logic.

---

# 6. Rule engine design

## Goal
The rule engine should decide what appears in the pack and how strongly it is emphasized.

## Input
- UserProfile
- task library
- card library
- risk templates
- arrival guide blocks

## Output
- ranked task list
- selected card set
- selected risks
- selected arrival-day guide blocks

## Example rules

### Rule group: Chinese ability
If `chinese_level = none`
- raise priority of communication tasks
- include driver card
- include hotel check-in card
- include please-speak-slowly card

### Rule group: solo travel
If `travel_party = solo`
- raise emergency fallback tasks
- raise itinerary sharing task
- emphasize hotel detail access

### Rule group: dietary restrictions
If dietary restrictions are present
- include food restriction card
- raise meal planning tasks
- add food-related risk summary

### Rule group: low tech confidence
If `tech_comfort = low`
- reduce the number of app tasks
- simplify output wording
- prioritize essential over optional tools

### Rule group: multi-city trip
If number of cities > 1
- include transition tasks
- add transport complexity risk

---

# 7. Ranking logic

A simple scoring model is enough for MVP.

## Suggested approach
Each task starts with a base score from its default priority.

Example:
- critical = 100
- important = 60
- optional = 30

Then add or subtract points based on matching rules.

Example:
- if task is relevant to no-Chinese traveler: +25
- if task is relevant to solo traveler: +15
- if task is low-value for this profile: -20

After scoring:
- sort tasks by score
- keep top tasks for each band
- render the final set in structured groups

This is easier to debug than fully freeform generation.

---

# 8. AI generation design

## AI should receive
- normalized traveler profile
- selected top risks
- selected tasks
- selected arrival blocks
- selected communication cards

## AI should generate
- summary paragraph
- short risk explanation text
- concise arrival-day wording

## AI should not generate from scratch
- task inventory
- task ranking
- card content
- factual structure of the result

## Principle
AI adds readability, not core logic.

---

# 9. API design sketch

A simple API surface is enough.

## POST /generate-pack
Input:
- UserProfile

Output:
- OutputPack

## POST /export-pack
Input:
- OutputPack

Output:
- PDF or export artifact

## Optional GET /sample-pack/:persona
Input:
- persona id

Output:
- sample output pack

This is enough for MVP.

---

# 10. Save strategy

The first version can avoid complex user accounts.

Possible approaches:
- generate pack and keep in memory for session
- create shareable result id later
- support export without requiring sign-in

This lowers friction for validation.

---

# 11. Analytics events

Useful early events:
- landing_view
- onboarding_start
- onboarding_complete
- pack_generated
- export_clicked
- save_clicked
- paywall_view

These events will help validate real user behavior.

---

# 12. Build sequence

Recommended implementation order:

## Phase 1
- static pages
- onboarding form
- local JSON content store
- simple rule engine
- results page with dummy output

## Phase 2
- real output generation from profile
- AI summary layer
- communication card selection
- arrival guide generation

## Phase 3
- export
- analytics
- premium gating or payment tests

This keeps the system small and testable.
