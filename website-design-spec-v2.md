# Website Design Specification — Version 2
## Miami-Dade Lost & Found Dog Resource Hub
**Revised to reflect: dual Protocol + Hub architecture, ownership verification protocol, shareable deep links, language-first design**

---

## 1. WHAT THIS SITE IS

This site solves two distinct but related problems:

**Problem 1 — No structure or workflow.** When someone loses or finds a dog, there is no standard protocol the community follows. Everyone gives different advice. People freeze. Dogs are lost. The solution is a clear, legally-grounded, step-by-step protocol that becomes the community's shared answer — shareable as a single link instead of 40 conflicting comments.

**Problem 2 — Scattered resources.** The tools and organizations that help with lost and found dogs exist but are fragmented across platforms, languages, and institutions. The solution is a centralized hub that organizes them in one place.

**These are two different use cases, served by two dedicated sections of the same site.** A person in crisis needs the Protocol. A person doing research, building community capacity, or setting up prevention needs the Hub. The site serves both without conflating them.

---

## 2. INFORMATION ARCHITECTURE

```
HOME
│
├── [SECTION 1: PROTOCOL]  ← Crisis tool. Shareable by deep link.
│   ├── /lost     →  "I Lost My Dog" — step-by-step flow
│   └── /found    →  "I Found a Dog" — step-by-step flow
│
└── [SECTION 2: HUB]       ← Reference library. Browse at any time.
    ├── /resources    →  Resource Directory
    ├── /prevention   →  Prevention Card
    └── /help         →  Community Help Menu
```

**The Protocol section and the Hub section are visually distinct.** Different background color, different header treatment. A user landing on `/found` knows immediately they are in action-mode, not browse-mode.

**Deep-linkable URLs are the core distribution mechanism.** When someone posts "I found a dog" on Instagram or NextDoor, a community member replies not with advice but with:

> "Go here → [site]/found — works in Spanish and Creole too"

That single reply replaces 40 conflicting comments. The URL *is* the protocol. This is the behavior change the initiative is driving toward.

---

## 3. SITE-WIDE DESIGN PRINCIPLES

### Language First
The language toggle (EN | ES | KR) is the **first interactive element on every page** — not a small flag in a corner. On mobile it appears directly below the site name, large and tap-friendly, before any other content. A person who does not read English must be able to find it without reading anything first.

Default behavior: detect browser language. If Spanish or Haitian Creole is detected, switch automatically and show a dismissible banner confirming the switch.

All content — including legal deadlines, step text, button labels, and contact info — is fully translated. Legal notices are translated with zero paraphrasing.

### One Action Per Step
Each step in the Protocol contains exactly one action. If an action has sub-actions, they appear as a sub-checklist under that step — not as separate top-level steps.

### Time is Structural, Not Decorative
Legal deadlines (72 hours, 24 hours, 3-day shelter hold) are built into the flow architecture — they determine step order and which steps are marked as non-skippable. They are not footnotes.

### Done Feels Done
Every checklist step has a checkbox. Checking it produces a visual confirmation. Progress is shown throughout: "Step 3 of 6." Checked state persists in localStorage if the user leaves and returns.

### No Dead Ends
Every page ends with a persistent "Stuck? Call 311" button. Every step with a legal requirement includes a direct phone number if the online option is inaccessible.

### Print-Ready
The Protocol pages (`/lost` and `/found`) have print stylesheets that produce clean, black-and-white, single-page checklists — no nav, no footer, just the steps and contact info. These are designed to be posted physically.

---

## 4. DESIGN SYSTEM

### Color Palette

| Role | Hex | Usage |
|---|---|---|
| Legal deadline / urgent | `#E8431A` | 72-hour warnings, 3-day hold notice, must-do callouts |
| Primary action | `#1A5EB8` | CTA buttons, step numbers |
| Complete | `#2A8C4A` | Checked steps, completion states |
| Time-sensitive (not legal) | `#C97B00` | Do-soon steps |
| Protocol background | `#FFF8F5` | Warm, slightly different from Hub |
| Hub background | `#F5F7FA` | Cooler, reference feel |
| Card surface | `#FFFFFF` | Step cards |
| Body text | `#1A1A1A` | All body copy |

