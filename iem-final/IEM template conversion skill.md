---
name: iem-template-manuscript-conversion
description: Convert a supplied manuscript DOCX into a supplied IEM Journal template DOCX by editing a copy of the original template package in place. Preserve the template's genuine Word structure and visual system; transfer all manuscript content without summarising; repair captions, equations, references, profiles, photos, sections, and layout; then render every page to PDF/PNG and pass strict structural, content, formula, and visual quality gates before delivery.
version: 1.0
owner: Low Choon Keat
language: UK English
primary_output: DOCX
---

# IEM Template Manuscript Conversion Skill

## 1. Mission

Convert a manuscript into the supplied IEM Journal template by editing a **copy of the actual template file**. Never rebuild the journal format from a blank document and never merely imitate its appearance.

The deliverable must preserve the manuscript's full substantive content while reproducing the template's real Word structure, page mechanics, typography, first-page design, column layout, captions, references, equations, and author-profile presentation.

A conversion is complete only after all pages have been rendered and inspected and all mandatory gates in this file have passed.

## 2. Required Inputs

Minimum inputs:

1. `IEM Journal paper template.docx`
2. The manuscript DOCX to be converted

Conditional inputs:

3. An older manuscript DOCX containing verified author photographs or profile text
4. A published IEM sample PDF or page image for visual comparison
5. A response letter or editorial instructions, if supplied
6. Replacement profile photographs or verified biographies, if supplied

If several candidate files exist, explicitly identify:

- the authoritative IEM template;
- the authoritative manuscript;
- the source of each author photograph;
- the source of each biography, email address, ORCID, affiliation, and professional title.

Never infer which photograph belongs to which author from file order alone. Use explicit textual adjacency, user confirmation, or another verifiable mapping.

## 3. Non-Negotiable Rules

### 3.1 Actual-template rule

- Copy the supplied IEM template DOCX and use that copy as the output base.
- Edit the copied package directly.
- Preserve the template's styles, headers, footers, sections, page dimensions, margins, relationships, theme, numbering definitions, settings, and package structure unless a specific change is required.
- Do not create a new blank DOCX and recreate a similar-looking layout.
- Do not use the manuscript DOCX as the base and merely apply template-like formatting.

### 3.2 Content-integrity rule

- Transfer the manuscript's full content.
- Do not summarise, compress, paraphrase, or omit content unless explicitly requested.
- Preserve all numbers, citations, DOI strings, URLs, equations, commands, technical decisions, tables, figures, captions, author names, affiliations, acknowledgements, and contribution statements unless the user specifically instructs otherwise.
- Do not invent missing results, authorship contributions, biographies, email addresses, ORCID identifiers, affiliations, figures, captions, equations, evidence, or references.
- If a critical input is absent, report the limitation instead of fabricating it.

### 3.3 Formatting rule

- Follow the actual IEM template and supplied IEM sample, not generic journal-design preferences.
- Do not apply blanket bold, italics, underlining, colour, or heading styles.
- Ordinary prose must remain ordinary body text.
- Bold only genuine titles, headings, author names in profiles, table headings, and essential labels supported by the template.
- Captions are not automatically bold. Match the template exactly.

### 3.4 QA rule

A DOCX must not be delivered before it has been:

1. structurally audited;
2. rendered to PDF and page PNGs;
3. visually inspected page by page at readable zoom;
4. corrected and re-rendered after every layout-sensitive change;
5. checked for Word-opening warnings, field-update prompts, unreadable-content repair prompts, and package corruption.

## 4. Output Naming

Use a clear final name such as:

`<ManuscriptCode>_IEM_Template_Final.docx`

Do not label intermediate files as `Final`. Use names such as:

- `_working.docx`
- `_formula_QA.docx`
- `_profiles_QA.docx`
- `_references_QA.docx`

Deliver only the final DOCX unless the user asks for the QA PDF or other intermediates.

## 5. End-to-End Workflow

## Step 1: Inventory and fingerprint every input

For every DOCX:

