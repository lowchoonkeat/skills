---
name: iem
description: "Autonomous IEM journal original-research paper-generation agent for beast-mode, no-token-budget, non-stop thesis-to-paper conversion. Use when the user wants the strongest IEM paper from a thesis or project folder, wants named and anonymous IEM DOCX outputs, needs aggressive literature, experiment, proof, citation, and review loops, or wants tier-1-quality standards applied to an IEM submission. This skill is for original-research manuscripts, not review or survey papers."
argument-hint: [INPUT_SOURCE_PATH="<thesis file/folder or project folder>" OUTPUT_PAPER_DIR="<target paper folder>" -- effort: beast]
allowed-tools: "*"
---

# IEM Journal Paper Generator

## Inputs parsed from $ARGUMENTS

```text
INPUT_SOURCE_PATH = "<full thesis file/folder or project folder>"
OUTPUT_PAPER_DIR = "<target paper folder>"
TEMPLATE_DOCX_PATH = "C:/Users/Chi/.claude/skills/iem/Paper template 2025.docx"
AUTHOR_AFFILIATIONS_PATH = "C:/Users/Chi/.claude/skills/iem/AUTHORS' AFFILIATIONS.docx"
TARGET_VENUE = "IEM Journal"
MODE = autonomous      # autonomous | controlled
EFFORT = beast         # default and expected mode
```

## Operating stance

- Beast mode is the default. Do not optimise for token thrift.
- Run end to end without pausing unless a hard blocker appears.
- Numeric pass counts below are minimums, not caps.
- Optimise for tier-1 paper discipline: strongest scope, strongest evidence, strongest writing, strongest audit trail.
- Stay honest. Never write claims the evidence cannot defend.
- Prefer upgrading evidence over polishing weak claims.
- Do not treat paper generation as a one-shot prompt. Build the paper through gated phases.

## Boundary with iem-review

- Use `/iem-review` for narrative reviews, survey papers, scoping reviews, and systematic reviews targeting IEM.
- Do not use `/iem` when the manuscript's value comes primarily from literature synthesis rather than new experiments, new theory, or new implementation evidence.
- If a source folder contains an IEM review-paper draft, hand off to `/iem-review` immediately instead of trying to force review logic into this skill.

## Beast profile

```text
LITERATURE_DISCOVERY_MIN = 60 papers
DEEP_READS_MIN = 20 papers or sections
SEARCH_BACKENDS = research-lookup + parallel-web + paper-lookup + semantic-scholar + deepxiv/alphaxiv/bgpt-paper-search as needed
OUTLINE_REVIEWS_MIN = 4
ABSTRACT_VARIANTS_MIN = 4
FIGURE_REDESIGNS_MIN = 2 alternatives per important figure
AUTO_PAPER_IMPROVEMENT_MIN = 6 rounds
AUTO_REVIEW_LOOP_MIN = 10 rounds or until converged
RESEARCH_REVIEW_MIN = 2 independent passes
ACADEMIC_REVIEW_MIN = 2 passes if major issues remain
CLAIM_AUDIT_MIN = 2 full audits
ABLATIONS_MIN = 12 whenever ablations are meaningful
PROOF_CHECK = mandatory when the paper has theorem, lemma, proposition, or bound-level claims
CODEX_REASONING_EFFORT = xhigh
```

## IEM hard constraints

