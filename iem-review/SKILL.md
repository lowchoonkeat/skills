---
name: iem-review
description: "Autonomous IEM journal review-paper generator for narrative, structured, scoping, and systematic review manuscripts. Use when the user wants an IEM-ready review article from a topic, source folder, or draft; wants named and anonymous IEM DOCX outputs; needs aggressive literature discovery, source verification, synthesis, reviewer loops, and strict IEM formatting for a review paper."
argument-hint: [INPUT_TOPIC_OR_SOURCE="<topic, source folder, draft, or report>" OUTPUT_PAPER_DIR="<target review-paper folder>" -- review-type: auto|narrative|structured|scoping|systematic -- effort: beast]
allowed-tools: "*"
metadata:
   version: "1.1.0"
   last_updated: "2026-04-25"
  status: active
  related_skills:
    - iem
    - deep-research
    - literature-review
    - academic-paper-reviewer
---

# IEM Review Paper Generator

## Inputs parsed from $ARGUMENTS

```text
INPUT_TOPIC_OR_SOURCE = "<topic, source folder, draft, or report>"
OUTPUT_PAPER_DIR = "<target review-paper folder>"
TEMPLATE_DOCX_PATH = "C:/Users/Chi/.claude/skills/iem/Paper template 2025.docx"
AUTHOR_AFFILIATIONS_PATH = "C:/Users/Chi/.claude/skills/iem/AUTHORS' AFFILIATIONS.docx"
TARGET_VENUE = "IEM Journal"
REVIEW_TYPE = auto      # auto | narrative | structured | scoping | systematic
MODE = autonomous       # autonomous | controlled
EFFORT = beast          # default and expected mode
```

## Operating stance

- Beast mode is the default. Do not optimise for token thrift.
- Run end to end without pausing unless a hard blocker appears.
- Numeric pass counts below are minimums, not caps.
- Optimise for tier-1 review-paper discipline: strongest landscape coverage, strongest synthesis, strongest citation hygiene, strongest audit trail.
- Stay honest. Never claim systematic completeness, meta-analytic strength, or empirical superiority that the evidence cannot defend.
- Prefer better source coverage and sharper synthesis over decorative prose.
- Treat review papers as argument-driven synthesis, not as paper piles or study-by-study catalogues.

## Why this skill exists

- `/iem` is for original-research IEM manuscripts built from thesis or project evidence, experiments, proofs, and claim audits.
- `/iem-review` is for review, survey, scoping, and systematic-review manuscripts whose value comes from literature synthesis, comparison, taxonomy, and deployment interpretation.
- `/deep-research` is a required engine inside this skill for field mapping, source verification, and systematic modes, but it is not a substitute for IEM-specific paper assembly.
- `/literature-review` is also required when search logging, screening, PRISMA-style transparency, or broader review-article discipline is needed.
- If another skill detects that the target output is an IEM review paper, it should hand off directly to `/iem-review` rather than routing through `/iem` first.

## Review-type selection

Use `auto` unless the user explicitly specifies the review type.

- `narrative`: focused interpretive synthesis around a clearly bounded topic, without claiming exhaustive systematic coverage.
- `structured`: default IEM mode for most engineering review papers. Requires transparent search logic, explicit inclusion boundaries, source grading, and comparison tables, but does not overclaim PRISMA-level completeness.
- `scoping`: broad landscape mapping where the literature is heterogeneous and the goal is coverage, taxonomy, and gap identification.
- `systematic`: only when reproducible search strings, screening logs, inclusion or exclusion criteria, source counts, and PRISMA-style reporting are genuinely feasible.

Rules:

- Never label the paper `systematic` unless the workflow actually records reproducible search and screening evidence.
- If a user draft overclaims review rigor, downgrade the label to the strongest honest type and explain the boundary inside the manuscript.
- For most IEM review articles, `structured` is the right default.

## Beast profile