- record filename and file size;
- count paragraphs, tables, sections, inline shapes, floating shapes, comments, tracked changes, footnotes, endnotes, hyperlinks, fields, equations, and media files;
- list section margins, page sizes, orientations, column counts, headers, and footers;
- list styles used in the first page, body, references, profiles, tables, captions, and equations;
- extract all media with dimensions and relationship locations;
- detect external relationships and automatic field-update settings;
- detect sample-manuscript residue in headers, footers, text boxes, shapes, tables, and document properties.

Create a source map before editing:

- Template-only elements to retain
- Template sample content to remove
- Manuscript content to transfer
- Manuscript media to transfer
- Older-file profile assets to reuse
- Unresolved information requiring explicit limitation

## Step 2: Render the untouched template and manuscript

Render both original files before editing.

Inspect:

- template first-page title and author treatment;
- abstract block and metadata panel;
- point at which the body becomes two columns;
- heading hierarchy;
- table and figure caption placement;
- equation alignment and numbering;
- reference indentation and numbering;
- profile heading bar, portrait size, biography arrangement, and column mode;
- header and footer placement;
- page-break and section-break behaviour.

Record the template's actual visual measurements. Do not trust text extraction alone.

## Step 3: Freeze the conversion specification

Before modifying the file, document the intended structure:

1. Full-width first-page title and author area
2. Full-width abstract and metadata arrangement
3. Continuous or next-page transition into the two-column article body
4. Two-column main text
5. Correctly placed tables, figures, equations, captions, references, acknowledgements, and author contributions
6. Full-width single-column Profiles section if the template uses that design

State any controlled exceptions before applying them.

## Step 4: Create the base copy

- Duplicate the actual template file.
- Never overwrite the user's original template.
- Remove only the template's sample manuscript content.
- Retain the template's package parts and structural components.
- Check text boxes, floating shapes, headers, footers, alternate content, and hidden or deleted text for residual sample material.

## Step 5: Replace the first-page content

### Title

- Use the template's title font, size, weight, alignment, and spacing.
- Do not enlarge the title because it looks visually prominent in another format.
- Preserve the exact manuscript title.

### Authors and affiliations

- Preserve author order and superscript affiliation markers.
- Preserve the corresponding-author marker.
- Use only verified affiliations and contact details.
- Match the template's restrained author treatment.

### Abstract

- Insert the full abstract without summarisation.
- Use full justification if the template sample uses full justification.
- Confirm that the final line is not artificially stretched.
- Preserve the template's abstract cell geometry and internal padding.
- Prevent crowding, clipping, and excessive type reduction.

### Metadata panel and keywords

- Preserve Received, Revised, Accepted, affiliation, corresponding-author, DOI, and keyword positions.
- Keep unresolved editorial fields blank or marked only as instructed.
- Do not invent dates or DOI values.
- Treat metadata and keyword tables as layout tables, not research tables. Do not assign them table numbers or captions.

## Step 6: Build the body in the template's real column structure

- Use the template's actual section mechanics.
- Keep title and abstract full width.
- Start the article body in two columns at the template-consistent location.
- Preserve the correct gutter, margins, line spacing, and body font.
- Do not accidentally place full-width objects inside a narrow column.
- Do not allow wide profile tables, wide equations, or wide tables to cross the column boundary.

For every section transition, inspect the underlying `w:sectPr`, `w:cols`, break type, and rendered result.

## Step 7: Transfer headings and body text

- Preserve the manuscript's logical section order.
- Match IEM heading typography and numbering.
- Do not promote explanatory sentences to headings.
- Do not create missing headings unless required to repair an obvious structural omission and doing so does not change meaning.
- Keep prose unbolded unless the source or template requires local emphasis.
- Preserve UK English.

## Step 8: Tables

For every table, determine whether it is:

1. a substantive research table;
2. a first-page layout table;
3. an author-contribution table;
4. a profile-layout table.

### Substantive table requirements

- Every substantive table must have exactly one caption.
- Use sequential numbering: Table 1, Table 2, Table 3, and so on.
- Place the caption in the template-prescribed position, normally above the table.
- Remove duplicate caption text and duplicate explanatory sentences such as repeated `Table 3.1` statements.
- Update all narrative references consistently.
- Do not number layout tables.
- Bold only the true header row and required row labels.
- Repeat header rows across pages when needed.
- Do not use fixed row heights that can clip text.
- Fit the table within the active column or deliberately switch to a full-width section if the template supports it.