1. Use UK English throughout.
2. Use only ASCII punctuation in prose. No em dash and no en dash.
3. Keep main-body text fully justified in the final DOCX.
4. Number every displayed equation sequentially on the right: (1), (2), (3), and so on.
5. Keep notation, symbols, equations, figures, tables, references, and claims internally consistent.
6. If the source thesis or project is broad, select one coherent strongest paper scope only.
7. Do not describe the final paper as a thesis, dissertation, student report, or coursework artifact.
8. In-text author-year citations should remain author-year style. The reference list must follow the IEM format expected by the existing template workflow.
9. Every reference must be metadata-verified and should include a DOI URL whenever one exists.
10. Keep captions unique. Only the real caption may start with `Figure X.` or `Table X.`.
11. If equations or nontrivial symbols are used, include a `List of notations` after `Keywords`.
12. Include `AUTHOR CONTRIBUTIONS`, `ACKNOWLEDGEMENTS`, `DATA AVAILABILITY`, and `CONFLICTS OF INTEREST` before `References`.
13. Include `PROFILES` after `References` in the named version.
14. The named DOCX must use the IEM author and affiliation style. The anonymous version must remove or blind identifying material.
15. Prefer peer-reviewed journals and flagship proceedings over weak or DOI-free sources.
16. Remove uncited references.
17. Do not let DOCX post-processing corrupt equations, subscripts, superscripts, Greek letters, or units.
18. Final outputs are named and anonymous DOCX files plus the full working package that produced them.
19. Keep visible spacing after title and heading blocks so the manuscript does not collapse into a dense wall of text.
20. Keep the title and author block centered when the IEM template expects centered front matter, but keep section and list headings aligned to the same left edge as the main body text. Do not mix centered and left-aligned section furniture by accident.
21. Do not leave the abstract body, abbreviation list body, or other manuscript prose ragged-left by accident. Main prose should remain fully justified.
22. Do not rely on inherited Heading styles if they introduce hidden left or hanging indents. Force numbered headings to the same body-text edge in the final DOCX.
23. When the user provides a strong sample paper from the target venue or article type, calibrate structure and package discipline against it. Adopt reusable structural patterns, not its wording.
24. Write Times New Roman explicitly into final DOCX styles and runs. Do not rely on template inheritance alone.
25. Only enable line numbering when the journal or user explicitly wants it for that specific deliverable. Do not propagate line numbering by default to supporting documents.
26. The named author block must render affiliation numerals as true superscripts or visually correct superscript glyphs in the final DOCX.
27. Keep figure captions and table captions as standalone paragraphs. Never collapse multiple captions into one paragraph.
28. Do not place a figure or table immediately after a major section heading without at least one orienting sentence or paragraph.
29. Ensure substantive tables show visible borders in the final DOCX unless the element is intentionally not a table, such as a plain-text abbreviation list.
30. Add visible spacing before and after figures, captions, and tables so they do not visually merge into surrounding text.

## Expanded skill stack

Use these skills deliberately. Do not skip a stronger specialist skill when it matches the task.

- Discovery and literature: `/deep-research`, `/research-lit`, `/research-lookup`, `/parallel-web`, `/paper-lookup`, `/semantic-scholar`, `/deepxiv`, `/alphaxiv`, `/bgpt-paper-search`, `/research-wiki`
- Thesis and paper ingestion: `/markitdown`, `/docx`, `/pdf`, `/xlsx`
- Fit, novelty, and critical research review: `/novelty-check`, `/research-review`, `/scientific-critical-thinking`
- Theory and proof integrity: `/formula-derivation`, `/proof-checker`, `/proof-writer`, `/sympy` when symbolic verification helps
- Experiments and evidence closure: `/analyze-results`, `/result-to-claim`, `/experiment-audit`, `/ablation-planner`, `/experiment-plan`, `/run-experiment`, `/monitor-experiment`, `/training-check`
- Writing and structuring: `/paper-plan`, `/scientific-writing`, `/paper-write`, `/markdown-mermaid-writing`
- Figures and visuals: `/paper-figure`, `/scientific-visualization`, `/paper-illustration`, `/paper-illustration-image2`, `/scientific-schematics`, `/mermaid-diagram`, `/matplotlib`, `/seaborn`
- Review and revision loops: `/peer-review`, `/academic-paper-reviewer`, `/scholar-evaluation`, `/auto-paper-improvement-loop`, `/auto-review-loop`, `/auto-review-loop-llm`
- Claims, references, and venue compliance: `/paper-claim-audit`, `/citation-audit`, `/citation-management`, `/venue-templates`, `/paper-compile`, `/simple-english`, `/humanizer`

## Known failure modes to catch early

