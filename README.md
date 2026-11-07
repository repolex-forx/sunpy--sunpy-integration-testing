# Repolex Knowledge Graph of sunpy/sunpy-integration-testing

RDF knowledge graph data for [sunpy/sunpy-integration-testing](https://github.com/sunpy/sunpy-integration-testing), parsed by [repolex](https://repolex.ai).

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
rlex download sunpy/sunpy-integration-testing
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8f39d77fd7e0c31c65ad43630b3b42423305aee0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8f39d77fd7e0c31c65ad43630b3b42423305aee0
│           └── chunk-001.nq.gz
├── blob
│   ├── 3d78fa06406d1850f81f745cc615a4e854a32447.nq.gz
│   ├── 40d95d374340eb42f97ecaf8e218548b27b05e24.nq.gz
│   ├── 4e840617024ca81d8748e2c4bbf56d216c2bfff6.nq.gz
│   ├── 7417a4fa28bb804c04c7e0f7d250c29b281372f3.nq.gz
│   ├── acb4e3eb8a20bab4351e200a05bcf7d94460cfc5.nq.gz
│   ├── c765c24e524a5ef9a4caaf41d20ff5698d2bc835.nq.gz
│   ├── cab1acc713b9d2ce6450e82e7f4b4c868e85dd1f.nq.gz
│   └── d581eb97ca5cbcf12d651eb7b4e1e0af237fd45f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8f39d77fd7e0c31c65ad43630b3b42423305aee0.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 15 files
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

[sunpy/sunpy-integration-testing](https://github.com/sunpy/sunpy-integration-testing)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
