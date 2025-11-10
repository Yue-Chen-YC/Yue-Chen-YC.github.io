---
layout: page
permalink: /resources/index.html
title: Resources and Tutorials
---

> **Latest Update:** 5th Nov 2025<br>

---

## Vocabulary Assessment – PPVT

### What is the PPVT?

The Peabody Picture Vocabulary Test (PPVT) is a standardized test of **receptive vocabulary**. On each trial, the examiner says a word, and the participant selects one picture out of four that best matches the meaning of that word. Because the response only requires pointing (rather than speaking or reading), the PPVT is widely used with children, multilingual speakers, heritage speakers, and populations where productive language may be limited.

Scores are norm-referenced by age and can be used to estimate vocabulary level, compare groups, or include receptive vocabulary as a covariate in experimental work.

[Download PPVT Tutorial (PDF)]({{ "/file/Vocabulary_PPVT.pdf" | relative_url }})

This PDF provides a brief introduction to the Peabody Picture Vocabulary Test (PPVT), including background, basal/ceiling rules, and example items for administration.

---

## Transcription & Corpus Analysis – CLAN

### What is CLAN?

**CLAN** (Computerized Language ANalysis) is the main software used with the **CHAT** transcription format and the TalkBank/CHILDES corpora. It supports:

- Creating and editing CHAT-formatted transcripts  
- Running automatic morphological analysis via **MOR**  or **batchalign2**
- Computing frequencies, MLU, TTR, Word Type, Word Tokens, and many other measures from transcripts  
- Working with multiple languages (e.g., `eng`, `zho`, `yue`, etc.)

It’s widely used in child language, clinical, and corpus-based research, and is basically the standard toolchain if you work with TalkBank data.

[Download CLAN Tutorial (PDF)]({{ "/file/CLAN_Tutorial.pdf" | relative_url }})

This PDF walks through installing CLAN on macOS, installing MOR grammars, finding CLAN on your laptop, setting up new scripts, using header and ID tiers, language codes, common shortcuts, and conventions for gestures, code-switching, and other CHAT symbols.


### Syntactic & Morphological Parsing with Batchalign2

**Batchalign2** is a command-line pipeline developed in the TalkBank project for **automatic morphological tagging and Universal Dependencies (UD) syntactic parsing**.  
It:

- Takes CHAT `.cha` transcripts as input  
- Produces `%mor` tiers (lemmas, POS tags, morphological features)  
- Produces `%gra` tiers (UD-style dependency parses)  
- Integrates with CLAN, so you can immediately use `kwal`, `freq`, etc. on the annotated corpus

**Typical workflow**:

- Use R or other scripts to format the raw text into valid .cha files (including headers such as @Begin, @Languages:, @ID, *ADU:, etc.).
- Use Batchalign2 in the local terminal to run batchalign morphotag ba_input ba_output.
- Inspect the %mor and %gra tiers in the output .cha files, and then use CLAN for further analyses (e.g., kwal +t%mor, kwal +t%gra).

[Download Batchalign2 Parsing Tutorial (PDF)]({{ "/files/Syntactic_Parsing_Documentation.pdf" | relative_url }})

This PDF provides step-by-step instructions for installing Batchalign2 with `uv`, preparing `.cha` files, running `batchalign morphotag` on input/output folders, and interpreting `%mor` and `%gra` tiers, with concrete examples from Italian data and suggestions for CLAN-based post-processing.

---

## Forced Alignment – Montreal Forced Aligner (MFA)

### What is MFA?

**Montreal Forced Aligner (MFA)** is an open-source toolkit for **forced alignment**: automatically aligning audio recordings with their transcripts to obtain word- and phone-level timestamps. It is widely used in phonetics, corpus linguistics, and clinical/experimental work where you need time-aligned segments but don’t want to hand-label everything in Praat.

MFA uses:
- Pre-trained **acoustic models** for many languages  
- Corresponding **pronunciation dictionaries**  
- Command-line workflows that can be integrated with other tools (e.g., Python, Praat, R)

Typical use cases include preparing data for formant analysis, VOT measurements, prosody studies, and large-scale speech corpora.

[Download Montreal Forced Aligner Tutorial (PDF)]({{ "/file/Montreal-Forced-Aligner.pdf" | relative_url }})

This PDF provides a step-by-step guide to installing MFA with Miniconda, setting up a dedicated environment, installing MFA, downloading acoustic models and pronunciation dictionaries (e.g., `english_us_arpa`, `mandarin_mfa`), and running alignment commands from the terminal with concrete path examples and sample output.

