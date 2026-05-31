[PROMPT.md](https://github.com/user-attachments/files/28434393/PROMPT.md)[Uploading PROMPT# Auro AI — Master Build Prompt
### Use this in Claude, Cursor, Windsurf, or any AI coding tool to rebuild the entire system

---

## OVERVIEW

Build a complete two-page web system for a brand called **Auro AI** — an AI education company that sells online courses to small business owners. The system consists of:

1. **Page 1 — Funnel Landing Page** (`index.html`)
   A standalone marketing page that captures leads via a form and redirects them to the course dashboard.

2. **Page 2 — Course Dashboard** (`dashboard.html`)
   A full interactive course player with a sidebar, 4 modules, 20 lessons, progress tracking, and lesson navigation.

Both pages are **single-file standalone HTML files** — all CSS and JavaScript embedded in `<style>` and `<script>` tags. No frameworks, no build tools, no external dependencies except Google Fonts.

---

## BRAND & DESIGN SYSTEM

Apply these exact values across both pages consistently.

**Brand name:** Auro AI
**Brand origin:** Latin roots — Aurora (dawn, new beginning) + Aurum (gold). Represents small businesses stepping into the AI era before competitors.
**Tagline:** "Don't Get Left Behind — AI Is the Future."
**Target audience:** Small business owners, no tech background required.

### Colors
```
Background:        #07070f  (near-black)
Surface/Card:      #0e0e1c  (dark navy)
Surface deeper:    #111124
Gold (primary):    #F7C63A
Orange (secondary):#FF6B35
Text primary:      #e8e8f0
Text muted:        #7a7a9a  (also #6e6e8e)
Border:            rgba(247,198,58,0.10–0.14)
Border subtle:     rgba(255,255,255,0.06)

Module accent colors:
  Finance:         #3ecfb2  (teal)
  Marketing:       #ff6b6b  (red)
  Customer Service:#a97cf8  (purple)
  Sales & Growth:  #4ade80  (green)
```

### Typography
```
Google Fonts import:
  Bebas Neue — all headings, logos, module names, prices
  DM Sans (weights 300, 400, 500, 600) — all body text, buttons, labels

Heading style: Bebas Neue, large tracking (0.02–0.12em), tight line-height (0.92–1.05)
Body style: DM Sans, 15–16px, line-height 1.65–1.8
Labels: 0.7–0.75rem, font-weight 600, letter-spacing 0.18–0.22em, text-transform uppercase
```

### Background Effects (apply to both pages)
```css
/* Gold grid overlay — fixed, full viewport */
background-image:
  linear-gradient(rgba(247,198,58,0.035) 1px, transparent 1px),
  linear-gradient(90deg, rgba(247,198,58,0.035) 1px, transparent 1px);
background-size: 52–60px 52–60px;
position: fixed; inset: 0; pointer-events: none; z-index: 0;

/* Radial gold glow — top center */
position: fixed; top: -200px; left: 50%; transform: translateX(-50%);
width: 860px; height: 560px;
background: radial-gradient(ellipse, rgba(247,198,58,0.11) 0%, rgba(255,107,53,0.05) 45%, transparent 70%);
```

### Buttons
```
Primary button: linear-gradient(135deg, #F7C63A, #FF6B35), color #07070f,
  font-weight 800, border-radius 6–7px, box-shadow gold glow,
  hover: translateY(-2px) + stronger shadow

Ghost/outline button: transparent background, 1.5px solid border,
  hover: border turns gold, text turns gold

Plan card buttons: transparent with colored border matching plan accent,
  hover: fills with plan accent color
```

---

## PAGE 1 — FUNNEL LANDING PAGE (`index.html`)

### Purpose
Marketing funnel page. Receives traffic from Meta/Instagram/Facebook ads. Collects name, email, and a short message. On submit, redirects to dashboard.html after a 5-second countdown.

### Sticky Navigation
- Left: Logo "Auro AI" in Bebas Neue, gold with glow. "AI" portion in white/text color.
- Right: Small trust indicator — green dot + "Free training · No credit card required"
- Background: semi-transparent dark + backdrop-filter blur, gold bottom border
- Height: 68px, sticky top

### Hero Section
Two-column grid (left: copy, right: video). Stacks to single column on mobile with video on top.

**Left column:**
- Eyebrow label (orange, uppercase): "Free Training for Small Business Owners"
- H1 (Bebas Neue, ~5–6rem): "AI Will Either / Work For You / Or Against You." — make "Work For You" gold
- Paragraph body text describing the course
- Bullet list (4 items, gold ✦ markers):
  - Cut hours of work down to minutes with AI automation
  - Custom AI assistants built for your business needs
  - Finance, Marketing, Sales & Customer Service covered
  - No coding. No jargon. Results from day one.
- Primary CTA button: "Watch the Free Training ↓" (smooth-scrolls to form)
- Social proof row: avatar stack (4 colored circles with initials) + "500+ small business owners already transforming their businesses"

**Right column — Video block:**
- Dark card with gold border and glow, border-radius 14px
- Video embed area (aspect-ratio 16/9) with a placeholder showing:
  - Centered play button (circle, gold border, gold play triangle inside)
  - Caption text: "Watch: 'Why Every Small Business Must Use AI Now'"
  - Note: "(Paste your video embed code here)"
- Include HTML comments with all 3 embed options: YouTube iframe, Vimeo iframe, HTML5 video tag
- Bottom caption bar: "⏱ 8-minute free training · Then claim your spot below"

**Hero entrance animation:** `@keyframes fadeUp` — staggered delay on each child element (0.05s, 0.15s, 0.25s, 0.32s, 0.4s, 0.5s)

### Stats Bar
Full-width dark band with gold top/bottom borders. 4-column grid:
- 72% · of businesses now use AI
- 10X · faster content & output
- 500+ · hours saved per year
- $4T+ · AI market by 2030

Numbers in Bebas Neue ~2rem, gold with glow. Labels in muted color, small.

### What You'll Learn Section
4 module preview cards in a responsive grid (auto-fit, min 260px). Each card:
- Module number tag (gold, small caps): "Module 01" etc.
- Module name in Bebas Neue
- Short description paragraph
- Dark card background, gold border, hover: border brightens + translateY(-3px)

Modules:
1. Finance & Bookkeeping — AI cash flow, reports, expense tracking, tax prep
2. Marketing on Autopilot — Ad copy, social automation, emails, brand voice
3. Customer Service AI — Chatbot, automated replies, reviews, FAQ systems
4. Sales & Lead Growth — Lead gen, outreach scripts, CRM automation, closing

### Instructor Section
Full-width band with darker background. Two-column layout:
- Left: Avatar circle (120px, gold gradient border, gold text initials "YN" — replace with img tag for real headshot)
- Right: Tag label "Your Instructor", Name in Bebas Neue large, bio paragraph in muted color
- Include HTML comment: "Replace YN with your headshot img tag"

### Lead Capture Form Section
Centered, max-width 820px. Header:
- Orange uppercase label: "Limited Spots Available"
- H2: "Get Instant Access — It's Free to Start" ("Instant Access" in gold)
- Subtext paragraph

Form card:
- Dark card background, gold border, border-radius 14px
- Gold/orange gradient top stripe (3px height)
- Form fields (2-column grid, collapses to 1-column on mobile):
  - First Name (required) + Last Name — side by side
  - Email Address — full width
  - Textarea: "What's your biggest business challenge right now?" — full width, min-height 100px
- Field styling: dark semi-transparent background, subtle white border, gold focus ring + glow
- Submit button: full-width, gold/orange gradient, "Start the Course — Free Instant Access →"
- Disclaimer text below button: lock icon + privacy assurance + unsubscribe note

**Form validation:**
- Check first name is not empty
- Check email matches valid email regex
- Show loading state ("Sending…") on submit button during processing

**Success state (shown after submit):**
- Hide form, show success message in same card
- Green checkmark circle icon
- Heading "You're In!" in green (Bebas Neue)
- Paragraph about checking email
- Countdown: "Redirecting in [N]s" with animated number counting from 5 to 0
- On reaching 0: `window.location.href = 'dashboard.html'`

**JS backend options (in comments):**
- Formspree (no backend needed)
- ConvertKit API
- Custom fetch POST to /api/leads
- Demo mode (1s timeout, then showSuccess) — active by default

**Meta Pixel integration:**
- Comment block at top of page showing where to paste pixel base code
- `fbq('track', 'Lead')` call inside showSuccess() — commented out, ready to enable

### Bottom CTA Section
Centered, radial gold glow background effect:
- H2 (Bebas Neue large): "Every Month You Wait Is a Month Behind." — "Month Behind." in gold
- Subtitle paragraph
- Primary button: "Get Free Access Now" — links directly to dashboard.html

### Footer
Centered, small text, top gold border:
- Logo mark in Bebas Neue (faded gold)
- "Built for small business owners ready to embrace the future."
- Links: Privacy Policy · Terms of Service · Contact
- Copyright line

---

## PAGE 2 — COURSE DASHBOARD (`dashboard.html`)

### Purpose
Full course player. Students land here after form submission. Shows a welcome screen on first visit, then the course content. Progress is saved to sessionStorage.

### CSS Variables needed
```css
--bg:         #07070f
--bg2:        #0d0d1c
--bg3:        #111124
--gold:       #F7C63A
--orange:     #FF6B35
--text:       #e8e8f0
--muted:      #6e6e8e
--border:     rgba(247,198,58,0.1)
--border2:    rgba(255,255,255,0.06)
--teal:       #3ecfb2
--red:        #ff6b6b
--purple:     #a97cf8
--green:      #4ade80
--sidebar-w:  310px
--header-h:   62px
```

### Fixed Top Header (62px height)
- Left: Hamburger menu button (mobile only, hidden on desktop)
- Logo: "Auro AI" in Bebas Neue gold
- Vertical divider (1px, subtle)
- Course name: "Business Mastery Program" in muted small text
- Right side: Progress pill — small bar + "X% complete" text
- Background: semi-transparent + backdrop blur + gold bottom border
- Position: fixed top 0, z-index 200

### Fixed Sidebar (310px wide, desktop)
- Position: fixed, full height below header, scrollable
- Background: #0d0d1c, right border
- Mobile: slides in from left with transform, overlay behind it

**Sidebar header:**
- "Your Progress" label
- Progress bar (6px height, gold/orange gradient fill)
- "X of 20 lessons complete" text

**Module groups (4 total, collapsible):**
Each module group has:
- Toggle button with: colored icon box (emoji + colored bg matching module accent), module title in Bebas Neue, "X/5 lessons" progress text, chevron arrow (rotates 180° when open)
- Lesson list (shown when module is open):
  - Each lesson item: circular check icon (fills green when complete), lesson title text, duration text (right-aligned)
  - Active lesson: left border accent in module color, slightly lighter background
  - Completed lesson: green filled circle with ✓

**Active lesson border colors:**
- Module 0 (Finance): teal left border
- Module 1 (Marketing): red left border
- Module 2 (Customer Service): purple left border
- Module 3 (Sales): green left border

### Main Content Area
Scrollable, margin-left equals sidebar width. On mobile, full width.

**Welcome Screen (shown on first visit):**
- Centered, full height
- Radial glow behind content
- Orange eyebrow label: "Welcome to Your Course"
- H1 (Bebas Neue large): "Auro AI Business Mastery" — "Business Mastery" in gold
- Subtitle paragraph
- 2×2 grid of module preview pills (colored dots + module names)
- Single large button: "Begin Module 1 →" — triggers course start, hides welcome, shows lesson 1

**Lesson View (shown when a lesson is active):**

Structure:
1. Breadcrumb: `Module Name › Lesson Title` in small muted text
2. Video block: 16:9 aspect ratio dark card with gold border
   - Centered play button (circle, module-color play triangle)
   - Lesson title and "(Paste your video embed here)" in muted text
   - Duration badge top-right corner
   - Include HTML comments for YouTube/Vimeo/MP4 embed
3. Module tag line: `[emoji] [Module Name] · [Lesson Tag]` in module accent color
4. H1: Lesson title in Bebas Neue ~2.5rem
5. Lesson meta row: duration, lesson number, "Completed" badge if done
6. Lesson body: HTML content with headings (h3), paragraphs, bullet lists (✦ markers), callout boxes, key takeaway boxes

**Callout box style:**
- Left border 3px in module accent color
- Dark semi-transparent background
- Bold uppercase label above content

**Key takeaway box style:**
- Gold border + gold tinted background
- "Key Takeaway" label in gold small caps
- White text content

**Bottom lesson navigation:**
- Three elements in a row (space-between):
  - ← Previous lesson button (dark card style, shows previous lesson title)
  - "Mark Complete & Continue →" button (gold/orange gradient) — or "✓ Completed" (green outline) if already done
  - Next lesson button (dark card style, shows next lesson title)
- Previous/Next buttons are disabled (opacity 0.25, no pointer events) at boundaries

**On "Mark Complete & Continue" click:**
1. Mark current lesson complete in state
2. Save to sessionStorage
3. If more lessons in module: advance to next lesson, re-render
4. If last lesson in module (not last module): show Module Complete screen
5. If last lesson of final module: show Course Complete screen

**Module Complete Screen:**
- Module emoji in large colored circle
- "Module [N] Complete!" heading in Bebas Neue
- Description mentioning next module
- Two buttons: "Start [Next Module] →" (gold gradient) + "Review Module" (ghost)

**Course Complete Screen:**
- Trophy emoji large
- Orange eyebrow: "Program Complete"
- H2: "You're an Auro AI Graduate." — "Auro AI Graduate." in gold
- Congratulatory paragraph
- 2×2 grid showing all 4 completed modules (icons + names)
- Button: "Review the Full Course ↩"

### JavaScript State Management
```javascript
// State object
let state = {
  started: false,
  currentModule: 0,    // 0–3
  currentLesson: 0,    // 0–4
  completed: {}        // keys like "0-1", "2-3" etc.
}

// Persist to sessionStorage on every change
// Load from sessionStorage on page init
// If state.started is true on load: skip welcome screen, render current lesson directly
```

### Key JS Functions to Build
```
buildSidebar()        — renders full sidebar HTML based on current state
renderLesson()        — renders current lesson view based on state.currentModule + state.currentLesson
goToLesson(mi, li)    — updates state, calls renderLesson() + buildSidebar()
markComplete()        — marks lesson done, determines next action (next lesson / module complete / course complete)
beginCourse()         — sets started=true, goes to lesson 0-0, builds sidebar
beginNextModule()     — increments currentModule, goes to lesson 0 of new module
showModuleComplete()  — renders module complete celebration screen
showCourseComplete()  — renders full course complete screen
toggleModule(mi)      — opens/closes a module group in sidebar
toggleSidebar()       — mobile: show/hide sidebar + overlay
flatLessons()         — returns flat array of all {mi, li, lesson} for prev/next navigation
overallPct()          — returns 0–100 overall completion percentage
hexToRgb(hex)         — converts hex color to "r,g,b" string for rgba() use
```

### Fade Animation
```css
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(16px); }
  to   { opacity: 1; transform: none; }
}
.fade-in { animation: fadeIn 0.4s ease both; }
```
Apply `.fade-in` class to lesson view content on every render.

---

## COURSE CONTENT DATA

Build this as a JavaScript array called `MODULES`. Each module has: id, title, icon, color, tagline, and a `lessons` array. Each lesson has: title, duration, tag (label), body (HTML string).

### Module 0 — Finance & Bookkeeping
Color: #3ecfb2 (teal) · Icon: 📊

| # | Title | Duration | Tag |
|---|-------|----------|-----|
| 1 | Why AI Is Changing Small Business Finance Forever | 8 min | Introduction |
| 2 | Setting Up AI Bookkeeping from Scratch | 14 min | Practical Setup |
| 3 | Cash Flow Forecasting with AI | 12 min | Advanced Skill |
| 4 | Automated Financial Reports & Tax Prep | 11 min | Automation |
| 5 | Building Your Custom Finance AI Assistant | 18 min | AI Assistant Build |

Key lesson content themes:
- Lesson 1: Pain of manual bookkeeping → AI transformation. Outcomes list. Callout: "Students cut 10 hrs/month to 90 minutes."
- Lesson 2: Tools (Claude/ChatGPT + Google Sheets + Zapier), CSV export, bookkeeping prompt template in callout box
- Lesson 3: 3-month forecast framework, 5-step process, bank approval benefit
- Lesson 4: Monthly report automation, weekly AI email P&L prompt, tax deduction organisation, student saved $2,400 example
- Lesson 5: Custom GPT/Claude Project setup, what to feed it, 10 test questions process

### Module 1 — Marketing on Autopilot
Color: #ff6b6b (red) · Icon: 📣

| # | Title | Duration | Tag |
|---|-------|----------|-----|
| 1 | The AI Marketing Revolution for Small Business | 7 min | Introduction |
| 2 | Writing AI Ad Copy That Actually Converts | 16 min | Ad Strategy |
| 3 | 30-Day Social Media Content in 10 Minutes | 13 min | Content Automation |
| 4 | Email Campaigns That Sell While You Sleep | 15 min | Email Automation |
| 5 | Your Custom Marketing AI Assistant | 17 min | AI Assistant Build |

Key lesson content themes:
- Lesson 1: Full marketing team output alone. List what module builds. Callout: "$500–$2,000/month social media manager replaced."
- Lesson 2: AIDA framework, ad copy prompt template in callout box, A/B testing approach
- Lesson 3: Content pillars system (5 pillars), 30-day calendar in 11 minutes stat, scheduling tools
- Lesson 4: $36 ROI per $1 spent stat, 5-email welcome sequence with timing, set-once automation
- Lesson 5: What to feed brand AI (voice guide, best content, customer profile, competitor examples)

### Module 2 — Customer Service AI
Color: #a97cf8 (purple) · Icon: 💬

| # | Title | Duration | Tag |
|---|-------|----------|-----|
| 1 | Never Miss a Customer Again with AI | 7 min | Introduction |
| 2 | Building Your First AI Chatbot (No Code) | 20 min | Chatbot Build |
| 3 | Automated Email Replies That Feel Human | 12 min | Email Automation |
| 4 | Review Management & FAQ Automation | 11 min | Reputation & Systems |
| 5 | Your Custom Customer Service AI | 16 min | AI Assistant Build |

Key lesson content themes:
- Lesson 1: 9x conversion rate in 5 minutes stat, list of what module builds
- Lesson 2: Tidio/ManyChat/Chatbase tools, what chatbot handles (pricing, bookings, complaints, escalation)
- Lesson 3: Zapier + AI email routing, contextual reply templates, natural-feeling delay, student quote
- Lesson 4: Google/Yelp review monitoring, de-escalation templates, follow-up review requests, smart FAQ connected to chatbot
- Lesson 5: What to train it on (products, policies, hours, complaints, tone), any team member can answer anything

### Module 3 — Sales & Lead Growth
Color: #4ade80 (green) · Icon: 🚀

| # | Title | Duration | Tag |
|---|-------|----------|-----|
| 1 | Building an AI-Powered Sales Machine | 8 min | Introduction |
| 2 | AI Lead Generation: Finding Your Ideal Customers | 17 min | Lead Generation |
| 3 | Writing Sales Scripts That Get Responses | 14 min | Outreach |
| 4 | CRM Automation: Never Lose a Lead Again | 13 min | Systems |
| 5 | Your Custom Sales AI & Course Completion | 20 min | AI Assistant Build |

Key lesson content themes:
- Lesson 1: AI as a tireless salesperson that doesn't get rejected. Pipeline ceiling removed.
- Lesson 2: LinkedIn/Google Maps/directory prospecting, dream customer lookalike profile, lead scoring prompt template
- Lesson 3: 3-message sequence (observation → value → direct ask), personalised openings at scale, 10 subject line variations
- Lesson 4: Automated pipeline (new lead → qualify → follow-up → meeting → proposal), Notion + Zapier + AI free stack
- Lesson 5: Sales AI capabilities, full recap of all 4 AI assistants built, what's next / call to action

---

## RESPONSIVE BREAKPOINTS

```css
/* Mobile sidebar toggle */
@media (max-width: 768px) {
  sidebar: hidden by default, slides in on hamburger click
  main: margin-left: 0 (full width)
  hamburger: visible
  header divider + course name: hidden
}

/* Hero stacks to single column */
@media (max-width: 860px) {
  hero grid: 1 column
  video goes above copy (order: -1)
}

/* Form grid collapses */
@media (max-width: 560px) {
  form-row: 1 column
}

/* Welcome module grid */
@media (max-width: 500px) {
  welcome-modules: 1 column
}

/* General small screen */
@media (max-width: 600px) {
  All multi-column grids: 1 column
  Hero h1: ~4rem
}
```

---

## FILE STRUCTURE

```
/
├── index.html          ← Funnel landing page
└── dashboard.html      ← Course player dashboard
```

Both files are self-contained. The only link between them is:
- In `index.html`: after form submit, `window.location.href = 'dashboard.html'`
- No shared CSS files, no shared JS files

---

## THINGS TO CUSTOMISE BEFORE GOING LIVE

Replace these placeholders in the code:

| Placeholder | Replace with |
|---|---|
| Video placeholder div | YouTube, Vimeo, or MP4 embed code |
| `YN` initials in instructor avatar | `<img src="headshot.jpg">` |
| Instructor name "Your Name Here" | Your real name |
| Instructor bio `[Add your bio…]` | Your real bio (2–3 sentences) |
| Meta Pixel comment block | Real pixel base code from Meta Ads Manager |
| `fbq('track', 'Lead')` — commented out | Uncomment once Pixel is live |
| Form backend — Formspree/ConvertKit | Real form endpoint or API key |
| Demo mode timeout block | Remove once real backend is connected |
| Privacy Policy / Terms of Service links | Real policy page URLs |
| Each lesson video placeholder | Real video embed per lesson |

---

## EMAIL SEQUENCE TO BUILD IN YOUR EMAIL TOOL

After form submission, trigger this sequence:

| Email | Send time | Subject | Content |
|---|---|---|---|
| 1 | Immediately | Welcome to Auro AI — Here's your access | Confirm signup, link to dashboard.html, personal welcome note |
| 2 | Day 2 | The real reason most businesses fall behind | Story about AI adoption, why now is critical |
| 3 | Day 4 | What our students built in week one | Social proof, specific results, module highlights |
| 4 | Day 6 | One AI prompt that saved 3 hours this week | Value content + soft mention of full course/paid plans |
| 5 | Day 8 | Your free access expires soon | Urgency email, full plan breakdown, direct buy link |

---

## META ADS SETUP NOTES

**Campaign objective:** Leads or Traffic
**Ad formats to run:** Reels (video), Feed (image/carousel), Stories (swipe-up)
**All ads link to:** index.html (your funnel landing page)
**CTA text on ads:** "Watch Free Training", "Get Free Access", "Learn More"
**Meta Pixel events to fire:**
- `PageView` — base code fires automatically on page load
- `Lead` — fire on form submit (inside showSuccess() function)
- `Purchase` — fire when a paid plan is bought (add to checkout page later)

**Retargeting audiences to build:**
- Visited index.html but did not submit form → show reminder ad
- Submitted form (Lead event fired) → exclude from top-funnel, show upgrade ads
- Watched 50%+ of your Reels video → warm audience, show direct offer ad

---

*Prompt written for the Auro AI project. Feed this entire document into Claude, Cursor, or any AI coding assistant and ask it to build the system exactly as specified.*
.md…]()
