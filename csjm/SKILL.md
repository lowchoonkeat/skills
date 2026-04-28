---
name: csjm
description: "Autonomous CSJM paper-generation agent for beast-mode, no-token-budget, non-stop thesis-to-paper conversion into a Computer Science Journal of Moldova submission package. Use when the user wants a CSJM-ready manuscript from a thesis or project folder, needs a LaTeX-first bundle using csjmol.sty and the official template, wants mandatory AI cover-letter support, or wants tier-1-quality research and proof standards applied to a CSJM submission."
argument-hint: [INPUT_SOURCE_PATH="<thesis file/folder or project folder>" OUTPUT_PAPER_DIR="<target paper folder>" -- effort: beast]
allowed-tools: "*"
---

# CSJM Journal Paper Generator

## Inputs parsed from $ARGUMENTS

```text
INPUT_SOURCE_PATH = "<full thesis file/folder or project folder>"
OUTPUT_PAPER_DIR = "<target paper folder>"
TEMPLATE_DIR = "C:/Users/Chi/.claude/skills/csjm"
MAIN_TEMPLATE_TEX_PATH = "C:/Users/Chi/.claude/skills/csjm/CSJM_template.tex"
STYLE_FILE_PATH = "C:/Users/Chi/.claude/skills/csjm/csjmol.sty"
DOI_STYLE_PATH = "C:/Users/Chi/.claude/skills/csjm/doi.sty"
BIB_STYLE_PATH = "C:/Users/Chi/.claude/skills/csjm/IEEEtran.bst"
REFERENCE_GUIDE_DOCX_PATH = "C:/Users/Chi/.claude/skills/csjm/Referencing_in_CSJM.docx"
AI_COVER_LETTER_TEMPLATE = "C:/Users/Chi/.claude/skills/csjm/AI_COVER_LETTER_TEMPLATE.md"
TARGET_VENUE = "Computer Science Journal of Moldova (CSJM)"
MODE = autonomous      # autonomous | controlled
EFFORT = beast         # default and expected mode
```

## Operating stance

- Beast mode is the default. Do not optimise for token thrift.
- Run end to end without pausing unless a hard blocker appears.
- Numeric pass counts below are minimums, not caps.
- Optimise for tier-1 paper discipline while staying truthful to the actual evidence and to CSJM fit.
- Build a submission package, not only a manuscript.
- CSJM is LaTeX first. DOCX is a convenience output only, never the primary submission artifact.

## Beast profile

```text
LITERATURE_DISCOVERY_MIN = 60 papers screened
DEEP_READS_MIN = 20 papers or sections
FINAL_REFERENCE_WINDOW = 12 to 25 curated references, as lean as the evidence allows
SEARCH_BACKENDS = research-lookup + parallel-web + paper-lookup + semantic-scholar + deepxiv/alphaxiv/bgpt-paper-search as needed
OUTLINE_REVIEWS_MIN = 4
ABSTRACT_VARIANTS_MIN = 4
FIGURE_REDESIGNS_MIN = 2 alternatives per important figure
AUTO_PAPER_IMPROVEMENT_MIN = 6 rounds
AUTO_REVIEW_LOOP_MIN = 10 rounds or until converged
RESEARCH_REVIEW_MIN = 2 independent passes
ACADEMIC_REVIEW_MIN = 2 passes if major issues remain
CLAIM_AUDIT_MIN = 2 full audits
PROOF_CHECK = mandatory when the paper has theorem, lemma, proposition, or bound-level claims
OVERFULL_HUNT = keep fixing until no serious overfull equations, algorithms, code blocks, or references remain
CODEX_REASONING_EFFORT = xhigh
```

## CSJM hard constraints

