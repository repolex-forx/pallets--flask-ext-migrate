# Repolex Knowledge Graph of pallets/flask-ext-migrate

RDF knowledge graph data for [pallets/flask-ext-migrate](https://github.com/pallets/flask-ext-migrate), parsed by [repolex](https://repolex.ai).

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
rlex download pallets/flask-ext-migrate
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 913e598e602979959a095d93057a6f7e0f3e0e05
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 913e598e602979959a095d93057a6f7e0f3e0e05
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a1005fb80541eff3023908c1b261174c50f34a7.nq.gz
│   ├── 0fe04a342d853adcd545a3558bd1c057842d9cbd.nq.gz
│   ├── 2b07072a6a31b73e9f1278b06fccdf81a6620ab9.nq.gz
│   ├── 41c230ca54899094a6f4f1bcc93159269a6dc51b.nq.gz
│   ├── 49ae4100e9c58f269f56b6bf4af6f17af919298b.nq.gz
│   ├── 4bf5d8ee3f66423172f4e835e5b7af3e8abf923f.nq.gz
│   ├── 58f9a1daf12905a30925f1e0ab57630fa8eb5ab1.nq.gz
│   ├── 7541e187073f84d5c64874b0b878021648629614.nq.gz
│   ├── 77a8cc9972a149321fc338693b158d4a3e93c114.nq.gz
│   ├── 98a3a26b5cd3b5602e3e0126294cc9db0a8d9d03.nq.gz
│   ├── bb8f9cbd16da383c1719e50273169cf21be70920.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fb09488773f4c34142047fd6042916ef1e6e8944.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 913e598e602979959a095d93057a6f7e0f3e0e05.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[pallets/flask-ext-migrate](https://github.com/pallets/flask-ext-migrate)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
