# Sprint 2 — Carrier / Formulation Evidence Map

## Goal

Identify the **smallest defensible carrier search space** for bench characterization of low-temperature/non-thermal aerosol generation. This document does **not** define a liquid recipe for human inhalation.

The formulation problem is coupled to the atomizer: viscosity, surface tension, volatility and hygroscopicity alter aerosol generation, plume persistence and respiratory deposition.

## Current evidence-driven candidate classes

| Class | Why include it | Main concern | Sprint-2 role |
|---|---|---|---|
| Water / simple aqueous system | Strong SAW literature; low viscosity; clean physical baseline | Rapid evaporation; aerosol still deposits water; microbiological/device issues | **Primary physical baseline** |
| Isotonic saline / simple saline | Extensive nebulizer literature; useful hygroscopic reference | Hygroscopic growth can substantially change inhaled size/deposition | **Respiratory-aerosol reference** |
| Propylene glycol (PG) | Established aerosol former and comparator | Not biologically inert; irritation/airway effects; thermal systems add degradation products | Comparator, not presumed-safe carrier |
| Glycerol / VG | Strong plume persistence and hygroscopic behavior in existing aerosol literature | High viscosity; SAW efficiency can collapse as viscosity rises; biological effects cannot be assumed absent | Comparator / stress test |
| Aqueous + polyol systems | Could expose trade-offs between atomizability, persistence and mass | Composition-dependent toxicology and hygroscopic growth | **Research space**, only after baselines |

No flavor, botanical, vitamin, essential oil, nicotine or pharmacologically active ingredient belongs in the initial screen.

## Key finding for SAW

SAW performance is strongly coupled to viscosity. Recent acoustic-thermal-flow work with glycerol/water systems reports increasing viscous dissipation and severe suppression of effective atomization as viscosity rises. Therefore a visually persistent carrier cannot be selected independently from the SAW mechanism.

### Hypothesis H2.1

A lower-viscosity, water-dominant carrier may provide substantially better SAW atomization efficiency than glycerol-rich systems, but may lose plume persistence through evaporation.

### Hypothesis H2.2

There may be an intermediate physical regime in which a small change in carrier properties increases optical persistence more than it increases emitted/deposited mass.

This is a hypothesis to test, not a proposed inhalation formulation.

## Aerosol evolution matters

The device outlet is only time zero. During transport and inhalation, droplets can:
- evaporate;
- absorb water;
- change composition;
- change aerodynamic diameter;
- coagulate;
- deposit regionally.

Hygroscopic aerosols can therefore have a materially different size distribution inside humid airways than at the outlet.

## Required measurements before formulation optimization

For each carrier class and atomizer:

1. Liquid density, viscosity and surface tension from reliable measurements/literature.
2. Aerosol output mass per standardized actuation interval.
3. Device and aerosol temperature.
4. Plume optical signal and persistence under controlled illumination.
5. Size distribution using an appropriate validated method when available.
6. Environmental temperature and relative humidity.
7. Evaporation/hygroscopic evolution.
8. Predicted respiratory deposition from validated aerosol models.
9. Chemical/material contamination.
10. Only later: biological response.

## Exploratory metrics

### Optical Aerosol Efficiency (OAE)

OAE = standardized optical plume signal / emitted aerosol mass

OAE is an engineering metric, **not a safety metric**.

### Exposure-adjusted optical efficiency

Future work may compare optical signal against modeled or measured deposited mass rather than emitted mass. This requires validated deposition estimates before it is meaningful.

## Decision matrix

A carrier should not advance because it makes the biggest cloud.

Advance only if it offers a useful joint profile across:
- atomization efficiency;
- reproducibility;
- optical efficiency;
- low device heating;
- manageable hygroscopic evolution;
- favorable predicted deposition;
- low chemical/material burden;
- acceptable preclinical evidence.

## Current working priority

For **SAW physics experiments**, begin conceptually from simple aqueous systems because they are well represented in SAW literature and avoid immediately confounding mechanism studies with high viscosity.

PG/VG remain important comparators because they represent the incumbent recreational aerosol-carrier space, but current evidence does not justify treating either as biologically inert.

## Open questions

- Can water-dominant SAW aerosol produce adequate optical density at low emitted mass?
- How rapidly does that plume disappear at realistic ambient humidity?
- Does saline improve or worsen the optical/deposition trade-off through hygroscopic growth?
- Can modest property changes improve OAE without strongly increasing deposited mass?
- Is SAW heating negligible under our relevant operating regime, or does viscous dissipation recreate a thermal problem?
- Which carrier properties dominate OAE: refractive index, droplet size, number concentration, evaporation rate, or combinations?
