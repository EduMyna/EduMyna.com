# Claude Code Context Document

**Last Updated:** March 25, 2026
**Purpose:** Session continuity for Claude Code - helps resume work across sessions

---

## Project Overview

**Project Name:** EduMyna.com
**Tech Stack:** Astro 5.16.6, Tailwind CSS 4.0, TypeScript
**Hosting:** GitHub repo `EduMyna/EduMyna.com`, likely auto-deployed (Vercel/Netlify/Cloudflare Pages)
**Local Dev:** `npm run dev` → runs on http://localhost:4323/ (ports 4321-4322 often occupied)

---

## Project Purpose

EduMyna is a 12-year educational technology journey documentation and pitch website. The site tells the founder's story (Gautam) from:
- **2012-2015:** Startup Village (physical incubator in Kochi)
- **2015-2018:** SV.CO (digital platform for student startups)
- **2018-2023:** Pupilfirst (LMS platform, university partnerships)
- **2023-2024:** Direct-to-consumer + Academic Bank of Credits
- **2024-Present:** EduMyna (AI-first education platform)

The website serves multiple audiences: investors, partners, students, and historians of the educational tech journey.

---

## Critical Files & Their Relationships

### Source of Truth Documents (Markdown)

1. **`MASTER_NARRATIVE_TIMELINE.md`** (36KB)
   - Complete chronological timeline (2009-2024)
   - Contains detailed events, metrics, partnerships, media links
   - **Recently updated:** Added "5 Acts Framework" with deep narrative dives
   - Used as reference for all other content
   - Sections:
     - Evolution Story: The 5 Acts Framework
     - Business Model Evolution Table
     - Key Insights From 12 Years
     - The Evolution Narrative (deep dives for each Act)
     - Detailed Timeline by Phase (original chronological content)

2. **`PITCH_DECK_NARRATIVE_SECTION8.md`** (20KB)
   - Investor pitch deck (Section 8 nonprofit positioning)
   - Revenue-focused, ₹2-5Cr ask

3. **`FOUNDER_STORY_DECK.md`** (15KB)
   - Team/partner recruitment deck
   - Mission-driven narrative

### Website Pages (Astro)

#### Three Narrative Versions (IMPORTANT - User wants to review these for consistency)

1. **`/story`** (`src/pages/story.astro`)
   - Original 12-year founder narrative
   - 8 chapters with photos and detailed storytelling
   - Written BEFORE the evolution framework
   - **Status:** May need alignment with evolution narrative

2. **`/evolution`** (`src/pages/evolution.astro`) ⭐ NEW
   - 5 Acts organizational transformation framework
   - Visual interactive timeline with color-coded phases
   - Business Model Evolution table
   - 6 Key Insights
   - Modern design with gradients
   - **Created:** March 25, 2026
   - **Status:** New, needs user review for accuracy

3. **`/master-timeline`** (`src/pages/master-timeline.astro`) ⭐ NEW
   - Renders `MASTER_NARRATIVE_TIMELINE.md` as webpage
   - Complete source document displayed in browser
   - Simple markdown-to-HTML conversion
   - **Created:** March 25, 2026
   - **Purpose:** Easy review without leaving website

#### Other Key Pages

- **`/links`** - Quick reference hub for all content (updated to highlight 3 narratives)
- **`/founder-story`** - Credibility page about Gautam
- **`/pitch`** - Web version of investor pitch
- **`/team-deck`** - Web version of team recruitment deck
- **`/press-mentions`** - 30+ media stories archive
- **`/blog`** - Blog posts (including "what-12-years-building-edtech-taught-me")

---

## The 5 Acts Framework (Core Narrative Structure)

This is the NEW organizing principle for the evolution story:

### Act I: The Physical Beginning (2012-2015)
- **Organization:** Startup Village, Kochi
- **Business Model:** Government grants + CSR funding
- **Delivery:** Physical incubator, in-person mentorship
- **Customer:** Any startup (all stages)
- **Key Learning:** "We built a community, not a platform"
- **Breakthrough Insight:** "At scale, one person can't help a thousand people"
- **Decision:** "Student startups only" (Jan 2015)

### Act II: The Digital Experiment (2014-2018)
- **Organization:** SV.CO (Startup Village Collective)
- **Business Model:** Freemium + cohort fees (₹5K-₹15K)
- **Delivery:** Web-only platform, structured progression
- **Customer:** Student startups exclusively
- **Key Learning:** Students need skills development, not startup advice
- **Breakthrough Question:** Changed from "help students start startups" to "help students become genuinely capable"
- **Decision:** Complete pivot to skills over startups (Nov 2017)

