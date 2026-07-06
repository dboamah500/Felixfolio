# Design System — Felixfolio (White Theme)

## Product Context
- **What this is:** Personal portfolio of Dr. Felix Tettey-Engmann — Intel Module Development Engineer, PhD researcher (20+ publications, 550+ citations), startup co-founder.
- **Who it's for:** Intel/NVIDIA/TSMC/ASML leadership and recruiters, research institutions, investors.
- **Project type:** Single-page static marketing/portfolio site (Bootstrap 5 Craftivo base, no build step).

## Aesthetic Direction
- **Direction:** Modern premium white — Apple/Vercel/Stripe polish, human and portrait-forward.
- **Decoration level:** Minimal — whitespace, hairline borders, and bold type do the work. No lab-metaphor gimmicks (owner explicitly rejected spec-table heroes, monospace labels, wafer motifs).
- **Mood:** Confident, exact, warm. Reads instantly as "accomplished semiconductor engineer and research leader."

## Typography
- **Display/Headings:** Fraunces (variable serif, optical size 9–144, weight 300–900, italics) — unique, elegant, "fancy" without being frivolous. Weight 700 default, section titles 740, letter-spacing −0.015 to −0.02em.
- **Body/UI/Nav:** Geist (variable, 300–800) — Swiss-clean counterpoint to the serif. Body weight 450, color `#3d4a63` (blue-slate), letter-spacing −0.01em.
- **Fancy accents:** `.gradient-text` spans render in Fraunces *italic* with the blue gradient — reserved for hero keywords and stat numbers.
  - Loading: `https://fonts.googleapis.com/css2?family=Geist:wght@300..800&family=Fraunces:ital,opsz,wght@0,9..144,300..900;1,9..144,300..900&display=swap`
- **Do not use:** Inter, Roboto, Space Grotesk, Raleway, Mulish (removed; overused or blacklisted).

## Color
- **Approach:** Restrained — white + ink + one blue accent family.
- **Ground:** `#ffffff`; alternating sections (`.light-background`): `#f2f6fc` (blue-tinted).
- **Ink (headings):** `#0a1633` (deep navy) · **Body text:** `#3d4a63` (blue-slate) — all neutrals are shades of blue.
- **Accent:** `#0b5cd8` (links, metrics, active nav, labels) · **Accent-2:** `#0e8f9d` (teal, gradient endpoint).
- **Gradient (`--accent-gradient`):** blue→teal, reserved for gradient text moments (hero keywords, stat numbers).
- **CTAs (`--accent-gradient-strong`):** deep blue gradient `#0b5cd8 → #0745a8` — blue pill buttons with white text (AA), soft blue glow `rgba(11, 92, 216, 0.26–0.30)`. Blue owns both links and actions; the dark CTA band (`.cta-box`) uses the same gradient.
- **Hairlines/borders:** `rgba(11, 92, 216, 0.13)` (blue-tinted glass borders) · **Shadows:** `rgba(15, 23, 42, 0.08–0.18)`, always soft.
- **Semantic:** success `#0e9f6e`.
- **Dark-on-photo captions** (gallery tile pills) intentionally stay dark for contrast over imagery.

## Cards
- **Surface:** white → ash-white gradient (`#ffffff → #fafcff`); **never dark/navy card surfaces, never gold accents** (owner rejected both).
- **Border:** 1px `rgba(11, 92, 216, 0.16)`; hover `rgba(11, 92, 216, 0.5)` with soft blue glow `rgba(11, 92, 216, 0.12)`.
- **Flair:** blue gradient top line sweeps in on hover (all card types); soft radial blue sheen fades in top-right corner; icon chips are blue-on-blue-tint.
- Applies to: `.service-item`, `.research-chip`, `.skill-card`, `.award-card`, `.pub-card`.

## Spacing
- **Base unit:** 8px (Craftivo/Bootstrap rhythm) · **Density:** spacious — generous section padding, max-width prose.

## Layout
- **Approach:** Grid-disciplined (Bootstrap 5), white pill glass navbar, alternating white/`#f6f7f9` sections, cards with 1px hairline borders + soft shadows, radius scale ~13–22px, pill (999px) for buttons/chips.

## Motion
- **Approach:** Intentional-subtle — AOS entrances, gentle hover lifts (translateY −2 to −5px), orb drift at whisper opacity (0.10–0.16 tints). `prefers-reduced-motion` fully honored (existing rules).

## Decisions Log
| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-07-06 | Dark navy theme → white theme | Owner request: "white theme, unique not generic"; conversion done entirely in the FELIX DESIGN LAYER of `assets/css/main.css` |
| 2026-07-06 | Rejected "Calibrated Instrument" metrology concept | Owner: too gimmicky; wants premium clean, judged on the real index.html |
| 2026-07-06 | Geist replaces Inter/Space Grotesk; headings 650–700, body 450 | Owner: "text bold, premium, elegant"; base's 300-weight titles overridden |
| 2026-07-06 | Black pill CTAs, blue reserved for links/metrics | Premium pattern (Apple/Vercel); avoids gradient-button slop |
| 2026-07-06 | CTAs switched black → deep blue (`#0b5cd8 → #0745a8`) | Owner request: "make the design blue premium"; blue now owns actions, links, and the CTA band |
| 2026-07-06 | Cards: white surfaces + blue hairline borders; navy+gold card experiment reverted | Owner: cards must stay white/ash-white with blue premium borders — no dark cards, no gold |
| 2026-07-06 | Social icons wear official brand colors (LinkedIn #0a66c2, Scholar #4285f4, Instagram #d62976 + gradient hover, Facebook #1877f2, WhatsApp #25d366, Email #ea4335); WhatsApp link added via wa.me | Owner request; the one sanctioned departure from the blue-only accent rule |
| 2026-07-06 | Fraunces serif display + italic gradient accents; all neutrals shifted to blue shades | Owner: "blue and shades of blue premium, bold texts, unique font type, fancy writing style" |
| 2026-07-06 | Footer text bold (600–700) and blue: name/headings in accent `#0b5cd8`, links/body in blue-slate `#2f4d80`, copyright strip `#f2f6fc` | Owner: "footer should be bold and blue colored text" |
| 2026-07-06 | Section titles at poster scale: clamp(2.75rem, 5.5vw, 4.5rem), weight 740; hero title is the page h1, logo wordmark demoted to <p> | Owner: "section heads big and visible enough"; /qa heading-semantics fix |
| 2026-07-06 | Gallery section added (isotope masonry, filters: Community/Projects/Personal/Video, GLightbox images + local mp4, blue pill filters); isotope + imagesloaded vendor scripts restored to index.html | Owner request: gallery for outreach, projects, personal pictures, videos |