- Never leave draft or placeholder author metadata in the named output once real author data is available. Named manuscript, disclosure blocks, profiles, and readiness files must all agree.
- Remove first-person and internal workflow language from final paper-facing assets. Terms such as reviewer, package assembly, placeholder, or similar workflow narration should not appear in the exported manuscript or companion disclosure files.
- Do not accept weak citation hygiene. Prefer stronger peer-reviewed sources, require DOI URLs whenever available, cite the primary dataset source directly, and add caveat citations when benchmark limitations materially affect interpretation.
- Validate manuscript text against the actual code and saved artifacts before export. Common failure points are split rules, random seeds, calibration sizes, duration windows, oracle definitions, fallback behavior, and fixed-threshold baselines.
- DOCX export needs an explicit quality gate: fully justified body text, correct equation numbering on the right, preserved mathematical formatting, and no font drift away from the target template styling.
- DOCX export also needs a section-furniture quality gate: the title and author block should stay centered when required by the template, while numbered headings and list headings must line up with the body-text edge instead of drifting through hidden style indents.
- Front-matter prose such as the abstract body and list-of-abbreviations body must be checked for full justification after export, not only the later manuscript sections.
- If a strong venue-matched sample is provided, compare the current draft against it for structure, table design, method transparency, and section flow before final export.
- Keep support files synchronized with the actual final outputs. Manifest, readiness notes, citation audit, and run log must match the built files, author metadata state, and final page count.
- Multi-round audit loops should diversify their attack surface. Separate passes should inspect claims, citations, methods-versus-code alignment, tone, anonymity, and package consistency.

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
5. If the paper is part of a larger ongoing project, update `/research-wiki` with the selected scope and core references.

### Phase 3 - Scope selection, venue fit, and novelty gate

1. Identify every plausible paper angle from the source material.
2. Select the single strongest IEM-suitable scope based on novelty, evidence strength, clarity, and figure availability.
3. Write `NARRATIVE_REPORT.md` with the selected scope, main research question, core hypothesis or method thesis, exactly three contributions unless the evidence strongly requires otherwise, the proposed section outline, and the planned figures and tables.
4. Run `/novelty-check` on the chosen scope.
5. Run `/research-review` or `/scientific-critical-thinking` to attack the scope before drafting.
6. If novelty is weak, reframe once and re-check. If it is still weak, stop only if no honest differentiating contribution exists.

### Phase 4 - Theory, formula, and proof gate

1. Run `/formula-derivation` for all equation-bearing claims.
2. If the selected paper contains theorem, lemma, proposition, bound, or convergence claims, run `/proof-checker`.
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
2. If a venue-matched sample paper or package is available, run `/venue-templates` and compare the current outline against that sample before locking structure and figure priorities.
3. Also use `/scientific-writing` to tighten argument structure at paragraph level if the draft is conceptually dense.
4. Build the figure plan using `/paper-figure`.
5. For architecture or workflow visuals, prefer `/scientific-schematics`, `/paper-illustration`, `/paper-illustration-image2`, or `/mermaid-diagram`. Use `/paper-illustration-image2` only when the local Codex native image bridge is available and a raster illustration is a better fit than a deterministic vector figure.
6. For quantitative plots, prefer `/scientific-visualization`, `/matplotlib`, or `/seaborn`.
7. For each major figure, compare at least two designs before final selection.
8. Ensure every figure and table maps to a specific claim or interpretive purpose.

### Phase 7 - Draft generation

1. Run `/paper-write` only after the earlier gates are satisfied.
2. Use `/scientific-writing` for sections that need better narrative flow, synthesis, or literature integration.
3. Keep the draft aligned to IEM formatting expectations: title, author block, abstract, keywords, list of notations when needed, numbered sections and subsections, required declaration blocks, references, and profiles.
4. Contributions in the Introduction must be an explicit numbered list:
   1. ...
   2. ...
   3. ...
5. Draft with strong verbs, precise baselines, honest limitations, and no filler.
6. Before export, scrub final prose for first-person narration and internal workflow wording.

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
- If any review flags venue mismatch, run `/venue-templates` and re-align immediately.
- Never let the humanizer touch equations, tables, figure labels, citations, units, or reference entries.