### Table QA

Check:

- caption exists exactly once;
- numbering is continuous;
- no contradictory numbering remains;
- no table crosses a column or page boundary incorrectly;
- no text is clipped;
- no row splits awkwardly;
- no blanket bold remains;
- no citation-style footnote numbers are accidentally retained as ordinary characters.

## Step 9: Figures and media

- Transfer every real manuscript figure with its corresponding caption.
- Do not invent figures or figure captions when no figure exists.
- Do not treat logos, signatures, placeholders, blank images, duplicate images, equation screenshots, or decorative remnants as figures.
- Keep image and caption together where practical.
- Preserve image quality and aspect ratio.
- Audit floating and anchored objects because Word and LibreOffice may position them differently.

## Step 10: Equations and mathematical notation

### 10.1 Formula sufficiency gate

Do not add equations merely to make the article look technical. Include equations only where they define the method, scoring model, transformation, objective, constraint, or reproducibility logic.

For every formula, identify:

- target quantity;
- role: definition, identity, proposition, approximation, heuristic, objective, constraint, or interpretation;
- assumptions;
- symbols and units;
- domain and boundary conditions;
- coefficient source or status;
- edge cases;
- relation to later analysis or implementation.

### 10.2 Evidence and meaning

- Never describe a heuristic formula as a validated law.
- Label provisional weights, caps, thresholds, and cluster counts as assumptions unless empirical evidence supports them.
- Do not claim that coefficients come from CVSS or another framework unless the source genuinely supports that derivation.
- Preserve the distinction between a support index, probability, risk score, psychometric measurement, and prediction.
- Define zero-denominator, missing-data, no-exposure, constant-feature, clipping, saturation, and duplicate-event cases.

### 10.3 Native Word mathematics

- Displayed formulae must use editable native Office Math, not images and not raw LaTeX.
- Use valid OMML structures for fractions, subscripts, superscripts, delimiters, matrices/vectors, summations, norms, and accents.
- Inline variables in ordinary prose normally use ordinary Word text with italic variables and proper subscripts, unless the template explicitly uses inline native math.
- Do not use visible underscore notation such as `w_c` in final prose.
- Do not set invalid MathML/OMML property nesting.
- Validate the DOCX in Microsoft Word-compatible structure after every OOXML change.

### 10.4 Equation numbering

- Number displayed equations consecutively as `(1)`, `(2)`, `(3)`, and so on.
- Centre the equation and right-align its number within the active column, matching the template sample.
- Ensure every equation number exists exactly once as a formal number.
- Cross-references in prose must match the displayed number.
- Do not restart numbering mid-paper unless the template requires it.

### 10.5 Formula visual QA

- Compare before and after conversion.
- Print to PDF and inspect every equation page.
- Confirm no missing symbols, square placeholder glyphs, malformed subscripts, flattened fractions, clipped expressions, oversized inline math, or column overflow.
- Confirm formula font size is proportionate to the body text; do not make equations conspicuously larger.
- Confirm Word opens without an unreadable-content or repair warning.

## Step 11: References

Default IEM conversion used in this workflow:

- Keep main-text citations in their existing APA author-date form unless the user explicitly requests a citation-style conversion.
- Sort the reference list alphabetically by first author or organisational author.
- Prefix each reference with continuous bracketed numbering: `[1]`, `[2]`, `[3]`, and so on.
- Use hanging indentation matching the template sample.
- Preserve every reference's wording, year, title, source, volume, issue, pages, DOI, and URL.
- Do not silently add, delete, renumber internally cited works, or modify metadata.

Reference QA:

- alphabetical order verified programmatically;
- numbering continuous with no gaps or duplicates;
- reference count unchanged unless a justified reference correction was requested;
- main-text author-date citations unchanged;
- no sample-template references remain;
- no broken DOI or URL caused by editing;
- no accidental underlining or blanket bold.

## Step 12: Author contributions

- Retain only contributions that are verified by the authors or supplied source.
- Do not fabricate contribution roles merely to make entries different.
- If the user requests a bounded number of roles, enforce it exactly.
- In this workflow, each author should normally have one to three concise, distinct tasks.
- Avoid assigning every author the identical phrase `Manuscript review and final approval`.
- Bold author names only if the template supports it; contribution text remains regular.
- Use consistent contribution terminology, preferably CRediT-aligned wording where truthful.

