# Tiny ATPL Trainers

Small single-page trainers for the parts of the ATPL syllabus that reward drilling rather than
reading — the tables, the thresholds and the numbers you either know cold or you don't.

Open [`index.html`](index.html) for the hub. Everything runs offline from the filesystem: no build
step, no dependencies, no network.

## Layout

```
index.html                              hub — lists every trainer, grouped by subject
assets/theme.css                        shared palette + common chrome
trainers/010-air-law/                   one directory per EASA syllabus subject
  wake-separation.html
trainers/050-meteorology/
  pressure-flight-level.html
```

Directories are named `<syllabus code>-<subject>`, following the EASA ATPL(A) numbering
(010 Air Law, 022 Instrumentation, 050 Meteorology, 061 General Navigation, and so on).

## Trainers

| Subject | Trainer | Drills |
|---|---|---|
| 010 Air Law | [Wake separation](trainers/010-air-law/wake-separation.html) | ICAO Doc 4444 time and distance minima, all four modes, plus the EASA/FAA variants |
| 050 Meteorology | [Sounding](trainers/050-meteorology/pressure-flight-level.html) | Standard pressure surfaces against their ISA flight levels |
| 062 Radio Navigation | [Frequency bands](trainers/062-radio-navigation/frequency-bands.html) | Classifying a frequency by service, the 108–112 MHz VOR/localizer split, and the ITU bands |

## Adding a trainer

1. Save the HTML into `trainers/<code>-<subject>/<name>.html`.
2. Link the shared theme in `<head>`:
   `<link rel="stylesheet" href="../../assets/theme.css">`
   and add the back-link as the first element of `<header>`:
   `<a class="crumb" href="../../index.html">All trainers</a>`.
3. Add one entry to the `TRAINERS` array at the bottom of `index.html`.

`assets/theme.css` supplies the palette, header, status bar, mode pills, multiple-choice buttons,
feedback line, reference key and completion overlay. Keep only layout that is specific to the
trainer in its own inline `<style>`. Subjects listed in `index.html` with no trainers stay hidden
until one exists, so the full subject list can sit there from the start.

## Roadmap

Candidates, unordered within each subject — to be prioritised.

**010 Air Law**
- [ ] Light gun signals — colour and pattern against meaning, air vs ground (matrix, same shape as wake separation)
- [ ] Annexes 1–19 — which annex covers what (matching)
- [ ] Squawk codes and emergency procedures — 7500/7600/7700, conspicuity, SSR basics

**022 Instrumentation**
- [ ] Altimeter errors — pressure and temperature corrections, "from high to low, look out below" (calculation drill)
- [ ] Compass turning and acceleration errors — ONUS/UNOS by hemisphere and heading
- [ ] ILS categories — DH and RVR minima per category (matrix)

**031 Mass & Balance**
- [ ] CG envelope — load the aircraft and keep the CG inside the envelope (visual, drag-to-load)

**032 Performance**
- [ ] Runway distance definitions — TORA/TODA/ASDA/LDA against a runway diagram with clearway and stopway
- [ ] V-speeds — V1, VR, V2, VMCG, VMCA, VMO/MMO (matching)
- [ ] Climb gradient ↔ rate of climb conversion

**040 Human Performance**
- [ ] Time of useful consciousness — altitude against TUC (matching, same shape as the sounding trainer)
- [ ] Hypoxia vs hyperventilation — sort the symptoms, then the correct response

**050 Meteorology**
- [ ] METAR/TAF decoding — decode the group, or read the raw report and answer
- [ ] ISA deviation — temperature at level, ISA dev, and its effect on true altitude
- [ ] Icing and turbulence — cloud type against hazard severity

**061 General Navigation**
- [ ] Variation and deviation — the CDMVT chain in both directions
- [ ] 1-in-60 rule — track error, closing angle, and the correction to make good
- [ ] Great circle vs rhumb line — convergency and conversion angle

**062 Radio Navigation**
- [x] Frequency bands — classify a frequency by service, plus the ITU bands
- [ ] VOR orientation — radial, TO/FROM and quadrant off a live compass rose (visual)
- [ ] ADF bearings — RB + MH = MB, both ways, including the wrap-around cases

**081 Principles of Flight**
- [ ] Bank angle, load factor and stall speed — the three quantities against each other
- [ ] Lift/drag curve — Vmd, Vmp, and what moves where with mass and configuration

## Note on sources

Figures follow ICAO baseline documents unless a trainer says otherwise; the wake separation
trainer's reference key lists the EASA and FAA departures from that baseline. Check the current
regulation for anything operational — these are study aids, not references.