```text
LITERATURE_DISCOVERY_MIN = 80 papers
DEEP_READS_MIN = 30 papers or sections
DATABASE_FAMILIES_MIN = 5 for systematic, 3 for structured or narrative
SEARCH_REFINEMENT_ROUNDS_MIN = 3
COMPARISON_TABLES_MIN = 3
THEMATIC_AXES_MIN = 4
FIGURES_MIN = 2
ABSTRACT_VARIANTS_MIN = 4
AUTO_PAPER_IMPROVEMENT_MIN = 6 rounds
REVIEW_PASSES_MIN = 2 independent passes
ACADEMIC_REVIEW_MIN = 2 passes if major issues remain
CITATION_AUDIT_MIN = 2 full audits
CODEX_REASONING_EFFORT = xhigh
```

## IEM hard constraints

1. Use UK English throughout.
2. Use only ASCII punctuation in prose. No em dash and no en dash.
3. Keep main-body text fully justified in the final DOCX.
4. Write Times New Roman explicitly into final DOCX styles and runs. Do not rely on template inheritance alone.
5. Only enable line numbering when the journal or user explicitly wants it for that specific deliverable. Do not propagate line numbering by default to cover letters, response letters, email drafts, author-information sheets, or manifests.
6. The named author block must render affiliation numerals as true superscripts or as visually correct superscript glyphs in the final DOCX.
7. Number every displayed equation sequentially on the right if equations are used.
8. Keep notation, symbols, figures, tables, references, and claims internally consistent.
9. Use the IEM template for title, author, and affiliation layout. Keep the title in sentence case unless acronym conventions require capitals.
10. The abstract must be citation-free and must state scope, review method, key synthesis findings, and the main conclusion.
11. Provide 5 to 7 keywords.
12. If the paper is abbreviation-heavy, include `List of abbreviations` after `Keywords`. If it is equation-heavy, include `List of notations` after `Keywords`.
13. Every numbered section should follow IEM style, for example `1.0`, `1.1`, and `1.1.1` where needed.
14. Include a dedicated `Review scope, method, and contribution` subsection early in the paper.
15. Do not present synthesis, tables, or narrative comparison as original experimental validation.
16. Never invent PRISMA counts, database yields, screening decisions, or search dates.
17. Every benchmark comparison must preserve dataset, split, task, metric, and threat-model boundaries. Do not compare incomparable numbers as if they were directly ranked.
18. Distinguish clearly between peer-reviewed evidence, standards, government or regulator advisories, and vendor or practitioner disclosures.
19. In-text citations remain author-year style. The reference list must follow the IEM format expected by the template workflow.
20. Every reference must be metadata-verified and should include a DOI URL whenever one exists.
21. Remove uncited references.
22. Include `AUTHOR CONTRIBUTIONS`, `ACKNOWLEDGEMENTS`, `DATA AVAILABILITY`, and `CONFLICTS OF INTEREST` before `References`.
23. Include `PROFILES` after `References` in the named version.
24. The named DOCX must use the IEM author and affiliation style. The anonymous version must remove or blind identifying material.
25. Do not let DOCX post-processing corrupt equations, symbols, subscripts, superscripts, Greek letters, figures, or table layout.
26. Final outputs are named and anonymous DOCX files plus the full working package that produced them.
27. The final manuscript must read like a journal review article, not a thesis chapter, student report, or annotated bibliography.
28. Keep numbered headings left-aligned, bold, aligned to the same left edge as the main body text, and separated from surrounding text by visible paragraph spacing.
29. Prefer prose paragraphs over bullet lists in the main review narrative. Reserve lists for true contribution statements, tightly bounded enumerations, or package-control artefacts.
30. Keep figure captions and table captions as standalone paragraphs. Never collapse multiple captions into one paragraph.
31. Do not place a figure or table immediately after a major section heading without at least one orienting sentence or paragraph.
32. Ensure substantive tables show visible borders in the final DOCX unless the element is intentionally not a table, such as a plain-text abbreviation list.
33. Add visible spacing before and after figures, captions, and tables so they do not visually merge into surrounding text.
34. Keep the title and author block centered when the template expects centered front matter, but keep numbered headings, abstract heading, list headings, and caption-list entries aligned to the same left edge as the main body text.
35. Keep visible spacing after title and heading blocks. Do not allow title, abstract, keyword, abbreviation, or caption-list sections to collapse into one dense block.
36. Keep the abstract body, abbreviation-list body, and other review prose fully justified. Do not leave front-matter prose ragged-left by accident.
37. Remove hidden heading-style indents or hanging indents in the final DOCX so headings and body text share the same visual left edge.
38. When a strong sample review paper is provided, calibrate the review against it for structure, method transparency, and synthesis discipline. Adopt reusable structural patterns, not the sample's wording.

