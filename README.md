# Authorial Writing Agent

An experimental AI-assisted writing system designed to help transform my own ideas into articles while preserving my authorial voice.

The goal is not to create an AI that decides what I think.

The goal is to build a system that helps me express what I already think in a consistent, recognizable writing style.

## Motivation

Writing with generative AI is fast, but it often introduces a recognizable generic tone:

- overly polished transitions;
- artificial hooks;
- repetitive rhetorical patterns;
- exaggerated conclusions;
- generic motivational language;
- arguments that sound plausible but are not necessarily mine.

This project explores a different approach.

Instead of asking a model to "write like me" based on a vague prompt, the system is being built around:

- a curated corpus of my own writing;
- structured metadata;
- an explicit `STYLE.md`;
- retrieval of relevant writing samples;
- evaluation of generated drafts;
- comparison between AI-generated and human-edited versions;
- continuous refinement of the writing profile.

## Core Principle

The author remains responsible for:

- the thesis;
- opinions;
- factual context;
- personal experiences;
- conclusions;
- convictions.

The system may help with:

- structure;
- clarity;
- organization;
- wording;
- retrieving relevant examples;
- identifying weak reasoning;
- reducing repetition;
- evaluating style consistency.

It must not manufacture an opinion simply because a similar one appears in the corpus.

## Current Status

The project is currently in the early experimentation stage.

Completed:

- initial repository structure;
- curated authorial corpus;
- corpus metadata;
- first version of the authorial style profile;
- first manual Writer experiment.

Not implemented yet:

- automated Writer pipeline;
- embeddings;
- vector store;
- RAG;
- Critic agent;
- Rewriter agent;
- automated evaluation;
- feedback loop;
- API;
- user interface.

## Repository Structure

```text
authorial-writing-agent/
├── corpus/
│   ├── article-001-cloud.md
│   ├── article-002-mmm.md
│   ├── article-003-it-certifications.md
│   ├── article-004-favorite-clean-code-chapter.md
│   ├── article-005-swe-first-opportunity-in-2026.md
│   ├── ...
│   ├── post-001-presenting-pert-project.md
│   └── metadata.json
│
├── style/
│   └── STYLE.md
│
└── README.md
```

This structure will evolve as implementation begins.

Planned directories include:

```text
prompts/
evals/
feedback/
cmd/
internal/
scripts/
```

## Corpus

The corpus contains selected texts that represent my writing style.

Each text is stored as Markdown and referenced by `metadata.json`.

Example:

```json
{
  "id": "article-005",
  "file": "article-005-swe-first-opportunity-in-2026.md",
  "year": 2026,
  "type": "career",
  "format": "article",
  "quality": "canonical",
  "topics": [
    "software engineering",
    "career development",
    "artificial intelligence",
    "junior engineers"
  ]
}
```

### Metadata

#### `type`

Describes the main nature of the content.

Current domain:

```text
technical
leadership
career
opinion
personal
```

#### `format`

Describes the writing format.

Examples:

```text
article
linkedin_post
```

#### `quality`

Describes how strongly a text should influence the authorial profile.

Current domain:

```text
canonical
good
legacy
```

- `canonical`: strong representation of the current desired style;
- `good`: useful reference, but not a primary stylistic model;
- `legacy`: older writing that still has value but should receive less influence.

#### `topics`

Describes what the text is about.

Unlike `type`, topics are intentionally open-ended.

## STYLE.md

`style/STYLE.md` is the explicit representation of recurring patterns extracted from the corpus.

It describes characteristics such as:

- tone;
- reasoning structure;
- sentence rhythm;
- level of formality;
- use of technical examples;
- use of personal experience;
- preferred article structure;
- rhetorical questions;
- strong claims and caveats;
- anti-patterns associated with generic AI-generated writing.

An important principle is that the style profile should be derived from repeated patterns in the corpus rather than from assumptions about how I think I write.

## Planned Architecture

The long-term writing flow is expected to look like this:

```text
Topic + Thesis + Notes + Current Context
                |
                v
          Corpus Retrieval
                |
                v
              RAG
                |
                v
           STYLE.md
                |
                v
             Writer
                |
                v
              Draft
                |
                v
             Critic
                |
                v
            Rewriter
                |
                v
        Human Review / Edit
                |
                v
         Final / Published Text
```

