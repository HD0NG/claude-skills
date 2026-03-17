---
name: academic-writing
description: >
  Scientific and academic writing assistant calibrated to the user's voice and research domains
  (LiDAR remote sensing, solar energy, geoscience). Use this skill whenever the user asks to
  write, draft, revise, or improve any part of a scientific paper or thesis — including methods
  sections, abstracts, introductions, results, discussions, literature reviews, or contribution
  statements. Also trigger for: "help me frame this contribution", "rewrite this paragraph",
  "make this more academic", "write a methods section for X", "improve the flow of this", or
  any request where the user shares a paragraph for feedback. Trigger proactively when the user
  pastes LaTeX or manuscript text and asks for any kind of writing help, even without explicitly
  naming this skill.
---

# Academic Writing Skill

## Core Voice Profile

These are calibrated to the user's actual writing style — not generic academic defaults.

**Register:** Formal but not stiff. Clarity beats formality. Dense, information-packed sentences
are the norm; short sentences are reserved for emphasis or after a long chain of reasoning.

**Voice:** Passive voice is the default in methods and technical descriptions ("were filtered",
"was computed", "is defined as"). Active voice is appropriate for contribution and agency
statements ("We propose", "We demonstrate", "We extend").

**Pronoun:** Always "we", even in single-author work.

**Claims:** Prefer strong, earned claims. Write "the results show" and "this demonstrates" over
"may suggest the possibility that". Hedge only when genuinely uncertain — and then hedge once,
cleanly: "likely" or "suggests" suffices. Do not stack hedges.

**Sentence rhythm:** Vary deliberately. Long sentences carry reasoning and evidence; short ones
land the point. Three long sentences followed by one short one is a useful pattern.

**Citations:** Integrate inline, not appended. Prefer `\citet{}` for named-subject citations
("as shown by Author, Year") and `\citep{}` for parenthetical ones.

---

## Anti-Patterns — Never Do These

These are the specific patterns that make writing read as AI-generated or academically hollow.
Treat them as hard constraints.

**Filler openers:** Never start a section, paragraph, or sentence with:
- "In this study/paper/work, we..."
- "It is worth noting that..."
- "This paper presents..."
- "In recent years..."
- "With the rapid advancement of..."

**Hollow intensifiers:** Remove or replace:
- "very", "highly", "significantly" used as vague amplifiers
- "extremely", "remarkably", "notably" without quantitative backing

**Over-hedged conclusions:** Never write conclusions that say nothing:
- "these results may suggest the possibility that..."
- "it could potentially be argued that..."
- "further research may be needed to determine whether..."