## Recommended section architecture

Use the strongest fit below, but keep the actual section titles aligned to the paper's subject.

### Default structured IEM review shape

1. `Introduction`
2. `Review scope, method, and contribution`
3. `Domain background, architecture, or system context`
4. `Thematic synthesis I`
5. `Thematic synthesis II`
6. `Comparative analysis, deployment implications, or challenge map`
7. `Open challenges and future directions`
8. `Conclusion`

### Systematic IEM review additions

- `Search strategy`
- `Inclusion and exclusion criteria`
- `Screening flow and source counts`
- `Quality appraisal or risk-of-bias summary`

Formatting rules inside the manuscript:

- Keep the abstract self-contained and citation-free.
- Put the review method early, not buried near the end.
- When a strong sample review paper is available, compare the draft against it before final export and explicitly decide which structural features should be adopted.
- Use at least one taxonomy or architecture figure and one comparison table.
- Only use quantitative cross-study charts when the source metrics are genuinely comparable.
- Keep captions unique. Only the real caption may begin with `Figure X.` or `Table X.`.
- Keep each item in the figure and table caption list on its own paragraph or line, not merged into a single caption block.
- Avoid bullet-heavy body sections when a paragraph comparison reads more like a journal article.
- Comparison tables support the argument; they do not replace it. Do not try to list every paper if a representative synthesis table serves the reader better.
- A strong review paper must explain why previous reviews are insufficient, what organising taxonomy is used here, and how the review method bounded the evidence.
- Even in a structured or narrative review, include explicit search logic, inclusion logic, and honest limits of completeness.
- Keep centered front matter and left-aligned numbered headings distinct. Do not solve a heading-indent problem by forcing the title or author block left.
- For long structured reviews, strongly consider explicit subsections for related-literature positioning, review questions, contribution list, and paper structure when they improve navigability.
- A structured review can legitimately emulate a systematic paper's discipline by stating objectives, guiding questions, search logic, evidence-extraction categories, and quality emphasis, even when it does not claim PRISMA completeness.

## Expanded skill stack

Use these skills deliberately. Do not skip a stronger specialist skill when it matches the task.

- Core review evidence engine: `/deep-research`, `/literature-review`, `/research-lit`, `/research-lookup`, `/parallel-web`, `/paper-lookup`, `/semantic-scholar`, `/deepxiv`, `/alphaxiv`, `/bgpt-paper-search`, `/research-wiki`
- Ingestion and evidence extraction: `/markitdown`, `/docx`, `/pdf`, `/xlsx`
- Synthesis, critique, and review: `/scientific-critical-thinking`, `/peer-review`, `/academic-paper-reviewer`, `/scholar-evaluation`, `/auto-paper-improvement-loop`, `/auto-review-loop`, `/auto-review-loop-llm`
- Writing and structure: `/paper-plan`, `/scientific-writing`, `/paper-write`, `/markdown-mermaid-writing`
- Figures and tables: `/paper-figure`, `/scientific-visualization`, `/scientific-schematics`, `/paper-illustration`, `/paper-illustration-image2`, `/mermaid-diagram`, `/matplotlib`, `/seaborn`
- Claims, citations, and compliance: `/citation-audit`, `/citation-management`, `/venue-templates`, `/paper-compile`, `/simple-english`, `/humanizer`
- Optional quantitative escalation only when justified: `/statistical-analysis`, `/paper-claim-audit`

## Known failure modes to catch early

