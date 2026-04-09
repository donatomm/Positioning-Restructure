# _KB-SCHEMA.md
> Positioning Knowledge Base — Schema Definition
> Topic: `positioning` | Maintained by: DMM

---

## Frontmatter Spec

Every file in this KB must open with this frontmatter block. No body content before the closing `---`.

```yaml
---
topic: positioning
subtopic: ""
use_case: []
source: ""
format: ""
status: draft | released | working-release
tags: []
---
```

---

## Controlled Vocabulary

### `subtopic`
Pick exactly one.

| Value | What it covers |
|---|---|
| `foundations` | What positioning is, why it matters, core theory |
| `competitive-analysis` | Defining, picking, and thinking about competition |
| `differentiation` | Differentiated value, no-differentiation situations, tech trend leverage |
| `category-design` | Category creation, mature vs. emerging markets, platform traps |
| `process-workshop` | Prep decisions, positioning exercises, worksheets, workshop formats |
| `messaging-copy` | Positioning-to-messaging bridge, homepage and LP translation |
| `sales-narrative` | Sales pitch, sales-first storytelling, enterprise selling |
| `pitfalls-diagnostics` | Mistakes, anti-patterns, positioning poison, bad positioning signals |
| `execution` | Post-positioning, testing, implementation, AI role in execution |
| `multi-product` | Multiple products, segments, and personas |
| `ai-context` | Positioning AI products, AI strategy, LLM discoverability |
| `solo-consulting` | Consultant-specific application, solo practice positioning |

---

### `use_case`
Pick one or more.

| Value | When to use it |
|---|---|
| `positioning-new-product` | First-time positioning of a new product or startup |
| `repositioning` | Changing existing positioning that is broken or stale |
| `competitive-strategy` | Choosing or responding to competition |
| `sales-enablement` | Equipping sales with positioning-derived narrative |
| `homepage-copy` | Translating positioning to homepage or LP |
| `positioning-audit` | Diagnosing whether current positioning is working |
| `category-creation` | Defining or creating a new market category |
| `multi-segment-strategy` | Positioning across multiple products, segments, or personas |

---

### `source`
Exact values only. Use `multiple` when a file blends two or more sources. Use `unknown` when origin is unclear.

`april-dunford` | `fletch` | `andy-raskin` | `emma-stratton` | `dmm` | `andy-chen` | `talya-heller` | `james-doman-pipe` | `michel-fortin` | `pierri` | `dave-gherard` | `yi-lin-pei` | `multiple` | `unknown`

---

### `format`
Pick exactly one.

| Value | Definition |
|---|---|
| `transcript` | Verbatim or near-verbatim capture from a talk, podcast, or session |
| `framework` | Structured model, methodology, or step-by-step system |
| `worksheet` | Fillable template or exercise with prompts |
| `synthesis` | Summarized or reprocessed source material |
| `case-study` | Real example with applied positioning analysis |
| `course-module` | Structured learning unit from a course or curriculum |
| `podcast-notes` | Notes or highlights from a podcast episode |
| `truncated` | Incomplete capture — source material cut short. Retrieval is partial. |

---

### `status`

| Value | Meaning |
|---|---|
| `draft` | Created and saved. Not yet in use. |
| `released` | Currently active and in production. |
| `working-release` | Previously released. Now being edited. Not current. |

---

### `tags`
Auto-generated on ingest. 3–8 keywords derived from file content. No controlled list — reflect actual concepts in the file.

---

## Body Structure

Fixed three-section order. No format constraint within sections.

```
## Summary
What this file says. 3–5 lines max.

## Content
Full material.

## Notes
Gaps, conflicts with other files, things to revisit.
```

---

## Duplicate Policy

Files prefixed with `Copy of` are presumed duplicates. Before classifying, either:
- Delete the copy and keep the original, or
- Add `duplicate_of: "original-filename"` to the frontmatter and resolve after classification.

Cowork will classify duplicates independently. Unresolved duplicates produce paired entries in the index.

---

## Cowork Prompt — Convert + Classify

> Process every file in this folder. Handle all formats: `.md`, `.pdf`, `.docx`.
>
> **Step 1 — Convert**
> For every `.pdf` and `.docx` file:
> - Extract all text content.
> - Save as a new `.md` file using the same filename (replace extension with `.md`).
> - Body structure: three sections in this order — `## Summary` (3–5 lines describing what the file covers), `## Content` (full extracted text, lightly cleaned — fix obvious OCR artifacts, preserve all substance), `## Notes` (leave blank, write only `_none_`).
> - Do not delete the original `.pdf` or `.docx`.
>
> **Step 2 — Classify**
> For every `.md` file (including newly converted ones):
> - Add the frontmatter block below at the very top of the file, before any other content.
> - Fill every field using only the controlled values in this schema.
> - Do not modify anything in the body.
>
> ```yaml
> ---
> topic: positioning
> subtopic: ""
> use_case: []
> source: ""
> format: ""
> status: draft
> tags: []
> ---
> ```
>
> **Classification rules:**
> - `subtopic` — pick exactly one from the subtopic table.
> - `use_case` — pick one or more from the use_case table.
> - `source` — identify the primary author or framework. Use exact values from the source list.
> - `format` — classify the file type. If the extracted content is clearly incomplete or cut off, use `truncated`.
> - `tags` — generate 3–8 keywords from the actual content. No generic terms like "positioning" or "marketing" — those are implied. Use specific concepts found in the file.
> - `status` — set to `draft` for all files.