1. Papers are in English only.
2. All visible manuscript content, including references, must use the Roman alphabet. If original-language metadata is needed, keep it commented in the LaTeX source.
3. The paper must use the official CSJM template and `csjmol.sty`.
4. The final submission package must include the main `.tex` file and the generated `.pdf`.
5. If any additional style files are used, include those `.sty` files in the package.
6. Figures must be in `.eps`, `.png`, or `.jpg` format and must fit the printable CSJM area.
7. Use the CSJM printable area and template geometry. The text width is 118 mm and the text height is 182 mm.
8. The paper must not exceed 25 pages in CSJM format. Target a tight, publication-quality manuscript rather than a bloated survey.
9. The bibliography must not exceed 25 items.
10. The paper must contain new, original results relevant to Computer Science, such as theory of software, theory of data, theory of computing, algorithms, AI, computing methodology, or discrete mathematics related to CS. A pure application paper that only applies an existing method to a domain problem is not suitable.
11. Do not produce a survey-paper-style manuscript unless the user explicitly confirms the work is invited. By default, write an original research article.
12. The front matter must include title, author list in Western name order, abstract of about 100 words, keywords, and MSC 2020 codes.
13. The end matter must include affiliation, postal address, email, and ORCID for each author. Funding information is recommended when available.
14. References must follow IEEE style with rich metadata. Use `IEEEtran.bst` if using BibTeX, or a carefully structured manual bibliography if not.
15. Reference numbering must follow the order of appearance in the paper.
16. Figures must have captions below the figure. Tables must have captions above the table.
17. Equations, algorithms, program text, and long references must be line-broken so they do not overflow the CSJM text width.
18. The AI disclosure cover letter is mandatory. It must name every AI service used and describe the exact role each one played.
19. Word-only submission is not acceptable for CSJM. DOCX can exist as an author convenience copy, but the submission artifact is the LaTeX package.

## Expanded skill stack

Use these skills deliberately. Do not skip a stronger specialist skill when it matches the task.

- Discovery and literature: `/deep-research`, `/research-lit`, `/research-lookup`, `/parallel-web`, `/paper-lookup`, `/semantic-scholar`, `/deepxiv`, `/alphaxiv`, `/bgpt-paper-search`, `/research-wiki`
- Thesis and paper ingestion: `/markitdown`, `/docx`, `/pdf`, `/xlsx`
- Fit, novelty, and critical research review: `/novelty-check`, `/research-review`, `/scientific-critical-thinking`, `/venue-templates`
- Theory and proof integrity: `/formula-derivation`, `/proof-checker`, `/proof-writer`, `/sympy`
- Experiments and evidence closure: `/analyze-results`, `/result-to-claim`, `/experiment-audit`, `/ablation-planner`, `/experiment-plan`, `/run-experiment`, `/monitor-experiment`, `/training-check`
- Writing and structuring: `/paper-plan`, `/scientific-writing`, `/paper-write`, `/markdown-mermaid-writing`
- Figures and visuals: `/paper-figure`, `/scientific-visualization`, `/paper-illustration`, `/scientific-schematics`, `/mermaid-diagram`, `/matplotlib`, `/seaborn`
- Review and revision loops: `/peer-review`, `/academic-paper-reviewer`, `/scholar-evaluation`, `/auto-paper-improvement-loop`, `/auto-review-loop`, `/auto-review-loop-llm`
- Claims, references, and packaging: `/paper-claim-audit`, `/citation-management`, `/paper-compile`, `/simple-english`, `/humanizer`, `/docx`

## Known failure modes to catch early

