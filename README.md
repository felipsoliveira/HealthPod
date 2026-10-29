# HealthPod

**Open-science research on lower-exposure recreational aerosols.**

HealthPod asks a deliberately falsifiable question:

> Can the sensory and visual experience of an inhaled aerosol be decoupled from the amount of material deposited in the respiratory tract?

This repository is a research platform, not a claim that any inhaled product is safe.

## MVP-0 — Experimental bench (updated 2026-10-28)

The **first operational MVP is an enclosed laboratory aerosol-measurement bench**, not a homemade vaping device and not a validated inhalation product. A commercial vibrating-mesh nebulizer (VMN) will be used first to develop reproducible optical, gravimetric and environmental measurements with a simple aqueous reference. Surface Acoustic Wave (SAW) remains the leading research candidate for a later, controlled comparison.

- [MVP-0 blueprint v0.2](research/BLUEPRINT_V0.md) — architecture, goals, scope and decision gates.
- [MVP-0 bench protocol v0.2](research/MVP0_BENCH_PROTOCOL.md) — controls, instrumentation, test sequence, measurements and safety stopping rules.
- [Blank MVP-0 data template](research/MVP0_RUN_TEMPLATE.csv) — one row per experimental replicate.
- [Formulation evidence map](research/FORMULATION-CANDIDATES.md) — evaluation of candidate liquid classes, **not** an inhalation recipe.

**Current stage:** documentation ready for engineering and institutional safety review. No physical prototype, experiment, inhalation test or safety validation is claimed.

## Current strategy

We compare aerosol-generation mechanisms under the same physical, chemical and biological framework. Our first technology candidate is **Surface Acoustic Wave (SAW) atomization** because it can generate dense micron-scale aerosols without conventional resistive-coil evaporation and has an established pulmonary-drug-delivery literature.

Candidate order for the first evidence cycle:

1. **SAW / microfluidic SAW** — primary candidate
2. Vibrating Mesh Nebulization (VMN)
3. Soft-Mist / mechanically driven microfluidic aerosol
4. Electrohydrodynamic atomization / electrospray
5. Jet/pneumatic nebulization — mature reference
6. Conventional nicotine-free thermal e-cigarette — recreational benchmark, not target architecture

This is an **investigation priority**, not a safety ranking.

## Research pillars

- Aerosol physics: size distribution, output mass, plume dynamics and optical density.
- Respiratory exposure: predicted/experimental regional deposition and emitted vs deposited mass.
- Chemistry: carbonyls, VOCs, metals and other relevant emissions.
- Biology: respiratory-cell response only after physicochemical screening.
- Sensory engineering: deferred until a candidate passes earlier gates.
- Open evidence: hypotheses, negative results, protocols and datasets should be publishable.

## Novel working hypothesis

A visually dense plume may not require maximizing aerosol mass. We will investigate an exploratory metric called **Optical Aerosol Efficiency (OAE)**:

`OAE = measured plume optical signal / emitted aerosol mass`

OAE is **not an established safety metric**. Its purpose is to test whether visual aerosol perception can be increased without proportionally increasing inhaled material. Respiratory deposition and toxicology remain separate required endpoints.

## Safety boundary

No candidate is described as “healthy” or “safe.” Early work is bench-first. Human inhalation is outside the initial research phases. A technology advances only through predefined evidence gates.

See [research/ROADMAP.md](research/ROADMAP.md), [research/CANDIDATES.md](research/CANDIDATES.md), and [SAFETY.md](SAFETY.md).