### Typography
- System font stack: `-apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif`
- Body size: 17px, line-height 1.6
- Step numbers: 48px bold, Trust blue
- Step titles: 22px bold
- Minimum font size: 15px — nothing smaller on mobile
- All legal notices: displayed in colored callout boxes, never as body text

### Layout
- Max content width: 680px
- Mobile-first (390px base)
- Touch targets: 48px minimum height
- All external links open in new tab

### Accessibility (WCAG 2.1 AA minimum)
- All images have alt text
- All interactive elements keyboard-navigable
- Focus visible on all interactive elements
- No color-only information — icons always paired with text
- No autoplay, no flashing, no animation unless user-toggled

---

## 5. PROTOCOL SECTION

### What makes the Protocol different from the Hub
- Entered from the homepage via two large, prominent buttons: "I LOST MY DOG" and "I FOUND A DOG"
- Each has its own shareable URL (`/lost`, `/found`)
- Warm background, action-oriented language, progress bar visible at all times
- Resources are embedded *within* each step — not linked to a separate page
- No browsing, no menus — just the next step

---

## 6. MODULE 1 — "I LOST MY DOG" (`/lost`)

### Page Entry

**Language toggle** — first element, prominent

**Headline:**
> "Let's find your dog. Do these steps in order."

**Legal callout (red-orange, top of page — cannot be scrolled past without seeing):**
> ⚠️ Miami-Dade County law: The shelter can only hold your dog for **3 days** before they become available for adoption. **Filing a report today protects your dog.**

**Time estimate:** "This checklist takes about 20 minutes to complete."

---

### PHASE 1 — RIGHT NOW (first 15 minutes)

**Step 1: Search your immediate area**
- Walk or drive within 2 blocks of where your dog was last seen
- Ask neighbors if they have seen your dog
*Why?* Most dogs are found within a few blocks of home in the first hour. If these two steps don't lead anywhere, move immediately to Step 2.

Sub-checklist:
- [ ] Searched my yard and street
- [ ] Asked 2–3 neighbors

---

### PHASE 2 — WITHIN THE HOUR

**Step 2: Post on these platforms (all free)**

**⚠️ Important tip — add your phone number directly in the post description:**
> Both Petco Love Lost and PawBoost hide your contact information from other users and send notifications by email — which frequently land in spam or "Other" folders. Do not rely on platform notifications alone. Put your phone number in the body of every post so finders can reach you directly without waiting on a platform email.

**How to post — in this order:**

