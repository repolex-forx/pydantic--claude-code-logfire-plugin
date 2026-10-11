# Repolex Knowledge Graph of pydantic/claude-code-logfire-plugin

RDF knowledge graph data for [pydantic/claude-code-logfire-plugin](https://github.com/pydantic/claude-code-logfire-plugin), parsed by [repolex](https://repolex.ai).

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
rlex download pydantic/claude-code-logfire-plugin
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0f1b1172a46ae34b0d67d866a42ee75f3f3876de
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0f1b1172a46ae34b0d67d866a42ee75f3f3876de
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c0b44d4d633f4be34e26d8a3082a542388149da.nq.gz
│   ├── 0dfbd073a69c4210644e2c878d510de0668fa5bc.nq.gz
│   ├── 0fd4bf090a5703961325ba9f23310bb656f19ca1.nq.gz
│   ├── 40af9bbeb2b6cc5312d504730b85f32db8af9eb1.nq.gz
│   ├── 527373cd44ea6109f8e4cb3f3470b974184ddfc5.nq.gz
│   ├── 567871d23037cdcfbf0cbd76316b77b03109d93a.nq.gz
│   ├── 5e51eacd288e98c6f3546efcedb0902e334bb464.nq.gz
│   ├── 80265dd3280cd798c23e3138b04c56c2807417c9.nq.gz
│   ├── 8d7ef4278286587a3ace0f721450ea6096e2902f.nq.gz
│   ├── 8e3212c627ca1ec4df88f5bc59776c7e731696ad.nq.gz
│   ├── a71c80c5655329cbe8448bc8f25735fd91c89e93.nq.gz
│   ├── b691e99375a8949c793998f8361263d18e89044a.nq.gz
│   ├── c17b93c3afe5c498ff304727e55e2ed7f3dd8233.nq.gz
│   └── f2aa567d56bfcf8fd9037a19bc522dfd40b3f5b7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0f1b1172a46ae34b0d67d866a42ee75f3f3876de.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[pydantic/claude-code-logfire-plugin](https://github.com/pydantic/claude-code-logfire-plugin)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
