# AGENTS.md

## Repository

A Markdown book manuscript: *The Art of IT Management*. 22 chapters in 7 parts, plus templates and appendices. There is no code, package manager, build, or test suite. It is a git repository tracking `https://github.com/Aishan-hn/IT_Book` on `main`. "Verification" means word counts, structural checks, and continuity checks — there is no linter to run.

## Sources of truth

- `README.md` — status table is the progress tracker. Update it whenever a part is drafted.
- `book/00-front-matter.md` — canon: cast, company facts, chapter map, per-part arc. Change facts here first.
- Chapter numbers are referenced from the front matter, README, and across chapters. Never renumber or insert a chapter without updating every reference.
- `templates/` files are standalone deliverables, also referenced from chapters by relative path (`templates/...`). Keep a template and its chapter worked example in sync.
- `appendices/` and `case-studies/` are planned but do not exist yet. Create them only when the relevant part is being written.

## Chapter contract

Every chapter uses these eight `##` sections, in order:

1. Learning objectives (4–7 measurable outcomes)
2. Opening scenario (Meridian, ~300 words)
3. Core concepts (numbered subsections 3.1, 3.2…)
4. Step-by-step method (purpose, inputs, outputs, numbered steps)
5. Case study (real organization: context → what happened → why it matters → transferable lessons)
6. Templates and tools (one filled-in worked example, not just a blank form)
7. Pitfalls and checklist (pitfall table + 8–10 checkbox items)
8. Key takeaways (6–8), Discussion questions (6), Further reading (sourced)

Target 4,000–4,800 words per chapter. Do not pad to hit the number.

## House style

- **British English with Oxford `-ize`**: *organization, recognize, prioritize, reorganization*; British nouns: *programme, centre, licence* (noun) / *license* (verb), *defence, behaviour*. This mix is deliberate — do not "correct" it to American.
- Second person, direct, willing to name failure modes. No motivational filler, no generic management advice.
- Currency: `€` for Meridian and European examples, `$` for US cases. Keep figures consistent with canon.
- Tables for comparisons, Mermaid for flows and structures. No ASCII art diagrams except the fixed stakeholder/capability quadrant sketches in templates.
- Files are UTF-8 without BOM with LF line endings. Windows PowerShell 5.1 renders `€` and `—` as `?` in console output; read with `[IO.File]::ReadAllText($p, [Text.Encoding]::UTF8)` before concluding a file is corrupted.

## Canon: Meridian Group

Fictional composite used in every chapter; each chapter advances it by one decision. Keep these facts stable:

- 4,500 employees, ~€1.4bn revenue, 9% EBITDA, three divisions: Financial Services 45%, Logistics 35%, Retail 20%.
- IT: 90 staff (38 infra/ops, 22 apps, 14 data, 8 security, 8 PMO), €58m opex (~4.1% of revenue), €11m capex.
- Board goals: online to 30% of retail revenue; logistics cost per parcel −12%; group operating cost −€40m.
- Cast: Priya Raman (Group IT Director, reports to CFO), Marcus Feld (CFO), Elena Voss (CEO), Tomás Ferreira (Logistics), Dr. Aisha Bello (Risk), Jonas Weber (Infrastructure), Sofia Marchetti (Security), Ravi Desai (Data).
- Continuity: Part I ends with a seven-initiative strategy, a stop list, a funded envelope with a pre-agreed 15% cut rule, and a capability map. Later parts must build on these, not re-invent them.

## Case-study rules

- Real cases come from public reporting, annual reports, regulator findings, or post-incident reviews; list the source in Further reading.
- Never invent a statistic. If a number is not public, describe the mechanism and sequence of events instead.
- Illustrative figures (Meridian, unit economics, worked examples) must be labelled as illustrative.
- Do not reuse the same company twice across chapters; the index in Appendix D will track them.

## Verify

Word count per file:

```powershell
Get-ChildItem -Recurse -File -Filter *.md | ForEach-Object {
  "{0,-45} {1,6}" -f $_.FullName.Replace((Get-Location).Path + '\',''),
    (Get-Content $_.FullName -Raw | Measure-Object -Word).Words
}
```

Structural check for a chapter:

```powershell
Select-String -Path book\NN-*.md -Pattern '^## '
```

## Version control

- Remote `origin` → `https://github.com/Aishan-hn/IT_Book`, branch `main`, tracking set.
- Commit at each part boundary with a message naming the part (e.g. `Add Part II: governance and organization`). Push only when asked.
- `.gitattributes` forces `eol=lf` and `core.autocrlf` is `false` locally; do not let a global setting renormalize the manuscript to CRLF.
- Identity is repo-local (`Aishan-hn` + GitHub noreply address). Do not change global git config.
- No `gh` CLI is installed; use `git` directly.

## Workflow

- Write part by part, in chapter order, and stop at the part boundary for review. Do not draft ahead into a part the user has not approved.
- After a part: update the README status table, and add any new templates.
- Edit drafted chapters with targeted edits; do not rewrite a whole chapter unless asked.
- If a chapter's method changes a fact established earlier (a number, an owner, a decision), fix the earlier file too.