- [ ] **Petco Love Lost** → [Button: Post Now] *(AI facial recognition will match your dog's photo against Found reports in real time — the most powerful search tool available)*
- [ ] **PawBoost** → [Button: Post Now]
  - PawBoost automatically distributes your post to its local Facebook pages, organized by area (Homestead is separate from Fort Lauderdale, etc.). After posting, **follow your local PawBoost Facebook page** and **turn on post notifications** so you see responses immediately.
- [ ] **Share your Petco Love Lost and PawBoost posts** to NextDoor and local Facebook groups — share the existing posts rather than creating new ones so all responses stay in one place. On NextDoor, also scroll recent posts — someone may have already found your dog.

**Post template** (expandable "Show me what to write"):
```
🚨 LOST DOG — [NEIGHBORHOOD] — [DATE]
Name: [Dog name]
Breed/mix: [Description]
Color and markings: [Be specific]
Last seen: [Street or intersection]
Contact: [Your phone number]
[CLEAR PHOTO]
```

---

### PHASE 3 — TODAY (legally important — do not skip)

**Step 3: File a report with Miami-Dade Animal Services**

Legal callout (red-orange):
> ⚠️ Filing an official report creates a record. This is your legal protection if your dog ends up at the shelter — and the clock is short. The shelter can only hold your dog for **3 days** before they become eligible for adoption.

**Important — if someone has already found your dog:**

Amber callout:
> 🏠 If a finder has your dog, ask them to **keep fostering it at home** while you work to reunite. Miami-Dade shelters are at or beyond capacity and resources are stretched. A dog is safer and better cared for in a home than in an intake facility. Finders are legally allowed to keep a found dog while searching for the owner — encourage them to do so.

**File your report** (do this even if you think someone has the dog — it creates an official record):
- **Call**: 311 or 305-468-5900
- **Email**: asdlostandfound@miamidade.gov
- **In person**: 3599 NW 79 Avenue, Doral FL 33122
  - Mon–Fri: 10:00 AM–6:30 PM | Sat–Sun: 10:00 AM–4:00 PM
  - Closed county holidays

Sub-checklist:
- [ ] Report filed with Animal Services
- [ ] Looked up my dog's microchip or license tag → [Button: Search Tag/Chip]
- [ ] Checked the shelter's current listings → [Button: View Shelter Animals]

**If your dog is already at the shelter — redemption fee notice (amber callout):**
> Bring your dog's **rabies certificate** — without it, your dog will not be released until a rabies shot is obtained.
> - Sterilized dog: **$50 + $10/day boarding**
> - Unsterilized dog: **$100 + $10/day boarding**
> - Second offense within 12 months: $75–$125 + boarding

---

### PHASE 4 — WITHIN 48 HOURS

**Step 4: Expand your search**

Sub-checklist:
- [ ] Make and distribute physical flyers within a 1-mile radius
  - *(Tips: large photo, your phone number in 36pt font minimum, "LOST DOG" bold at top)*
  - → [Download print-ready flyer template]
- [ ] Register on **Pet Harbor** → [Button: Search Pet Harbor]
- [ ] Post on **24Petconnect** → [Button: Post on 24Petconnect]
- [ ] Visit the shelter in person — walk the kennels, ask staff for help

---

### PHASE 5 — ONGOING

**Step 5: Keep going**
- [ ] Check all platforms daily
- [ ] Check the shelter's listings daily
- [ ] Update your posts if you have new information

**When your dog is found:**
- [ ] Update all posts: "FOUND — thank you everyone"
- [ ] Notify Animal Services so your report is closed
- [ ] Take a photo of the reunion — you earned it

**Completion state:**
> ✅ You've completed all urgent steps. Keep checking daily.
> Stuck? Call **311** anytime.

---

## 7. MODULE 2 — "I FOUND A DOG" (`/found`)

### Page Entry

**Language toggle** — first element, prominent

**Headline:**
> "You did the right thing by stopping. Here's exactly what to do — step by step."

**Legal deadline banner (red-orange, top of page — cannot be scrolled past):**
> 🔴 **72-HOUR LEGAL DEADLINE**
> Miami-Dade County law requires you to:
> 1. Notify Animal Services, AND
> 2. Have the dog scanned for a microchip
>
> Both must be done **within 72 hours** of finding the dog. Failure may result in a civil penalty.
> ⏱️ Your 72 hours started when you found the dog.

**Time estimate:** "This checklist takes about 30 minutes to complete."

---

### PHASE 1 — RIGHT NOW

**Step 1: Check for identification**

Visual decision tree (not a paragraph — rendered as branching UI):

```
Does the dog have a collar with a tag?
│
├── YES → Is there a phone number on the tag?
│         ├── YES → Call it now. You may be done! ✅
│         └── NO → Is there a rabies tag or license number?
│                   ├── YES → Look it up → [Button: Search Tag/Chip]
│                   └── NO → Continue to Step 2
│
└── NO → Continue to Step 2
```

*Note: The Miami-Dade Tag/Microchip Lookup tool can identify the owner from a license or rabies tag number alone.*

---

### PHASE 2 — WITHIN 2 HOURS

**Step 2: Get the dog scanned for a microchip**

Legal callout (red-orange):
> ⚠️ Required by Miami-Dade County Ordinance. Must be done within 72 hours of finding the dog.

Options:
- **Any private veterinary clinic** — most will scan for free or low cost. Call ahead.
- **Miami-Dade Animal Services** — 3599 NW 79 Ave, Doral FL 33122
  - Mon–Fri: 10:00 AM–6:30 PM | Sat–Sun: 10:00 AM–4:00 PM

**If chip is found — legal requirement (red-orange):**
> ⚠️ You must contact the registered owner within **24 hours**. This is required by law.
> Continue to Step 5 (Owner Verification) as soon as the owner responds.

**If no chip is found:**
> Continue to Step 3.

---

### PHASE 3 — WITHIN 72 HOURS (required by law)

**Step 3: File the official report — and keep the dog with you**

Legal callout (red-orange):
> ⚠️ Miami-Dade County law requires you to notify Animal Services within 72 hours. Failure to do so may result in a civil penalty.

**The goal is to keep this dog out of the shelter.** Miami-Dade's shelter system is at or beyond capacity. A dog in a home is safer, calmer, and has a much better chance of being reunited with its owner than a dog in an intake facility. You are doing the right thing by fostering.

**How to file the official report (do one of these):**

- [ ] **Online (preferred):** Submit via Petco Love Lost — this form directly notifies Miami-Dade Animal Services. It is the official reporting mechanism. → [Button: File Official Report via Petco Love Lost]
- [ ] **By phone:** Call **311** or **305-468-5900** if you cannot complete the online form

That's it for this step. You do not need to go to the shelter.

**Amber callout — approaching the 72-hour deadline and still no owner?**
> If you are nearing 72 hours, have not found the owner, and are unable to continue fostering, go to Miami-Dade Animal Services in person to complete a **foster application** — this keeps the dog legally in your care beyond the 72-hour window while the search continues.
> - 3599 NW 79 Avenue, Doral FL 33122
> - Mon–Fri: 10:00 AM–6:30 PM | Sat–Sun: 10:00 AM–4:00 PM

---

### PHASE 4 — TODAY

**Step 4: Post publicly so the owner can find you**

**Wording guidance (displayed in a callout box — not prose):**
> Use this exact wording pattern. Unclear posts slow everything down.
>
> ✅ Write: **"I HAVE FOUND A DOG — [Neighborhood] — [Date]"**
> ❌ Do not write: "Lost dog" — that means *your* dog is missing, which is the opposite
>
> Include: photo, color, breed or mix, where found, **your phone number in the description**
> Do not include: your home address

**⚠️ Important tip — add your phone number directly in the post description:**
> Both Petco Love Lost and PawBoost hide your contact information from other users and send notifications by email — which frequently land in spam or "Other" folders. Do not rely on platform notifications alone. Put your phone number in the body of every post so owners can reach you directly without the platform as an intermediary.

**How to post — in this order:**

- [ ] **Post on Petco Love Lost** with a clear photo → [Button: Post Now] *(AI will automatically compare your post against existing lost dog reports — this is the most powerful matching tool available)*
- [ ] **Post on PawBoost** → [Button: Post Now]
  - PawBoost automatically distributes your post to its local Facebook pages — these are organized by specific area (e.g., Homestead has a separate page from Fort Lauderdale). After posting, **follow your local PawBoost Facebook page** and **turn on post notifications** so you see responses in real time, not hours later.
- [ ] **Share your Petco Love Lost and PawBoost posts** to NextDoor and any local Facebook groups — do not create new separate posts; share the existing ones so all responses stay in one place
- [ ] **Check existing "Lost" reports** on Petco Love Lost and PawBoost — does this dog match anyone already searching?

---

### PHASE 5 — WHILE YOU WAIT

**Step 5: Keep the dog safe**

> You are **legally allowed** to keep the dog in your home while you search for the owner. You do not have to take the dog to the shelter.

- Provide water, food, and a safe, calm space
- Keep the dog separated from other pets until temperament is known
- If the dog appears injured or ill, call 311 for low-cost vet options
- Check your posts daily for responses

---

### PHASE 6 — WHEN THE OWNER CONTACTS YOU *(new)*

**Step 6: Verify ownership before releasing the dog**

This step protects you, protects the dog, and creates an accountable record. Do not release the dog before completing it.

**Callout (amber):**
> Anyone can claim a dog. Before you hand the dog over, you need to confirm this is actually their dog. This is standard practice and the owner will understand.

**How to verify — ask for at least two of the following:**

- [ ] **Describe the dog's markings without being prompted.** Ask the owner: "Can you describe any distinguishing marks, scars, or features?" If they can describe something you didn't mention in your post, that's a strong indicator.
- [ ] **Photos from before the dog went missing.** Ask them to show you photos of themselves with the dog on their phone. Look for consistency with the dog in front of you.
- [ ] **Vet records** showing the dog's name, breed, and their name as owner.
- [ ] **Microchip registration certificate** with their name and the chip number.
- [ ] **Miami-Dade dog license** in their name — they can look it up at miamidade.gov/Apps/ASD/TagSearch/ if they have the tag number.

**Document the handover — for your own records:**
- [ ] Take a photo of the owner's ID (driver's license or government ID) — ask permission, explain it's for your records
- [ ] Take a photo of the dog with the owner at the moment of return
- [ ] Note the date, time, and location of the handover

