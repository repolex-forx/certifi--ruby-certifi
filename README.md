# Repolex Knowledge Graph of certifi/ruby-certifi

RDF knowledge graph data for [certifi/ruby-certifi](https://github.com/certifi/ruby-certifi), parsed by [repolex](https://repolex.ai).

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
rlex download certifi/ruby-certifi
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 101b2e2ed59c88b841050fc27a68f712f211d036
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 101b2e2ed59c88b841050fc27a68f712f211d036
│           └── chunk-001.nq.gz
├── blob
│   ├── 19906abbab0eb8315c15378a15cbaf840bea55a1.nq.gz
│   ├── 1f8776cad66452c742e518b5f07442267792fbd0.nq.gz
│   ├── 31cafb5d8865b0cff5237214f9f4401f9f453f10.nq.gz
│   ├── 5900697866ce070e4a8d102cf529a1aa377cfdeb.nq.gz
│   ├── 802b53ff11e347c9bd2cabebeff5c51f716f1db9.nq.gz
│   ├── a37b22e2d57c8167d29e4700f90d095ad7ea5158.nq.gz
│   ├── b5271f94ddcc12e2e7bb9f9de8d2e24afc4037e7.nq.gz
│   ├── cae1dec3abe0e53b5e9931b4827899fe8b5921e1.nq.gz
│   ├── cc247abd5eafa4dbbd34f80099a59c0c5d5b12b2.nq.gz
│   ├── e474204650242c21a62ce8c59153f77106324dab.nq.gz
│   └── fb2a6c2c62b0b9a0def610db78f970e70ccbc59d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 101b2e2ed59c88b841050fc27a68f712f211d036.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[certifi/ruby-certifi](https://github.com/certifi/ruby-certifi)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