- Claiming `systematic review` status without reproducible screening records.
- Writing study-by-study summaries instead of theme-level synthesis.
- Mixing incomparable benchmarks across different datasets, splits, or threat models.
- Leaning on blogs, vendor posts, or preprints for core claims when stronger peer-reviewed sources exist.
- Leaving the review method vague or implicit.
- Forgetting to explain why earlier reviews or adjacent surveys are insufficient for the present review question.
- Treating the review's contribution as if it were a new model, new dataset, or new experiment when it is actually synthesis.
- Letting comparison tables become paper dumps instead of representative synthesis devices.
- Overgeneralising benchmark results into real-world deployment claims without external validation.
- Reporting quantitative tables whose extracted values have not been checked back to the original paper.
- Letting PRISMA or flow counts drift between logs, diagrams, and manuscript text.
- DOCX export drifting away from IEM layout, justification, or caption order.
- Forcing the title or author block left when the template expects centered front matter.
- Leaving the abstract body or abbreviation-list prose left-aligned instead of justified after a formatter change.
- Leaving line numbering on by default across every DOCX deliverable, especially reviewer-facing support documents.
- Assuming template fonts will survive export without explicitly writing Times New Roman into the final DOCX XML.
- Allowing author affiliation markers to flatten into normal baseline digits instead of superscripts.
- Leaving hidden Heading-style left or hanging indents in place so headings no longer line up with the main body text.
- Letting figures appear directly under a section heading before the section has been oriented for the reader.
- Merging multiple figure and table captions into one paragraph in the caption-list section.
- Exporting comparison tables without visible borders, which makes the review package look unfinished in Word.
- Seeing a strong sample review paper and copying its wording instead of extracting its structural lessons.
- Leaving the introduction too flat when the paper would benefit from explicit related-work positioning, review questions, and a paper roadmap.

## Required workflow

### Phase 0 - Preflight and control files

1. Create or update these working files in OUTPUT_PAPER_DIR:
   - `RUN_LOG.md`
   - `SOURCE_LEDGER.md`
   - `SEARCH_PROTOCOL.md`
   - `SCREENING_LOG.md`
   - `EVIDENCE_MATRIX.md`
   - `THEME_MAP.md`
   - `COMPARISON_TABLES.md`
   - `NARRATIVE_REPORT.md`
   - `CITATION_AUDIT.md`
   - `FINAL_READINESS_SUMMARY.md`
   - `PRISMA_FLOW.md` when review type is `systematic`
2. Determine the honest review type before writing any claims about coverage.
3. Autonomous mode: keep moving. Controlled mode: report after each phase.

### Phase 1 - Intake, scope, and boundary setting

1. Load INPUT_TOPIC_OR_SOURCE. If it is a folder, recursively inspect all relevant drafts, notes, spreadsheets, citations, figures, rebuttals, and prior reviews.
2. Normalise source material with `/markitdown`, `/docx`, `/pdf`, and `/xlsx` as needed.
3. Define the review question, topic boundary, time window, evidence types, and target readership.
4. Record inclusion and exclusion logic in `SEARCH_PROTOCOL.md`.
5. If an existing draft claims more rigor than the saved evidence can support, downgrade the paper type to the strongest honest label and record why.

### Phase 2 - Discovery and field mapping

1. Run `/deep-research` in a mode aligned to the review type:
   - `narrative` or `structured`: use `lit-review` or `full`
   - `scoping`: use `full`
   - `systematic`: use `systematic-review`
2. Run `/literature-review` to strengthen search strategy, source aggregation, and review-specific evidence handling.
3. Supplement with `/research-lookup`, `/paper-lookup`, `/semantic-scholar`, `/parallel-web`, `/deepxiv`, `/alphaxiv`, and `/bgpt-paper-search` when deeper extraction or broader coverage is needed.
4. Prefer peer-reviewed sources. Use standards, government or regulator advisories, and vendor disclosures only where they are the correct primary evidence for protocol, incident, or product-specific facts.
5. Build `SOURCE_LEDGER.md` and `THEME_MAP.md` so every likely section has supporting evidence before drafting begins.
6. If the topic is part of a broader project, update `/research-wiki` with the selected scope and key references.