### Phase 9 - Claim audit, citation audit, and compile validation

1. Run `/paper-claim-audit` with zero-context verification against raw result files.
2. Run `/citation-audit` with zero-context verification across the bibliography and surrounding claim contexts so wrong-context citations, metadata drift, and phantom references are caught before final export.
3. Run `/citation-management` across all references:
   - verify title, authors, year, venue
   - verify DOI
   - remove uncited items
   - replace weak sources where stronger sources exist
   - ensure the primary source is cited for each dataset or benchmark used in the paper
   - add caveat citations when benchmark integrity or split protocol materially affects interpretation
4. Run `/paper-compile` for structural validation even though DOCX is the final export target.
5. If the draft contains tables sourced from spreadsheets, validate them against the source with `/xlsx`.
6. Explicitly verify that manuscript wording matches the implemented protocol: split seed, calibration sizes, context truncation, oracle definition, and baseline setup.
7. Do not export until every major claim is supported or explicitly scoped as partial, the citation audit is clean, equation numbering is continuous, and captions are unique.

### Phase 10 - IEM template export and package assembly

1. Use TEMPLATE_DOCX_PATH as the final template anchor.
2. Use AUTHOR_AFFILIATIONS_PATH if author metadata needs structured mapping.
3. Export:
   - `<paper_slug>_IEM_WITH_AUTHORS.docx`
   - `<paper_slug>_IEM_WITHOUT_AUTHORS.docx`
4. Also assemble the working package: source manuscript markdown, figure sources, derived tables, audit reports, and final citation log.
5. Verify the named DOCX for full justification, correct equation numbering, stable maths formatting, final author metadata, explicit Times New Roman styling, superscript affiliation markers, heading alignment with the main text edge, standalone captions, visible table borders, and correct spacing around figures and tables.
6. Verify the anonymous DOCX for full justification, correct equation numbering, zero author-identifying leakage, explicit Times New Roman styling, correct heading alignment, standalone captions, visible table borders, correct spacing around figures and tables, and no accidental line numbering unless explicitly requested.
7. If a convenience PDF can be generated cleanly, include it, but DOCX remains the required endpoint for this skill.

### Phase 11 - Final quality gate

Do not stop until this checklist passes or a hard blocker is explicitly recorded.

- Scope is single, coherent, and differentiated.
- All major claims are evidence-backed.
- Theory and proof gate is clean where applicable.
- Results tables match source data.
- Citations and DOIs are verified.
- UK English is consistent.
- No em dash or en dash remains.
- IEM formatting blocks are present.
- Named and anonymous outputs are both complete.
- No author-identifying data leaks into the anonymous version.
- No placeholder metadata, first-person narration, or internal workflow wording remains in the exported paper-facing files.
- Figures and tables are publication quality.
- Final prose reads like a journal paper, not a thesis extraction.
- DOCX export preserves heading alignment, front-matter justification, superscript affiliations, line-numbering scope, caption separation, visible table borders, and spacing around display elements.
- Manifest, readiness notes, and audit files match the actual exported outputs.

## Fallback policy

- If a preferred external search or review backend is unavailable, fall back to another listed skill and continue.
- If API-based illustration is unavailable, redraw locally using scientific-visualization or mermaid or matplotlib.
- If experiments cannot be rerun, make the limitation explicit and downgrade the claim.
- If the project cannot honestly support tier-1-quality evidence, still produce the strongest truthful IEM paper and document the gap.

## Final deliverables

1. `FINAL_READINESS_SUMMARY.md`
2. `RUN_LOG.md`
3. `FIELD_LANDSCAPE.md`
4. `NARRATIVE_REPORT.md`
5. `DERIVATION_PACKAGE.md` when applicable
6. `RESULTS_ANALYSIS.md`
7. `EXPERIMENT_SCHEDULE.md`
8. `CITATION_AUDIT.md`
9. `<paper_slug>_IEM_WITH_AUTHORS.docx`
10. `<paper_slug>_IEM_WITHOUT_AUTHORS.docx`
11. Any supporting figures, source tables, and review reports used to justify the final manuscript