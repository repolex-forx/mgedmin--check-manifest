# Repolex Knowledge Graph of mgedmin/check-manifest

RDF knowledge graph data for [mgedmin/check-manifest](https://github.com/mgedmin/check-manifest), parsed by [repolex](https://repolex.ai).

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
rlex download mgedmin/check-manifest
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5073ecd69f872358611507c3d09409b1b5df2971
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5073ecd69f872358611507c3d09409b1b5df2971
│           └── chunk-001.nq.gz
├── blob
│   ├── 0019e50511ed0109815b8669923edee0023f63c1.nq.gz
│   ├── 182fe947da6d3e73d24ea30db4452478b2795689.nq.gz
│   ├── 329185f69e1ae2bc29f6b493e8d310e69c4a99b0.nq.gz
│   ├── 39057d9b8ccc25bf7647df72d943183f7b01292a.nq.gz
│   ├── 436d29f5cc3963b04c56413dbfe7127d7312339b.nq.gz
│   ├── 6966d94ab1d156c7ba6c7693dc22ffcd0135a249.nq.gz
│   ├── 6d8cc4355850d5a19fb6d1b7cb7c5f239b222a22.nq.gz
│   ├── 6fc1f24e5755f8126c3fa9c0319645dd8b431a00.nq.gz
│   ├── 7e06ce5a1e22aadb5e316dd4b834c9af72d5f75a.nq.gz
│   ├── 81e404e086451f085edfd251ed7c3ec897039793.nq.gz
│   ├── 8473b34e4e7baec42f9a9cb683c9f9559ba639e6.nq.gz
│   ├── 9bf7038d9aad1e8af24116170b0c9de63204c07a.nq.gz
│   ├── b8f05225dc00a16d67304a9ef41c3edaf5b14d26.nq.gz
│   ├── bbc64a4093e8e8f715d477287fa4e3dbff688978.nq.gz
│   ├── de19fefcb9bfc737468827022f64de119925df2b.nq.gz
│   ├── e3a8a8b36e1f1fe66edd7e962b4b5dd646982587.nq.gz
│   └── e47dbe4e5a62eda8138e24dd5c0c9d65fbaeb077.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5073ecd69f872358611507c3d09409b1b5df2971.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[mgedmin/check-manifest](https://github.com/mgedmin/check-manifest)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