### Act III: University Integration Era (2018-2023)
- **Organization:** Pupilfirst
- **Business Model:** B2B2C corporate-funded university programs
- **Delivery:** LMS platform with credit integration
- **Customer:** Corporates + Universities
- **Key Experiments:** Hackkar (failed), Apple @ Manipal (worked), Facebook VR (mission misalignment), Freshworks (mission alignment = success)
- **Key Learning:** "Mission alignment isn't soft—it's operational"
- **Platform Achievement:** Built LMS comparable to $100M+ platforms, open-sourced

### Act IV: The Great Unbundling (2023-2024)
- **Organization:** Pupilfirst (D2C pivot)
- **Business Model:** Subscription (₹999/month or ₹4,999/6 months)
- **Delivery:** Self-serve platform + Academic Bank of Credits (ABC)
- **Customer:** Individual students directly
- **Key Decision:** "LITE is a failure—stop it" (Nov 2023 - B2B2C too slow)
- **Philosophy:** Unbundle degrees, offer re-bundling on student's terms

### Act V: The AI Revolution (2024-Present)
- **Organization:** EduMyna
- **Business Model:** Subscription + AI-driven unit economics
- **Delivery:** AI-augmented learning (automated grading, personalized paths, 24/7 assistants)
- **Customer:** Millions of students
- **Key Insight:** To reach millions at ₹999/month, need intelligent automation at every layer
- **The Integration:** Pupilfirst infrastructure + The Second Design pedagogy + AI-first delivery

---

## Important Decisions & Patterns

### Content Strategy
1. **Three versions of the narrative exist** - User plans to review them for consistency
2. **MASTER_NARRATIVE_TIMELINE.md is source of truth** - update it first, then derive other content
3. **Open source philosophy** - transparency, knowledge sharing (reflected in Pupilfirst being open-sourced)
4. **Honest storytelling** - includes failures (Hackkar, LITE, Vizag expansion)

### Design Patterns
1. **Responsive-first** - all pages mobile-optimized
2. **Tailwind CSS** - utility-first styling
3. **Dark hero sections** - `bg-slate-900` with light text for headers
4. **Color-coded phases** - Each Act has distinct color (amber, blue, purple, emerald, rose/violet)
5. **Gradient accents** - Modern feel with `bg-gradient-to-br`
6. **Stats boxes** - Grid of metrics with borders and hover effects
7. **Timeline visualizations** - Vertical timelines with connecting lines

### Code Patterns
1. **Astro components** - Use `@/layouts/Layout.astro` and `@/components/container.astro`
2. **Prose styling** - Use `prose prose-slate prose-lg` for markdown/long-form content
3. **Images** - Stored in `/public/images/story/` directory
4. **No React needed** - Pure Astro for static content

### Git Workflow
1. **Always commit with descriptive messages**
2. **Use Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>**
3. **Push to `origin main`** after committing
4. **Auto-deployment** - likely configured, check after push

---

## Recent Work (March 25, 2026)

### What Was Accomplished

1. **Converted Office files to PDF** (409 files)
   - Used LibreOffice headless conversion
   - 299 .docx, 78 .xlsx, 27 .pptx, 5 .doc → PDF
   - Reason: Claude Code can read PDFs but not binary Office files

2. **Analyzed Origin Story folder**
   - Read strategic documents from 2015, 2018, 2023
   - Extracted evolution narrative from PDFs
   - Identified 5 Acts framework from documents

3. **Created /evolution page**
   - New visual showcase of organizational transformation
   - Interactive timeline, business model evolution table
   - 6 key insights from 12 years

4. **Created /master-timeline page**
   - Renders markdown source as webpage
   - Allows easy review without GitHub

5. **Updated MASTER_NARRATIVE_TIMELINE.md**
   - Added 5 Acts Framework section at top
   - Added deep narrative dives for each Act
   - Added Business Model Evolution table
   - Added Key Insights section

6. **Updated /links page**
   - Highlighted three narrative versions for review
   - Added new pages to navigation

### What's Pending

**USER WANTS TO REVIEW THREE NARRATIVES FOR CONSISTENCY:**
1. `/story` - Original version
2. `/evolution` - New 5 Acts version
3. `/master-timeline` - Complete markdown source

