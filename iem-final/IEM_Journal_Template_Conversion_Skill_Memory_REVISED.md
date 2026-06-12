## IEM Journal Template Conversion Skill / Memory File

**Purpose:** Use this file as a reusable instruction set for converting a manuscript/paper into the final IEM Journal format by copying the manuscript content into the uploaded **IEM Journal paper template.docx**, while visually matching the supplied IEM template/sample.

**Primary rule:** Use the uploaded **IEM Journal paper template.docx** as the document base. Do **not** create a document layout from scratch. The completed DOCX may be saved as a separate output copy for safety, but all formatting, sections, headers, styles, margins, page setup, and layout must be inherited from the uploaded IEM template wherever possible.

---

## Required and Optional Input Files

### Required files
- **Paper/manuscript DOCX**  
  Example: `AI_Driven_Parking_Violation_Detection_IEM_WITH_AUTHORS.docx`
- **IEM Word template**  
  `IEM Journal paper template.docx`
- **This conversion instruction/memory MD file**, if available

### Optional but useful files
- **IEM sample/review paper PDF**, if a separate visual reference is available.
- **Author Contributions and Profile.docx**, if author biographies, emails, ORCID IDs, contribution statements, or profile photos are required.
- Screenshots from the user showing specific table/header/profile formatting.

---

## High-Level Task

Generate a final DOCX that looks like the IEM Journal template/sample, not merely a text transfer.

The agent must:
- Use **IEM Journal paper template.docx** as the layout base.
- Copy the manuscript content into the template.
- Treat existing article text in the template as sample content unless it is part of the reusable template structure.
- Preserve the journal-like visual structure:
  - first-page title/author/affiliation/abstract/keywords layout,
  - two-column body text where appropriate,
  - full-width tables/figures where needed,
  - IEM-style running headers,
  - IEM-style table formatting,
  - IEM-style author profiles.
- Reuse existing Word styles, paragraph styles, table styles, section settings, margins, headers, footers, and page setup from the IEM template wherever possible.
- Avoid recreating formatting manually unless the template style cannot be reused.
- Validate the completed DOCX before returning it.

### Content fidelity rule
Do **not** rewrite, summarise, paraphrase, or academically edit the manuscript content unless the user explicitly requests it. The primary task is formatting and template conversion. Only correct obvious formatting artefacts caused by extraction or transfer.

---

## Critical Lessons Learned / Mistakes to Avoid

### 1. Use the IEM template as the base, not a newly designed file

The uploaded IEM template may contain a complete sample article, not only blank placeholders. Treat all existing article text as replaceable sample content unless it is part of the reusable template structure, such as headers, margins, section layout, table styling, profile layout, or page setup.

Implementation guideline:
- Open the uploaded IEM Journal paper template as the base document.
- Preserve template page setup, margins, section layout, headers/footers, styles, and visual structure.
- Replace the sample article content with the manuscript content.
- Do **not** recreate the document from scratch.
- Save the completed document as a separate output copy to avoid overwriting the user's original uploaded template.

### 2. Do not leave original template metadata or affiliation text

The original template may contain unrelated author affiliation text such as:

```text
1,2 Department of Mechanical Engineering, Ahmadu Bello University, Zaria, Nigeria.
3 Department of Civil Engineering Camarines Norte State College, Dae, Philippine.
*Corresponding author:
chidieberehyg@gmail.com
DOI: https://doi.org/10.54552
```

This must be replaced with the actual manuscript author affiliation/corresponding-author/DOI information.

Checklist:
- Search the final DOCX text for unrelated old template text.
- Confirm old affiliations, old emails, and old DOI values are not present.
- Confirm actual author affiliations appear before Abstract.

### 3. Author line must use superscripts

Do not leave author markers as baseline text. For example, do not leave:

```text
Low Choon Keat1*, Yap Li Ying1, Tan Bee Sian1, Phoon Gar Chi2, and Chong Kim Soon3
```