## Step 13: Author profiles

### 13.1 Template visual

Match the actual IEM profile design:

- start Profiles on a new page if needed;
- switch the Profiles section to one full-width column;
- retain the preceding article and references in two columns;
- use a full-width grey banner;
- centre `PROFILES` in white bold text;
- place a compact portrait on the left;
- place the biography in the wide right area;
- use a borderless layout table;
- keep the author name bold at the start of the biography;
- keep the remaining profile text regular;
- include email and ORCID on separate lines when verified;
- prevent each photo-biography row from splitting across pages.

### 13.2 Identity and source gate

For every profile, maintain a mapping record:

- author name;
- photo source filename;
- photo relationship or extracted media name;
- biography source;
- email source;
- ORCID source;
- verified spelling.

Never assume that `image1.jpg` belongs to the first author. Media numbering reflects package insertion order, not author identity.

If the user supplies profile screenshots, use the screenshots only as evidence for layout, text, or photo identity. Extract a portrait from a screenshot only when no original portrait file exists and the crop can be made without including neighbouring text or other content.

### 13.3 Profile QA

- all author-photo mappings verified;
- all portraits have correct aspect ratio;
- no portrait is assigned to the wrong author;
- no profile table crosses a two-column boundary;
- grey heading bar spans the full text width;
- biography text is not clipped;
- no invented title, degree, affiliation, email, ORCID, or research interest;
- spelling of author names is consistent across title page, contribution table, references, and profiles.

## Step 14: Remove Word warning triggers

Audit and remove only genuinely unused or inappropriate inherited items:

- `w:updateFields` when it causes an unnecessary external-field prompt;
- `w:updateLinks` when not required;
- unused external relationships inherited from the template sample;
- sample hyperlinks, mailto links, and attached-template references;
- stale INCLUDETEXT, INCLUDEPICTURE, DDE, LINK, or other external field instructions.

Do not remove valid manuscript hyperlinks or fields simply to silence a warning. Determine whether each relationship is used before removal.

After the fix, verify:

- Word does not ask to update fields referring to another file;
- Word does not report unreadable content;
- equations remain editable;
- hyperlinks that should remain still work;
- the document archive is valid.

## Step 15: Sample-residue removal

Search all package parts, not only normal paragraphs, for:

- sample title;
- sample author names;
- sample affiliations;
- sample profile text and photograph;
- sample references;
- sample equations and figures;
- sample headers and footers;
- sample email addresses;
- sample hyperlinks;
- `CONFIDENTIAL` or other sample labels;
- hidden, deleted, tracked, or alternate-content sample text.

A final document containing any unintended sample residue fails.

## 6. Mandatory Quality Gates

## Gate A: Base-file authenticity

PASS only if:

- output was created from a copy of the supplied IEM template;
- retained package components can be traced to that template;
- the document was not recreated from blank;
- original user files remain untouched.

## Gate B: Content completeness

PASS only if:

- every required manuscript section is present;
- all tables, figures, equations, references, acknowledgements, author contributions, and profiles are accounted for;
- no substantive content was summarised or omitted;
- no content was invented.

## Gate C: First-page fidelity

PASS only if:

- title and authors match the template's restrained treatment;
- abstract and metadata fit cleanly;
- abstract justification matches the sample;
- keyword layout is correct;
- no text is overcrowded or clipped;
- the transition to two columns is correct.

## Gate D: Typography and emphasis

PASS only if:

- ordinary prose is not blanket-bold;
- headings follow the genuine hierarchy;
- captions follow template styling;
- tables do not contain indiscriminate bold text;
- equation size is proportionate;
- profile names are bold but biographies are regular.

## Gate E: Tables and figures

PASS only if:

- every substantive table and figure has exactly one correct caption;
- numbering is continuous;
- narrative references match;
- layout tables are not numbered;
- no object overflows its column;
- no duplicate caption or explanatory line remains.

## Gate F: Mathematics

PASS only if:

