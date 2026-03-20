---
name: shoemaker-cpa-brand
description: Applies Shoemaker CPA's official brand identity to any frontend artifact, page layout, component, document, or visual asset. Use this skill whenever generating UI, HTML, React, landing pages, components, email templates, social media assets, presentations, or any visual deliverable for Shoemaker CPA or Luke Shoemaker's accounting firm. Also trigger when the user mentions "Shoemaker," "shoemaker-cpa," "Luke's site," or references the multifamily office / business advisory website project. This skill must be used alongside the frontend-design skill for all page and component generation.
---

# Shoemaker CPA — Brand Identity Skill

## Overview

Shoemaker CPA is a Virginia-based accounting firm built around two pillars: a **multifamily office** for integrated tax and wealth management (partnership with CFP Jesse Stacy), and a **business advisory practice** for closely held family businesses under $20M in revenue. The firm was acquired by Luke Shoemaker, CPA, who is modernizing a 650-client legacy practice into a premium, coordinated advisory model.

This skill ensures every artifact produced for this project is on-brand without manual correction.

---

## Brand Color System

Use CSS custom properties. Every artifact must define these at `:root` or the top-level container.

```css
:root {
  /* Primary palette — navy-to-blue gradient system */
  --color-midnight:    #000026;  /* Deepest navy. Hero backgrounds, footer, high-contrast sections */
  --color-navy:        #18224d;  /* Secondary dark. Nav backgrounds, card backgrounds, section breaks */
  --color-blue:        #1160ad;  /* Primary accent. Links, borders, trust signals, active states */
  --color-sky:         #48a4d5;  /* CTA accent. Buttons, hover states, interactive elements */
  --color-ice:         #cfe4f2;  /* Light wash. Section backgrounds, subtle fills, breathing room */

  /* Functional tokens */
  --color-bg-dark:     #000026;
  --color-bg-medium:   #18224d;
  --color-bg-light:    #cfe4f2;
  --color-bg-white:    #ffffff;
  --color-text-on-dark:  #ffffff;
  --color-text-on-light: #000026;
  --color-text-muted:    #48a4d5;
  --color-accent:        #1160ad;
  --color-cta:           #48a4d5;
  --color-cta-hover:     #1160ad;
  --color-divider:       rgba(17, 96, 173, 0.2);
}
```

### Color Usage Rules

- **Dark sections** (hero, footer, alternating content blocks): Use `--color-midnight` or `--color-navy` as background. White text. Blue accents for links and interactive elements.
- **Light sections** (content areas, about, forms): Use `--color-ice` or white. Midnight text. Blue accents for emphasis.
- **CTAs**: Primary buttons use `--color-sky` background with white text. Hover shifts to `--color-blue`. Secondary/ghost buttons use transparent background with `--color-blue` border and text.
- **Never** use the blues as large background fills on their own — they're accents, not primaries. The palette anchors on dark navy and light ice/white, with blue as the connecting thread.
- **Gradients**: When used sparingly, gradient from `--color-midnight` to `--color-navy` for dark sections. Or `--color-ice` to white for light sections. No multi-color rainbow gradients. No purple. No green (Luke mentioned liking green early on but the approved brand direction is the navy-blue system).

---

## Typography

```css
/* Font imports — use Google Fonts for Tiempos substitute, system Helvetica */
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;1,400&display=swap');

:root {
  /*
   * Brand specifies: Tiempos Regular (headline), Helvetica (sub/body)
   *
   * Tiempos is a commercial font (Klim Type Foundry). For web artifacts and
   * prototypes, use Playfair Display as the closest available substitute —
   * it shares the editorial serif character, high contrast, and premium feel.
   * Final Webflow build will use licensed Tiempos files.
   *
   * Helvetica is a system font and available natively on macOS/iOS.
   * Use the standard Helvetica stack with Arial fallback for cross-platform.
   */
  --font-headline: 'Playfair Display', 'Tiempos Regular', Georgia, serif;
  --font-body: Helvetica, 'Helvetica Neue', Arial, sans-serif;
}
```

### Typography Hierarchy