The markers must be superscripted in Word runs:

```text
Low Choon Keat¹*, Yap Li Ying¹, Tan Bee Sian¹, Phoon Gar Chi², and Chong Kim Soon³
```

Implementation guideline:
- Rebuild the author byline paragraph run-by-run.
- Author names are normal runs.
- Affiliation markers and corresponding-author asterisks are superscript runs.
- Preserve the paragraph font/style from the template.

Validation:
- Programmatically inspect the author paragraph runs.
- Confirm superscript runs include all required affiliation markers and corresponding-author markers.

### 4. Only include the actual manuscript authors

Do not include extra names from supplementary profile files unless the paper author line includes them.

Validation:
- Search the final DOCX for non-author names.
- If non-author names appear in profile/contribution sections, remove them unless explicitly requested.

### 5. Author Contributions must follow author order

The Author Contributions section must follow the same order as the author byline.

Validation:
- Extract text between `AUTHOR CONTRIBUTIONS` and `ACKNOWLEDGEMENTS` or the next major heading.
- Confirm author names appear in the same order as the paper author line.
- Confirm no placeholder text such as `[contribution details to be completed]` remains unless the user intentionally requested placeholders.

### 6. Table format must match the sample/template screenshot

The correct IEM-style table format is:
- Caption centered above table.
- Caption italic.
- Full outer border.
- Full internal vertical and horizontal gridlines.
- Header row grey shading.
- Header text bold and centered.
- Body text centered unless source formatting requires otherwise.
- Table must stay inside the page box.
- Wide tables should become full-width sections, then return to two-column body layout after the table.

Do not use horizontal-rule-only academic table style unless the IEM template/sample explicitly uses that style for the relevant table.

Validation:
- Every table should have grid borders: top, bottom, left, right, insideH, insideV.
- Header row should have grey shading, e.g. `D9D9D9`.
- Captions should appear above tables, centered and italic.
- Table count should match the source unless a deliberate change is documented.

### 7. Figures must preserve source content and fit the IEM layout

Figure handling:
- Keep figures inside page/column width.
- Center figures.
- Preserve figure order and numbering.
- Keep captions close to the relevant figure.
- Do not accidentally convert figure captions into body paragraphs.
- Use full-width sections for wide figures where needed, then return to two-column layout.

Validation:
- Image count should match the source unless a deliberate change is documented.
- Figures should not overflow margins.
- Captions should remain readable and correctly numbered.

### 8. Equation handling

Preserve equations carefully.

Guidelines:
- Preserve equations as editable Word equations if possible.
- If equations cannot be preserved as editable objects, keep them visually accurate.
- Maintain equation numbering and cross-references.
- Check that subscripts, superscripts, Greek symbols, mathematical operators, and special characters are not corrupted.

Validation:
- Compare equation count and numbering against the source manuscript.
- Inspect key equations visually if possible.
- Confirm equation cross-references remain meaningful.

### 9. References

Reference handling:
- Preserve all references from the manuscript.
- Do not invent, remove, or reorder references unless explicitly requested.
- Keep citation numbering or author-year style consistent with the manuscript and IEM requirement.
- Verify that every in-text citation has a corresponding reference entry where possible.
- Verify that reference entries do not contain broken line spacing, missing punctuation, or accidental template references.

Validation:
- Confirm old template references are removed unless intentionally retained.
- Confirm the source manuscript reference list is present.
- Check that reference formatting is consistent across entries.

### 10. Profiles section must match the sample/template visual

The correct profile section formatting is:
- Full-width section.
- Author names line above profile block if template/sample shows it.
- Horizontal rule above/below as in the sample.
- Dark grey `PROFILES` bar with white bold text.
- Each profile row has:
  - photo/profile image or placeholder on the left,
  - biography text on the right,
  - author name bold uppercase at the start,
  - email address on its own line,
  - ORCID line if available.

For missing profile images, use a photo placeholder. Do not invent personal degrees, roles, awards, emails, or ORCID IDs unless provided.