- Never leave placeholder or draft author metadata in any paper-facing asset once real author data is available. The manuscript, end matter, AI cover letter, and readiness files must all carry the same final names, affiliations, e-mail addresses, and ORCID identifiers.
- Remove first-person and internal-process language from the final paper-facing assets. Words such as reviewer, package assembly, placeholder, stress test, or similar workflow narration are not acceptable in the manuscript or disclosure files.
- Do not accept weak citation hygiene. Prefer strong peer-reviewed sources, require DOI metadata whenever available, cite the primary dataset source directly, and add benchmark-caveat citations when known dataset limitations materially affect interpretation.
- Validate manuscript wording against the actual code and saved artifacts before finalizing claims. Typical failure points are duration windows, train/validation/test split rules, random seeds, calibration-set sizes, oracle definitions, baseline thresholds, fallback behavior, and capped training counts.
- Keep the reference list lean. Do not force the bibliography upward to hit an arbitrary floor if the paper is stronger with fewer well-justified references.
- CSJM style files may leak stale or coloured heading metadata. Neutralize visible issue-title or hyperlink styling in the manuscript if the bundled style defaults are not submission-appropriate.
- DOCX is a convenience copy only, but it still needs a quality gate: Times New Roman, black text and headings, justified body paragraphs, and right-aligned sequential equation numbers without damaging formulas.
- After the final rebuild, synchronize all bundle-control files such as `SUBMISSION_MANIFEST.md`, `FINAL_READINESS_SUMMARY.md`, `RUN_LOG.md`, `CITATION_AUDIT.md`, `NARRATIVE_REPORT.md`, and `FIELD_LANDSCAPE.md` so they match the actual PDF page count, bibliography size, author metadata state, and audit outcome.
- Ten audit rounds are more useful when diversified. Separate passes should attack claims, citations, methods-versus-code alignment, journal tone, and package consistency rather than repeating the same generic review prompt.

## Required workflow

### Phase 0 - Preflight and control files

1. Run `/get-available-resources` if experiments, retraining, or large figure regeneration may be required.
2. Create or update these working files in OUTPUT_PAPER_DIR:
   - `RUN_LOG.md`
   - `MASTER_EVIDENCE_INDEX.md`
   - `FIELD_LANDSCAPE.md`
   - `NARRATIVE_REPORT.md`
   - `DERIVATION_PACKAGE.md` when theory is present
   - `RESULTS_ANALYSIS.md`
   - `EXPERIMENT_SCHEDULE.md`
   - `CITATION_AUDIT.md`
   - `SUBMISSION_MANIFEST.md`
   - `FINAL_READINESS_SUMMARY.md`
3. Autonomous mode: keep moving. Controlled mode: report after each phase.

### Phase 1 - Intake and evidence indexing

1. Load INPUT_SOURCE_PATH. If it is a folder, recursively inspect all relevant thesis, manuscript, slide, spreadsheet, figure, code, and notes files.
2. Use `/markitdown`, `/docx`, `/pdf`, and `/xlsx` to normalise source material.
3. Build `MASTER_EVIDENCE_INDEX.md` with every claim candidate, figure or table candidate, dataset, result file, theorem or proof candidate, and baseline or comparator.
4. If the source material contains code or experiment logs, index reproducibility status and missing assets.

### Phase 2 - Field mapping and citation mining

1. Run a beast-mode literature pass using `/deep-research`, `/research-lookup`, `/paper-lookup`, and `/semantic-scholar`.
2. Use `/deepxiv`, `/alphaxiv`, and `/bgpt-paper-search` when section-level reading or richer extraction is useful.
3. Prefer peer-reviewed sources. Use preprints only when necessary for novelty or very recent work.
4. Produce `FIELD_LANDSCAPE.md` with problem framing, strongest related-work clusters, closest competing methods, open gaps, and high-quality candidate references with DOI metadata.
5. Curate aggressively. Final references must fit within the CSJM cap of 25 items.

### Phase 3 - CSJM fit gate, scope selection, and novelty gate

1. Identify every plausible paper angle from the source material.
2. Reject angles that are only applications of an existing method to a domain problem without a genuine algorithmic, theoretical, or methodological contribution.
3. Select the single strongest CSJM-suitable scope based on originality, technical contribution, proof or algorithmic depth, evidence strength, and figure availability.
4. Write `NARRATIVE_REPORT.md` with the selected scope, main research question, core technical contribution, the proposed section outline, and the planned figures and tables.
5. Run `/novelty-check` on the chosen scope.
6. Run `/research-review` or `/scientific-critical-thinking` to attack the scope before drafting.
7. If novelty or venue fit is weak, reframe once and re-check. If the work still looks like an application-only paper, stop and report that it is not honestly suitable for CSJM.