| Element | Font | Weight | Size (desktop) | Size (mobile) | Case |
|---------|------|--------|----------------|---------------|------|
| H1 (hero headline) | `--font-headline` | 600 | 56–72px | 36–44px | Sentence case |
| H2 (section headline) | `--font-headline` | 500 | 40–48px | 28–34px | Sentence case |
| H3 (card/subsection) | `--font-headline` | 500 | 28–32px | 22–26px | Sentence case |
| Subheadline / Eyebrow | `--font-body` | 500 | 14–16px | 12–14px | UPPERCASE, letter-spacing: 0.08em |
| Body text | `--font-body` | 400 | 16–18px | 15–16px | Sentence case |
| Small / Caption | `--font-body` | 400 | 13–14px | 12–13px | Sentence case |
| Button text | `--font-body` | 500 | 15–16px | 14–15px | Sentence case |
| Nav links | `--font-body` | 400 | 15px | 14px | Sentence case |

### Typography Rules

- **Headlines are always serif** (`--font-headline`). This is the single biggest differentiator from generic CPA sites that use all-sans-serif stacks.
- **Body is always sans-serif** (`--font-body`). Clean, neutral, high legibility.
- **Never use all-caps for headlines.** Uppercase is reserved for eyebrow labels and small utility text only.
- **Line height**: Headlines at 1.1–1.2. Body at 1.5–1.7. Generous but not loose.
- **Max body text width**: 680px. Prevents readability fatigue on wide screens.
- **Letter spacing on headlines**: -0.01em to -0.02em (slight tightening for premium feel).

---

## Voice & Tone

Shoemaker CPA's copy sits at the intersection of **professional credibility** and **human approachability**. It should feel like talking to a smart advisor who respects your time, not a firm trying to impress you with jargon.

### Tone Guardrails

- **DO**: Speak plainly. Use first person ("we" for the firm, "you" for the client). Be specific about what the firm actually does. Acknowledge that financial decisions are stressful.
- **DO**: Use confident, declarative sentences. "We coordinate your tax and wealth strategy under one roof." Not: "We strive to provide integrated solutions for your financial needs."
- **DON'T**: Use corporate buzzwords — "synergy," "leverage," "solutions," "holistic approach," "optimize your financial journey."
- **DON'T**: Be overly casual or jokey. This is people's money and their family businesses. Warmth, not comedy.
- **DON'T**: Be vague. Every statement should pass the "so what?" test.

### Headline Style

Headlines should be benefit-driven or position-establishing, not feature-listing.

**Good:**
- "Your tax strategy and wealth plan shouldn't live in separate rooms."
- "Year-round advisory for the businesses families build."
- "One team. One plan. No blind spots."

**Bad:**
- "Comprehensive Tax and Wealth Management Services"
- "Welcome to Shoemaker CPA"
- "Trusted Accounting Firm in Virginia"

---

## CTA Hierarchy

Every page must include both CTAs. They are persistent and consistent site-wide.

| Priority | Label | Action | Style |
|----------|-------|--------|-------|
| Primary | "Schedule a Conversation" | Calendly booking link | Solid button, `--color-sky` bg, white text |
| Secondary | "Client Login" | TaxDome portal link | Ghost button or utility link, `--color-blue` border/text |
| Tertiary | "Subscribe to Our Newsletter" | Email capture / newsletter embed | Inline form or text link, used in footer and Resources page |

### CTA Rules

- "Schedule a Conversation" — not "Book a Call," not "Get Started," not "Contact Us." The word "conversation" is intentional. It's low-pressure and signals that Luke listens before he prescribes.
- "Client Login" lives in the utility nav (top-right of header), never in the main nav flow. Existing clients need it; prospects don't.
- Never use "Learn More" as a standalone CTA. If linking to a deeper page, be specific: "See how we work with business owners" or "Explore the multifamily office model."

---

## Layout Principles

### Spatial Rules

- **Section padding**: 80–120px vertical on desktop, 48–64px on mobile.
- **Container max-width**: 1200px, centered.
- **Grid**: 12-column grid for complex layouts. Simple sections can use flexbox.
- **Rhythm**: Alternate between dark and light sections to create visual breathing. Avoid more than two consecutive light or dark sections.
- **Asymmetry is fine**: The front-end design skill encourages grid-breaking. For Shoemaker CPA, this means offset images, text blocks that don't center-align everything, and occasional diagonal or overlapping elements — but always controlled. This is a financial firm, not a skateboard brand.

### Component Patterns

