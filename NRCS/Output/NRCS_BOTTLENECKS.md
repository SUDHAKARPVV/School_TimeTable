# NRCS Timetable — Feasibility & Bottleneck Report

**Result:** solver **OPTIMAL**, **0 hard-rule violations**, independent audit passes all
checks over **500** slots (12 classes, 20 teachers). One rule needed a 1-period relaxation
(§1) and one data point needs your confirmation (§2).

## 1. Gowtham window (P2–P3 only) — 1-period relaxation

New rules: Gowtham is morning-only **and** must not get Period 1 or Period 4 → he can only
teach in **P2 and P3** (2 periods/day = 12 slots/week). But he teaches **13 Maths periods**
(Class 9 = 7, Class 10 = 6). 13 > 12, so the solver moved **one** period —
**Gowtham → Class 9, Period 5** — and kept the rest in P2/P3.

**To keep Gowtham strictly in P2–P3:** reduce his Maths by 1 period/week for Class 9 or 10,
or allow him one more morning period (P1 or P4).

## 2. G.K & Computer for Classes 9 & 10 — set to 0 (please confirm)

The committed data again lists **G.K = 1 and Computer = 1 for Classes 9 & 10 with no teacher**
in the allotment. Per your earlier instruction ("Classes 9 & 10 don't have G.K & Computer"),
I set both to **0** again (Classes 9 & 10 now total 40 periods → 2 free/Recreation slots each,
which is fine). If you want them, add a teacher in the allotment and I'll re-run.

## 3. Rules applied (this revision)
- **Chalapathi & Sonu**: afternoon only (not P1–P4). Chalapathi P5–P7, Sonu P5–P8.
- **Gowtham**: P2–P3 (morning, not P1 & P4). **Sunita / Riya / Bheema**: P1–P4.
- Karate = **Thursday P6, all classes**; P.E.T = **P5–P7**; Oral pinned **P1 for L.K.G**;
  Ravi teaches Eng Gram to 8–10; leisure after 2–3 periods (Study Hour not counted).
- Study Hour from the Period-1 sheet (Class 5 falls back to its P1 teacher); Class 10 has no
  study hour.

## 4. Teacher weekly occupancy (of 47 usable slots; Study-Hour supervision incl.)

| Teacher | Load | Teacher | Load |
|---------|------|---------|------|
| Sai Lakshmi | 41 | Naga mani | 31 |
| Maha | 41 | D.V.Rao | 30 |
| Sitha | 40 | Sonu | 18 |
| Pallavi | 36 | Sunitha | 18 |
| Swathi | 35 | Ravi | 17 |
| Tulasi | 34 | Riya | 15 |
| Bhavani | 33 | Gowtham | 13 |
| Fathima | 33 | Bheema | 12 |
| Lalitha | 32 | Maheswari | 10 |
| Sangeetha | 32 | Chalapathi | 10 |

## 5. Cross-school — ✅ no clashes
Chalapathi (NRHS P1–P3 / NRCS P5–P7), Gowtham, Riya, Sunitha all have disjoint windows
across the two schools. See [`CROSS_SCHOOL_CONFLICTS.md`](../../CROSS_SCHOOL_CONFLICTS.md).