*Why this matters:* Dog theft is real. Disputes happen. A documented handover protects you legally and ensures the right dog goes to the right person. It also closes the loop on any reports you filed.

**After handover:**
- [ ] Update all posts: "REUNITED — thank you everyone ❤️"
- [ ] Notify Miami-Dade Animal Services that the dog has been returned to owner
- [ ] Close your Pet Harbor registration

**Completion state:**
> ✅ You completed every step — including the legal requirements.
> You made a difference. Thank you.
> Questions? Call **311** or **305-468-5900**.

---

## 8. HUB SECTION

The Hub is a reference library — calmer design, browse-friendly, not crisis-mode. Accessed from the main navigation. Each Hub page is a dedicated URL.

---

## 9. MODULE 3 — RESOURCE DIRECTORY (`/resources`)

### Design
Card grid layout. Four categories, each collapsible. Cards show: name, what it's for, access method, and cost. All links verified and updated periodically.

### Category A: Official — Report & Search

| Resource | What it's for | Access | Cost |
|---|---|---|---|
| Miami-Dade Animal Services | File lost/found report, chip scan, shelter intake | 311 or 305-468-5900 / asdlostandfound@miamidade.gov / 3599 NW 79 Ave, Doral | Free |
| Miami-Dade Tag/Chip Lookup | Identify owner from license tag or chip number | miamidade.gov/Apps/ASD/TagSearch/ | Free |
| Petco Love Lost | AI facial recognition matching + official report form | petcolove.org/lost | Free |
| Pet Harbor | Register found pet, search lost pets | petharbor.com | Free |
| 24Petconnect | Secondary search and post platform | 24petconnect.com | Free |

