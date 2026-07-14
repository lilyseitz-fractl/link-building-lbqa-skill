# 1 — PC QA Checklist (LIVING FILE — Amy maintains this)

> **Amy:** this is one of the two files you'll update most often. When you catch a data problem in a DJ's PC that the skill should have flagged, add it as a new bullet in the right section below. New checks take effect the next time anyone runs the skill. Keep each check concrete and testable.

This checklist runs **before any write-up is created**. The PC is the source of all the data in the WU, so a flaw in the PC becomes a flaw in the WU (and a credibility problem with the publisher). The QA must be **shown to the DJ in the chat** — list every check and its result, claim by claim where relevant. If anything fails, **stop and ask the DJ to fix the PC and re-upload it**; do not write the WU on a flawed PC.

This is a document-level review of what's verifiable in the PC itself. It does **not** replace the DJ's full Data QA against the Tableau/source data — it catches what can be checked from the PC's own text and numbers.

---

## Check 1 — Key Takeaway coverage (required)

Every key takeaway at the top of the PC must also appear in the body section it belongs to (under that section's Study Findings).

- List each KT.
- For each, name the body section where its content appears.
- Mark ✓ (found) or ✗ (missing).
- **Any ✗ is a fail** — tell the DJ which KT isn't represented in a body section.

Present this as a short table in the chat: `KT | Appears in section | ✓/✗`.

---

## Check 2 — Qualifier-to-number logic (required)

Every verbal qualifier must match its number. This is the most common PC error. Flag any mismatch.

Reference (use these bands):

| Phrase | Valid range |
|---|---|
| "nearly half" / "almost half" | ~45–49% |
| "half" / "1 in 2" | ~48–52% |
| "over half" / "more than half" | >50% (52%+) |
| "a majority" / "most" | >50% |
| "nearly/almost [X]" | just under X (within ~1–4 points) |
| "over [X]" / "more than [X]" | strictly greater than X |
| "1 in 3" | ~31–35% |
| "1 in 4" | ~24–26% |
| "1 in 5" | ~19–21% |
| "2 in 5" | ~38–42% |
| "3 in 5" | ~58–62% |
| "3 in 4" | ~73–77% |
| "4 in 5" | ~78–82% |
| "1 in 6" | ~15–18% |

Classic failures to catch:
- "**nearly half (41%)**" — 41% is NOT nearly half. (41% ≈ "over 2 in 5" or "more than 40%.")
- "**most (48%)**" — 48% is not a majority; it's a plurality at best. Use "nearly half."
- "**over half (50%)**" — 50% is not *over* half. Use "half."
- "**1 in 3 (28%)**" — 28% rounds to closer to 1 in 4.
- Rounding a number up into a more impressive band ("almost 6 in 10" for 54%).

For each qualifier in the KTs and findings, confirm the number supports the words. Flag every mismatch with the suggested fix.

---

## Check 3 — Math & internal consistency (required)

- **Same stat, stated the same everywhere.** A figure in a KT must match the same figure in its body section and in the methodology. Flag any drift (e.g., KT says 55%, body says 54%).
- **Percentages that should total ~100% do.** If a single-select breakdown sums to 97% or 103%, the PC needs a rounding disclaimer ("Percentages not totaling 100% are due to rounding"). If it sums to something far off (e.g., 88%), something's missing — flag it. Multi-select questions can exceed 100% — that's fine, but it should be evident from the wording.
- **Comparisons are supported by their numbers.** "X tops Y (23% vs. 14%)" — confirm 23 > 14 and that both numbers appear. "12 percentage points higher" — confirm the subtraction.
- **No impossible values:** nothing over 100% for a single share, no negative counts, subgroup percentages that exceed the group, etc.
- **Sample sizes are consistent** and any subgroup small enough to be unreliable is acknowledged (the PC may note "directional only" for tiny n).
- **Percent change vs. percentage points** are used correctly (a move from 20% to 30% is +10 percentage points, or +50%, not "+10%").

---

## Check 4 — Claim soundness (required)

- Every claim is **logical and supported by the study** — nothing overreaching or unsupported by the data the PC contains.
- **Rankings/superlatives are precise** — "the highest among the brands surveyed," not a blanket "the highest" the data can't support.
- **Causation isn't claimed from correlation** — the data shows what people said/did, not why, unless the study measured it.
- **Findings are attributable to the asset** in their section (each section's findings actually relate to that section's visual).

---

## Check 5 — Completeness for write-up (required)

Confirm the PC contains what the WU needs. Flag anything missing:

- Title / Title Tag, Client, Domain, Article Type
- Intro material, Key Takeaways
- For each section: an asset (with alt text) and at least the findings to write from
- Methodology (with sample size, fielding period, and — for surveys — the 18+ line)
- About [Client] direction (or a note that the CM doc supplies or skips it)
- Anything the **CM doc** specifically requires that the PC is missing (special methodology language, demographic notes, banned topics/competitors, subtitle, etc.)

---

## Output of the QA step

Post a clear, scannable QA report in the chat with each check and its result. End with one of:

- **✅ PC QA PASSED — proceeding to the write-up.** (Only when every required check passes.)
- **⛔ PC QA — ISSUES FOUND.** Then a numbered list of every specific issue (quote the PC text, give the fix), and the instruction: *"Please correct these in the PC, re-export it as HTML, and re-upload it so I can build the write-up."* Do not write the WU.

---

## Amy's notes / additional checks

<!-- Amy: add new PC checks here as you discover them. One concrete, testable bullet each.
Example format:
- [Client or general] Check that <specific thing>. Caught on <campaign> when <what happened>.
-->