**Expected Next Steps:**
- User will review all three pages
- User will provide feedback on inconsistencies, inaccuracies, or narrative misalignments
- Claude should update all three sources to ensure consistency
- Final narrative should be accurate representation of 12-year journey

---

## How to Resume Work

### Starting a New Session

1. **Check what's running:**
   ```bash
   npm run dev
   # Opens http://localhost:4323/
   ```

2. **Key pages to check:**
   - http://localhost:4323/story
   - http://localhost:4323/evolution
   - http://localhost:4323/master-timeline
   - http://localhost:4323/links

3. **If user gives feedback on narratives:**
   - Update `MASTER_NARRATIVE_TIMELINE.md` first (source of truth)
   - Then update `src/pages/evolution.astro`
   - Then update `src/pages/story.astro`
   - Ensure consistency across all three

4. **When making content changes:**
   - Read the existing content first
   - Preserve the voice and style
   - Keep the "honest failures" approach
   - Maintain specific metrics and dates

### Common Tasks

**Adding a new page:**
```bash
# Create in src/pages/
# Use Layout component from @/layouts/Layout.astro
# Add to /links page for reference
```

**Updating narrative content:**
```bash
# 1. Update MASTER_NARRATIVE_TIMELINE.md
# 2. Update relevant .astro page
# 3. Test locally
# 4. Commit and push
```

**Deploying changes:**
```bash
git add -A
git commit -m "Description

Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>"
git push origin main
```

---

## Key Metrics to Remember

These should be consistent across all narratives:

- **500 startups** supported (promised 48, delivered 500)
- **3,139 jobs** created
- **₹45 crores** funding raised by startups
- **₹14.6 crores** total investment
- **1,500+ learners** through The Second Design/RealWorldReady
- **10,000 Raspberry Pis** distributed (Learn to Code program)
- **Dec 5, 2018:** pupilfirst.com domain registered
- **Nov 2023:** "LITE is a failure—stop it" decision
- **₹999/month or ₹4,999/6 months:** Current pricing model
- **63% rated 10/10:** RealWorldReady program outcomes

---

## Important Context About Gautam

- Co-founder of Startup Village (2012-present legacy)
- Co-founder of Pupilfirst (still is, but vision divergence led to parallel path)
- Founded The Second Design with Dr. Aruna Kesavan (2022)
- Now building EduMyna as integration of all learnings
- 12+ years in education technology
- Partnerships: Facebook, Apple, Freshworks, 4 state governments, MIT
- Philosophy: "Help others enable themselves" (unchanged since 2009)
- Approach: Open source, honest about failures, systems thinking

---

## Origin Story Folder

**Location:** `/Users/gauthamgautham/Code/EduMyna/EduMyna Origin Story/`

**Contains:** 956 files documenting 12-year journey
- Strategic documents, pitch decks, financial models
- Photos from events, campus, Silicon Valley trips
- Partnership agreements, government proposals
- All converted to PDF for Claude Code readability

**Key documents read:**
- SV Context & Questions - March 2015.pdf
- Strategic Review - Feb_March 2018 - Founders_ Perspective.pdf
- SV.CO Context and Direction Document October 2018.pdf
- Pupilfirst Status Update - Nov 2023.pdf

---

## Troubleshooting

### Dev server issues
- Ports 4321, 4322 often occupied → usually runs on 4323
- Check: `tail -f /tmp/claude/-Users-gauthamgautham-Code-EduMyna/tasks/[task-id].output`

### Markdown rendering issues
- Don't use `@apply` in `<style>` blocks with Tailwind 4.0
- Use direct CSS properties instead
- The prose classes handle most markdown styling

### Image references
- Images in `/public/images/story/`
- Reference as `/images/story/filename.jpg` in pages

---

## Questions to Ask User When Resuming

1. "Would you like me to continue working on the narrative consistency review?"
2. "Have you reviewed the three narrative versions (/story, /evolution, /master-timeline)?"
3. "Do you have feedback on the accuracy of the 5 Acts framework?"
4. "Are there any specific sections or dates that need correction?"

---

## Additional Resources

- **GitHub Repo:** https://github.com/EduMyna/EduMyna.com
- **Pupilfirst (referenced):** https://www.pupilfirst.org/
- **The Second Design:** https://theseconddesign.com/

---

**End of Context Document**

This document should be updated whenever significant decisions are made or project structure changes.
