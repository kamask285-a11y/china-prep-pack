# Content System

## Purpose
China Prep Pack depends on structured content, not only freeform AI text.

This document defines the content assets that power the MVP.

The purpose of the content system is to make output:

- consistent
- practical
- personalizable
- easier to maintain
- safer than full freeform generation

---

# 1. Core content layers

The MVP should use five main content layers.

## Layer 1: Prep task library
This is the main task inventory that powers the checklist.

Examples:
- save hotel address in Chinese
- prepare a backup payment method
- create an offline travel folder
- plan airport-to-hotel route

## Layer 2: Communication card library
This contains ready-to-show bilingual cards for real travel situations.

Examples:
- driver card
- hotel check-in card
- ask-for-help card
- food restriction card
- payment problem card

## Layer 3: Risk summary templates
These templates explain why certain areas matter more for a given traveler profile.

Examples:
- no Chinese ability risk
- multi-city complexity risk
- food restriction risk
- low-tech setup risk
- solo travel risk

## Layer 4: Arrival-day blocks
These are modular content blocks used to assemble the first-day guide.

Examples:
- before landing
- at the airport
- transport to hotel
- after check-in
- first meal
- first local step

## Layer 5: Summary generation inputs
These are the structured inputs passed to AI so the product can generate a calm, personalized summary.

---

# 2. Prep task library

## Purpose
The prep task library is the most important content asset in the MVP.

It should contain structured, reusable, filterable tasks.

## Required fields
Each task should include:

- `id`
- `category`
- `title`
- `priority_default`
- `recommended_timing`
- `why_it_matters`
- `risk_if_missing`
- `fallback_option`
- `conditions`

## Example categories
- documents
- payments
- internet
- apps
- transport
- accommodation
- communication
- food_culture
- emergency
- arrival_day

## Authoring rule
A task should not be vague.

Bad example:
- prepare properly before your trip

Good example:
- save your hotel address in Chinese
- prepare a backup payment method
- keep an offline copy of your bookings

## Content principle
A task should always feel actionable.
The user should understand:
- what to do
- why it matters
- what happens if it is skipped
- what to do if it fails

---

# 3. Communication card library

## Purpose
The card library gives the user high-confidence support in common real-world interactions.

## Required fields
Each card should include:

- `card_id`
- `scenario`
- `title`
- `english_text`
- `chinese_text`
- `notes`
- `conditions`

## Initial scenario set
- transport
- hotel
- help
- directions
- food ordering
- dietary restrictions
- payment issues
- connectivity questions

## Design rule
Cards should be:
- short
- legible on mobile
- realistic for spoken interaction
- safe to show to another person directly

## Product implication
Cards should not be shown to every user equally.
They should be prioritized based on:
- Chinese ability
- dietary restrictions
- main concerns
- arrival-day relevance

---

# 4. Risk summary templates

## Purpose
Risk templates turn profile differences into meaningful user-facing guidance.

## Why they matter
Users should feel:
- the product understands them
- the output is not generic
- they know what to focus on first

## Template examples

### No Chinese ability
You do not speak much Chinese, so destination visibility and communication support matter more for your trip.

### Multi-city travel
You are moving across multiple cities, so transport transitions and booking access matter more than usual.

### Dietary restrictions
You have food-related constraints, so meal planning and communication cards are more important for you.

### Low-tech confidence
You may benefit from fewer tools and clearer sequencing, rather than a large number of apps and options.

### Solo travel
Because you are traveling alone, backup planning and quick access to your key information matter more.

## Structure
A risk template should:
- mention the user trait
- explain why it matters
- guide attention without creating fear

---

# 5. Arrival-day content blocks

## Purpose
Arrival-day content should be modular instead of written from scratch every time.

## Block set
- before landing
- airport arrival
- transport selection
- destination display
- payment readiness
- check-in stabilization
- first meal simplification
- first small outing
- first-night review

## Rule
Each block should focus on one decision or one task cluster.
The first-day guide should feel short, calm, and ordered.

---

# 6. AI content generation boundaries

## AI should generate
- personalized summary wording
- natural-language risk summary
- stitched arrival-day narrative
- final user-facing tone adjustments

## AI should not invent freely
- task inventory
- card contents
- priority logic
- factual structure of the pack

## Principle
Structure first, language second.
This makes the product more reliable and easier to improve.

---

# 7. Content maintenance rules

## Rule 1
High-frequency scenarios come first.

## Rule 2
Any reusable logic should become structured content.

## Rule 3
When a user repeatedly needs the same explanation, create a template for it.

## Rule 4
Keep content conservative and practical.
Avoid overly broad or inspirational travel writing.

## Rule 5
Write for execution under stress, not for entertainment.

---

# 8. Recommended repository structure

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

This keeps content separate from application logic.

---

# 9. MVP content priority

For the first version, the highest-priority content assets are:

1. prep task library
2. communication cards
3. risk templates
4. arrival-day blocks

These four are enough to create a useful first product.
