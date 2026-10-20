# Repolex Knowledge Graph of graphql-python/flask-graphql

RDF knowledge graph data for [graphql-python/flask-graphql](https://github.com/graphql-python/flask-graphql), parsed by [repolex](https://repolex.ai).

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
rlex download graphql-python/flask-graphql
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0d45561607950b68458925537f116298fc81b4d3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0d45561607950b68458925537f116298fc81b4d3
│           └── chunk-001.nq.gz
├── blob
│   ├── 0fa13a13f82ea79ff61cc99794a900c9bce4af75.nq.gz
│   ├── 3546b1d6d326a243bb84dc9048e9831457716054.nq.gz
│   ├── 4a557101bb04e7becddbd97932a6eaf58610dd12.nq.gz
│   ├── 52554b12f7440a86754a78a204d31dace2e3346d.nq.gz
│   ├── 5b3ee3cfec7ff7b62383449661eb45a2dc250956.nq.gz
│   ├── 642f015bf654723c3863819074fc78c5dbe328a6.nq.gz
│   ├── 6a6be069861d34c2854970cf5ae4fca1343f1cfd.nq.gz
│   ├── 72ab3650db0b43e1efa4c3765ad0fd02e2143801.nq.gz
│   ├── 84f1d23d838058f37efb7673420fb25d93c2cfb3.nq.gz
│   ├── 961a8e022547fe98908ba78b2a1d261d80810212.nq.gz
│   ├── a6f33e3d914c85cab68f5bdb26f452bfeab56ad2.nq.gz
│   ├── b6ff2043f2cc918fa4bdf6f3de58edf53146f133.nq.gz
│   ├── d8a626ef9123c936747cbb54da6b6c5ceedf9b25.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fdb5c9a144dfcc0a26fe3bbd0cbf5137b6561ceb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0d45561607950b68458925537f116298fc81b4d3.nq.gz
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

[graphql-python/flask-graphql](https://github.com/graphql-python/flask-graphql)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
