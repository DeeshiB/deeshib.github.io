---
name: deeshi-website-visual-language
description: >
  Deeshi.co visual language system and blog entry generator. TRIGGER when: user mentions
  "deeshi.co", "deeshi blog", "blog entry", "write a post for deeshi", "create a blog",
  "deeshi website", or invokes /deeshi-website-visual-language. Use this skill to generate
  blog content, pages, or components that follow the deeshi.co brand system.
  DO NOT TRIGGER when: user is working on unrelated web projects or non-deeshi content.
argument-hint: "[blog topic or page to create]"
---

# Deeshi.co — Visual Language System & Blog Generator

**Source of truth:** Moodboard v7 — `/Users/deepshikhabhardwaj/Documents/Claude folder 2026/site-moodboard-v7-combined.html`

---

## Brand Identity

- **Name:** Deeshi (दीशी) — Deepshikha Bhardwaj
- **Logo:** दी→ (दी in Devanagari inside a circle + arrow). Signifies direction, not arrival.
- **Domain:** deeshi.co
- **Tagline:** "What is the human's job when AI does the work?"

## Two Content Streams

Every blog entry belongs to one (or both) streams:

| Stream | Hindi | Color | Topics |
|---|---|---|---|
| **The Lab** | प्रयोगशाला | kumkum (#c25040) | AI judgment, editorial architecture, methodology, compression, evaluation |
| **The Classroom** | कक्षा | neel (#16606e) | Education, pedagogy, AI tools for parents/kids, Indian boards, worksheets |

The unifying question across both: **"What survives compression?"**

---

## Color Palette — Named After Materials, Not Hex Codes

| Color | Hindi | English | Hex | Role |
|---|---|---|---|---|
| चंदन | Chandan | Sandalwood | `#e8dcc8` | Page background, calm |
| स्याही | Syahi | Ink | `#2a2520` | Primary text |
| हल्दी | Haldi | Turmeric | `#d49520` | Foundational accent, auspicious, section markers |
| कुमकुम | Kumkum | Vermillion | `#c25040` | The Lab stream, annotations, marks |
| नील | Neel | Indigo | `#16606e` | The Classroom stream, depth |
| मिट्टी | Mitti | Clay | `#a87d56` | Grounding, earth, services |
| मेहँदी | Mehendi | Henna | `#4d7a53` | Growth, patience |
| सिंदूर | Sindoor | Sindoor | `#b83228` | Sacred, emphasis |

**Background:** cream `#f7f3ec` with subtle radial gradient washes of haldi-light, kumkum-light, neel-light, mitti-light.

### CSS Variables

```css
:root {
  --ink: #2a2520;
  --ink-80: rgba(42,37,32,0.80);
  --ink-60: rgba(42,37,32,0.60);
  --ink-40: rgba(42,37,32,0.40);
  --ink-20: rgba(42,37,32,0.20);
  --ink-10: rgba(42,37,32,0.10);
  --cream: #f7f3ec;
  --cream-dark: #ece5d8;
  --haldi: #d49520;
  --haldi-light: rgba(212,149,32,0.12);
  --haldi-glow: rgba(212,149,32,0.30);
  --kumkum: #c25040;
  --kumkum-light: rgba(194,80,64,0.10);
  --neel: #16606e;
  --neel-light: rgba(22,96,110,0.08);
  --mitti: #a87d56;
  --mitti-light: rgba(168,125,86,0.12);
  --mehendi: #4d7a53;
  --chandan: #e8dcc8;
  --sindoor: #b83228;
}
```

---

## Typography

| Role | Font | CSS Variable | Usage |
|---|---|---|---|
| **English body & headings** | Crimson Pro | `--serif` | Primary thinking voice. Elegant, high-contrast, editorial. |
| **Hindi / Devanagari** | Baloo 2 | `--deva` / `--deva-serif` | Rounded, friendly, approachable. Used for Hindi text, concept labels, section accents. |
| **Handwriting** | Kalam | `--hand` | Margin notes, annotations, personal asides. Indian Type Foundry — culturally authentic. |
| **Monospace** | IBM Plex Mono | `--mono` | Labels, tags, metadata, navigation, dates. |

### Typography Rules
- English is PRIMARY. Hindi is accent/add-on — never the dominant language.
- Headings: Crimson Pro, 700 weight, `clamp(24px, 3.2vw, 32px)`
- Body: Crimson Pro, 400 weight, 17px, line-height 1.65
- Handwriting annotations: Kalam, 18-20px, slightly rotated (`transform: rotate(-1.5deg)`)
- Mono labels: IBM Plex Mono, 13px, uppercase, letter-spacing 1px
- Devanagari whispers: Baloo 2, 14-20px, opacity 0.4-0.6

```css
--serif: 'Crimson Pro', Georgia, serif;
--hand: 'Kalam', cursive;
--mono: 'IBM Plex Mono', monospace;
--deva: 'Baloo 2', sans-serif;
--deva-serif: 'Baloo 2', sans-serif;
```

---

## Cultural Elements

- **Kolam left border:** Fixed 48px border of radial-gradient dots (haldi, kumkum, neel) running down the left side of every page.
- **Kolam dividers:** SVG dot-and-curve patterns between sections, opacity 0.2.
- **Marigold motif:** Real photograph (Tagetes erecta from Wikimedia), bottom-right corner, 500px, 10% opacity, breathing CSS animation. Soft, hidden, NOT prominent.
- **Gradient washes:** Subtle radial gradients of haldi-light, kumkum-light, mitti-light, neel-light in the background.
- **Hindi as whisper:** Section markers have Hindi first (small) + English label. Not bilingual — just a cultural accent.

---

## Layout Principles

- **Hub-and-spoke:** Click-to-explore, NOT long scroll. Tabs/sections that swap content.
- **Collapsible intro:** Full intro (logo, name, headline, culture anchor) collapses to compact bar (दी→ deeshi दीशी | tagline) when user navigates to a section.
- **Max-width:** 960px, left-padded for kolam border (72px left padding).
- **NO boxy grids, NO card-based UIs, NO template-y layouts.**
- **Margin notes** in Kalam font, slightly rotated, positioned absolutely.
- **Stream-colored left borders** (3px) on content blocks: kumkum for lab, neel for classroom.

---

## Templates

When creating a blog entry or page for deeshi.co, **always ask the user which template(s) to use.** Present this list:

### 1. SUTRA (सूत्र) — Thesis Banner
A gradient-bordered block for the central argument of a post. Top and bottom borders are tricolor gradients (haldi → kumkum → neel). Contains:
- Thesis statement in large serif (Crimson Pro, 300 weight, 20-28px)
- Key phrases underlined in haldi
- Devanagari translation below
- Handwritten annotation in kumkum (Kalam, rotated)

**Best for:** Opening a post with its core argument. "Here is what I'm saying."

```html
<div class="thesis-block">
  <p class="thesis-text">
    Your thesis with <span class="ul-haldi">underlined key phrases</span>
    and <strong>bold emphasis</strong>.
  </p>
  <span class="thesis-deva">हिंदी अनुवाद यहाँ।</span>
  <span class="thesis-annotation">^ handwritten aside</span>
</div>
```

---

### 2. PARAKH (परख) — Concept Grid
A 2-4 column grid of Hindi concepts with color-coded left borders. Each concept has:
- Large Devanagari heading (Baloo 2, 32px, bold)
- Transliteration in mono (uppercase, 13px)
- Meaning in serif
- "Maps to →" connection in handwriting

**Best for:** Introducing vocabulary, frameworks, or a set of related ideas.

```html
<div class="culture-grid">
  <div class="culture-concept">
    <div class="cc-deva">परख</div>
    <div class="cc-transliterate">PARAKH</div>
    <div class="cc-meaning">Evaluation. Discernment.</div>
    <div class="cc-maps-to">→ maps to: your connection</div>
  </div>
  <!-- repeat for each concept -->
</div>
```

---

### 3. DHARA (धारा) — Stream Card
A content block with a colored left border (kumkum for lab, neel for classroom). Contains:
- Devanagari stream name
- English stream name in handwriting (Kalam, 26px)
- Description paragraph
- Topic tags in mono pill badges

**Best for:** Labeling which stream a post belongs to. Showing the two-stream structure.

```html
<div class="stream-current stream-lab">
  <div class="stream-name-deva">प्रयोगशाला</div>
  <div class="stream-name">the lab</div>
  <div class="stream-desc">Description of what this covers.</div>
  <div class="stream-topics">
    <span class="stream-topic">#tag</span>
  </div>
</div>
```

---

### 4. SEEDI (सीढ़ी) — Positioning Ladder
"Not this → but this" comparison lines. Crossed-out text on the left, haldi arrow, bold text on the right, optional Devanagari label.

**Best for:** Defining what something is by contrasting what it isn't. Correcting assumptions.

```html
<div class="positioning-flow">
  <div class="pos-line">
    <span class="pos-not">what it's not</span>
    <span class="pos-arrow">→</span>
    <span class="pos-is">what it actually is</span>
    <span class="pos-deva">हिंदी</span>
  </div>
</div>
```

---

### 5. RANG (रंग) — Color Narrative
Story paragraphs where cultural color names appear as colored inline text (`.cs-h` for haldi, `.cs-k` for kumkum, `.cs-n` for neel, `.cs-m` for mitti, `.cs-me` for mehendi).

**Best for:** Weaving cultural references into analytical prose. Making color do semantic work.

```html
<div class="color-story">
  <p><span class="cs-h">हल्दी (Haldi)</span> is foundational warmth — description here.</p>
  <p><span class="cs-k">कुमकुम (Kumkum)</span> is the analytical mark — description here.</p>
</div>
```

---

### 6. CHINHA (चिह्न) — Section Marker
Bilingual section header with Hindi label (Baloo 2, haldi) + English label (Kalam) + a trailing gradient line.

**Best for:** Starting every major section of a post.

```html
<div class="section-marker">
  <span class="sm-hindi">हिंदी</span>
  <span class="sm-english">english label</span>
</div>
```

---

### 7. NEEM (नींव) — Culture Anchor
A callout block with a 3px left border that's a tricolor gradient (haldi → kumkum → neel). For grounding statements.

**Best for:** Cultural context, methodology statements, "why this matters" asides.

```html
<div class="culture-anchor">
  <p>
    <strong>The bold opening claim.</strong>
    Supporting context and reasoning.
  </p>
</div>
```

---

### 8. KOLAM (कोलम) — Section Divider
SVG kolam dot-and-curve pattern at 20% opacity. Used between major sections.

**Best for:** Visual breathing room between ideas. NOT decorative — structural.

```html
<div class="kolam-divider">
  <svg viewBox="0 0 400 60" fill="none" stroke="currentColor" stroke-width="1.2">
    <circle cx="200" cy="30" r="4"/><circle cx="160" cy="30" r="3"/><circle cx="240" cy="30" r="3"/>
    <circle cx="120" cy="30" r="2.5"/><circle cx="280" cy="30" r="2.5"/>
    <circle cx="180" cy="12" r="2.5"/><circle cx="220" cy="12" r="2.5"/>
    <circle cx="180" cy="48" r="2.5"/><circle cx="220" cy="48" r="2.5"/>
    <path d="M160 30 Q180 8 200 30 Q220 52 240 30" stroke-dasharray="3 3"/>
    <path d="M160 30 Q180 52 200 30 Q220 8 240 30" stroke-dasharray="3 3"/>
    <path d="M120 30 Q140 20 160 30" stroke-dasharray="2 3"/>
    <path d="M240 30 Q260 40 280 30" stroke-dasharray="2 3"/>
  </svg>
</div>
```

---

### 9. DARSHAN (दर्शन) — Site Preview Mockup
A rounded-corner card showing a miniature website preview: dark nav bar (with दी→ logo, nav items in mono), cream body with hero text and post listing with stream-colored borders.

**Best for:** Showing how content will look on the actual site. Design presentations.

```html
<div class="preview">
  <div class="preview-nav">
    <div class="preview-d">दी</div>
    <span class="preview-arrow">→</span>
    <span class="preview-nav-item active">writing</span>
    <span class="preview-nav-item">projects</span>
  </div>
  <div class="preview-body">
    <div class="preview-hero-name">hi, i'm deeshi <span class="preview-hero-deva">दीशी</span></div>
    <div class="preview-hero-title">Post Title Here</div>
    <div class="preview-hero-sub">Subtitle or description.</div>
    <div class="preview-post pp-lab">
      <div class="preview-post-tag">the lab</div>
      <div class="preview-post-title">Post Title</div>
      <div class="preview-post-excerpt">Excerpt text.</div>
    </div>
  </div>
</div>
```

---

### 10. TIPPANI (टिप्पणी) — Margin Note
Absolutely positioned handwritten annotation in Kalam font, kumkum color, slightly rotated. With optional Devanagari sub-note.

**Best for:** Personal asides, "wait —" moments, self-interruptions, metacommentary.

```html
<span class="margin-note" style="right:-10px;top:40px;--rot:-3deg">
  this is the interesting part →
  <span class="margin-note-deva">यही तो बात है</span>
</span>
```

---

### 11. NAKSHA (नक्शा) — IA Tree
Vertical node tree with colored dots (haldi, kumkum, neel, mitti, mehendi) and connected lines. Each node has a page name + Devanagari label + description.

**Best for:** Showing site structure, information architecture, navigation flows.

```html
<div class="ia-flow">
  <div class="ia-node ia-home">
    <div class="ia-page">
      <span class="ia-page-name">/ home</span>
      <span class="ia-page-deva">घर</span>
    </div>
    <div class="ia-desc">Description of this page.</div>
  </div>
</div>
```

---

### 12. PATTI (पट्टी) — Domain/Brand Card
Elevated card with shadow, hover-lift animation. For showcasing a brand choice, recommendation, or featured item.

**Best for:** Highlighting a decision, recommendation, or featured element.

```html
<div class="domain-picks">
  <div class="domain-pick dp-fav">
    <div class="dp-name">deeshi.co</div>
    <div class="dp-why">Reason for this choice.</div>
    <div class="dp-hand">handwritten note</div>
  </div>
</div>
```

---

## Voice & Tone Rules

When writing blog content for deeshi.co:
- **Conversational.** Think out loud. Change your mind in front of the reader.
- **Epistemically honest.** Admit what you don't know. Audit your own claims.
- **Never "expert" or "thought leader."** Always "practitioner with a question."
- **Dry humor, self-deprecating,** embedded in analysis.
- **Three-part structures** over binary ones (three perspectives, three lenses).
- **Cultural grounding is methodology,** not decoration. Don't tokenize.
- **Hindi as accent.** One or two Hindi words per section, always with English context. Never dominant.

---

## MANDATORY: On Every Skill Invocation

**EVERY TIME this skill is triggered — no exceptions — start by displaying this template menu and moodboard link BEFORE doing anything else:**

---

**deeshi.co — visual language system**
**दी→** | [Open Moodboard v7 (live reference)](file:///Users/deepshikhabhardwaj/Documents/Claude%20folder%202026/site-moodboard-v7-combined.html)

Which templates do you want to use?

| # | Template | Hindi | What it does |
|---|---|---|---|
| 1 | **SUTRA** | सूत्र | Thesis banner — gradient-bordered central argument |
| 2 | **PARAKH** | परख | Concept grid — Hindi concepts with color-coded borders |
| 3 | **DHARA** | धारा | Stream card — lab/classroom content label with tags |
| 4 | **SEEDI** | सीढ़ी | Positioning ladder — "not this → but this" |
| 5 | **RANG** | रंग | Color narrative — cultural color names inline |
| 6 | **CHINHA** | चिह्न | Section marker — bilingual header with gradient line |
| 7 | **NEEM** | नींव | Culture anchor — tricolor-bordered callout |
| 8 | **KOLAM** | कोलम | Section divider — SVG dot pattern |
| 9 | **DARSHAN** | दर्शन | Site preview mockup |
| 10 | **TIPPANI** | टिप्पणी | Margin note — handwritten aside |
| 11 | **NAKSHA** | नक्शा | IA tree — vertical node map |
| 12 | **PATTI** | पट्टी | Brand card — elevated recommendation card |

Want me to open the moodboard for reference? (y/n)

---

**Then offer to open the moodboard file** using: `open "/Users/deepshikhabhardwaj/Documents/Claude folder 2026/site-moodboard-v7-combined.html"`

**Wait for the user to pick templates before proceeding.**

---

## Process: Creating a Blog Entry

After the user selects templates:

1. **Identify the stream:** Is this The Lab or The Classroom?
2. **Generate the HTML** using the chosen templates, the color palette, the typography system, and the cultural elements documented above.
3. **Apply the voice rules** — write in Deeshi's voice, not generic blog voice.
4. **Include stream-appropriate colors** — kumkum borders for lab posts, neel borders for classroom posts.

---

## What NOT To Do

- No boxy grids or card-based layouts
- No generic web template aesthetics
- No clinical/corporate colors
- No making Hindi the dominant language (English primary, Hindi accent)
- No "thought leader" or "expert" positioning
- No decorative animation (purposeful only)
- No standard card UIs or long-scroll pages