### Category B: Community — Post & Search

| Resource | What it's for | Access | Notes |
|---|---|---|---|
| PawBoost | Post lost/found; auto-generates local Facebook group posts by area | pawboost.com | Free; covers Facebook distribution automatically |
| NextDoor | Neighborhood-level posts | nextdoor.com | Free |

*Note on Facebook: PawBoost automatically posts to local Facebook groups it has generated by geographic area. This is already organized. Users do not need to manage Facebook groups manually — PawBoost handles it.*

### Category C: Shelters & Rescues

| Resource | Address | Hours | Notes |
|---|---|---|---|
| Miami-Dade Animal Services | 3599 NW 79 Ave, Doral FL 33122 | M–F 10AM–6:30PM, Sa–Su 10AM–4PM | Official county shelter. Frequently at capacity. |

*A curated list of local rescue organizations with contact information and current capacity status. Capacity status should be updated periodically — most rescues are at or beyond capacity as of 2026.*

### Category D: Free & Low-Cost Services

| Service | How to Access | Cost |
|---|---|---|
| Microchip scanning | Any vet clinic (call ahead) | Usually free |
| Microchip scanning | Miami-Dade Animal Services (walk in) | Free |
| Low-cost microchipping events | miamidade.gov/animals (check calendar) | Free–low cost |
| Dog licensing | miamidade.gov/animals or in person | Varies |
| Emergency vet guidance | Call 311 | Free |

