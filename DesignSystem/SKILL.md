---
name: decisive-future-business-design
description: Use this skill to generate well-branded interfaces and assets for 「決勝！未來商務」(Decisive Future Business) — a keynote-presentation visual system for a Traditional-Chinese 經典企業 AI 加速器 (Classic Enterprise AI Accelerator) program. The system is gold-on-black, austere, and presentation-first. Contains palette, typography, eight canonical slide templates, line-icon conventions, and copy / tone rules.
user-invocable: true
---

# 決勝！未來商務 — Brand Design Skill

Read `README.md` first — it is the source of truth. The short version:

- **Palette · only these four:** `#141414` 紋理深黑 · `#D4AF37` 璀璨金 · `#F5F5F5` 柔和白 · `#8A8A8A` 石墨灰. No tints, no gradients, no off-brand accents.
- **Type:** Noto Sans TC for Chinese, Montserrat for Latin/digits. Wide tracking (10–25%). H1 gold/bold, H2 white/medium, body white/regular, captions grey/light.
- **Grid:** 8pt base; every gap is `8 × n`. 5% safe-margin on every slide edge.
- **Motion:** fade only, 0.2–0.3s. No slide-ins, no bounces, no spring, no parallax.
- **Imagery:** B&W high-contrast only. Type over imagery always sits on a 70–80% `#141414` mask.
- **Icons:** line only, 1.5–2px stroke, gold or white. Default substitute = Lucide (CDN). Never emoji.
- **Corners:** 0px almost everywhere; 2px max on portraits / QR.
- **Voice:** Traditional Chinese, authoritative, low-volume, declarative sentences ending in 。— no `！` except inside the brand mark itself, no `你/妳`, no emoji, no exclamatory copy.

## When invoked
- If creating slides / mocks / throwaway visuals: link `colors_and_type.css` and copy directly from `slides/` (8 canonical templates: cover, chapter, speaker, quote, three-columns, data, big-number, thank-you). Copy assets out of `assets/` rather than referencing them by absolute path.
- If working on production code: read `colors_and_type.css` and lift the variables verbatim. Treat `--bg`, `--gold`, `--fg`, `--muted`, `--x`, `--x-2…`, the type tokens, and `--t-fade` as the contract.
- For icons, prefer line SVGs at 1.5–2px stroke. If using a library, use Lucide. Never mix icon families.

## If invoked with no further instruction
Ask the user what they want to build (deck, single slide, web mock, social asset), then ask: how many slides / variants; any specific data, names, dates, photography to include; any deviation from the canonical four colors. Default to producing static HTML at 1920×1080 using the `slides/` templates as the seed.

## Forbidden
- Bluish-purple gradients, soft cards with rounded corners + colored left-border accents, drop-shadows on cards.
- Emoji in body copy. Unicode pictographs as icons (✓ ★ ➤).
- Mixing simplified Chinese into Traditional Chinese copy.
- More than one gold highlight per chart.
- Any color outside the four-color palette.
