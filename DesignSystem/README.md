# 決勝！未來商務 Design System
**Decisive! Future Business — Design System**

A complete visual design system for "決勝！未來商務" (Decisive Future Business), a Traditional-Chinese business-presentation theme for a 經典企業AI加速器 (Classic Enterprise AI Accelerator) program. The system targets keynote-style presentations: dark theatre lighting, gold-on-black typography, austere whitespace, B&W imagery.

> **Source documents**
> - `uploads/style-guide.pdf` — original Traditional-Chinese style index (4 pages, "簡報設計風格索引")
>
> No codebase, Figma, or product UI was provided. This system is therefore presentation-only — there are no app or web UI kits, only `slides/` and the visual foundations they share.

---

## 1 · Brand Concept

The system is built around three core principles, all in service of a high-prestige stage talk:

| Principle | Chinese | Meaning |
|---|---|---|
| Immersive & Focused | 沉浸與聚焦 | Deep dark backgrounds + high contrast remove distraction — the audience sees only the speaker and the content. |
| Authoritative & Valuable | 權威與價值 | Black-and-gold palette + stable, restrained layouts signal expertise, high stakes, and a premium audience experience. |
| Minimal & Powerful | 簡潔與力量 | Strict "less is more" — large blank/black space is deliberate so every word and chart lands with weight. |

If a design choice does not visibly serve at least one of those three, remove it.

---

## 2 · Content Fundamentals

The original guide is written in Traditional Chinese; the design system inherits the same voice for any speaker-facing content.

