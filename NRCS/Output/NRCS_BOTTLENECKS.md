# NRCS Timetable — Feasibility & Bottleneck Report

**Result:** solver status **OPTIMAL**, **0 hard-rule violations**, independent audit
(`python audit.py --school NRCS ...`) passes all 9 checks over 504 slots. One rule had
to be relaxed by a single period — see §1.

## 1. Morning-window conflict (Class 9) — 1-period relaxation

Rule: **Gowtham, Sunita, Riya, Bheema teach mornings only (P1–P4).** But **Class 9**
needs **25** periods from these morning-only teachers:

| Subject | Teacher | Periods |
|---------|---------|---------|
| Hindi | Riya | 5 |
| Maths | Gowtham | 7 |
| Physics + Chemistry | Bheema | 3 + 4 = 7 |
| Social | Sunitha | 6 |
| **Total** | | **25** |

A class has only **24** morning slots (P1–P4 × 6 days), so 25 can't fit. The solver
placed **one** period — **Riya (Hindi) → Class 9, Period 5** — and kept everything else
strictly P1–P4. (Class 10 is at exactly 24, zero slack.)

**To keep everyone strictly P1–P4:** reduce one of Class 9's morning-only subjects by
1 period/week (e.g. Hindi 5→4), or reassign one subject to a non-morning-only teacher.

## 2. Data quirks handled (please confirm)

- **"Phy/Che" vs "Chemisty":** the allotment has a combined *Phy/Che* row (Lalitha for
  6–7, Bheema for 8–10). Physics uses that row; **Chemistry for Classes 6–7 inherits the
  same teacher (Lalitha)** since the *Chemisty* row only lists 8–10.
- **Eng Gram Classes 1–5:** the plan gives 1 period/week but the allotment only lists
  Ravi for 6–10, so **Classes 1–5 Eng Gram inherit their English teacher (Maha)**.
- **Study Hour:** taken from the Period-1 sheet's *Study Hour* row; Class 5 was blank so
  it falls back to its Period-1 teacher (Maha). **Class 10** has no Period-1/Study-Hour
  entry → treated as **no study hour** (P8 is a teaching slot, matching the sample).
- **P.E.T = "P.E"** and **Karate = "Martial Arts"** are treated as parallel activities.

## 3. Rules applied
Sonu afternoon only (P5–P8); Gowtham P2–P4 (P1 & P5 leisure); Sunita/Riya/Bheema P1–P4;
Karate = Thursday P6 (Classes 1–8); P.E.T = P5–P7; Oral pinned to P1 for L.K.G; Ravi
teaches Eng Gram to 8–10 (and 6–7); leisure after 2–3 periods (Study Hour not counted).

## 4. Teacher weekly occupancy (of 48; Study-Hour supervision included)

| Teacher | Load | Teacher | Load |
|---------|------|---------|------|
| Sai Lakshmi | 41 | Sangeetha | 32 |
| Maha | 41 | Naga mani | 31 |
| Sitha | 40 | D.V.Rao | 30 |
| Pallavi | 36 | Sonu | 18 |
| Swathi | 35 | Bheema | 18 |
| Tulasi | 34 | Sunitha | 18 |
| Bhavani | 33 | Ravi | 17 |
| Fathima | 33 | Riya | 15 |
| Lalitha | 32 | Gowtham 13 · Maheswari 10 · Chalapathi 10 |

## 5. Cross-school note
Some teachers work at both NRHS and NRCS. See
[`CROSS_SCHOOL_CONFLICTS.md`](../../CROSS_SCHOOL_CONFLICTS.md) — Riya/Sunitha/Gowtham/
Chalapathi have **no** clash (complementary morning/afternoon windows), but
**Lalitha** clashes 23× **if** NRHS "M.LALITHA" and NRCS "Lalitha" are the same person.
