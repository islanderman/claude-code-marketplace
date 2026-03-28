---
name: science-bowl-question-prep
version: 1.0.0
author: Jerry Yang <jerry@chenyang.us>
description: >
  Ingest, categorize, solve, proofread, and format Science Bowl sample questions
  into structured study materials. Use when you have Science Bowl PDF question sets
  and want to produce categorized question files, full solutions, and printable PDFs.
category: middle-schooler
agents:
  - middle-schooler:science-bowl-instructor
triggers:
  - "categorize science bowl questions"
  - "prepare science bowl study materials"
  - "ingest science bowl PDFs"
  - "science bowl question prep"
  - "generate science bowl solutions"
modes:
  standalone: true
  teammate: true
---

# Science Bowl Question Prep

Activate EXPERT MODE: execute the full Science Bowl question pipeline with systematic precision.

## Purpose

This skill orchestrates the complete Science Bowl question preparation workflow: parsing sample question PDFs, categorizing by subject and topic, generating detailed solutions, proofreading all output, and compiling printable PDFs.

---

## Workflow

### Step 1: Input Ingestion

- Read all PDF files under `./sample-questions`
- Read study notes from `./study-notes` (authoritative taxonomy and ordering)
- Parse all questions from all PDFs

### Step 2: Question Categorization

Categorize questions strictly according to:

- Subjects and topic hierarchy defined in the study notes
- The **exact topic order** in the study notes must be preserved (reflects Science Bowl frequency analysis)

Ensure:

- Correct numerical ordering of questions
- Proper Markdown formatting
- Accurate rendering of:
  - Mathematical expressions (LaTeX)
  - Chemical formulas
  - Scientific notation and symbols

If a question does not map to any existing topic, place it in a `Miscellaneous` section at the very end.

### Step 3: Output Structure (Categorization)

- Output directory: `./questions/`
- One Markdown file per **subject**
- Each file contains questions grouped by topic, following the study-notes order exactly

### Step 4: Solution Generation

Create a **separate Markdown file** containing full solutions:

- Clear, concise, and logically structured reasoning
- Written at a level comprehensible to middle school students
- For **multiple-choice** questions:
  - Explain every option, including why incorrect choices are wrong
- For **short-answer** questions:
  - Explain what the question is asking and justify the final answer
- For **math, physics, and chemistry**:
  - Provide step-by-step derivations or inductive reasoning
- Any fundamental or critical concept used in a solution:
  - Explicitly highlight it
  - Explain why it is important

### Step 5: Proofreading and Validation

Before generating any PDFs, perform a **full proofreading and validation pass**:

- Verify no typographical, grammatical, or formatting errors
- Verify all math and chemistry are in LaTeX format
- Validate mathematical notation renders correctly and consistently
- Confirm chemical formulas and equations are accurate
- Check units, symbols, and scientific terminology for consistency
- Confirm question numbering is continuous and correct
- Confirm topic ordering exactly matches the study notes
- Confirm no questions are missing, duplicated, or miscategorized
- Re-read all explanations for logical completeness and age-appropriate clarity
- Verify each subtitle starting with `##` has `\newpage` before it

**Only proceed to PDF generation after all proofreading checks pass.**

### Step 6: PDF Generation

- Generate PDFs from the validated Markdown files
- Output directory: `./PDFs/questions`

## Performance Requirements

- Process subjects sequentially
- Categorization algorithm must be **O(n)** with respect to question count
- Do not use quadratic or nested cross-referencing approaches
- Perform a single pass over PDFs with direct topic assignment using the study-notes taxonomy

## Final Outputs

| Output | Location |
|--------|----------|
| Categorized question files | `./questions/` (one per subject) |
| Solution file | `./questions/` |
| Generated PDFs | `./PDFs/questions` |

## Constraints

- Topic alignment and ordering fidelity are **non-negotiable**
- Accuracy, formatting correctness, and pedagogical clarity take precedence over brevity
- Do not omit questions
- Do not reorder topics
- Do not degrade mathematical, chemical, or scientific rigor
- Do not generate PDFs until proofreading is fully complete
