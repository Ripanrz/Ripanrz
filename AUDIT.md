# Repository & Profile Review — Ripanrz/Ripanrz

**Review date:** 9 November 2026  
**Scope:** README, hero media, technology taxonomy, project summaries, GitHub activity cards, and contact links.

## Incident: Hero image invisible on GitHub

The previous README embedded a composite SVG which, in turn, referenced four JPG strips using relative `<image>` URLs. GitHub rendered the SVG's CSS-animated leaves but did not load the nested raster images in the SVG. This caused the exact failure reported by the repository owner: falling leaves appeared on a blank banner.

## Corrective change

- Render all four JPG strips as **direct HTML image elements in README.md**. GitHub now resolves them as normal repository images rather than nested resources inside an SVG.
- Keep a separate self-contained `anime-leaves.svg` containing only vector leaves and CSS animation. It has no nested image references.
- Retire the broken composite `anime-study-banner.svg`.
- Respect `prefers-reduced-motion` for the decorative leaf animation.

## Other profile requirements retained

- One `Featured Projects` section.
- Software and frameworks grouped in Technology Stack.
- Physical platforms and devices listed separately.
- GitHub statistics, Top Languages, and contribution snake retained.
- Contact section uses exactly four badges: Email, LinkedIn, Instagram, and GitHub.
- Duplicate simulation and FPGA tool listings removed from the hardware section.

## Validation

- [x] Hero JPG strips are used directly from README HTML.
- [x] SVG leaf animation has no `<image>` or external file dependencies.
- [x] Broken nested-image SVG removed from README and repository.
- [x] Exactly one Featured Projects heading.
- [x] Four contact badges; no duplicate plain-text contact list.
- [x] GitHub statistics and contribution snake remain.
- [x] README HTML div tags are balanced.
- [ ] Confirm the rendered profile on GitHub after merge.

## Limitations

This is a static repository and rendering correction, not a penetration test or full runtime verification of third-party statistics providers. GitHub's final README rendering should be visually checked after merge.