### Phase 3 - Screening, verification, and evidence grading

1. Deduplicate sources and log screening decisions in `SCREENING_LOG.md`.
2. Verify metadata and DOI coverage with `/citation-management`.
3. For each retained source, record study type, dataset, benchmark conditions, threat model, limitations, and relevance to the review question in `EVIDENCE_MATRIX.md`.
4. For `systematic` reviews, produce reproducible counts and a PRISMA-style flow. For other review types, still provide transparent search dates, scope boundaries, and reasons for emphasis.
5. Remove weak or redundant sources that do not support core claims.

### Phase 4 - Synthesis design and comparison system

1. Run `/venue-templates` to calibrate IEM structure and formatting expectations before the outline is locked. If a strong sample review paper is available, compare against it here and adopt structural patterns rather than wording.
2. Run `/paper-plan` to design the section logic and argument spine.
3. Use `/scientific-writing` to sharpen the framing, the review thesis, and the paragraph-level logic.
4. Organise the paper by themes, taxonomies, failure modes, deployment lenses, or comparative questions rather than by one-paper-at-a-time summaries.
5. Build `COMPARISON_TABLES.md` so each table answers a specific question, such as architectures, datasets, metrics, threat classes, deployment costs, unresolved trade-offs, or representative study patterns. A review table does not need to enumerate every paper if a tighter representative table better supports the synthesis.
6. Run `/scientific-critical-thinking` to test whether themes are coherent, whether null results or contradictions have been buried, and whether the paper is overstating what the literature supports.

### Phase 5 - Figure and table system

1. Produce at minimum:
   - one search, screening, or workflow figure
   - one taxonomy, architecture, or challenge-map figure
   - one substantive comparison table
2. Use `/scientific-schematics`, `/paper-illustration`, `/paper-illustration-image2`, or `/mermaid-diagram` for taxonomy, PRISMA, or workflow figures. Use `/paper-illustration-image2` only when the local Codex native image bridge is available and a raster illustration is preferable to a deterministic vector figure.
3. Use `/paper-figure`, `/scientific-visualization`, `/matplotlib`, or `/seaborn` for quantitative comparison plots only when the metrics are truly comparable.
4. Do not generate fake pooled charts from inconsistent source settings.
5. Ensure every figure or table maps to a synthesis claim, not mere decoration.

### Phase 6 - Draft generation

1. Run `/paper-write` only after the earlier gates are satisfied.
2. Use `/scientific-writing` for sections that need sharper synthesis, better transitions, or more careful literature integration.
3. Keep the draft aligned to IEM formatting expectations: title, author block, abstract, keywords, list of abbreviations or notations when needed, numbered sections, required declaration blocks, references, and profiles.
4. In the Introduction, include an explicit numbered contribution list framed as review contributions, for example taxonomy, structured comparison, deployment interpretation, or future-work agenda.
5. Make the review method explicit and early.
6. Keep the prose precise, restrained, and citation-aware. Do not use filler or internal workflow language.

### Phase 7 - Multi-layer review loop

Run the review chain in this order. Fix issues between steps.

1. `/peer-review`
2. `/academic-paper-reviewer`
3. `/scientific-critical-thinking`
4. `/scholar-evaluation`
5. `/auto-paper-improvement-loop`
6. `/auto-review-loop`
7. `/auto-review-loop-llm` if the preferred review backend is unavailable
8. `/simple-english`
9. `/humanizer` on prose sections only: Abstract, Introduction, synthesis sections, Discussion, Conclusion

Rules:

- If reviewers say the review method is unclear, return to Phase 3 or Phase 4.
- If reviewers flag unsupported comparative claims, return to Phase 3 and re-check the evidence matrix.
- If reviewers flag structural weakness, return to Phase 4.
- Never let the humanizer touch equations, tables, figure labels, citations, units, or reference entries.

### Phase 8 - Citation, numeric, and integrity audit

1. Run `/citation-audit` with zero-context verification across the bibliography and surrounding claim contexts so wrong-context citations and metadata drift are caught before export.
2. Run `/citation-management` across all references:
   - verify title, authors, year, venue
   - verify DOI
   - remove uncited items
   - replace weak sources where stronger sources exist
   - ensure the primary source is cited for each dataset, standard, advisory, or benchmark claim
