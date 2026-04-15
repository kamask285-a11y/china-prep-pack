# MVP PRD

## Product name
China Prep Pack

## Product type
A personalized pre-departure travel prep tool for first-time international travelers visiting China.

---

# 1. Product goal

The MVP should help a first-time traveler to China answer four practical questions:

1. What should I prepare before I leave?
2. What matters most for someone like me?
3. What should I do on arrival day?
4. How can I handle basic communication situations with less stress?

The product should reduce uncertainty, increase readiness, and create a feeling of confidence before departure.

---

# 2. Target user

Primary target:

- first-time travelers to China
- English-speaking users
- limited or no Chinese ability
- free or semi-independent travelers
- smartphone users

Secondary support:

- travelers with food restrictions
- solo travelers
- lower-tech users who still want digital guidance

---

# 3. MVP scope

## Included in MVP
- onboarding form
- personalized checklist
- arrival-day guide
- communication cards
- personalized risk summary
- save or export support

## Excluded from MVP
- booking flights or hotels
- real-time navigation
- live attraction or restaurant recommendation engine
- community content or social posting
- full multi-day itinerary planner
- heavy account system

---

# 4. User flow

## Step 1: landing page
The user understands what the product does and starts onboarding.

## Step 2: onboarding form
The user enters trip details, profile details, and main concerns.

## Step 3: generation
The system filters tasks, applies rules, selects cards, and generates a personalized output pack.

## Step 4: results page
The user reviews a structured prep pack.

## Step 5: save or export
The user keeps the pack for later use during travel.

---

# 5. Core features

## F1. Onboarding form

### Goal
Collect enough information to personalize the output without creating too much friction.

### Input fields
Trip basics:
- nationality
- language
- first time in China
- trip length
- cities visiting

Traveler profile:
- solo / couple / family / friends
- Chinese ability
- technology comfort
- budget level

Restrictions and concerns:
- dietary restrictions
- religion needs
- main concerns such as payment, internet, transport, food, language, apps

### Requirements
- should feel light and fast
- should be finishable in 1-3 minutes
- every field should influence output logic

---

## F2. Personalized checklist

### Goal
Give the user a ranked set of tasks to complete before departure.

### Output sections
- Critical
- Important
- Optional

### Each task should include
- title
- why it matters
- risk if missing
- fallback option
- recommended timing

### Logic
Checklist results should vary meaningfully based on profile.

Examples:
- users with no Chinese should see communication tasks more prominently
- multi-city travelers should get transition tasks
- users with food restrictions should get dining preparation tasks earlier

---

## F3. Arrival-day guide

### Goal
Help the user navigate the first hours after arrival in China.

### Sections
- before landing
- at the airport
- getting to the hotel
- after check-in
- first meal
- first local step

### Requirements
- should be short and calming
- should focus only on the highest-value actions
- should not overwhelm the user with too many options

---

## F4. Communication cards

### Goal
Give the user practical bilingual cards for common travel situations.

### Initial card set
- driver card
- hotel check-in card
- ask-for-help card
- directions card
- food restriction card
- please speak slowly card
- payment problem card

### Requirements
- easy to show on a phone screen
- simple English and Chinese
- selected dynamically based on user profile

---

## F5. Personalized risk summary

### Goal
Make the user feel understood and highlight what matters most.

### Output examples
- You do not speak Chinese, so address and communication preparation matter more.
- You are traveling across multiple cities, so transfer planning matters more.
- You have dietary restrictions, so first-meal planning and food cards are more important.

### Requirements
- should not feel generic
- should connect clearly to user inputs
- should help the user focus, not scare them

---

## F6. Save or export support

### Goal
Allow the user to keep and reuse the prep pack during travel.

### MVP support
- saveable results page
- printable or export-friendly layout
- PDF export if feasible

### Requirements
- mobile-friendly
- easy to revisit
- useful offline if exported

---

# 6. Pages

## Page 1: Landing
Purpose:
- explain the product in seconds
- motivate the user to start

Key content:
- one-line value proposition
- short explanation
- call to action

## Page 2: Onboarding
Purpose:
- collect trip and profile information

Key content:
- step-by-step form
- clear field labels
- low-friction flow

## Page 3: Results
Purpose:
- present the personalized prep pack

Key sections:
- summary
- priority checklist
- arrival-day guide
- communication cards
- warnings and tips

## Page 4: Export
Purpose:
- save or download the pack

---

# 7. Content system dependencies

The MVP depends on three structured content layers:

1. task library
2. rules and priority logic
3. communication card library

AI should not invent everything freely.
It should work on top of structured content.

---

# 8. Personalization logic

The system should adapt output based on:

- first time in China
- Chinese ability
- travel party
- dietary restrictions
- religion needs
- technology comfort
- number of cities
- primary concerns

This can be implemented first with rules, then supported by AI-generated wording.

---

# 9. Success criteria

The MVP is successful if:

- users complete onboarding
- users feel the pack is clearly personalized
- users save or export the result
- users say the product is more useful than a generic guide
- early users show willingness to pay for a full version

---

# 10. Build principles

The first version should be:

- narrow
- practical
- structured
- calm in tone
- mobile-friendly
- easy to iterate

The goal is not to build a super app.
The goal is to create a sharp and valuable wedge product.
