# middle-schooler

Education and tutoring toolkit for middle school academic competitions. Specialized agents and skills for Spelling Bee and National Science Bowl (NSB) preparation.

## What's Included

### Agents

| Agent | Focus |
|-------|-------|
| `spelling-bee-instructor` | Competition-grade spelling bee prep with NLP-powered word analysis, etymology teaching, and adaptive practice |
| `science-bowl-instructor` | NSB curriculum synthesis across 6 subjects using TF-IDF, BM25, and n-gram analysis of question corpora |

### Skills

| Skill | Purpose |
|-------|---------|
| `science-bowl-question-prep` | Ingest, categorize, solve, proofread, and format Science Bowl questions into structured study materials and PDFs |

## Usage

### Spelling Bee

```
Generate a spelling bee study guide for 6th grade level
Quiz me on Greek-origin words
I keep misspelling words with "ph" — help me practice
```

### National Science Bowl

**Study material generation** (uses the science-bowl-instructor agent):

```
Generate Science Bowl study notes for all 6 subjects from my sample questions
Create a curriculum overview with topic frequency analysis
```

**Question preparation** (uses the science-bowl-question-prep skill):

```
Categorize science bowl questions from my PDFs by subject and topic
Generate solutions for all Science Bowl sample questions
Prepare science bowl study materials from ./sample-questions
```

### NSB Subjects Covered

| Subject | Topics Include |
|---------|---------------|
| Life Science | Cell biology, genetics, ecology, anatomy, classification |
| Physical Science | Forces, motion, energy, matter, chemical reactions |
| Earth and Space Science | Geology, weather, astronomy, plate tectonics |
| Math | Algebra, geometry, statistics, measurement |
| Energy | Forms of energy, transfer, conservation, sources |
| General Science | Scientific method, tools, cross-disciplinary concepts |

## Installation

```bash
/plugin marketplace add https://github.com/islanderman/claude-code-marketplace
/plugin install middle-schooler
```
