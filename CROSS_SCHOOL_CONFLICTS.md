# Cross-School Conflict Check (NRHS ∩ NRCS)

Run: `python cross_check.py`

Some teachers appear at **both** schools. A shared teacher must not be scheduled at the
same day+period in both timetables. Teachers are matched **by name** (leading initials
like `D.` are stripped) — **please confirm whether same-named teachers are the same
person**; if they are different people, ignore the clash.

## Result

| Teacher (NRHS = NRCS) | NRHS periods | NRCS periods | Clash |
|-----------------------|--------------|--------------|-------|
| CHALAPATHI = Chalapathi | 1–3 | 4–7 | ✅ none |
| D.GOWTHAM = Gowtham | 6–8 | 2–5 | ✅ none |
| RIYA = Riya | 5–8 | 1–4 | ✅ none |
| SUNITHA = Sunitha | 5,6,8 | 1–4 | ✅ none |
| **M.LALITHA = Lalitha** | 1–7 | 1–7 | ⚠️ **23 clashes** |

## Interpretation

- **Riya, Sunitha, Gowtham, Chalapathi — no clash.** Their morning/afternoon windows at
  the two schools are complementary (afternoon at NRHS, morning at NRCS), so they never
  overlap. This strongly suggests they are intentionally the same staff splitting the day
  between the two schools — and the rules are set up correctly for that.

- **Lalitha — 23 clashes.** NRHS `M.LALITHA` (Telugu, Classes 6–10) and NRCS `Lalitha`
  (Phy/Che + Biology, Classes 6–7) are both unrestricted (any period P1–P7), so they
  overlap heavily.

### If M.LALITHA and Lalitha are the SAME person
This is a real conflict. Fix by giving her a window at one school so the two don't
overlap — e.g. restrict NRCS `Lalitha` to the afternoon (P5–P7) or NRHS `M.LALITHA` to
the morning — or move some of her classes to another teacher. Tell me the preferred
split and I'll re-solve both schools and re-run this check to confirm zero clashes.

### If they are DIFFERENT people
No action needed — the name match is a coincidence.