### Phase 4 - Theory, formula, and proof gate

1. Run `/formula-derivation` for all equation-bearing claims.
2. If the selected paper contains theorem, lemma, proposition, bound, convergence, or correctness claims, run `/proof-checker`.
3. If a proof gap is fixable, use `/proof-writer` to repair it and then re-run `/proof-checker`.
4. Keep `DERIVATION_PACKAGE.md` aligned with the draft. Any symbol change triggers a refresh.
5. Do not draft theory-heavy claims until this gate is green.

### Phase 5 - Evidence closure and experiment gap removal

1. Run `/analyze-results` on all result tables, logs, and metrics.
2. Run `/result-to-claim` on every major claim.
3. Run `/experiment-audit` to detect integrity risks or evaluation gaps.
4. If claims are only partially supported, use `/ablation-planner` and `/experiment-plan` to schedule missing evidence.
5. If code and data are available locally or remotely, run the feasible experiments with `/run-experiment`, then monitor via `/monitor-experiment` and `/training-check`.
6. Integrate all locally feasible new results before advancing.
7. Keep unsupported claims out of the draft. Reframe or remove them.

### Phase 6 - Outline, structure, and figure system

1. Run `/paper-plan` at beast effort.
2. Also use `/scientific-writing` to tighten argument structure at paragraph level if the draft is conceptually dense.
3. Build the figure plan using `/paper-figure`.
4. For architecture or workflow visuals, prefer `/scientific-schematics`, `/paper-illustration`, or `/mermaid-diagram`.
5. For quantitative plots, prefer `/scientific-visualization`, `/matplotlib`, or `/seaborn`.
6. For each major figure, compare at least two designs before final selection.
7. Ensure every figure and table maps to a specific claim or interpretive purpose.

### Phase 7 - LaTeX-first draft generation

1. Draft against `MAIN_TEMPLATE_TEX_PATH` rather than inventing a new layout.
2. Keep the draft aligned to CSJM format expectations: title, author block in Western name order, abstract of about 100 words, keywords, MSC 2020 codes, numbered sections and subsections, appendices when needed, bibliography in IEEE style, and author information block at the end with affiliation, address, email, and ORCID.
3. Keep the bibliography within 25 items.
4. If using BibTeX, generate and maintain a `.bib` file with `IEEEtran.bst`.
5. If not using BibTeX, keep manual bibliography entries precise and annotate categories in source comments when helpful.
6. Draft with precise definitions, readable proofs, and careful line breaks for equations and algorithms.
7. Before treating the draft as submission-ready, scrub final prose for first-person narration and internal workflow wording.

### Phase 8 - Multi-layer review loop

Run the review chain in this order. Fix issues between steps.

1. `/peer-review`
2. `/academic-paper-reviewer`
3. `/scholar-evaluation`
4. `/auto-paper-improvement-loop`
5. `/auto-review-loop`
6. `/auto-review-loop-llm` if the preferred review backend is unavailable
7. `/simple-english`
8. `/humanizer` on prose sections only: Abstract, Introduction, Related Work, Discussion, Conclusion

Rules:
- Review counts are minimums. Keep iterating until the paper is stable or a hard blocker emerges.
- If any review flags claim and evidence mismatch, return to Phase 5.
- If any review flags theory inconsistency, return to Phase 4.
- If any review flags venue mismatch, return to Phase 3 and re-check CSJM suitability.
- Never let the humanizer touch equations, proofs, tables, figure labels, citations, units, or reference entries.

### Phase 9 - Claim audit, citation audit, and LaTeX compile validation

1. Run `/paper-claim-audit` with zero-context verification against raw result files.
2. Run `/citation-management` across all references:
   - verify title, authors, year, venue
   - verify DOI and richer metadata where available
   - remove uncited items
   - replace weak sources where stronger sources exist
   - ensure the primary source is cited for each dataset or benchmark used in the paper
   - add explicit limitation or caveat citations when benchmark integrity is a live issue
   - keep the final list within the CSJM cap of 25 items
