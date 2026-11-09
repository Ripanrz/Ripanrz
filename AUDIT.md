# Repository & Profile Review — Ripanrz/Ripanrz

**Review date:** 9 November 2026  
**Scope:** GitHub profile README, hero illustration assets, technology taxonomy, project summaries, contributor statistics, and contact section.

## Executive Summary

The profile has been revised around the anime banner selected by the repository owner. The previous simplified vector drawing was retired because it did not match the intended cinematic art direction.

The new hero uses the supplied anime scene as its visual source, split into lightweight local image strips and composed in an SVG wrapper. The wrapper adds a subtle falling-leaf animation and respects the browser's `prefers-reduced-motion` setting.

## Changes

| Area | Change |
|---|---|
| Hero banner | Replaced the simplified cartoon SVG with the chosen anime scene: two students studying beneath an autumn maple tree at sunset. |
| Motion | Added gentle leaf movement as an overlay; the underlying illustration remains stable to avoid distracting motion. |
| Project layout | Replaced the old `Selected Projects & Engineering Work` heading with exactly one `Featured Projects` section. |
| Technology taxonomy | Kept software/frameworks in Technology Stack and physical platforms in Hardware, Devices & Platforms. |
| Duplicate inventory | Removed the repeated FPGA toolchain row and the separate hardware-simulation tools line because those tools are already listed in Technology Stack. |
| GitHub activity | Kept profile statistics, top languages, and the contribution snake; removed overlapping streak and extra metrics panels. |
| Contact | Replaced plain-text contact links with exactly four badges: Email, LinkedIn, Instagram, and GitHub. |
| Language | Indonesian is used for profile narrative; standard English engineering terms remain where they are the accepted technical vocabulary. |

## Technical Content

Featured projects are summarized once each:

- **SECURE-TINY:** ASCON-AEAD128, RTL design, datapath/control FSM, buffering, trusted vectors, and FPGA target.
- **COCOCHIRP:** Active acoustic-chirp, signal processing, Physics-Informed TinyML, and edge inference for non-destructive coconut assessment.
- **Project MAMBA:** Black-box test design, Equivalence Partitioning, Boundary Value Analysis, Data Segregation, UAT, BRD, and FSD.
- **Project OCE Agent:** Agentic AI workflow orchestration and conversational-memory tooling.

The hardware section distinguishes microcontrollers, single-board computers, PLC/controller platforms, robotics hardware, the DE10-Nano FPGA target, and instrumentation. Tools such as Quartus Prime, Yosys, LibreLane, Proteus, FluidSIM, CX-One, ISPSoft, DOPSoft, and DobotStudio are kept in the software/toolchain inventory, not duplicated as physical hardware.

## Validation

- [x] README has one `Featured Projects` heading.
- [x] Old `Selected Projects & Engineering Work` heading is absent.
- [x] Contact section contains four badge links and no plain-text duplicate list.
- [x] README no longer points to the retired simplified `study-under-tree.svg`.
- [x] FPGA/EDA toolchain is not repeated in the hardware table.
- [x] The duplicate simulation-tools line below the hardware table is removed.
- [x] Dynamic GitHub profile stats, top-language card, and contribution snake remain.
- [x] New hero asset uses local repository image strips, not third-party image hosting.
- [x] Animated SVG includes a reduced-motion fallback.

## Limitations

This is a static content and presentation review. It is not a penetration test, accessibility audit, or end-to-end validation of every external statistics provider. GitHub profile cards and contribution graphics depend on third-party services and GitHub Actions availability. The visual result should be checked in GitHub's rendered README because SVG image-loading policies can differ from local browser previews.

Hardware entries distinguish platforms or targets from personally owned devices. A target-platform mention should not be interpreted as proof that the physical board was available for hands-on testing.
