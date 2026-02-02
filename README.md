# CBP Family β — ATCUN + HxxxH clamp library

This document describes **Family β** of the CBP peptide library: **ATCUN-like Cu(II) capture peptides** that also embed an internal **HxxxH (i,i+4) clamp** to (i) stabilize α-helical structure and (ii) provide a secondary interaction/metal-contact patch.

Family β is the main **“mechanism-plus-modulation”** set: it tests whether adding a clamp on top of ATCUN sequestration can improve **Aβ engagement** and increase the probability of **α-helical induction** (or, at minimum, reduce β-prone metrics) while remaining interpretable.

---

## 1) What “Family β” means (operational definition)

A peptide belongs to **Family β** if it satisfies all of the following:

- **ATCUN-like head present:** N-terminus starts with `DAH` or `GGH` (H₂N–X–X–His)
- **N-terminus is free** (not acetylated) so the ATCUN-like Cu(II) binding mode is enabled
- Contains an **internal HxxxH** motif beyond the head region (e.g., `HAAAH`, `HQAAH`, `HRAAH`)
- Uses an **EAAK-type helical scaffold** for solubility and structural conditioning
- Optional **single Trp-based anchor** at the C-terminus (`LWKK`, `AWKK`, `WKK`, `LYWKK`)

**Design intent:** preserve the clean Cu(II) capture behavior of ATCUN while adding a controlled secondary lever to bias helicity and/or interaction geometry.

---

## 2) Family β members (ordered by length)

> Source of truth: `CBP_mapping_enriched.csv` and `consideration.md`

### 2.1 Short constructs (≤30 aa)
- **CBPβ1**: `DAHEAAKEAAKEAAKHAAAHLWKK` (24 aa)  
  *Role:* clamp position test (HxxxH closer to C-terminus).

- **CBPβ2**: `DAHEAAKEAAKHAAAHEAAKLWKK` (24 aa)  
  *Role:* champion ATCUN + canonical `HAAAH` clamp.

- **CBPβ3**: `DAHEAAKEAAKHQAAHEAAKLWKK` (24 aa)  
  *Role:* clamp alternative (`HQAAH`) to probe His microstate sensitivity.

- **CBPβ4**: `DAHEAAKEAAKHRAAHEAAKLWKK` (24 aa)  
  *Role:* polar/cationic clamp (`HRAAH`) to raise local electrostatic engagement.

- **CBPβ5**: `DAHEAAKEAAKHAAAHEAAKLYWKK` (25 aa)  
  *Role:* stronger aromatic anchor (`LYWKK`); monitor for β-templating risk.

- **CBPβ6**: `DAHEAAKEAAKEAAKHQAAHEAAKWKK` (27 aa)  
  *Role:* extra EAAK before clamp (“more helix conditioning”) + `HQAAH`.

- **CBPβ7**: `DAHEAAKEAAKEAAKHAAAHEAAKAAWKK` (29 aa)  
  *Role:* longer <30 aa construct with reduced C-terminal fraying (`AAWKK`).

### 2.2 Long constructs (>30 aa)
- **CBPβ8**: `DAHEAAKEAAKEAAKEAAKHQAAHEAAKEAAKLWKK` (36 aa)  
  *Role:* `HQAAH` clamp in long context.

- **CBPβ9**: `DAHEAAKEAAKEAAKEAAKHRAAHEAAKEAAKLWKK` (36 aa)  
  *Role:* `HRAAH` clamp in long context.

- **CBPβ10**: `DAHEAAKEAAKEAAKHAAAHEAAKEAAKEAAKAWKK` (36 aa)  
  *Role:* clamp + propagation + softer anchor (`A-WKK`).

- **CBPβ11**: `DAHEAAKEAAKEAAKEAAKEAAAKHAAAHEAAKLWKK` (37 aa)  
  *Role:* long scaffold + internal clamp (“propagation-first” architecture).

- **CBPβ12**: `DAHEAAKEAAKEAAKEAAKEAAKHAAAHEAAKEAAKWKK` (39 aa)  
  *Role:* high stability (length) + clamp + minimal anchor (`WKK`).

- **CBPβ13**: `DAHEAAKEAAKEAAKEAAKHAAAHEAAKEAAKEAAKLYWKK` (41 aa)  
  *Role:* robust propagation + stronger aromatic anchor (`LYWKK`).