- **Cards**: Subtle borders using `--color-divider`, not drop shadows. On hover, border shifts to `--color-blue`. Clean, flat, no rounded corners over 8px.
- **Section dividers**: Thin 1px lines using `--color-divider`, or use color-block transitions (dark section → light section) instead of explicit dividers.
- **Images**: When using placeholder or stock imagery, favor: office environments, Virginia landscape, professional but candid people shots. Avoid: generic handshake photos, calculator-and-spreadsheet clichés, stock photos of diverse boardrooms that feel forced.
- **Icons**: If used, line-style icons only. Consistent stroke weight. Navy or blue on light backgrounds, white or ice on dark backgrounds.

### Navigation

```
┌─────────────────────────────────────────────────────────┐
│ [Logo]   Home | Multifamily Office | Business Advisory  │
│          | About | Resources | Contact                  │
│                                    [Client Login] [CTA] │
└─────────────────────────────────────────────────────────┘
```

- Logo left-aligned, uses the horizontal lockup from the brand guidelines.
- Main nav center or left-aligned after logo.
- Utility nav right-aligned: "Client Login" as a text link, "Schedule a Conversation" as a small solid button.
- On mobile: hamburger menu, CTA button persists in header.
- Nav background: `--color-navy` or white, depending on page context. Dark nav for pages with light hero sections, transparent/white nav for pages with dark hero sections.

---

## Audience Context

When generating content or layouts, understand which audience a page serves:

### Multifamily Office Audience
- **Who**: High-net-worth individuals, typically 45–70, with complex tax situations and existing wealth management needs.
- **What they want**: Coordination between their CPA and financial advisor. One team, one plan. No conflicting advice.
- **Emotional state**: Frustrated by fragmentation. Worried about blind spots. Want to feel handled.
- **Visual tone**: Calmer, more white space, premium/editorial feel. Lean into `--color-ice` backgrounds.

### Business Advisory Audience
- **Who**: Owners of closely held family businesses, $5–20M revenue. Operators, not passive investors.
- **What they want**: A CPA who understands their business, not just their tax return. Year-round strategic support.
- **Emotional state**: Overwhelmed, wearing too many hats. Want someone in their corner who's proactive.
- **Visual tone**: Slightly more energetic, structured, authoritative. Lean into `--color-navy` and `--color-midnight` backgrounds.

---

## Logo Usage

The brand mark is a geometric, angular icon that sits above or beside "Shoemaker CPA" in Tiempos-style serif lettering.

- **Horizontal lockup**: Icon left, text right. Use in navigation headers.
- **Stacked lockup**: Icon above, text below. Use in footer, hero sections, or standalone brand moments.
- **Icon only**: Use at small sizes (favicon, social profile thumbnails, apparel chest placement).
- **Minimum clear space**: The icon's own width on all sides.
- **On dark backgrounds**: White or `--color-ice` logo. Never place the navy logo on a dark background.
- **On light backgrounds**: `--color-midnight` or `--color-navy` logo.
- **Never**: Stretch, rotate, recolor with non-brand colors, add effects (shadows, glows, outlines).

---

## Motion & Interaction

- **Page load**: Staggered fade-in. Hero headline first, then subtext, then CTA, then below-fold content. Use `animation-delay` in 100–150ms increments. Subtle translate-y (10–20px) paired with opacity. Duration: 600–800ms with ease-out.
- **Scroll reveals**: Sections fade in as they enter viewport. Use Intersection Observer. Subtle, not dramatic — 20px translate-y max.
- **Hover states**: Buttons shift from `--color-sky` to `--color-blue`. Cards get a border-color transition. Links get an underline slide-in. All transitions 200–300ms ease.
- **No**: Parallax backgrounds, bouncing elements, particle effects, animated gradients, or anything that makes this feel like a tech startup landing page.

---

## Anti-Patterns (What to Avoid)

These are the things that make CPA firm websites look identical. Do not do any of them:

1. **White background + blue accent + stock handshake hero image** — the single most common CPA site pattern. We use dark navy heroes instead.
2. **Three equal-width service columns with icons** — ("Tax Prep | Bookkeeping | Advisory"). We use distinct pillar pages with real content instead.
3. **"Welcome to [Firm Name]" as the hero headline** — a wasted opportunity. Lead with a value proposition.
4. **Cluttered footer with every page link, social icon, and legal disclaimer crammed together** — clean, organized footer with clear hierarchy.
5. **Generic "About Us" with a paragraph of corporate-speak** — Luke has a real story. Use it.
6. **Testimonial carousels with anonymous quotes** — if we use testimonials, they're static, attributed, and integrated into the page flow.
7. **Overly rounded corners, heavy drop shadows, gradient buttons** — the Shoemaker aesthetic is flat, sharp, editorial.