## RAG

RAG stands for Retrieval-Augmented Generation.

Instead of sending the entire corpus to the model every time, the system will:

1. receive the topic, thesis, and current context;
2. search the corpus for semantically relevant writing samples;
3. retrieve the most useful excerpts;
4. provide them to the Writer together with `STYLE.md`;
5. generate the draft using those examples as stylistic context.

The corpus teaches through examples.

`STYLE.md` teaches through explicit rules.

They serve different purposes.

## Feedback Loop

The system is also intended to learn from the difference between what the AI generates and what I actually keep.

Planned flow:

```text
Generated Draft
      +
Human Final Version
      |
      v
 Editorial Diff
      |
      v
Recurring Patterns
      |
      +--------------------+
      |                    |
      v                    v
Update Corpus      Suggest STYLE.md Changes
```

A published or accepted article can become a new corpus example.

Repeated editorial corrections may eventually suggest new rules for `STYLE.md`.

The system should not modify `STYLE.md` autonomously.

Human approval remains required.

## Authorial Safety

The system should preserve authenticity without introducing unnecessary personal exposure or inventing sensitive context.

It should:

- avoid fabricating personal experiences;
- avoid turning inferred traits into explicit personal claims;
- avoid exposing unnecessary sensitive details;
- distinguish individual experience from general claims;
- preserve user-provided boundaries;
- keep factual context separate from stylistic imitation.

Authenticity should not require unlimited disclosure.

## Development Roadmap

The project is being built incrementally.

### Phase 1 — Corpus

- create repository;
- select representative texts;
- convert texts to Markdown;
- create metadata.

### Phase 2 — Style Profile

- identify recurring authorial patterns;
- create `STYLE.md`;
- document anti-patterns.

### Phase 3 — Manual Writer MVP

Input:

```text
topic
thesis
context
notes
format
```

Context:

```text
STYLE.md
+
manually selected corpus examples
```

Output:

```text
Markdown draft
```

The purpose of this phase is to validate whether the style model works before adding infrastructure.

### Phase 4 — Evaluation

- create controlled writing cases;
- compare generated texts with expected authorial characteristics;
- define qualitative style metrics.

### Phase 5 — RAG

- generate embeddings;
- create vector store;
- implement semantic retrieval;
- add metadata-aware retrieval.

### Phase 6 — Writer / Critic / Rewriter

Implement a pipeline where:

```text
Writer -> Critic -> Rewriter
```

Each stage has a separate responsibility.

### Phase 7 — Learning Loop

- persist generated drafts;
- persist human-edited versions;
- generate editorial diffs;
- identify recurring corrections;
- propose improvements to `STYLE.md`.

### Phase 8 — Productization

Possible future additions:

- Go backend;
- REST API;
- article workspace;
- style score;
- corpus management;
- review interface.

## Possible API

A future endpoint may look like:

```http
POST /articles/draft
```

Example input:

```json
{
  "topic": "AI-assisted software development",
  "thesis": "AI can accelerate implementation, but engineering judgment remains essential.",
  "context": [
    "More engineering teams are adopting coding agents",
    "Generated code still requires review and contextual validation"
  ],
  "notes": [
    "Fundamentals matter",
    "Product context matters",
    "Good prompts depend on good technical judgment"
  ],
  "format": "article"
}
```

## Technology Direction

The project is expected to explore:

- Go;
- LLM APIs;
- embeddings;
- vector search;
- RAG;
- prompt engineering;
- evaluation;
- feedback loops;
- domain-oriented architecture.

The exact infrastructure is intentionally not fixed yet.

The objective is to introduce complexity only when the previous stage has already demonstrated value.

## Philosophy

This project follows one central principle:

> The model should help write the article, not invent the author.

The ideal workflow starts with something like:

```text
Thesis:
Producing code is becoming cheaper with AI.

Context:
Junior engineering roles are increasingly competitive.

Arguments:
- fundamentals matter;
- product understanding matters;
- AI output still needs judgment.
```

And produces a draft that feels consistent with the author's existing writing without replacing the original thought process.

## License

This is currently a personal experimental project.

Licensing decisions may change as the implementation evolves.