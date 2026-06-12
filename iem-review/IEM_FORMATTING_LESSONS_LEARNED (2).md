# IEM Formatting Lessons Learned

Date: 2026-06-12

Purpose: This single Markdown file records the IEM formatting mistakes found during conversion and the corrected rules to prevent the same problems in future IEM review-paper formatting work.

## Final output rule

For this task, provide only:

1. one corrected DOCX manuscript; and
2. one Markdown lessons-learned file.

Do not output multiple Markdown files unless the user explicitly asks for separate logs, patches, audits, or readiness files.

## Mistakes made and required future corrections

### 1. Approximated the layout instead of using the provided template or sample discipline
- Mistake: Earlier outputs approximated IEM formatting from memory and manual assumptions.
- Correction: When `Paper template 2025.docx` or a valid IEM-formatted sample is provided, use that file as the formatting anchor. Copy the manuscript content into the template/sample-derived structure instead of designing a new layout.

### 2. Added line numbering by mistake
- Mistake: Word line numbering was enabled, causing `1, 2, 3...` to appear beside body text.
- Correction: Never enable line numbering by default. Remove `w:lnNumType` from every section unless the user explicitly requests line numbering.

### 3. Added footer or page-number fields by mistake
- Mistake: Page numbering/footer fields were added although the template says production may add headers, footers, or page numbers.
- Correction: Do not add page numbers, headers, or footers unless the user explicitly asks.

### 4. Left blue hyperlink formatting in references
- Mistake: DOI links inherited Word Hyperlink style, producing blue or underlined text.
- Correction: References and DOI URLs must be plain black Times New Roman unless the user explicitly asks for active blue hyperlinks. Remove `Hyperlink` run style, underline, theme colour, and direct blue colour.

### 5. Did not apply requested bracketed reference numbering initially
- Mistake: The reference list was left as unnumbered APA-style entries.
- Correction: If the user asks for numbered references, prefix each reference with `[1]`, `[2]`, `[3]`, and so on.

### 6. Used the wrong table border model
- Mistake: Tables were formatted with too many internal horizontal lines and inconsistent borders.
- Correction: Follow the supplied sample paper. Substantive tables should be centred, use black Times New Roman text, have no vertical borders, and use only top and bottom horizontal rules by default. Do not add inside horizontal grid lines unless the sample or user explicitly requires them.

### 7. Used Word Heading styles too aggressively
- Mistake: Earlier conversions relied on Word Heading styles, which introduced hidden spacing and alignment drift.
- Correction: Follow the sample's direct formatting pattern: Normal-style paragraphs, 12 pt Times New Roman, black text, bold section headings, justified body text, centred title/author block, and controlled spacing.

### 8. Front matter spacing was not aligned with the sample
- Mistake: Extra blank paragraphs and inconsistent spacing appeared around title, authors, affiliations, abstract, and keywords.
- Correction: Use the supplied sample pattern: title centred, author line centred, affiliations centred and italic, corresponding-author line centred and italic, `Abstract` heading, abstract paragraphs, and `Keywords`.

### 9. Captions were not consistently sample-matched
- Mistake: Captions were not consistently treated as standalone black paragraphs with the right alignment.
- Correction: Keep each caption as its own paragraph. Table captions go above tables and are left-aligned or justified following the sample; figure captions go below figures and are centred.

### 10. Did not inspect the target sample deeply before rebuilding
- Mistake: The earlier fix used the template but did not sufficiently learn from the user's known-good sample.
- Correction: When the user supplies a good sample, inspect the sample's paragraph spacing, margins, title block, heading formatting, table borders, table font sizes, caption placement, and reference formatting before generating the corrected DOCX.

### 11. Created too many Markdown support files
- Mistake: Two Markdown files were produced: one mistake log and one skill patch file.
- Correction: For the user's requested deliverable, consolidate all mistakes, fixes, and future conversion rules into one Markdown file only.

### 12. Figure sizing and caption pairing were not checked carefully enough
- Mistake: A tall PRISMA-style figure was inserted too large, spilled across pages, and visually separated from its caption. Image order was also at risk when relying on relationship order rather than body order.
- Correction: Extract figures in actual document body order using each paragraph's embedded relationship ID. Fit tall figures by height rather than width, insert a page break before tall figures when necessary, and keep each figure with its correct caption.

### 13. Too many short paragraphs were created from source line breaks
- Mistake: Source paragraphs that functioned like a list, such as Stream A-D, the three SafePhase contribution statements, indicator lists, mode descriptions, and research-agenda items, were kept as separate paragraphs. This created excessive paragraph breaks and made the paper look like a report instead of a journal article.
- Correction: During IEM conversion, merge short sequential list-like explanatory paragraphs into one compact prose paragraph when they belong to the same idea. Keep true headings, captions, tables, figures, and references separate.

### 14. Whole-document review was not strict enough before delivery
- Mistake: Formatting was fixed locally around reported screenshots, but similar paragraph-fragment issues remained elsewhere.
- Correction: After any local fix, scan the entire document for repeated formatting patterns, including short fragment paragraphs, figure overflow, table border inconsistency, caption placement, colour drift, and reference formatting.

## Required quality gate for all future IEM conversions

Before returning the final file, reopen the DOCX and verify:

- no blue font remains;
- no line numbers appear beside body text;
- no accidental footer or page-number fields are present;
- all text is black Times New Roman;
- body paragraphs are justified;
- title and author block are centred;
- author affiliation numbers are superscripted;
- headings are bold and aligned with the body text edge;
- table captions are above tables;
- figure captions are below figures;
- tall figures fit within a page and do not spill out of the page area;
- figure images match their captions in body order;
- list-like fragments are not over-split into many short paragraphs anywhere in the document;
- table borders follow the supplied sample: no vertical borders and no unnecessary inside horizontal grid lines;
- references follow the user-requested numbering style;
- the output was generated using the provided template/sample as formatting anchor, not a fresh guessed layout;
- only one DOCX and one Markdown file are returned unless the user asks for more.
