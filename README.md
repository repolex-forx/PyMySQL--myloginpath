# Repolex Knowledge Graph of PyMySQL/myloginpath

RDF knowledge graph data for [PyMySQL/myloginpath](https://github.com/PyMySQL/myloginpath), parsed by [repolex](https://repolex.ai).

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
rlex download PyMySQL/myloginpath
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2dc7b2d23208a68e9b5278fdc53f5b01894bbe82
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2dc7b2d23208a68e9b5278fdc53f5b01894bbe82
│           └── chunk-001.nq.gz
├── blob
│   ├── 051bc2716df9863427375b3d53e776c29d933e83.nq.gz
│   ├── 0f456e6da34d6f7d6a19dab16b2c6747e9856f11.nq.gz
│   ├── 130b9a3f0f009b5bd30b3a67c276e2861899e65b.nq.gz
│   ├── 1558e0314bdef8e0eadcc889192a738d899ff211.nq.gz
│   ├── 2ec13a7429ae73dc8415e38b8a2e96f8c628c81f.nq.gz
│   ├── 35f3d1b37c1762f600c76e5c68cafe9f5c55d916.nq.gz
│   ├── 39a2b6e9a55b8aaa96d0ee0e1c8f956c5c662e75.nq.gz
│   ├── 5480d8549759c30edfa62c9c5e51f91b27ce2a8f.nq.gz
│   ├── 6ea8da22a7290c611dfab23406f5725d767b155d.nq.gz
│   ├── 7b2c36913c63d66f66f17e407fe4a86193dd4077.nq.gz
│   ├── a54f2b28726b63e55607f97c1d35e525f836ca97.nq.gz
│   ├── ad0709aa1a74dccb43dfa71269110a0712b6bfdf.nq.gz
│   ├── e65215d9a42117fe69399a502446d92c080bbbd8.nq.gz
│   ├── e974383db1552ec4a192e6c2226d74fa2c7dea06.nq.gz
│   └── f80630cc5cc67a8c50a94d0bd489667bd63b6ab1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2dc7b2d23208a68e9b5278fdc53f5b01894bbe82.nq.gz
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

[PyMySQL/myloginpath](https://github.com/PyMySQL/myloginpath)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