---

## 10. MODULE 4 — PREVENTION CARD (`/prevention`)

**Frame:** "The 3 things that reunite dogs fastest — before they go missing."

Designed to be printed as a double-sided card and shared at vet offices, HOA boards, and community centers. QR code links to this page.

---

### Prevention 1: Microchip your dog — and keep the registry current

A chip with an old phone number is useless. The chip is only as good as what's registered to it.

**Steps:**
1. Get chipped (~$25–$45 at most vets; free at county events)
2. Register the chip immediately (AKC Reunite, HomeAgain, AVID, or 24Petwatch)
3. Update your phone number every time it changes

→ Look up your chip or license tag: miamidade.gov/Apps/ASD/TagSearch/

---

### Prevention 2: Use a readable ID tag

Tags work even without a scanner. The right finder can call you immediately — no app, no vet required.

**Best practice:**
- Include: dog's name + your cell phone number
- Format: embossed directly on collar, or large slide-on tag
- Font large enough to read while the dog is moving — not a small dangling disc
- Replace when worn, faded, or info changes

*Community insight: Tags printed directly on the collar in large letters are easiest for finders to read on an excited dog.*

---

### Prevention 3: License your dog in Miami-Dade County

Licensing is required by county law and links your dog to your address and contact info in the county database. A licensed dog can be identified in seconds via the tag lookup tool.

→ [Link: License your dog with Miami-Dade]

---

### Bonus: Home escape audit

- Check fence for ground-level gaps — especially after rain, wind, or landscaping
- Test gate latches: can they be nosed or pawed open?
- Know your dog's preferred escape route and reinforce it
- Keep ID tags on even indoor dogs — one open door is all it takes

---

## 11. MODULE 5 — COMMUNITY HELP MENU (`/help`)

**Frame:** "You don't have to do everything. Pick ONE thing."

**Important reframe from v1:** The highest-leverage action for most community members is not donating or fostering — it is **replacing their own advice with this protocol.** That behavior change scales instantly and costs nothing.

---

### Card 1: SHARE THE PROTOCOL *(2 minutes, free — highest impact)*
**Icon:** 📢
**What:** When you see someone posting "I lost my dog" or "I found a dog" — stop typing your own advice and share this link instead.
> `/lost` for someone who lost a dog
> `/found` for someone who found one
**Why it matters:** One clear protocol beats 40 conflicting comments. Every time someone shares this link instead of their own advice, the community gets a little more coordinated.
**CTA:** [Copy link to share] [Copy /lost link] [Copy /found link]

---

### Card 2: DONATE *(5 minutes, any amount)*
**Icon:** 💛
**What:** Give what you can to local rescues covering costs for found animals.
**Concrete anchors:**
- $5 = microchip registration for one dog
- $15 = ID tag set for 5 dogs
- $49 = one day of emergency boarding for a found stray
**CTA:** [See vetted local Miami-Dade rescues accepting donations]

---

### Card 3: VOLUNTEER *(a few hours/month)*
**Icon:** 🙋
**What:**
- Help post flyers when a dog is lost nearby
- Scan lost/found posts and flag potential matches
- Be the person in your neighborhood group who shares the protocol link
**CTA:** [Sign up — 2 minutes, no commitment]

---

### Card 4: FOSTER *(days or weeks, your schedule)*
**Icon:** 🏠
**What:** Temporarily keep a found dog safe in your home while an owner is located or an adoption is arranged.
**Who it's for:** Anyone with a safe space. No experience required. You can specify what you can and can't handle.
**CTA:** [Apply to foster]

---

### Card 5: ADOPT
**Icon:** 🐾
**What:** Miami-Dade shelters are at or above capacity. Adoption directly creates space for dogs brought in as found strays.
**CTA:** [See dogs available now — Pet Harbor Miami-Dade]

---

## 12. GLOBAL ELEMENTS

