---
name: simple-english
description: "Rewrite academic prose into simpler, clearer formal UK English without changing the claims, numbers, citations, notation, or technical meaning. Use when the user asks to simplify writing, improve thesis prose, reduce stiffness, enforce a no-first-person academic tone, strengthen paragraph flow, or produce cleaner plain-English revisions of scholarly text."
argument-hint: [INPUT_PATH_OR_TEXT="section, manuscript, or pasted prose"]
allowed-tools: "*"
---

# Simple English

Use this skill to simplify academic writing while preserving the exact technical meaning.

The target style is formal, restrained, and readable. The prose should feel human and natural, but not colloquial. It should use formal UK English, active voice where possible, steady logical progression, and varied sentence rhythm without sounding mechanical.

When users mention `AI rate`, `AIGC rate`, or detector concerns, translate that into a legitimate writing goal: produce clearer, more original, less formulaic academic prose that reflects the actual argument and evidence. Do not optimise for evading Turnitin or any AI detector. The purpose is always authentic scholarly communication, not gaming detection systems.

## Goals

- Explain complex ideas as simply as possible without flattening their meaning.
- Use formal UK English spelling and phrasing.
- Prefer precision, brevity, and active voice.
- Maintain a natural academic flow with smooth paragraph-to-paragraph progression.
- Reduce stiffness without becoming conversational.
- Avoid repetitive logic patterns, repetitive vocabulary, and repetitive sentence openings.

## Hard constraints

1. Do not change numbers, equations, symbols, units, citations, figure labels, table labels, or algorithm names.
2. Do not add new claims or remove important caveats.
3. Do not simplify by becoming vague.
4. Use formal UK English: for example, `analyse`, `optimise`, `labelling`, `modelling`.
5. Avoid first-person pronouns by default. Do not use `I` or `we` unless the user explicitly asks for that voice.
6. Avoid colloquialisms, inflated jargon, filler, and performative complexity.
7. If a sentence is already clear, leave it alone.
8. Do not use this skill to disguise plagiarism, bypass similarity checks, hide unattributed copying, or evade AI-detection systems such as Turnitin. Preserve honest academic standards.

## Style guide

- Use a clear introduction, development, and conclusion at the scale that fits the input.
- Prefer natural signposting over mechanical transitions. Good transitions include `Furthermore`, `Conversely`, `In practice`, `This matters because`, `Against this background`, `Taken together`, and short summary pivots.
- Avoid rigid sequence markers such as `first`, `second`, and `then` unless genuine procedural order is required.
- Do not force every paragraph into the same structure.
- Mix sentence lengths. Avoid long runs of clipped short sentences, but also avoid chains of overextended sentences.
- Prefer concrete wording to abstract inflation.
- Maintain hierarchy and progression so the argument feels cumulative rather than flat.
- Keep the tone academic, rigorous, and readable, not bureaucratic.
- Use active voice whenever it improves clarity.
- Prefer direct verbs over noun-heavy constructions.
- Use natural paragraph bridges. A brief summary pivot, a motivating question, or a context-setting clause is better than abrupt paragraph switching.

### What makes prose sound human (and not formulaic)

Academic writing often suffers from a small set of recurring patterns that, while grammatically correct, make the text sound mechanical. To produce natural, human scholarly prose, actively avoid:

- Repeated use of the same lexical bundles (e.g., “it is worth noting that”, “it should be emphasised that”, “it has been observed that”). Replace with direct, specific statements.
- Overused parallel structures such as “not only … but also …” or overly balanced “on the one hand … on the other hand …” patterns that become predictable.
- Rigid topic sentences that all follow the same “This section discusses …” or “We will now examine …” template. Vary paragraph openings by leading with the substantive point, a question, or a brief scene-setting clause.
- Chains of short, declarative sentences of identical length that produce a staccato, robotic rhythm. Similarly, avoid long sequences of complex sentences all structured the same way. Instead, compose a rhythm that alternates between medium-length statements, occasional short emphatic sentences, and longer explanatory ones.
- Excessive use of “moreover”, “furthermore”, “in addition” when simple logical connectors (e.g., “and”, “but”, “because”, “so”) would sound more natural without sacrificing formality. Save those formal connectors for points that genuinely need emphasis.
- Artificial hedging that weakens the prose without adding precision. Use hedging only when the uncertainty is real and necessary to the claim.

Instead, aim for a voice that sounds like a clear-thinking scholar articulating a careful argument – varied in sentence architecture, precise in vocabulary, and steady in tone. The writing should feel as if a human writer made conscious choices about emphasis and rhythm, not as if a template filled in the blanks.

## Procedure

1. Identify the exact text span to revise.
2. Preserve all technical anchors: metrics, datasets, baselines, equations, citations, qualifiers, and scope conditions.
3. Diagnose the main readability problems before rewriting: stiffness, unnecessary length, jargon density, repetitive transitions, weak paragraph flow, or passive construction.
4. Rewrite at sentence and paragraph level, not just by swapping individual words.
5. Improve order and emphasis when needed so the logic unfolds more naturally.
6. Use smoother transitions between ideas and paragraphs when the original jumps too abruptly.
7. If presenting data or conclusions, add only clarifying context that is already implicit in the source text or explicitly supplied by the user. Do not invent evidence, observations, or personal experiences.
8. If the original is ambiguous, flag the ambiguity instead of guessing.
9. Return the revised text. When useful, add a short note describing the main style changes.

## Thesis-oriented defaults

- Formal academic register.
- Natural, non-mechanical transitions.
- Clear hierarchy and progression.
- Fewer overlong sentences.
- No `I` or `we` by default.
- No empty intensifiers or ornamental phrasing.
- Human, steady, restrained tone.
- More layered sentence rhythm without sounding ornate.
- Smoother logic between paragraphs and subclaims.

## Typical uses

- Simplify an abstract.
- Clean up thesis paragraphs written in an overly stiff or inflated style.
- Improve introduction, related work, discussion, or conclusion prose.
- Make rebuttal or response text easier to read while staying formal.
- Reduce unnecessary academic inflation in paper drafts.
- Convert dense technical prose into clearer, more accessible scholarly writing.

## Thesis rewrite note

If the user provides a thesis title, chapter role, or paragraph purpose, use that context to tighten progression and emphasis. Treat requests to `reduce AI rate` as requests for better scholarly prose.