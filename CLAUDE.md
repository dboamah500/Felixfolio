# Felixfolio — Portfolio of Dr. Felix Tettey-Engmann

Personal portfolio website for **Dr. Felix Tettey-Engmann**, built on the BootstrapMade
"Craftivo" template (Bootstrap 5.3, vanilla JS). Static site: no build step, no framework.
Open `index.html` directly or serve the folder with any static server.

## Architecture (preserve this)

- `index.html` — single-page portfolio; all main sections live here, anchored nav
- `assets/css/main.css` — the only first-party stylesheet (Craftivo base + our design layer)
- `assets/js/main.js` — first-party JS (nav toggle, scroll behavior, AOS/Swiper/GLightbox init)
- `assets/vendor/` — Bootstrap, Bootstrap Icons, AOS (scroll animations), Swiper, GLightbox,
  Isotope, Typed.js, Waypoints, imagesloaded, php-email-form. Do not modify vendor files.
- `img/` — Felix's real photos and resume. **Reuse these; never invent placeholder people.**
- `forms/contact.php` — contact form backend (needs PHP hosting; degrade gracefully without it)
- Secondary pages: `404.html`, `privacy.html`, `terms.html` (keep branded), and template
  leftovers `starter-page.html`, `portfolio-details.html`, `service-details.html`.

Conventions: keep the Craftivo section/markup patterns (`<section class="… section">`,
AOS `data-aos` attributes, CSS custom properties in `:root`). Improve the UI in place;
do not rewrite working code or swap frameworks.

## Design language

**White theme** (as of 2026-07-06): premium, minimal, memorable — reference points: Apple,
Vercel, Stripe, Linear, Intel. White ground, blue-shaded neutrals, bold Fraunces serif
display + Geist body, one blue accent family, blue-pill CTAs, blue hairline card borders,
brand-colored social icons, subtle motion, generous clean
spacing. Always read `DESIGN.md` before making any visual or UI decision — fonts, colors,
spacing, and direction are defined there; do not deviate without explicit user approval.
Avoid generic-template look, stock clichés, and heavy skill progress bars. The site should
read instantly as: *"accomplished semiconductor engineer and research leader."*
The owner rejects concept-heavy/gimmicky design (spec-table heroes, monospace-everywhere,
lab-metaphor decoration); show design changes on the real `index.html`, not mockup pages.
Audience: Intel leadership, NVIDIA, TSMC, ASML, Applied Materials, Lam Research, KLA,
research institutions, investors, startup collaborators.

## About Felix (source of truth for content)

Canonical narrative bio: `content/about-felix.md` ("Building Technology That Improves
Lives"). About-section copy, hero intro, and the SEO description derive from it.

- **Dr. Felix Tettey-Engmann** — Module Development Engineer, **Intel Corporation**
- Identity: Semiconductor Engineer · Research Scientist · Innovator · Entrepreneur · Operations Leader
- Specialties: semiconductor manufacturing, EUV/DUV lithography, reticle engineering,
  yield optimization, root cause analysis, process development, advanced manufacturing,
  nanotechnology, biomaterials, tissue engineering, additive manufacturing
- Research: **20+ publications, 550+ citations**; former Graduate Researcher,
  North Carolina A&T State University (PhD)
- Entrepreneurship: Co-founder & COO, **GRADCAB**; Head of Services, **Inested LLC**;
  Licensed Financial Professional
- Awards: Outstanding Graduate Research Award, Subrata Saha Excellence Award, GRASAG Award,
  ISEN Awards, research competition awards

### Contact & links

- Email: fatettey2020@gmail.com · Phone: +1 (424) 603-8035
- LinkedIn: https://www.linkedin.com/in/felix-tettey-engmann-phd-b45284138
- Instagram: https://www.instagram.com/scolosis
- Facebook: https://www.facebook.com/share/18kGKBhmcc/
- Google Scholar: link from Research/Publications sections

## Site sections (index.html order)

Hero (headline + portrait + CTAs: View Resume / Publications / Contact, subtle animated
background) → About (narrative story, not resume bullets) → Experience timeline (Intel,
NC A&T, GRADCAB, Inested, Financial Professional; animated cards) → Semiconductor
Engineering (EUV/DUV lithography, reticle inspection, defect analysis, yield, process
development, RCA, HVM) → Research (biomaterials, nanotech, 3D bioprinting, electrospinning,
additive manufacturing, characterization; metrics + Google Scholar button) → Skills
(categorized cards, no progress bars: Semiconductor / Research / Programming / Data /
Lab / Leadership / Operations / Business; tools: Python, SQL, Tableau, OriginLab, R,
ImageJ, MS Office) → Awards → Entrepreneurship (GRADCAB, Inested) → Community & Advocacy
(mentoring, teaching math in underserved communities, judging competitions, civic
engagement; photo gallery with GLightbox) → Gallery (isotope-filtered: Community /
Projects / Personal / Video; GLightbox images + local video) → Publications (4 real papers with links;
Scholar profile: https://scholar.google.com/citations?user=eHQKo_YAAAAJ) →
Contact (email, phone, LinkedIn, Scholar, location, socials; static mailto form — NO PHP).

## Assets in `img/` (real, on disk — always reuse, never duplicate)

- `Hero.jpeg` — blue-suit studio portrait, **hero image**
- `social.jpeg` — circular About-card portrait (also OG/Twitter image)
- `work.jpeg` — Felix at Intel Gordon Moore Park, Experience/Intel
- `felix-speaking.jpg` — speaking at podium, Entrepreneurship/GRADCAB
- `felix-community.jpg`, `felix-event.jpg`, `felix-mentorship-group.jpg`,
  `felix-mentorship-group2.jpg`, `felix-lab-bw.jpg` — community/mentorship gallery
- `felix-casual.jpg`, `felix-collage.jpg`, `felix-event-2.jpg`, `felix-office.jpg`,
  `felix-video.mp4` — Gallery section (Personal/Community/Video tiles)
- `Felix-Tettey-Engmann-Resume.docx` (and `.pdf` if generated) — Resume download button target
- SEO: keep title/description/OG/Twitter/JSON-LD in `index.html` head in sync with content

## Quality bar

Fast loading (lazy-load below-the-fold images, width/height attributes, no oversized
images), accessible (semantic headings, alt text, contrast, keyboard nav), fully
responsive, SEO complete. Refactor duplication into reusable patterns; keep it simple.

## Skill routing

When the user's request matches an available skill, invoke it via the Skill tool. When in doubt, invoke the skill.

Key routing rules:
- Product ideas/brainstorming → invoke /office-hours
- Strategy/scope → invoke /plan-ceo-review
- Architecture → invoke /plan-eng-review
- Design system/plan review → invoke /design-consultation or /plan-design-review
- Full review pipeline → invoke /autoplan
- Bugs/errors → invoke /investigate
- QA/testing site behavior → invoke /qa or /qa-only
- Code review/diff check → invoke /review
- Visual polish → invoke /design-review
- Ship/deploy/PR → invoke /ship or /land-and-deploy
- Save progress → invoke /context-save
- Resume context → invoke /context-restore
- Author a backlog-ready spec/issue → invoke /spec
