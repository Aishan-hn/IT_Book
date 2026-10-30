# The Art of IT Management

**Strategies, Techniques, and Leadership**

A practical book for aspiring and experienced IT managers. Twenty-two chapters, seven parts, a continuous worked case, and a library of ready-to-use templates.

---

## Status

| Part | Chapters | State |
|---|---|---|
| Front matter | — | ✅ Drafted |
| I. Foundations | 1–3 | ✅ Drafted |
| II. Governance and Organization | 4–6 | ⬜ Planned |
| III. Delivery | 7–9 | ⬜ Planned |
| IV. Risk, Security, and Resilience | 10–12 | ⬜ Planned |
| V. Financials and Value | 13–15 | ⬜ Planned |
| VI. Transformation and Innovation | 16–18 | ⬜ Planned |
| VII. People and Leadership | 19–22 | ⬜ Planned |
| Appendices A–E | — | ⬜ Planned |

## Repository layout

```
AI_Book/
├── README.md                  This file: map, conventions, build notes
├── book/
│   ├── 00-front-matter.md     Title, preface, how to use, cast of characters
│   ├── 01-role-of-it-manager.md
│   ├── 02-understanding-the-business.md
│   └── 03-it-strategy-and-planning.md
├── templates/                 Standalone, fillable templates
│   ├── stakeholder-map.md
│   ├── capability-heat-map.md
│   └── strategy-on-a-page.md
├── appendices/                (planned)
└── case-studies/              (planned) long-form cases
```

## How the book is built

Every chapter follows the same eight-part rhythm, so you always know where to look:

1. **Learning objectives** — what you will be able to do afterwards.
2. **Opening scenario** — a decision faced by Meridian Group's IT leadership.
3. **Core concepts** — the ideas, models, and vocabulary.
4. **Step-by-step method** — a repeatable procedure with inputs, outputs, and owners.
5. **Case study** — a real organization, what it did, what it cost, what transferred.
6. **Templates and tools** — one worked example, filled in.
7. **Pitfalls and checklist** — how this goes wrong, and a pre-flight list.
8. **Takeaways, questions, reading** — for retention and for teaching.

### The Meridian thread

A fictional composite company, **Meridian Group**, runs through all twenty-two chapters. Each chapter advances its story by one decision, so you see a strategy become a roadmap, a roadmap become a funded portfolio, and a portfolio become a governed, secure, staffed operation. The cast and starting conditions are in `book/00-front-matter.md`.

Meridian is deliberately unremarkable: 4,500 employees, three divisions, a ninety-person IT function, an aging core system, a half-finished cloud migration, and a board that has just discovered cyber risk. Most readers will recognize it.

### Real cases

Real-world cases are drawn from public reporting, company disclosures, regulator findings, and published post-incident reviews. Where a figure is quoted, it is a figure the organization or a regulator published. Where the public record is thin, the case describes the mechanism and the documented sequence of events rather than inventing numbers. Sources for further reading appear at the end of each chapter and are consolidated in Appendix E.

### Conventions

- **Bold** introduces a term defined in the glossary.
- `Monospace` marks a field name in a template.
- Tables compare options; diagrams show flow or structure.
- Diagrams are written in **Mermaid** so they render on GitHub, in VS Code, and in most Markdown toolchains.
- "In practice" boxes give the short version for a busy week.
- Word budgets are advisory, not enforced.

## Building a single manuscript

With [Pandoc](https://pandoc.org) installed:

```bash
# Single Markdown file, in reading order
pandoc book/00-front-matter.md book/01-*.md book/02-*.md book/03-*.md \
  -o manuscript.md --wrap=none

# Word document with a table of contents
pandoc book/*.md -o "The Art of IT Management.docx" \
  --toc --toc-depth=2 --reference-doc=reference.docx
```

For Mermaid rendering in DOCX/PDF, export diagrams to SVG first (`mmdc -i diagram.mmd -o diagram.svg`) and reference the image files.

## Audience

- **Newly appointed IT managers and team leads** moving from doing to leading.
- **Experienced managers** who need the governance, financial, and transformation vocabulary their executives already use.
- **Aspiring CIOs** building a portfolio of evidence for the next role.
- **Business leaders** who want to know what good IT management looks like from the inside.

No prior management training is assumed. Some familiarity with IT operations, projects, or software delivery helps but is not required.

## A note on honesty

Management writing fails when it promises certainty. This book does not. It gives you frameworks that have survived contact with real organizations, tells you where they break, and shows you the judgment calls that no framework can make for you. Where the evidence is contested — agile scaling, maturity models, outsourcing economics — the text says so.