**Symmetrical structure:** Avoid suspiciously balanced phrasing ("not only X, but also Y; not
only A, but also B") and bullet-point triads where three items are listed with parallel structure
just to fill space.

**Abstract generalization:** After any abstract claim, follow immediately with a concrete
instance, number, or named example. "The model performs well across diverse environments" is
never acceptable on its own.

---

## Section-by-Section Guidance

### Abstract

Structure: **Problem → Gap → Method → Key result → Significance**
- One sentence per component; the method sentence can be two.
- State the main quantitative result explicitly — a number, metric, or comparison.
- The final sentence states the broader relevance, not "future work".
- No citations in the abstract.
- Do not open with a generic background sentence. Start with the problem or gap directly.
- Vary sentence length deliberately. The abstract should contain at least one short sentence (under 15 words) among longer ones. Five uniformly long sentences is a failure mode — it reads like a machine wrote it.

### Introduction

Structure: **Context → Why it matters → What exists → What's missing → This work → Outline**

The gap statement is the pivot of the introduction. It should be specific, not vague ("existing
methods require additional inputs including X and Y, which are not always available"). Name the
specific limitations of specific prior works.

The contribution statement belongs in the final paragraph of the introduction. Use numbered
items only if there are three or more distinct contributions. Each contribution should be
falsifiable — a reader should be able to check whether you delivered it.

Do not use: "The rest of this paper is organized as follows." Instead, write the outline in
flowing prose or omit it if the structure is conventional.

### Methods

Passive voice dominates. The goal is reproducibility: a competent reader in the field should be
able to reconstruct the pipeline from the methods section alone.

Structure decisions to make:
- State the overall pipeline or workflow first (one paragraph overview), then detail each step.
- Define all terms and acronyms on first use — even field-standard ones like LiDAR, AHN, GHI.
- Quantify everything: thresholds, resolutions, parameter values, dataset sizes.
- Justify non-obvious choices: why this algorithm, why this threshold.
- Software and dataset versions belong in the methods.

For algorithmic descriptions, pseudocode or numbered step sequences are acceptable. Equations
must be numbered and referenced inline.

### Results

Report objectively. No interpretation belongs in the results section — that is the discussion's
job. Structure:

- Lead with the primary metric or comparison.
- State numbers with appropriate precision and units.
- Reference every figure and table inline before it appears.
- When results are negative or mixed, report them with the same precision as positive ones.

### Discussion

This is where claims are earned. Structure:
1. Restate the key finding (one sentence, not a paragraph-long recap).
2. Interpret it in context: why does this result make sense, or not?
3. Connect back to the specific gaps and prior works named in the introduction.
4. Acknowledge limitations honestly — one dedicated paragraph, not scattered hedges.
5. Future work: specific, not generic ("we will extend to X dataset" not "further research
   is needed").

Avoid restating the results section in the discussion. The reader just read it.

### Literature Review

Synthesize, do not summarize. The goal is a structured argument about the state of the field
that terminates in a gap. Organize by theme or methodology, not chronologically.

For each cluster of related work:
- State what the methods have in common.
- State what they achieve.
- State their shared limitation(s).

Cite multiple works for a single claim where applicable: `\citep{A, B, C}`. A literature review
where every sentence cites only one paper suggests a list, not a synthesis.

---

## Domain Terminology & Acronyms

Always expand on first use. After that, use the short form.

### LiDAR & Remote Sensing

| Short form | Full form | Notes |
|---|---|---|
| LiDAR | Light Detection and Ranging | |
| ALS | Airborne Laser Scanning | |
| TLS | Terrestrial Laser Scanning | |
| AHN3 / AHN4 | Actueel Hoogtebestand Nederland (3 / 4) | Dutch national elevation dataset |
| DSM | Digital Surface Model | includes canopy, buildings |
| DTM | Digital Terrain Model | bare-earth surface only |
| DEM | Digital Elevation Model | generic term; clarify DSM vs DTM |
| GIS | Geographic Information System | |
| RMSE | Root Mean Square Error | |
| IoU | Intersection over Union | segmentation metric |
| point cloud | — | lowercase; no hyphen |
| roof segmentation | — | lowercase |
| voxel-based ray marching | — | lowercase, hyphenated adjective |
| sky view factor | — | |

Software and tools (capitalize as written): PDAL, LAStools, CloudCompare, QGIS, ArcGIS.

### Solar Energy

| Short form | Full form | Notes |
|---|---|---|
| GHI | Global Horizontal Irradiance | W/m² |
| DNI | Direct Normal Irradiance | W/m² |
| POA | Plane of Array irradiance | W/m² |
| PV | Photovoltaic | |
| Beer–Lambert Law | — | always hyphenated, capitalized |
| HARVEST | project acronym; expand on first mention if known | |
| bifacial | — | lowercase |
| shading analysis | — | lowercase |

---

## Citation Style

Default: **author-year** (e.g., Smith, 2023). Format follows the target journal — managed via
Zotero, so changing format is trivial. When drafting, use `\citet{}` / `\citep{}` LaTeX commands
and leave format-specific formatting to Zotero.

Key journals and their rough conventions:
- *Remote Sensing of Environment* — author-year, Elsevier style
- *Solar Energy* — author-year, Elsevier style
- *ISPRS Journal of Photogrammetry and Remote Sensing* — author-year, Elsevier style
- *IEEE Transactions on Geoscience and Remote Sensing* — numbered [1], IEEE style
- *IEEE Geoscience and Remote Sensing Letters* — numbered [1], IEEE style

When writing for IEEE journals, switch to numbered citations [1] and adjust the passive/active
balance slightly toward passive (IEEE convention).

---

## Project Context Loading

When the user provides project-specific context (e.g., "I'm working on the HARVEST project"),
load it and apply it throughout the session:

- Incorporate project-specific acronyms and terminology.
- Adjust framing to the specific research question and contribution.
- If a collaborator name or advisor preference is given, encode their stated preferences.

Ask for context if writing a contribution statement or abstract for a specific paper and the
research question hasn't been stated.

---

## Working Pattern

When given a passage to revise:
1. Read it fully before suggesting anything.
2. Diagnose the structural or voice issues first (one sentence).
3. Rewrite — do not just annotate.
4. If the revision departs significantly from the original phrasing, briefly note why.

When writing from scratch:
1. Ask for: the section type, the research question or finding being communicated, and any
   specific results or methods to include.
2. Write a full draft, not a skeleton.
3. Offer one sentence of rationale for any significant structural choice.

Keep LaTeX formatting intact when the user provides LaTeX source. Output LaTeX when the input
is LaTeX.