3. Verify every table entry and quoted number against the original source.
4. Ensure that standards or advisories are cited only for claims they actually support.
5. If the review performs original recomputation, pooled quantitative synthesis, or meta-analysis, run `/statistical-analysis` or `/paper-claim-audit` as appropriate and verify all derived numbers. Otherwise, state clearly that the paper is a structured synthesis rather than a pooled quantitative meta-analysis.
6. Confirm that the chosen review-type label remains honest after the final draft stabilises.

### Phase 9 - IEM template export and package assembly

1. Use TEMPLATE_DOCX_PATH as the final template anchor.
2. Use AUTHOR_AFFILIATIONS_PATH if author metadata needs structured mapping.
3. Export:
   - `<paper_slug>_IEM_WITH_AUTHORS.docx`
   - `<paper_slug>_IEM_WITHOUT_AUTHORS.docx`
4. Also assemble the working package: source manuscript markdown, figure sources, comparison tables, screening logs, audit reports, and final citation log.
5. Verify the named DOCX for full justification, correct caption order, stable maths and table formatting, final author metadata, explicit Times New Roman styling, superscript affiliation markers, heading alignment with the main text edge, standalone captions, visible table borders, and correct spacing around figures and tables.
6. Verify the anonymous DOCX for full justification, correct caption order, zero author-identifying leakage, explicit Times New Roman styling, correct heading alignment, standalone captions, visible table borders, correct spacing around figures and tables, and no accidental line numbering unless explicitly requested.

### Phase 10 - Final quality gate

Do not stop until this checklist passes or a hard blocker is explicitly recorded.

- Review question and scope are explicit.
- Review type is honestly labelled and matches the recorded method.
- Search and screening transparency are as strong as the claimed review type requires.
- Sources are metadata-verified and the citation audit is clean.
- Synthesis is thematic and comparative, not a catalogue of summaries.
- Cross-study tables compare like with like.
- Core claims are bounded and evidence-backed.
- The abstract is citation-free and concrete.
- UK English is consistent.
- No em dash or en dash remains.
- IEM formatting blocks are present.
- Named and anonymous outputs are both complete.
- No author-identifying data leaks into the anonymous version.
- No placeholder metadata, first-person narration, or internal workflow wording remains in exported paper-facing files.
- Figures and tables are publication quality.
- DOCX export preserves heading alignment, front-matter justification, superscript affiliations, line-numbering scope, caption separation, visible table borders, and spacing around display elements.
- Manifest, readiness notes, and audit files match the actual exported outputs.

## Fallback policy

- If `/deep-research` is unavailable, fall back to `/literature-review` plus the listed discovery skills, but record the reduced rigor.
- If a systematic review cannot be supported honestly, downgrade to `structured` rather than faking PRISMA discipline.
- If clean cross-study metric comparability is not available, use qualitative comparison tables instead of numeric ranking.
- If illustration backends are unavailable, redraw locally using `/scientific-visualization`, `/mermaid-diagram`, or `/matplotlib`.
- If DOCX export is imperfect, keep the source markdown, audit files, and export notes synchronized so the final manual pass is bounded and auditable.

## Final deliverables

1. `FINAL_READINESS_SUMMARY.md`
2. `RUN_LOG.md`
3. `SOURCE_LEDGER.md`
4. `SEARCH_PROTOCOL.md`
5. `SCREENING_LOG.md`
6. `EVIDENCE_MATRIX.md`
7. `THEME_MAP.md`
8. `COMPARISON_TABLES.md`
9. `NARRATIVE_REPORT.md`
10. `CITATION_AUDIT.md`
11. `PRISMA_FLOW.md` when applicable
12. `<paper_slug>_IEM_WITH_AUTHORS.docx`
13. `<paper_slug>_IEM_WITHOUT_AUTHORS.docx`
14. Any supporting figures, source tables, screening records, and review reports used to justify the final manuscript