Validation:
- Profiles should include only actual paper authors unless explicitly requested.
- Profile order should follow author order.
- No non-author profile should remain from old template/sample content.

### 11. Running headers must match the IEM visual style

The template/sample running header has:
- grey uppercase header text,
- thin grey horizontal rule underneath,
- small corner/bracket-style marks at left and right,
- no running header on the first page.

Important:
- The first page should have no running header.
- Later pages may use title header or author header depending on odd/even/template behavior.
- Do not put the same author header on every page if the original template alternates title/author headers.
- The visual style matters, not only the text.

Recommended implementation:
- Enable odd/even headers if needed.
- First-page header is blank.
- Primary/odd header can use paper title left-aligned.
- Even header can use author names right-aligned.
- Use grey text and grey horizontal rule.
- Use a small table in the header to emulate the corner marks if direct shape editing is difficult.

Example title header:

```text
PARKING VIOLATION DETECTION: VISION, LICENCE PLATES AND EDGE-CLOUD ENFORCEMENT
```

Example author header:

```text
LOW CHOON KEAT, YAP LI YING, TAN BEE SIAN, PHOON GAR CHI,
CHONG KIM SOON
```

### 12. Do not overwrite user's manual fixes unnecessarily

If the user says “I fixed it myself already”, apply only the requested small change.

Example:
- If user says “put back the superscripts”, only restore author-line superscripts.
- Do not alter affiliations, contributions, profiles, or layout unless asked.

---

## Source Content Integrity Checks

Before returning the final file, confirm:
- All source paper sections are transferred.
- No source section heading is missing.
- Abstract, keywords, references, acknowledgements, author contributions, and profiles are transferred if present.
- Table and figure numbering remains consistent.
- In-text citations still correspond to the reference list where possible.
- Equations, symbols, subscripts, superscripts, and special characters are preserved.
- No source body text is accidentally omitted because of section breaks, tables, figures, or profile formatting.

---

## Recommended Automated Workflow

### Step 1: Load files
- Load the paper DOCX.
- Load `IEM Journal paper template.docx`.
- Load this memory/instruction MD file if supplied.
- Optionally use the IEM sample/review paper PDF as visual reference.
- If supplied, load author profile/contribution files.

### Step 2: Extract paper content

Extract:
- Title
- Author line
- Affiliations
- Corresponding author information
- DOI, if available
- Abstract
- Keywords
- Main body sections
- Figures and captions
- Tables and captions
- Equations and equation numbers
- End sections:
  - Author Contributions
  - Acknowledgements
  - Data Availability
  - Conflicts of Interest
  - References
  - Profiles

### Step 3: Use IEM template as the base
- Open the uploaded `IEM Journal paper template.docx` as the base document.
- Preserve the template’s page setup, margins, section layout, headers/footers, styles, and visual structure.
- Replace the sample article content with the manuscript content.
- Do not recreate the document from scratch.
- Save the completed document as an output copy to avoid overwriting the user’s original uploaded template.

### Step 4: Apply IEM layout
- First page: preserve IEM template structure.
- Body: two-column layout where appropriate.
- Tables/figures: use full-width sections where needed.
- After each full-width table/figure, return to two-column body layout.

### Step 5: Format tables

Apply:
- centered italic caption above table,
- full grid borders,
- grey header row,
- centered cell text unless source format requires otherwise,
- table width inside page boundaries.

### Step 6: Format figures
- Keep figures inside page/column width.
- Center figures.
- Figure captions should match sample style.
- Ensure figure captions are not accidentally converted to body paragraphs.

### Step 7: Format equations
- Preserve editable equations when possible.
- Preserve equation numbering.
- Ensure mathematical notation remains visually correct.

### Step 8: Format references
- Transfer all source references.
- Remove old template references.
- Keep citation style consistent.
- Check line breaks and spacing.

