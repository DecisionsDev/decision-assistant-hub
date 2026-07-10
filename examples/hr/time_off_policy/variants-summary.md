# Acme Corp Time Off Policy — Variant Set Summary

Base policy: **428 words**, **12 decision points**.
All files are in the `policy-variants/` folder.

---

## Variant Overview Table

| File | Variant | Purpose | Word Count | Target Range | DPs | Changes vs. Original |
|---|---|---|---|---|---|---|
| `variant-1-control.md` | 1 — Control | Paraphrase only; test phrasing dependency | 408 | 385–470 | 12 | None |
| `variant-2-longer-same-dps.md` | 2 — Longer, Same DPs | Narrative noise; test extraction under verbosity | 962 | 856–1,284 | 12 | None (added framing only) |
| `variant-3-same-length-more-dps.md` | 3 — Same Length, More DPs | Reasoning density under tight space | 482 | 385–492 | 15 | +3 new (A, B, C) |
| `variant-4-longer-more-dps.md` | 4 — Longer, More DPs | Reasoning depth with proportional space | 1,003 | 856–1,284 | 15 | +3 new (A, B, C) |
| `variant-5-shorter-same-dps.md` | 5 — Shorter, Same DPs | Extraction from stripped text | ~224 | 214–300 | 12 | None (compressed only) |
| `variant-6-shorter-fewer-dps.md` | 6 — Shorter, Fewer DPs | Sanity-check floor | 218 | 214–300 | 8 | −4 removed (DP-2, DP-4, DP-5, DP-8) |
| `variant-7-longer-18dps.md` | 7 — Longer, 18 DPs | Scaled reasoning depth | 782 | 700–900 | 18 | +6 new (A, B, C, D, E, F) |
| `variant-8-longer-24dps.md` | 8 — Longer, 24 DPs | Maximum reasoning depth | 1,143 | 1,100–1,400 | 24 | +12 new (A–L — see below) |

---

## Decision Point Reference

### Original 12 Decision Points

| ID | Decision Point |
|---|---|
| DP-1 | Is the employee a regular full-time employee? |
| DP-2 | Is the employee NOT a supplemental employee? |
| DP-3 | Does the employee observe one of the 8 fixed U.S. holidays listed? |
| DP-4 | Is the employee requesting a personal choice holiday? |
| DP-5 | Has the manager approved the personal choice holiday? |
| DP-6 | Does the employee have fewer than 10 years of service? → 15 vacation days |
| DP-7 | Does the employee have 10+ years of service? → 20 vacation days |
| DP-8 | Was the employee hired before Jan 1, 2004 AND has 20+ years of service? → 25 vacation days |
| DP-9 | Is the vacation increment half-day, full-day, or multi-day? |
| DP-10 | Has the manager approved the vacation request? |
| DP-11 | Does the vacation request align with business needs? |
| DP-12 | Does the vacation request align with employee preference? |

### New Decision Points (Variants 3 & 4 only — 3 new each)

| ID | Decision Point |
|---|---|
| DP-NEW-A | Is the employee hired mid-year? → Prorate vacation by full calendar months remaining ÷ 12, round down to nearest half-day. |
| DP-NEW-B | Can unused personal choice holidays carry over to the next year? → No; all expire December 31 of the grant year. |
| DP-NEW-C | Can sick days be used for a family member's illness? → Yes, up to 3 of 6 days; remaining 3 reserved for employee's own illness (cap-within-a-cap). |

### Additional New Decision Points (Variants 7 & 8)

These DPs appear in Variants 7 and 8 in addition to all 15 DPs from Variants 3 & 4.

**New in Variant 7 only (6 total new: A–F):**
Variants 7 and 8 include DP-NEW-A, B, C from above, plus:

| ID | Decision Point |
|---|---|
| DP-NEW-D | Is the employee part-time? → Not eligible for any benefits in this policy. |
| DP-NEW-E | Can vacation days be carried over? → Yes, maximum 5 days; excess expires December 31. |
| DP-NEW-F | Does sick leave exceed 3 consecutive days? → Yes: medical certificate required. No: none needed. |

**Additional new in Variant 8 only (12 total new: A–L):**
Variant 8 includes all of the above plus:

| ID | Decision Point |
|---|---|
| DP-NEW-G | Can an employee take vacation during their first 90 days? → No. |
| DP-NEW-H | Are personal choice holidays pro-rated for mid-year hires? → Hired on or before July 1: 4 PCHs. After July 1: 2 PCHs. |
| DP-NEW-I | Can an employee donate sick days to a colleague? → No. Non-transferable. |
| DP-NEW-J | Does the vacation absence exceed 10 consecutive working days? → 11+: written leave plan required, HR approved. 10 or fewer: manager approval only. |
| DP-NEW-K | Does bereavement leave reduce the sick day balance? → No. Separate entitlement. |
| DP-NEW-L | Does a fixed holiday fall on a weekend? → Saturday: preceding Friday observed. Sunday: following Monday observed. |

### Removed Decision Points (Variant 6 only)

| ID | Decision Point | Reason for Removal |
|---|---|---|
| DP-2 | Is the employee NOT a supplemental employee? | No longer applicable — personal choice holidays, the only benefit it gated, were removed |
| DP-4 | Personal choice holiday request condition | Personal choice holidays removed entirely from policy |
| DP-5 | Manager approval for personal choice holidays | Removed with DP-4 |
| DP-8 | Hired before Jan 1, 2004 AND 20+ years of service (25-day tier) | 25-day tier dropped; 2-tier vacation table only |

---

## DP Presence Matrix

| DP | V1 | V2 | V3 | V4 | V5 | V6 | V7 | V8 |
|---|---|---|---|---|---|---|---|---|
| DP-1 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| DP-2 | ✓ | ✓ | ✓ | ✓ | ✓ | — | ✓ | ✓ |
| DP-3 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| DP-4 | ✓ | ✓ | ✓ | ✓ | ✓ | — | ✓ | ✓ |
| DP-5 | ✓ | ✓ | ✓ | ✓ | ✓ | — | ✓ | ✓ |
| DP-6 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| DP-7 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| DP-8 | ✓ | ✓ | ✓ | ✓ | ✓ | — | ✓ | ✓ |
| DP-9 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| DP-10 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| DP-11 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| DP-12 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| DP-NEW-A | — | — | ✓ | ✓ | — | — | ✓ | ✓ |
| DP-NEW-B | — | — | ✓ | ✓ | — | — | ✓ | ✓ |
| DP-NEW-C | — | — | ✓ | ✓ | — | — | ✓ | ✓ |
| DP-NEW-D | — | — | — | — | — | — | ✓ | ✓ |
| DP-NEW-E | — | — | — | — | — | — | ✓ | ✓ |
| DP-NEW-F | — | — | — | — | — | — | ✓ | ✓ |
| DP-NEW-G | — | — | — | — | — | — | — | ✓ |
| DP-NEW-H | — | — | — | — | — | — | — | ✓ |
| DP-NEW-I | — | — | — | — | — | — | — | ✓ |
| DP-NEW-J | — | — | — | — | — | — | — | ✓ |
| DP-NEW-K | — | — | — | — | — | — | — | ✓ |
| DP-NEW-L | — | — | — | — | — | — | — | ✓ |
| **Total** | **12** | **12** | **15** | **15** | **12** | **8** | **18** | **24** |

---

## Tag Legend

| Tag | Meaning |
|---|---|
| `same` | Present in this variant; identical rule to the original policy |
| `new` | Present in this variant; does not exist in the original policy |
| `removed` | Present in the original policy; deliberately omitted from this variant |
