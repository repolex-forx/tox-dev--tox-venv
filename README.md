# Repolex Knowledge Graph of tox-dev/tox-venv

RDF knowledge graph data for [tox-dev/tox-venv](https://github.com/tox-dev/tox-venv), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download tox-dev/tox-venv
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── dab94edb9612897e95fa330d187b9e87fcab1350
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── dab94edb9612897e95fa330d187b9e87fcab1350
│           └── chunk-001.nq.gz
├── blob
│   ├── 069445bcf5e5a645daccb0356e2440d4625dcedd.nq.gz
│   ├── 0dd6011703b8a6e5a845608777d826aab83a59b0.nq.gz
│   ├── 2422d2ce315ce12f6f8a73d69fb045bf1b5da2da.nq.gz
│   ├── 43f3b28c74e320cbd9d524b34fc2beb81d784089.nq.gz
│   ├── 5ed470ad72e287f6b2dcdc0d08174308df0ec11c.nq.gz
│   ├── 7250ab0cab4e2e3961f6b77ff059325d72b76d49.nq.gz
│   ├── 84229f457bb049aca8293530623abac81690b239.nq.gz
│   ├── 8b36b3b626840f87281aabd564a57c70ad69f655.nq.gz
│   ├── 8e25c88b28e1e117d8a388e6c3cd710fc07daf94.nq.gz
│   ├── 9f4e75492c61eba7bf8ed45a8d78b84e58751e3e.nq.gz
│   ├── a5f3d156a76a578d5b5743936d6ac3ee91e8be96.nq.gz
│   ├── c1f55bf4cd178af58d0b6bb43f5a2cb78900c1f8.nq.gz
│   ├── db92dc7ed540fa1fff1b9dbc06ce6b9239fcac72.nq.gz
│   ├── dd8933da25cf041fcc84cfe29ffea73af8216c0a.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── dab94edb9612897e95fa330d187b9e87fcab1350.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[tox-dev/tox-venv](https://github.com/tox-dev/tox-venv)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