---

## 3) Why Family β exists (scientific rationale)

### 3.1 ATCUN-like Cu(II) capture remains the primary functional lever
The N-terminus (DAH/GGH) is intended to capture Cu(II) in a structurally defined manner via N-donors
(free amine + backbone amides + His(3) imidazole). Family β builds on that baseline, not against it.

### 3.2 HxxxH clamps add a controlled “secondary lever”
Placing two His residues at **i and i+4** positions aligns them on one helix face. The clamp can:
- stabilize local helicity (reduced conformational entropy),
- provide an additional metal-contact patch (context-dependent),
- tune interaction geometry with Aβ without adding long hydrophobic segments.

### 3.3 Anchor tuning tests “how much hydrophobic engagement is necessary”
Single Trp-based anchors are used to provide controlled hydrophobic contact:
- `WKK` < `AWKK` < `LWKK` < `LYWKK` (increasing hydrophobic engagement)
This allows testing whether α-induction in Aβ requires stronger hydrophobic engagement, while monitoring β-templating risk.

---

## 4) Practical caveats (critical for correct interpretation)

### 4.1 His clamps increase microstate complexity
Unlike Family α baselines, β-family peptides can show:
- His tautomer/protonation variability,
- multiple Cu-contact geometries (especially outside the ATCUN head),
- sequence-dependent residence-time heterogeneity.

**Action:** track coordination states explicitly (distance/geometry clustering); do not overfit single snapshots.

### 4.2 Do not assume the clamp “steals Cu” from the ATCUN head
In many designs, the clamp is best treated as a **helix/interaction modulator**, not as the primary Cu site.
The correct question is: *does adding the clamp change Cu occupancy in competition, or change Aβ structural metrics at fixed Cu occupancy?*

### 4.3 Watch for hydrophobic overreach (especially LYWKK)
`LYWKK` constructs (CBPβ5, CBPβ13) are intentionally more interaction-prone.
They must be evaluated against:
- **β-templating risk** (undesired β stabilization),
- peptide self-association,
- concentration-dependent artifacts.

---

## 5) Recommended readouts (Family β workflow)

### 5.1 Apo peptide (sanity baseline)
- Helicity (DSSP; or CD if experimental)
- Self-association check (peptide–peptide contacts)

### 5.2 Cu(II)-bound peptide
- ATCUN head stability: Cu–N distances, coordination number, geometry metrics
- Clamp involvement (if any): Cu–His(clamp) distances and frequency
- Cu exposure (SASA) as reactivity proxy

### 5.3 Competition (Aβ + Cu + CBPβ)
- Cu occupancy fraction: peptide vs Aβ
- Aβ secondary structure shift: α-helix fraction, β-content, and kinetics of transitions
- Aβ–peptide contacts: hotspot residues, residence times, contact maps
- Aggregation-prone proxies: inter-Aβ contacts, compaction metrics, β-zipper-like patterns

If feasible:
- ΔG_exchange for `Aβ–Cu + peptide → Aβ + peptide–Cu`

---

## 6) How to use Family β in decision-making

### 6.1 Within-family ranking
Prefer peptides that:
1) keep **Cu strongly captured** (dominant peptide-bound Cu in competition),
2) increase **Aβ α-helical population** and/or reduce β-prone metrics,
3) do not self-associate and do not promote long-lived Aβ oligomeric intermediates,
4) show consistent behavior across replicates and ionic strengths.

### 6.2 Attribution rule (α → β increment)
Any claimed improvement from a β-family peptide must be quantified relative to:
- at least one **α-family baseline** (same length/anchor class if possible), and
- at least one **γ-family acetylated control** where ATCUN is disabled.

---

## 7) Minimal recommended benchmark subset (if you need to downselect)
If you need a compact set that spans the β-family design space:

- **CBPβ2** (champion, HAAAH + LWKK)
- **CBPβ3** (HQAAH variant)
- **CBPβ4** (HRAAH variant)
- **CBPβ6** (extra EAAK before clamp)
- **CBPβ13** (long propagation + LYWKK “upper engagement”)
Plus the required references:
- one **α-family baseline** (e.g., CBPα2 or CBPα5),
- one **γ-family control** (e.g., CBPγ1).

---