3. Run `/paper-compile` repeatedly until LaTeX errors are gone and serious overfull lines are fixed.
4. Check equations, algorithms, code snippets, tables, and bibliography lines specifically for width violations.
5. If the draft contains tables sourced from spreadsheets, validate them against the source with `/xlsx`.
6. Explicitly verify that manuscript wording matches the implemented protocol: split seed, calibration sizes, context truncation, oracle definition, and baseline setup.
7. Do not package the submission until every major claim is supported or explicitly scoped as partial, the citation audit is clean, and the LaTeX build is stable.

### Phase 10 - CSJM submission package assembly

1. Produce the main submission bundle:
   - `<paper_slug>_CSJM.tex`
   - `<paper_slug>_CSJM.pdf`
   - `<paper_slug>.bib` when BibTeX is used
   - copied figure files in allowed formats
   - `csjmol.sty`
   - `doi.sty` if used
   - `IEEEtran.bst`
   - any additional required `.sty` files
2. Produce the mandatory AI disclosure cover letter from `AI_COVER_LETTER_TEMPLATE`:
   - `AI_COVER_LETTER.md`
   - `AI_COVER_LETTER.txt`
3. Produce an author convenience copy:
   - `<paper_slug>_CSJM.docx`
4. If the DOCX convenience copy is exported, post-process and verify it for Times New Roman, black text, justified body paragraphs, preserved formula layout, and right-aligned equation numbering.
5. Update `SUBMISSION_MANIFEST.md` with the exact files included in the package and what each file is for.

### Phase 11 - Final quality gate

Do not stop until this checklist passes or a hard blocker is explicitly recorded.

- Scope is genuinely suitable for CSJM and not merely an application paper.
- All major claims are evidence-backed.
- Theory and proof gate is clean where applicable.
- Results tables match source data.
- Citations are verified and fit within the 25-item cap.
- The manuscript stays within the 25-page limit.
- The abstract is about 100 words.
- Keywords and MSC 2020 codes are present.
- Western name order is used.
- Author affiliation, address, email, and ORCID blocks are complete.
- No placeholder metadata, first-person narration, or internal workflow wording remains in paper-facing files.
- Figures are in acceptable formats and tables and figures use the correct caption placement.
- No serious overfull equations, algorithms, code, or bibliography lines remain.
- The AI cover letter is complete and explicit.
- The LaTeX submission bundle is complete.
- The DOCX convenience copy exists, but the package remains LaTeX-first.
- The DOCX convenience copy, if present, uses Times New Roman, black text, justified body paragraphs, and correct equation numbering.
- All control documents reflect the actual final page count, bibliography size, and metadata state of the built bundle.

## Fallback policy

- If a preferred external search or review backend is unavailable, fall back to another listed skill and continue.
- If API-based illustration is unavailable, redraw locally using scientific-visualization or mermaid or matplotlib.
- If experiments cannot be rerun, make the limitation explicit and downgrade the claim.
- If the project cannot honestly support a CSJM-fit original research contribution, stop and say so rather than forcing a bad submission.

## Final deliverables

1. `FINAL_READINESS_SUMMARY.md`
2. `RUN_LOG.md`
3. `FIELD_LANDSCAPE.md`
4. `NARRATIVE_REPORT.md`
5. `DERIVATION_PACKAGE.md` when applicable
6. `RESULTS_ANALYSIS.md`
7. `EXPERIMENT_SCHEDULE.md`
8. `CITATION_AUDIT.md`
9. `SUBMISSION_MANIFEST.md`
10. `<paper_slug>_CSJM.tex`
11. `<paper_slug>_CSJM.pdf`
12. `<paper_slug>.bib` when used
13. `<paper_slug>_CSJM.docx`
14. `AI_COVER_LETTER.md`
15. `AI_COVER_LETTER.txt`
16. Any figure files, style files, and review reports required to reproduce or submit the manuscript