- all displayed formulas are valid editable native Word equations;
- inline notation follows the intended prose style;
- all symbols are defined;
- assumptions and edge cases are stated;
- coefficients and thresholds are traceable or explicitly provisional;
- equation numbering is continuous and correctly aligned;
- displayed and inline mathematics survives PDF rendering;
- Microsoft Word opens without repair warnings.

## Gate G: References

PASS only if:

- reference list is alphabetically sorted;
- bracket numbering is continuous;
- hanging indentation matches the template;
- main text remains APA author-date where instructed;
- reference metadata is unchanged;
- sample references are absent.

## Gate H: Profiles

PASS only if:

- Profiles is a full-width single-column section where required;
- the grey banner visually matches the template;
- portraits and biographies are compact and aligned;
- every portrait-to-author mapping is verified;
- profile text, email, ORCID, degree, affiliation, and title are evidence-based;
- no profile row is clipped or split badly.

## Gate I: Word compatibility and package integrity

PASS only if:

- `unzip -t` reports no package error;
- all XML parts parse;
- relationships resolve;
- no unreadable-content warning appears;
- no unnecessary external-field update prompt appears;
- no raw LaTeX remains;
- no placeholder glyphs appear in the rendered PDF;
- page count is plausible and no abnormal blank page exists.

## Gate J: Full visual inspection

PASS only if every rendered page has been examined for:

- clipping;
- overlap;
- missing glyphs;
- broken tables;
- formula defects;
- incorrect columns;
- oversized content;
- header/footer displacement;
- awkward page breaks;
- profile overflow;
- duplicate content;
- sample residue;
- unexplained blank areas.

A spot check is insufficient.

## 7. Known Failure Modes and Required Corrections

These failures occurred in prior conversions and must be actively prevented.

### Failure 1: Using the manuscript as the base

Symptom: The output looks similar to IEM but preserves the manuscript's original sections and formatting.

Correction: Start again from a copied IEM template package.

### Failure 2: Treating visual resemblance as template compliance

Symptom: Oversized title, crowded abstract, incorrect spacing, or non-template fonts.

Correction: Render the untouched template and measure the actual presentation before editing.

### Failure 3: Blanket bold formatting

Symptom: Body paragraphs, table contents, captions, or profiles appear uniformly bold.

Correction: Remove direct bold formatting except from genuine semantic elements.

### Failure 4: Duplicate or wrong table captions

Symptom: `Table 3.1` appears twice while the table should be `Table 1`.

Correction: Audit captions and narrative references as one numbering system; ensure exactly one caption.

### Failure 5: Missing mathematical symbols

Symptom: Definition lines begin with `=` because the source symbols were stored as unsupported equation objects or lost during conversion.

Correction: Inspect source OOXML, reconstruct every missing symbol, and verify both XML and rendered pages.

### Failure 6: Fake or flattened native equations

Symptom: Equations are technically inside Office Math but behave like flat text, show malformed subscripts, or render poorly.

Correction: Use correct OMML structures for every mathematical construct and validate in Word-compatible OOXML.

### Failure 7: Invalid OMML font-size properties

Symptom: Microsoft Word reports unreadable content and offers to repair the file.

Correction: Place `w:rPr` in the correct direct position under `m:r`; never insert unsupported nested control properties.

### Failure 8: Oversized inline mathematics

Symptom: Inline variables increase line height and look larger than body text.

Correction: Use ordinary Word text with italic variables and proper subscripts in prose; reserve native Office Math for displayed equations unless the template requires otherwise.

### Failure 9: Missing equation numbers

Symptom: Formulas appear without `(1)`, `(2)`, and `(3)` although the template sample numbers them.

Correction: Centre equations, right-align numbers, and audit the sequence.

### Failure 10: Formula section lacks conceptual coherence

Symptom: Counts are compared despite unequal exposure; no zero-exposure rule; coefficients appear validated without evidence; K is declared without evaluation conditions.

Correction: Freeze the target quantity, define assumptions, normalise exposure, specify boundary cases, state provisional parameters, and include only justified objective/normalisation formulas.

### Failure 11: External-field warning

Symptom: Word asks whether to update fields referring to another file.

Correction: Audit inherited update settings and unused external relationships; remove only unused triggers; revalidate all hyperlinks and fields.

