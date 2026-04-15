# Information Architecture and Copy

## Purpose
This document defines how the MVP should be structured from the user's point of view.

It covers:
- page structure
- information hierarchy
- interface modules
- initial product copy direction

The goal is to make the product feel calm, useful, and easy to navigate.

---

# 1. Product tone

The product voice should be:

- calm
- practical
- reassuring
- direct
- not overly promotional
- not overly robotic

The user should feel that the product is helping them prepare, not selling them travel excitement.

Good tone examples:
- Here is what matters most for your trip.
- These are the most important things to prepare before you go.
- Keep this ready for your first day.

Avoid:
- exaggerated marketing language
- vague inspiration
- overly long explanations
- generic travel-blog wording

---

# 2. Information architecture overview

The MVP should have four main pages.

## Page 1: Landing
Purpose: explain the product and encourage the user to start.

## Page 2: Onboarding form
Purpose: collect key profile and trip inputs.

## Page 3: Results page
Purpose: present the personalized prep pack.

## Page 4: Save/export
Purpose: help the user keep the pack for later use.

---

# 3. Page 1: Landing

## Main purpose
The landing page should answer three questions quickly:

1. What is this?
2. Is it for me?
3. What will I get?

## Recommended structure
- hero section
- value explanation
- output preview
- call to action

## Suggested copy

### Hero title
Get ready for China with a personalized prep pack

### Hero subtitle
For first-time travelers to China. Prepare payments, internet, transport, communication, and arrival-day essentials in one place.

### CTA
Build my prep pack

### Supporting value points
- Personalized checklist
- Arrival-day guide
- Ready-to-use communication cards
- Advice based on your travel profile

---

# 4. Page 2: Onboarding form

## Main purpose
Collect only the inputs that matter for personalization.

## Structure
A step-by-step form is recommended.

### Step 1: About your trip
Fields:
- Is this your first time in China?
- How long is your trip?
- Which cities are you visiting?
- What language do you prefer?

### Step 2: About you
Fields:
- Are you traveling solo, as a couple, or with others?
- How comfortable are you with Chinese?
- How comfortable are you with travel apps and digital tools?

### Step 3: Restrictions and concerns
Fields:
- Do you have any food restrictions?
- Do you have any religious travel needs?
- What are you most concerned about?

## Suggested form copy

### Page title
Tell us about your trip

### Step title example
What should we help you prepare for?

### Submit CTA
Generate my prep pack

## UX rules
- keep the form lightweight
- avoid unnecessary free-text fields
- every input should affect output logic
- prefer multiple choice over open-ended writing

---

# 5. Page 3: Results page

## Main purpose
Present a structured output that feels immediately useful.

## Recommended section order
1. Summary
2. Priority checklist
3. Arrival-day guide
4. Communication cards
5. Warnings and tips
6. Save/export CTA

---

## Section 1: Summary

### Goal
Help the user understand what matters most before reading details.

### Content
- short traveler profile description
- top 2-3 risk reminders
- a confidence-building sentence

### Suggested labels
- Your travel profile
- What matters most for your trip
- Your top preparation priorities

---

## Section 2: Priority checklist

### Goal
Show the user what to do, in order of importance.

### Structure
- Critical
- Important
- Optional

### Each checklist item should show
- title
- short reason
- fallback option or note

### Suggested heading
Your priority checklist

### Suggested helper text
These are the most useful things to prepare before your trip.

---

## Section 3: Arrival-day guide

### Goal
Reduce stress during the first few hours after landing.

### Structure
- Before landing
- At the airport
- Getting to your hotel
- After check-in
- First meal
- First local step

### Suggested heading
Your arrival-day guide

### Suggested helper text
Use this guide to keep your first day simple and manageable.

---

## Section 4: Communication cards

### Goal
Provide instantly usable support for common situations.

### Suggested heading
Your communication cards

### Suggested helper text
Save these on your phone and show them when needed.

### Card UI suggestion
Each card should include:
- title
- English line
- Chinese line
- optional usage note

---

## Section 5: Warnings and tips

### Goal
Surface profile-specific reminders without overwhelming the user.

### Suggested heading
Things to watch for

### Examples
- Keep your hotel address easy to show.
- Do not rely on only one payment method.
- Keep your first meal simple on arrival day.

---

## Section 6: Save/export CTA

### Goal
Encourage reuse during the trip.

### Suggested CTA labels
- Save this prep pack
- Download as PDF
- Keep this for your first day

---

# 6. Page 4: Save/export

## Main purpose
Support future access and offline use.

## Suggested content
- download option
- print-friendly option
- reminder to save key cards and address details

## Suggested copy
Save this prep pack before your trip so you can open it quickly when needed.

---

# 7. Copywriting principles

## Principle 1: clarity first
Use short sentences and clear verbs.

## Principle 2: guidance over explanation
Show the user what to do next.

## Principle 3: reassurance without hype
The product should feel steady, not dramatic.

## Principle 4: profile relevance
The copy should reflect the user's real situation.

## Principle 5: mobile readability
Write for quick scanning on a phone.

---

# 8. Microcopy examples

## CTA examples
- Build my prep pack
- Generate my prep pack
- Save this prep pack

## Loading state examples
- Building your personalized prep pack
- Organizing what matters most for your trip

## Empty state examples
- No food-related cards are needed for this trip profile.
- No extra transition steps are needed for a single-city trip.

## Error state examples
- Something went wrong while generating your pack. Please try again.
- We could not build your pack from the current input. Please review your trip details.

---

# 9. UI priority rule

If screen space is limited, the product should prioritize:

1. Summary
2. Critical checklist tasks
3. Arrival-day guide
4. Communication cards
5. Everything else

This keeps the most useful content visible first.