- **Language:** Traditional Chinese (繁體) for body copy and titles; English used only for proper nouns, numbers, acronyms, and chapter labels like `CHAPTER 01`. No simplified Chinese.
- **Tone:** authoritative, measured, slightly formal. Confident statements over enthusiastic hype. No exclamation marks inside body copy (the brand mark itself uses one — `決勝！未來商務` — that's the only allowed `！`).
- **Person:** rarely "我", almost never "你" — talks _about_ the topic ("企業如何…", "市場將會…") rather than to the reader. Lectern voice, not chat voice.
- **Casing for English:** TITLE CASE or ALL CAPS for chapter/section labels (`THANK YOU`, `Q&A`, `CHAPTER 01`). Body English follows normal sentence case.
- **No emoji.** The system explicitly forbids decorative glyphs in body copy — every visual element has to come from the palette, type system, or a line icon.
- **Numbers and metrics:** Western digits (2026, $4.2B), never full-width. Pull the most important number out at H1/H2 scale in gold; everything else stays in body white.
- **Quotes:** use curly typographic quotes 「」 for Chinese, "" for English. The decorative giant `"` glyph used as background art on quote slides is a 20%-opacity graphite-grey object, not a quote mark used for reading.
- **Density:** one slide = one idea. Most slides have **fewer than 30 Chinese characters**. If a slide needs a paragraph, the paragraph is the slide.
- **Examples of in-brand copy:**
  - `決勝！未來商務` (master wordmark)
  - `沉浸與聚焦` (chapter title; 4-character balanced compound)
  - `克制地使用設計元素，奉行「少即是多」原則。` (body — declarative, ends with 。)
  - `THANK YOU` (closing slide — English, all caps, gold)

---

## 3 · Visual Foundations

### Palette
Exactly four colors. No tints, no gradients, no off-brand accents.

| Token | Name | HEX | RGB | Role |
|---|---|---|---|---|
| `--bg` | 紋理深黑 Textured Deep Black | `#141414` | 20, 20, 20 | Page background, image overlay |
| `--gold` | 璀璨金 Brilliant Gold | `#D4AF37` | 212, 175, 55 | Titles, key data point, dividers, the one thing the eye should land on |
| `--fg` | 柔和白 Soft White | `#F5F5F5` | 245, 245, 245 | Body copy, subtitles |
| `--muted` | 石墨灰 Graphite Grey | `#8A8A8A` | 138, 138, 138 | Captions, footnotes, secondary chart series, "ghost" background art |

**Gold is the rarest colour.** On a normal slide, gold occupies < 20% of inked pixels — usually just the title, one number, or a 1px rule. If everything is gold, nothing is.

### Typography
- **Chinese:** 思源黑體 / **Noto Sans TC** (Google Fonts)
- **Latin/digits:** **Montserrat** (Google Fonts)
- Both are free Google Fonts — no licensing concern, no local font files required, but `fonts/` contains a fallback `@font-face` declaration loading from the Google CDN.

| Level | Use | Family / Weight | Size (pt) | Color | Tracking |
|---|---|---|---|---|---|
| H1 | Chapter title | Noto Sans TC Bold / Montserrat Bold | 44 – 56 | Gold | 15 – 25 % |
| H2 | Page subtitle | Noto Sans TC Medium / Montserrat Medium | 28 – 36 | White | 10 – 15 % |
| P  | Body | Noto Sans TC Regular | 20 – 24 | White | 5 – 10 % |
| Accent | Pull quotes | Noto Sans TC Regular Italic | 24 – 28 | Grey | 10 % |
| Note | Caption / footnote | Noto Sans TC Light | 14 – 16 | Grey | 5 % |

Chinese letter-spacing of 15–25% is unusually wide; this is intentional — it slows the eye and reinforces the formal, "carved" feel.

### Spacing & grid
- Base unit **X = 8pt**. Every gap, padding, and offset is `8 · n` (8, 16, 24, 32, 48, 64, 96).
- Safe margin: **5%** of slide on every edge. No content crosses that line, including the corner Logo.
- 12-column implicit grid; the "speaker intro" template hard-codes a 4:6 split.

### Backgrounds & imagery
- Default background: solid `#141414`. **No gradients.** No noise overlays beyond a very subtle 2-3% film grain if used (optional, never required).
- Photography is **always high-contrast black & white** — never colour, never duotone other than pure greyscale. Treat photos as theatre lighting: deep blacks, bright highlights, no mid-grey mush.
- For text over imagery, drop a **70–80% opacity `#141414` mask** on top of the image first, then place the type. Never put white type directly on a photo without the mask.
- Hand-drawn illustrations, stock vectors, doodles, and emoji are **forbidden**.

### Lines, dividers, borders
- Divider rule: **1 px solid gold** (`#D4AF37`). Used to separate label from value or section from section.
- No multi-pixel borders, no rounded card outlines, no inner-shadow. Containers are usually invisible — composition is by alignment, not boxes.
- Where a "card" is needed (e.g., bio panel), it is just a region with consistent padding on `--bg`. No fill change, no border, no shadow.

### Corner radii
- **0 px almost everywhere.** Sharp corners reinforce the "carved" aesthetic. The single exception: QR codes and speaker portraits may use a **2 px** radius at most; treat that as the cap, not the default.

### Shadows / elevation
- **None.** No box-shadow on cards or charts. The brand achieves depth via contrast (black vs gold), not via simulated light.

### Transparency & blur
- Used sparingly. Two sanctioned uses:
  1. The 70–80% black mask over imagery.
  2. The 20%-opacity giant `"` glyph behind quote slides.
- No backdrop-blur, no frosted glass, no parallax.

### Motion
- **Page transition:** Fade only, 0.3 s.
- **Object reveal:** Fade-in only, 0.2–0.3 s, used solely for stepped reveals. Never on every element.
- No slide-in, no zoom, no bounce, no spring, no easing curves other than `ease` / `ease-in-out`.
- Hover (web-rendered slides): targets dim by **15% opacity** or shift to gold; never scale or wiggle.
- Active/press: shift to gold momentarily (no scale).

### Charts
- Only palette colours. Highlight series = gold; everything else = grey.
- **Strip away** chart background, frame, gridlines, shadows, 3-D effects.
- One gold "hero" data point per chart — that is the slide's argument.
- All chart text in Noto Sans TC at Note (14–16pt) or P (20–24pt) sizes.

### Layout rules / fixed elements
- Bottom-right corner: small wordmark or chapter dot. Never a logo at top of slide.
- Page number (when used): bottom-left, Note style, grey.
- Header bars, breadcrumbs, footers, watermarks — none.

---

## 4 · Iconography

The original guide gives a single explicit rule: **simple, unfilled, line icons**, coloured gold or white. There is no built-in icon set, no codebase to copy from, and no Figma library.

- **Recommended set:** [Lucide](https://lucide.dev) — line-style, consistent 2 px stroke, free, CDN-available at `https://unpkg.com/lucide@latest/dist/umd/lucide.js`. This is the system's default icon source.
- Stroke weight: **1.5 – 2 px**. Never filled. Never multi-colour.
- Sizes: 16 / 24 / 32 / 48 px on the 8pt grid.
- Colour: gold (`--gold`) when the icon is the highlight of the line, white (`--fg`) when it is incidental, grey (`--muted`) for footnote-level icons.
- **No emoji**, no Unicode pictographs as icons (no ✓ ★ ➤), no Material/Heroicons mixed in. Pick line icons from one family per deck.
- **Substitution flag:** Lucide is a CDN substitute — the original guide did not name an icon system. If the user has a preferred line set, swap it into `assets/icons/`.

---

## 5 · Index of this design system

| Path | What it is |
|---|---|
| `README.md` | This file. |
| `SKILL.md` | Cross-compatible skill prompt so a Claude Code / agent can pick up this system. |
| `colors_and_type.css` | CSS variables + semantic type rules (`h1`, `h2`, `p`, `.accent`, `.note`). Drop-in stylesheet for any new slide or artifact. |
| `fonts/` | `@font-face` declarations pointing at Google Fonts (Noto Sans TC, Montserrat). |
| `assets/` | Logos and wordmarks generated for the brand mark `決勝！未來商務`, plus a sample B&W speaker portrait placeholder. |
| `slides/` | The five canonical slide types from Part 5 of the guide, plus a chart slide and a content slide — rendered as one HTML file each, 1920×1080. |
| `preview/` | The cards that populate the Design System tab. |

---

## 6 · Font Substitution Note

The original guide names **思源黑體 (Noto Sans TC)** and **Montserrat**. Both are free Google Fonts — no licensing substitution was needed. If you require local `.ttf`/`.otf` files (e.g. for InDesign export, offline keynote, or production print), please drop them into `fonts/` and we'll update `@font-face` to use them. The current `fonts/fonts.css` loads them from the Google Fonts CDN.

---

## 7 · Caveats

- No real product UI was provided, so this system covers slides + tokens only. There are no app or web UI kits.
- The brand wordmark and logo here are **generated for this system** — they are typographic constructions of `決勝！未來商務` using the brand's own type rules. If you have an official logo lockup, drop it into `assets/` and we'll wire it in.
- The system substitutes **Lucide** as the line-icon set; the guide named no specific icon library.