### Persistent Footer (all pages)
```
📞 Lost & Found Hotline: 311 or 305-468-5900
✉️  asdlostandfound@miamidade.gov
📍 Miami-Dade Animal Services
   3599 NW 79 Avenue, Doral, FL 33122
   Mon–Fri: 10AM–6:30PM | Sat–Sun: 10AM–4PM
```

### Persistent "Stuck?" button
Fixed, bottom-right, all pages:
> Stuck? Call 311

### Emergency modal
If a user indicates the dog is injured or in immediate danger:
> 🚨 Injured animal? Call Miami-Dade Animal Services: **305-468-5900** or **311**

---

## 13. COMMUNITY PROTOCOL CARD (offline distribution)

A separate design asset — not a page, but a printable/shareable card.

**Front:**
- "LOST A DOG?" with QR code → `/lost`
- "FOUND A DOG?" with QR code → `/found`
- Available in English, Spanish, Creole

**Back:**
- The 3 most critical legal facts (72 hours, 3 days, chip requirement)
- Miami-Dade Animal Services phone: 311 or 305-468-5900

**Distribution:**
- Posted at vet offices, HOA bulletin boards, pet stores, community centers
- Shared as an image on Instagram/Facebook/NextDoor
- QR codes work from phone screens (no printing required)

---

## 14. LEGAL COMPLIANCE — ALL REQUIREMENTS SURFACED

| Miami-Dade Requirement | Where it appears |
|---|---|
| Found pet reported to Animal Services within 72 hours | Module 2 top banner, Step 3 |
| Found pet scanned for microchip within 72 hours | Module 2 banner, Step 2 |
| If chip found, contact owner within 24 hours | Module 2 Step 2 decision branch |
| Shelter hold is 3 days for dogs over 6 months | Module 1 top callout, Step 3 |
| Owner must present rabies certificate to redeem | Module 1 Step 3 callout |
| Redemption fee schedule | Module 1 Step 3 |
| Civil penalty for failure to report found pet | Module 2 banner |
| Finder may keep pet at home while searching | Module 2 Step 5 |

---

## 15. TWO CORE PROBLEMS THIS SITE ADDRESSES

Stated explicitly here for alignment across the team:

**Problem 1 — Scattered resources.** The tools and organizations exist but are fragmented across platforms, languages, and institutions. No one place to find them. The Hub section solves this.

**Problem 2 — No workflow or structure.** When someone encounters a lost or found dog, there is no standard protocol the community follows. Advice is inconsistent, crowdsourced, and often paralyzing. The Protocol section solves this — and the community's job is to circulate it as a link, not to reinvent it each time.

---

## 16. CONTENT LOCALIZATION (for translation handoff)

All text content is stored in a single JSON file per language (EN/ES/KR). Strings are keyed by module and step. Legal notice strings are flagged `[LEGAL — do not paraphrase]` and must be translated verbatim.

Translation priority order (most critical first):
1. All red-orange legal deadline callouts
2. Module 2 (Found Dog) — all steps
3. Module 1 (Lost Dog) — all steps
4. Footer contact block
5. Module 3 resource directory
6. Module 4 prevention card
7. Module 5 community menu
8. Navigation labels and UI chrome

---

## 17. HANDOFF NOTES FOR CLAUDE CODE

**Stack:** Static site or lightweight React app. No backend required unless the volunteer sign-up form (Module 5, Card 3) submits to a form handler.

**State management:** All checklist progress in localStorage. No accounts, no sign-ins.

**External links:** All open in new tab. The official Miami-Dade report form is hosted on Petco Love Lost — deep link directly to it.

**Print styles:** `@media print` on `/lost`, `/found`, and `/prevention` produces clean, black-and-white, single-page output. No nav, no footer — just steps and contact info.

**Analytics:** Track language selection, section visited (Protocol vs Hub), module, and step-level drop-off. This data will show where the protocol is losing people.

**Accessibility:** WCAG 2.1 AA minimum throughout. Decision tree in Module 2 Step 1 must be keyboard-navigable with clear focus states.