### Step 9: Format author profiles
- Full-width profile section.
- Grey `PROFILES` bar.
- Photo/placeholder left, biography right.
- Only actual listed authors.
- Use profile order that matches author order.

### Step 10: Running headers
- First page blank header.
- Later pages follow template/sample style.
- Grey text + horizontal rule + corner marks.

### Step 11: Final validation

Run the validation checklist below before returning the file.

---

## Final Validation Checklist

### Text checks
- No old template affiliations remain.
- No unrelated old template email remains.
- No old DOI remains unless intended.
- All paper authors are present.
- No non-paper authors are included.
- No `[to be completed]` remains unless intentionally left for unknown email/profile information.
- No `[contribution details to be completed]` remains.

### Source content checks
- All source paper sections are present.
- Abstract, keywords, references, acknowledgements, author contributions, and profiles are present if they exist in the source.
- No source heading or body section is missing.
- In-text citations and reference entries remain consistent where possible.

### Author byline checks
- Superscripts are applied to all affiliation markers.
- Corresponding-author asterisk is superscripted with the affiliation marker.

### Contribution checks
- Author contribution order matches paper author order.

### Table checks
- Table count matches source unless deliberately changed.
- Captions exist above tables.
- Header shading exists.
- Full grid borders exist.
- Tables do not overflow page margins.

### Image/figure checks
- Image count matches source unless deliberately changed.
- Figures are within page/column width.
- Captions are close to their figures and correctly numbered.

### Equation checks
- Equation count and numbering are preserved where possible.
- Subscripts, superscripts, Greek letters, and mathematical operators are not corrupted.
- Equation references remain meaningful.

### Reference checks
- Old template references are removed unless intentionally retained.
- Source manuscript references are present.
- Reference style is consistent.
- Broken line spacing or missing punctuation is fixed where caused by conversion.

### Header checks
- First page header is blank.
- Later page headers contain correct title/author text.
- Header visual resembles sample: grey text, rule, corner marks.

### Profile checks
- Profiles include only actual manuscript authors unless the user requested otherwise.
- Profile order follows author order.
- Missing photos use placeholders.
- No invented degrees, roles, awards, emails, or ORCID IDs are added.

### DOCX integrity check
- Test DOCX as ZIP archive.
- Open with `python-docx` to ensure no corruption.

### Unresolved item report
In the final response, mention any unresolved items, such as:
- missing author emails,
- missing profile photos,
- missing ORCID IDs,
- unresolved DOI,
- low-resolution figures,
- equations that could not be preserved as editable objects,
- any source formatting that could not be fully reproduced.

---

## Python Implementation Notes

When generating files programmatically:
- Use `python-docx` for DOCX editing.
- Use the uploaded IEM template as the base document.
- Use section breaks for one-column/two-column switching.
- Use Word XML (`w:cols`) to control columns.
- Use Word XML table borders for gridline tables.
- Use Word XML cell shading for grey header row.
- Use run-level formatting for superscripts.
- Save output in the working directory.
- Validate using `zipfile.ZipFile(...).testzip()`.
- Do not rely only on `doc.paragraphs`; also inspect tables, headers, footers, text boxes if accessible, and section-level content.

---

## Common Bug Fixes

### Bug: Inserted paragraphs appear in reverse order

When using `paragraph._p.addprevious(new_element)` repeatedly before the same anchor paragraph:
- If inserting in a loop, be careful with order.
- Verify final order by reading back the generated document.
- Always validate the final extracted block.

### Bug: Header text appears in body text extraction

Running header text may not show in `doc.paragraphs` because it is in section headers. Validate headers separately:

```python
for section in doc.sections:
    section.header.paragraphs
    section.even_page_header.paragraphs
    section.first_page_header.paragraphs
```

If header uses tables, inspect `section.header.tables` too.

### Bug: Profile text inside tables is not found in `doc.paragraphs`

Profiles may be in table cells. Validate by iterating through all tables and all cells.

