# Repolex Knowledge Graph of falconry/pecyn

RDF knowledge graph data for [falconry/pecyn](https://github.com/falconry/pecyn), parsed by [repolex](https://repolex.ai).

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
rlex download falconry/pecyn
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fef9333136c717855499f90ec0180d6a75059a9d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fef9333136c717855499f90ec0180d6a75059a9d
│           └── chunk-001.nq.gz
├── blob
│   ├── 03b7ce3ce6307859e042e7f7a9b3d606a83c4619.nq.gz
│   ├── 246861a296215789147f11b3244eede7add569c1.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 5d4147416970cc3bf33ab27a37cc669cd63b9b09.nq.gz
│   ├── 690caa8d0f9b86b2722dd16f3dad9fd4488bdadc.nq.gz
│   ├── 71cc600762e73e87480bfc6ac82a07b35e62a6ce.nq.gz
│   ├── 7a79b82cc9036b8a46c877b5cd384b57ad7ddd75.nq.gz
│   ├── 9a2340e66bdd6f0b46c831a1b11ee6813156ae58.nq.gz
│   ├── a245ecde6d41980428c8dd4c1b32506d09474e5f.nq.gz
│   ├── a3990419b103e8420e8b531e28b5ada8d2412269.nq.gz
│   ├── a9a6ca197b70d58db8bc052f2f4ac441e696fdbe.nq.gz
│   ├── b3f8b52dd3dd0633ab7ccd4ceb76046f36e62de8.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f3867474a73c2162ba043ef368dbf35aec5c050c.nq.gz
│   └── f6beb1b0cb661adb403b8e66b4b58d637d021169.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fef9333136c717855499f90ec0180d6a75059a9d.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 22 files
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

[falconry/pecyn](https://github.com/falconry/pecyn)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
