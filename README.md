# Repolex Knowledge Graph of jupyterhub/jupyterhub.github.io

RDF knowledge graph data for [jupyterhub/jupyterhub.github.io](https://github.com/jupyterhub/jupyterhub.github.io), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterhub/jupyterhub.github.io
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 12fcc920d1d350a6d0b0d9e87ecca115319708a7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 12fcc920d1d350a6d0b0d9e87ecca115319708a7
│           └── chunk-001.nq.gz
├── blob
│   ├── 0674b52dd3c7c37c40de18fa58b7b1bb9c626a19.nq.gz
│   ├── 22f0a2f71e864a8eedcbf035245282532ac93c6a.nq.gz
│   ├── 2884039f6e6a60a490900c8edec03b1dba2cd11e.nq.gz
│   ├── 449d9efac44df378370596281aee815690fc099c.nq.gz
│   ├── 495e49d77f5822b4d1b4145e9c37ed18ae8deed7.nq.gz
│   ├── 57e371dbed2f3871ffba04568d04084f2433ae31.nq.gz
│   ├── 7471799bcf41d07da63866d21bde873b8b3eebdf.nq.gz
│   ├── 76f5fa84b1b7a49c1bc80dd5dd18754a6db0b2ca.nq.gz
│   ├── 79d231db65c2c668d6a8386277bab23b8cfcbcde.nq.gz
│   ├── 7b571cfef42a205624b0e8f40cee4b24067e218d.nq.gz
│   ├── afb5743e02bb4fa319b3c80d19ea4c42487141d2.nq.gz
│   ├── b6235328d28d70923e7dd844765d612eacd972a1.nq.gz
│   ├── b73ee5549cb4407f8ea6880d0c76bae123b8906e.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e919b1e5a7b9404aab2308676816df377e84851c.nq.gz
│   └── fcb6989c6102d306a32ab76b226c4e4ac92f66aa.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 12fcc920d1d350a6d0b0d9e87ecca115319708a7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[jupyterhub/jupyterhub.github.io](https://github.com/jupyterhub/jupyterhub.github.io)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
