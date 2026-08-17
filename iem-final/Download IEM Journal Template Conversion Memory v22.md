# IEM Journal Template Conversion Memory v22

**Status:** Current lessons index, dated 17 August 2026.  
**Operational authority:** `IEM_TEMPLATE_MANUSCRIPT_CONVERSION_SKILL_v1_1.md`.  
**Supersedes:** `IEM_Journal_Template_Conversion_Skill_Memory_REVISED_v21.md`.

## Purpose

This file records the concrete failures and lessons from the Eco-Secure Edge conversion. It is intentionally not a second full copy of the conversion workflow. Keeping two complete specifications caused drift. All executable rules now live in the v1.1 skill file.

## Errors observed and permanent lessons

1. **False completion claim.** An output was described as template-compliant before its first-page structure, real columns, figures, equations, and Profiles layout had been verified. Never call a file final while a mandatory defect remains.
2. **Effective manuscript-base conversion.** The template package was cleared and the manuscript was appended, so manuscript sections and formatting became the effective layout. Transfer content element by element into the template's real structures.
3. **Insufficient reading of supplied evidence.** The template, published sample PNGs/PDF, skill file, and memory were not fully compared before editing. Inventory and render all authoritative inputs first.
4. **Visual resemblance mistaken for structural compliance.** The document looked journal-like but lacked genuine Word section and column mechanics. Audit `w:sectPr` and `w:cols`.
5. **Single-column article body.** Main text initially remained full width. The normal article body must use genuine two-column sections.
6. **Incorrect first-page title placement.** The title was placed inside the left abstract cell beside the grey metadata panel. Title and author byline are full-width single-column elements above the abstract/metadata layout.
7. **Incorrect author placement.** The author byline was also confined to the left front-matter cell. Keep the byline full width and preserve superscript markers.
8. **Affiliation markers not superscripted everywhere.** Superscript was applied to the byline but omitted from affiliation paragraphs and metadata. Audit every occurrence.
9. **Wrong terminology.** “Hyperscript” was accepted informally before correction. Use the correct term, superscript.
10. **Template residue remained in unused header parts.** Sample author/title/CONFIDENTIAL text survived in header XML even when not visible. Search all package parts, including unused headers, shapes, and alternate content.
11. **Running-header approximation without exact sample comparison.** Header mechanics and styling were changed before the complete published sample was used as the visual target. Reproduce the supplied template/sample, not a generic journal header.
12. **Duplicated notation representation.** A formal notation table was followed by a redundant plain-text list.
13. **Raw notation names.** Plain words such as alpha, beta, tau_alpha, and tau_beta appeared instead of proper symbols.
14. **Duplicate automatic and manual numbering.** Contribution paragraphs rendered as `1. 1.`, `2. 2.`, and `3. 3.` because literal numbers were combined with Word numbering.
15. **Equation-width overflow.** Equations (8) and (9) crossed or crowded the column boundary.
16. **Equation paragraph formatting leaked into prose.** The explanatory paragraph after Equations (8) and (9) inherited centred alignment instead of justified body alignment.
17. **Figure/chart clipping.** A chart's rightmost category/bars were clipped after conversion to two columns.
18. **Visuals crossed the gutter.** Some figures were not resized to the active column width.
19. **Profiles section initially lacked correct structure.** Profiles were not reliably full width with the sample's grey banner and compact photo-biography layout.
20. **Trailing profile spill page.** The last profile email moved to a page by itself and was initially overlooked.
21. **Overconfident QA summaries.** Statements such as “all pages inspected” were made while user screenshots still exposed obvious defects. QA claims must correspond to the latest rendered file and observed pages.
22. **Repeated version escalation.** Routine local fixes produced V2 through V9 rather than maintaining one active working file until a meaningful milestone. Keep retries temporary; create durable versions only for user-facing milestones or material states.
23. **Local feedback triggered broader changes.** Some corrections modified more than the exact defect raised. Apply local fixes and preserve unaffected sections.
24. **Humanisation introduced layout reflow.** Clearer prose reduced page count. This is acceptable, but it requires one final full render because pagination and section transitions may move.
25. **Two overlapping instruction files.** The skill and memory duplicated rules and could diverge. v1.1 is now authoritative; v22 records only lessons and deltas.

## Required operating pattern

- Read and render the template, manuscript, and published sample before editing.
- Freeze the first-page and section map before content transfer.
- Use one active working DOCX.
- Fix verified defects locally.
- Run only checks tied to a live failure or the mandatory final delivery gate.
- Render every page after the final meaningful edit.
- State plainly when the file is correct; state plainly when it is not.

## Current canonical files

- `IEM_TEMPLATE_MANUSCRIPT_CONVERSION_SKILL_v1_1.md`: complete authoritative workflow.
- `IEM_Journal_Template_Conversion_Memory_v22.md`: this lessons index.

Do not maintain another full duplicated copy of the skill inside the memory file.