### Failure 12: References in reverse alphabetical order

Symptom: References begin with Z and end with A.

Correction: Sort programmatically A to Z, then add continuous bracket numbers and preserve main-text APA citations.

### Failure 13: Profiles remain inside a two-column section

Symptom: Biography text is clipped at the column boundary and a wide invisible table extends beyond the column.

Correction: Insert a section break and make the Profiles page one full-width column while preserving the preceding two-column body.

### Failure 14: Incorrect profile banner

Symptom: `PROFILES` appears as ordinary black text instead of the template's grey band with centred white text.

Correction: Reproduce the template's actual banner geometry, fill, alignment, and typography.

### Failure 15: Wrong author-photo mapping

Symptom: One author's biography is paired with another author's photograph.

Correction: Maintain a verified mapping register; never infer identity from media filenames or order.

### Failure 16: Invented profile information

Symptom: A short affiliation is expanded into an unsupported biography, title, email, ORCID, or research-interest list.

Correction: Use only supplied or verified profile information; leave unavailable fields omitted.

### Failure 17: Unchecked PDF rendering

Symptom: XML checks pass, but visual output contains clipping, placeholder glyphs, or overflow.

Correction: Render after every layout-sensitive or equation-sensitive change and inspect all pages.

## 8. Programmatic Audit Checklist

Before delivery, produce an internal report containing at least:

- base template filename and checksum;
- output filename;
- page count;
- section count and column count per section;
- table count;
- substantive table-caption list;
- figure-caption list;
- equation count and numbering list;
- native Office Math object count;
- reference count and first/last entries;
- profile count;
- author-photo mapping list;
- external relationship count;
- field instruction count;
- updateFields/updateLinks count;
- raw LaTeX occurrence count;
- sample-residue search results;
- package-integrity result;
- rendered-page inspection status for every page.

## 9. Final Delivery Summary

When returning the final DOCX, provide only a short factual summary:

- actual IEM template used as base;
- manuscript content transferred without summarisation;
- key formatting repairs;
- table/figure caption actions;
- formula actions and equation count;
- reference actions and reference count;
- profile/photo actions;
- page count;
- Word-compatibility and render-QA result;
- any unresolved evidence or author-owned information still needing verification.

Do not claim PASS if any mandatory gate lacks evidence.

## 10. Reusable Execution Prompt

Use the following prompt with this skill:

```text
Convert the attached manuscript DOCX into the attached IEM Journal template DOCX.

Use the IEM template as the actual base file. Edit a copy of that template directly. Do not recreate or imitate the format from a blank DOCX, and do not use the manuscript as the base.

Transfer all manuscript content without summarising, compressing, omitting, or inventing material. Preserve numbers, citations, references, tables, figures, formulas, technical decisions, author order, affiliations, and meaning.

Follow every requirement and mandatory quality gate in IEM_TEMPLATE_MANUSCRIPT_CONVERSION_SKILL.md. In particular:
- preserve the template's real styles, headers, footers, sections, page setup, first-page abstract arrangement, and two-column body;
- prevent blanket bold formatting;
- repair substantive table and figure captions and numbering;
- keep layout tables unnumbered;
- use valid editable native Word equations for displayed formulas;
- use ordinary formatted text for inline variables unless the template requires inline native math;
- number displayed equations consecutively and match the sample alignment;
- keep main-text APA author-date citations unchanged;
- alphabetise the reference list and add continuous bracket numbers;
- create the Profiles section in the template's full-width grey-banner format;
- use only verified author-photo mappings and verified profile information;
- remove sample-template residue and unnecessary external-field warning triggers;
- print to PDF, render every page to PNG, inspect every page, correct defects, and repeat until every gate passes.

Return only the final DOCX plus a concise QA summary. Do not report completion if any mandatory gate is unverified.
```

## 11. Completion Standard

The task is successful only when the document is simultaneously:

- derived from the real template;
- substantively complete;
- visually faithful;
- mathematically coherent;
- citation and reference consistent;
- profile and photograph accurate;
- free from sample residue;
- free from Word warnings;
- structurally valid;
- clean on every rendered page.

Anything less is an intermediate draft, not a final conversion.
