# IEM Journal Template Conversion Skill / Memory File

**Purpose:** Use this file as the reusable instruction set for converting a manuscript/paper into the final IEM Journal format by copying the paper content into `IEM Journal paper template.docx`, while visually matching the supplied IEM template/sample.

## Required Input Files

The user should upload exactly these core files:

1. **Paper/manuscript DOCX**  
   Example: `AI_Driven_Parking_Violation_Detection_IEM_WITH_AUTHORS.docx`
2. **IEM Word template**  
   `IEM Journal paper template.docx`
3. **IEM sample/review paper PDF**  
   `IEM journal review paper.pdf`

Optional but useful:

4. **Author Contributions and Profile.docx** if author biographies, emails, ORCID IDs, contribution statements, or profile photos are required.
5. Screenshots from the user showing specific table/header/profile formatting.

---

# High-Level Task

Generate a final DOCX that looks like the IEM Journal template/sample, not merely a text transfer.

The agent must:

1. Use `IEM Journal paper template.docx` as the layout base.
2. Copy the manuscript content into the template.
3. Preserve the journal-like visual structure:
   - first page title/author/affiliation/abstract/keywords layout,
   - two-column body text where appropriate,
   - full-width tables/figures where needed,
   - IEM-style running headers,
   - IEM-style table formatting,
   - IEM-style author profiles.
4. Validate the generated DOCX before returning it.

---

# Critical Lessons Learned / Mistakes to Avoid

## 1. Do not leave original template metadata or affiliation text

The original template may contain unrelated author affiliation text such as:

```text
1,2 Department of Mechanical Engineering, Ahmadu Bello University, Zaria, Nigeria.
3 Department of Civil Engineering Camarines Norte State College, Dae, Philippine.
*Corresponding author:
chidieberehyg@gmail.com
DOI: https://doi.org/10.54552
```

This must be replaced with the actual manuscript author affiliation/corresponding-author/DOI information.

For the parking-violation paper, use:

```text
1 Department of Information and Communication Technology, Faculty of Computing and Information Technology, Tunku Abdul Rahman University of Management and Technology, 53300 Kuala Lumpur, Malaysia

2 Department of Creative Industries, Faculty of Communication and Creative Industries, Tunku Abdul Rahman University of Management and Technology, 53300 Kuala Lumpur, Malaysia

3 Department of Electrical and Electronic Engineering, UCSI University, Kuala Lumpur, Malaysia

*Corresponding author:
lowck@tarc.edu.my

DOI: [to be assigned]
```

Checklist:

- Search the final DOCX text for unrelated old template text.
- Confirm old affiliations, old email, and old DOI are not present.
- Confirm actual author affiliations appear before `Abstract`.

---

## 2. Author line must use superscripts

Do not leave author markers as baseline text:

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
- `1*`, `1`, `1`, `2`, and `3` are superscript runs.
- Preserve the paragraph font/style from the template.

Validation:

- Programmatically inspect the author paragraph runs.
- Confirm superscript runs include: `1*`, `1`, `1`, `2`, `3`.

---

## 3. Only include the actual manuscript authors

For the parking-violation manuscript, the only authors are:

```text
Low Choon Keat¹*, Yap Li Ying¹, Tan Bee Sian¹, Phoon Gar Chi², and Chong Kim Soon³
```

Do not include extra names from supplementary profile files unless the paper author line includes them.

Names that were mistakenly included before and must not appear as authors/profiles/contributions unless explicitly listed in the paper:

```text
Lim Fung Ji
Voo Nyuk Mee
Loo Bee Wah
Pua Bee Lian
Ting Tin Tin
```

Validation:

- Search the final DOCX for non-author names.
- If non-author names appear in profile/contribution sections, remove them.

---

## 4. Author Contributions must follow author order

The Author Contributions section must follow the same order as the author byline.

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

Do not reverse this order. A previous wrong order was:

```text
Chong Kim Soon
Phoon Gar Chi
Tan Bee Sian
Yap Li Ying
Low Choon Keat
```

Validation:

- Extract text between `AUTHOR CONTRIBUTIONS` and `ACKNOWLEDGEMENTS`.
- Confirm the first names are exactly:
  1. Low Choon Keat
  2. Yap Li Ying
  3. Tan Bee Sian
  4. Phoon Gar Chi
  5. Chong Kim Soon
- Confirm no placeholder text such as `[contribution details to be completed]` remains.

---

## 5. Table format must match the sample/template screenshot

The correct IEM-style table format is:

- Caption centered above table.
- Caption italic.
- Full outer border.
- Full internal vertical and horizontal gridlines.
- Header row grey shading.
- Header text bold and centered.
- Body text centered.
- Table must stay inside the page box.
- Wide tables should become full-width sections, then return to two-column body layout after the table.

Do not use horizontal-rule-only academic table style.

Validation:

- Every table should have grid borders: top, bottom, left, right, insideH, insideV.
- Header row should have grey shading, e.g. `D9D9D9`.
- Captions should appear above tables, centered and italic.

---

## 6. Profiles section must match the sample/template visual

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

For missing profile images, use a photo placeholder.

For the parking-violation paper, profiles should include only:

1. Low Choon Keat
2. Yap Li Ying
3. Tan Bee Sian
4. Phoon Gar Chi
5. Chong Kim Soon

### Yap Li Ying profile filler

If Yap Li Ying has only affiliation information and no full biography, use a conservative affiliation-based profile:

```text
YAP LI YING is affiliated with the Department of Information and Communication Technology, Faculty of Computing and Information Technology, Tunku Abdul Rahman University of Management and Technology (TAR UMT), Malaysia. Her academic and research interests are aligned with information and communication technology, intelligent systems, computer vision applications, and AI-driven smart-city solutions, including parking-violation detection and enforcement-support workflows.
Email address: [to be completed]
```

Do not invent personal degrees, roles, awards, or ORCID unless provided.

---

## 7. Running headers must match the IEM visual style

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
- First page header is blank.
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

---

## 8. Do not overwrite user’s manual fixes unnecessarily

If the user says “I fixed it myself already”, apply only the requested small change.

Example:

- If user says “put back the superscripts”, only restore author-line superscripts.
- Do not alter affiliations, contributions, profiles, or layout unless asked.

---

# Recommended Automated Workflow

## Step 1: Load files

- Load the paper DOCX.
- Load `IEM Journal paper template.docx`.
- Optionally use `IEM journal review paper.pdf` as visual reference.
- If supplied, load author profile/contribution file.

## Step 2: Extract paper content

Extract:

- Title
- Author line
- Affiliations
- Abstract
- Keywords
- Main body sections
- Figures and captions
- Tables and captions
- End sections:
  - Author Contributions
  - Acknowledgements
  - Data Availability
  - Conflicts of Interest
  - References
  - Profiles

## Step 3: Create output from template

- Copy `IEM Journal paper template.docx` to a new file.
- Replace template title, author line, affiliations, abstract, keywords.
- Delete template body sample content.
- Insert paper body content.

## Step 4: Apply IEM layout

- First page: preserve IEM template structure.
- Body: two-column layout where appropriate.
- Tables/figures: use full-width sections where needed.
- After full-width table/figure, return to two-column layout.

## Step 5: Format tables

Apply:

- centered italic caption above table,
- full grid borders,
- grey header row,
- centered cell text,
- table width inside page boundaries.

## Step 6: Format figures

- Keep figures inside page/column width.
- Center figures.
- Figure captions should match sample style.
- Ensure figure captions are not accidentally converted to body paragraphs.

## Step 7: Format author profiles

- Full-width profile section.
- Grey `PROFILES` bar.
- Photo/placeholder left, biography right.
- Only actual listed authors.

## Step 8: Running headers