### Bug: Activity limit or workspace reset

If the tool workspace does not contain the latest generated file:
- Ask the user to upload the latest DOCX.
- Do not rebuild from an older file unless the user confirms.

---

## Project-Specific Memory: Parking-Violation Paper Only

The following details apply **only** when the source manuscript is the parking-violation paper. For any new manuscript, extract author information from the uploaded paper and do not reuse these details automatically.

### Parking-violation paper affiliations

Use:

```text
1 Department of Information and Communication Technology, Faculty of Computing and Information Technology, Tunku Abdul Rahman University of Management and Technology, 53300 Kuala Lumpur, Malaysia
2 Department of Creative Industries, Faculty of Communication and Creative Industries, Tunku Abdul Rahman University of Management and Technology, 53300 Kuala Lumpur, Malaysia
3 Department of Electrical and Electronic Engineering, UCSI University, Kuala Lumpur, Malaysia
*Corresponding author:
lowck@tarc.edu.my
DOI: [to be assigned]
```

### Parking-violation paper authors

Only include these authors:

```text
Low Choon Keat¹*, Yap Li Ying¹, Tan Bee Sian¹, Phoon Gar Chi², and Chong Kim Soon³
```

Do not include the following names as authors/profiles/contributors unless explicitly listed in the paper:

```text
Lim Fung Ji
Voo Nyuk Mee
Loo Bee Wah
Pua Bee Lian
Ting Tin Tin
```

### Parking-violation paper Author Contributions order

Correct order:

```text
AUTHOR CONTRIBUTIONS
Low Choon Keat: Conceptualisation, study design, supervision, literature synthesis, manuscript drafting, and critical revision.
Yap Li Ying: Literature search, source screening, evidence extraction, manuscript drafting, and review support.
Tan Bee Sian: Data validation, visualisation, formal analysis, manuscript review, and editing.
Phoon Gar Chi: Literature review, writing—review and editing, visual-content review, and critical revision.
Chong Kim Soon: Technical review, edge-cloud architecture review, validation of engineering interpretation, manuscript review, and editing.
ACKNOWLEDGEMENTS
```

Do not reverse this order.

### Parking-violation paper profile list

Profiles should include only:
- Low Choon Keat
- Yap Li Ying
- Tan Bee Sian
- Phoon Gar Chi
- Chong Kim Soon

#### Yap Li Ying profile filler

If Yap Li Ying has only affiliation information and no full biography, use a conservative affiliation-based profile:

```text
YAP LI YING is affiliated with the Department of Information and Communication Technology, Faculty of Computing and Information Technology, Tunku Abdul Rahman University of Management and Technology (TAR UMT), Malaysia. Her academic and research interests are aligned with information and communication technology, intelligent systems, computer vision applications, and AI-driven smart-city solutions, including parking-violation detection and enforcement-support workflows.
Email address: [to be completed]
```

Do not invent personal degrees, roles, awards, or ORCID unless provided.

---

## Final Deliverable Naming Convention

Use incremental names such as:

```text
IEM_Template_Manuscript_FINAL.docx
```

or detailed names during iterations:

```text
IEM_Template_Manuscript_vXX_FINAL_IEM_FORMATTED.docx
```

The final answer should include:
- Download link.
- Short summary of changes.
- Validation checklist results.
- Any unresolved items or assumptions.

---

## Minimal Prompt for Future Agent

Use this exact prompt in a future session:

```text
Please convert my paper into the IEM Journal template. I uploaded:
1. the paper DOCX,
2. IEM Journal paper template.docx,
3. this IEM conversion skill/memory file,
4. optional sample/review PDF or author profile/contribution files if available.
Use the uploaded Word template as the layout base and copy my paper content into it. Do not recreate the document from scratch. Match the visual style of the template/sample, including first page, author superscripts, affiliations, table style, figure style, equations, references, running headers, author contributions, and profiles. Follow the validation checklist in the skill file before returning the final DOCX.
```
