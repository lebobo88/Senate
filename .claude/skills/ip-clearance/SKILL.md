---
name: ip-clearance
description: "Minerva's protocols — FTO analysis structure, trademark clearance search ladder, the OSS license compatibility matrix with copyleft-boundary analysis, copyright/work-for-hire chains, and creative-asset clearance for the Garland. Search before clearing; epistemic status always stated."
allowed-tools:
  - Read
  - Write
  - Glob
  - Grep
---

# IP Clearance

**The Minerva rule:** clearance follows a search actually run. Where no
search can be run (Phase-1: no live patent/trademark databases), the output
is a *search specification* plus risk frame — explicitly
`[SEARCH NOT PERFORMED — clearance unavailable]` — never a soft clearance.

## Freedom-to-Operate (FTO) Structure

1. **Define the accused thing** — the product/feature/process, element by
   element (you cannot clear a vibe).
2. **Search specification** — jurisdictions, classification codes (IPC/CPC),
   keyword families, assignee watchlist, date horizon.
3. **Claim mapping** — for each relevant patent found: independent claims
   → element-by-element chart vs. the product. All elements present ⇒
   exposure; missing element ⇒ note design space.
4. **Design-around options** — per exposure: which element can change,
   cost/feasibility tier.
5. **Verdict** — clear / clear-with-design-around / exposed /
   search-required — with confidence and injunction-risk note (injunction
   beats damages in priority).

## Trademark Clearance Ladder

```
Step 1: Identical-mark knockout (same mark, same/related class, target jurisdictions)
Step 2: Confusingly-similar sweep (sight/sound/meaning; class-adjacent goods)
Step 3: Famous-mark dilution check (fame transcends class)
Step 4: Common-law / trade usage (unregistered rights jurisdictions)
Step 5: Domain/social handle collision (commercial reality check)
```

Verdict per mark per jurisdiction: cleared / conditional (coexistence
plausible) / blocked / search-required — confidence attached, classes
recorded (Nice classification).

## OSS License Compatibility Matrix

Combining INTO a proprietary, distributed product:

| Inbound license | Permissive use | Static link | Modify+distribute | Network service (SaaS) |
|---|---|---|---|---|
| MIT / BSD / Apache-2.0 | OK (notices; Apache: patent grant + NOTICE file) | OK | OK (keep notices) | OK |
| LGPL-2.1/3.0 | OK | conditional (relink-ability required) | copyleft on the library | OK |
| MPL-2.0 | OK (file-level copyleft) | OK | modified files stay MPL | OK |
| GPL-2.0/3.0 | derivative-work risk | **copyleft trigger** | **copyleft trigger** | OK (distribution trigger only) |
| AGPL-3.0 | derivative-work risk | **copyleft trigger** | **copyleft trigger** | **copyleft trigger (network clause)** |

Analysis rules:
- The **boundary question** decides GPL-family risk: what counts as one
  program (linking, address space, process boundaries) — analyze, don't
  assume.
- **AGPL in a SaaS stack is a Critical flag** — the network clause defeats
  the SaaS loophole.
- License **versions matter** (GPLv2-only vs. v2-or-later; Apache-2.0 is
  GPLv3- but not GPLv2-compatible).
- Obligations inventory per component: notices, license text, source
  offer, modification statements. Feeds
  `open-source-license-compatibility@1`.

## Copyright & Trade Secret Chains

- **Ownership chain**: author → (work-for-hire? valid assignment? present
  tense "hereby assigns" beats promise-to-assign) → claimant. Break in the
  chain = flag.
- **Contractor risk**: work-for-hire categories are narrow for
  commissioned works — assignment language still required.
- **Trade secret hygiene**: identified? reasonable measures (access
  control, NDAs, marking)? value-from-secrecy articulable?

## Creative-Asset Clearance (Garland interface)

For RLM-Creative assets: third-party marks/characters/music in the frame ·
reference-material provenance · model releases for recognizable persons ·
stock-license scope (resolution, territory, commercial use, AI-derivative
terms) · style-imitation risk for living artists (flag, tier, route).
Verdict feeds `governance-c2pa` before signing.

## Required Logging

What was searched (or specified for search), where, when, with what terms ·
claim/mark charts produced · verdicts with confidence · obligations
inventory · epistemic status on every clearance.