- First page blank header.
- Later pages follow template/sample style.
- Grey text + horizontal rule + corner marks.

## Step 9: Final validation

Run these checks before returning the file:

### Text checks

- No old template affiliations remain.
- No unrelated old template email remains.
- No old DOI remains unless intended.
- All paper authors are present.
- No non-paper authors are included.
- No `[to be completed]` remains unless intentionally left for unknown email/profile info.
- No `[contribution details to be completed]` remains.

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

### Image checks

- Image count matches source unless deliberately changed.
- Figures are within page/column width.

### Header checks

- First page header is blank.
- Later page headers contain correct title/author text.
- Header visual resembles sample: grey text, rule, corner marks.

### DOCX integrity check

- Test DOCX as ZIP archive.
- Open with `python-docx` to ensure no corruption.

---

# Python Implementation Notes

When generating files programmatically:

- Use `python-docx` for DOCX editing.
- Use section breaks for one-column/two-column switching.
- Use Word XML (`w:cols`) to control columns.
- Use Word XML table borders for gridline tables.
- Use Word XML cell shading for grey header row.
- Use run-level formatting for superscripts.
- Save output in the working directory.
- Validate using `zipfile.ZipFile(...).testzip()`.

---

# Common Bug Fixes

## Bug: Inserted paragraphs appear in reverse order

When using `paragraph._p.addprevious(new_element)` repeatedly before the same anchor paragraph:

- If inserting in a loop, be careful with order.
- In many cases, inserting in normal order before the same anchor keeps order, but verify by reading back the generated document.
- Always validate the final extracted block.

## Bug: Header text appears in body text extraction

Running header text may not show in `doc.paragraphs` because it is in section headers. Validate headers separately:

```python
for section in doc.sections:
    section.header.paragraphs
    section.even_page_header.paragraphs
    section.first_page_header.paragraphs
```

If header uses tables, inspect `section.header.tables` too.

## Bug: Profile text inside tables is not found in `doc.paragraphs`

Profiles may be in table cells. Validate by iterating through all tables and all cells.

## Bug: Activity limit or workspace reset

If the tool workspace does not contain the latest generated file:

- Ask the user to upload the latest DOCX.
- Do not rebuild from an older file unless the user confirms.

---

# Final Deliverable Naming Convention

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

---

# Minimal Prompt for Future Agent

Use this exact prompt in a future session:

```text
Please convert my paper into the IEM Journal template. I uploaded:
1. the paper DOCX,
2. IEM Journal paper template.docx,
3. IEM journal review paper.pdf,
4. this IEM conversion skill/memory file.

Use the Word template as the layout base and copy my paper content into it. Match the visual style of the template/sample, including first page, author superscripts, affiliations, table style, figure style, running headers, author contributions, profiles, and references. Follow the validation checklist in the skill file before returning the final DOCX.
```


### 28. DOI/reference verification and standard DOI formatting

**Mistake learned:** Some references had incomplete or questionable DOI information. Examples included a missing DOI for the IJIRCST energy-efficient fog computing article, an unverified Nanotechnology Perceptions DOI, and an incorrect Bitcoin white paper citation using a Wright/SSRN DOI rather than the original Nakamoto white paper source.

Required handling:
- Standardise valid DOI entries as `https://doi.org/...`, not mixed `doi:` and DOI URL forms.
- Strip trailing punctuation from the DOI link itself.
- Add missing confirmed DOIs when reliable publisher metadata confirms the DOI.
- Do not keep suspicious/unverified DOIs; use the publisher article URL if DOI verification is not available.
- Cite the Bitcoin white paper as Nakamoto, S. (2008) with the original white paper URL, not the Wright/SSRN DOI.

Validation:
- Confirm all references remain sequentially numbered.
- Confirm no `doi: 10.` prefix remains when DOI URL style is required.
- Confirm corrected references for Nanotechnology Perceptions, IJIRCST, and Nakamoto are present.
