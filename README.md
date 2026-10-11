# Repolex Knowledge Graph of agronholm/pythonfutures

RDF knowledge graph data for [agronholm/pythonfutures](https://github.com/agronholm/pythonfutures), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/pythonfutures
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 738e37148b2f7ecd86cbb8c271f9e033ae66eff8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 738e37148b2f7ecd86cbb8c271f9e033ae66eff8
│           └── chunk-001.nq.gz
├── blob
│   ├── 063077578f97b1ee6fe7f1fabe5c02d7358fda0f.nq.gz
│   ├── 0a9f4f521d34ec3669e0d9b9ff4714e3769b133d.nq.gz
│   ├── 0da2b3e64c34bc4efaf7740c1988587ad03125a9.nq.gz
│   ├── 13050037f7c33acbc8dad71420cbb44bb7cada00.nq.gz
│   ├── 37156bad1675dfbe88ed783ad7cb3a0efe1833e1.nq.gz
│   ├── 3e8021b56e5fdcd7dedf614501e6fa8d90f42516.nq.gz
│   ├── 428b14bdfe4cd734ce8d147c05537dea19d9be29.nq.gz
│   ├── 52860d0435a368ad1937bbd5c9770ffe99715f07.nq.gz
│   ├── 5cea44c8819730e27f5ac264e6e5a8c933a2ac92.nq.gz
│   ├── 6405445cb0d19dfe8bbf2a759aab49efec1647e8.nq.gz
│   ├── 7be4dc3f1f6c648fcbfee34978e098838154e7a6.nq.gz
│   ├── 86e0af7fe6f309dc626f7f47e4da2b326c1ca5f1.nq.gz
│   ├── a8d65b16b600cfb21829642e7fe99fb57c9eda55.nq.gz
│   ├── b36383a61027f0875a3cb103edc8f2a4528a3289.nq.gz
│   ├── b9685cefe5a283f168803927b3007e890dbe6abc.nq.gz
│   ├── bb327faf05ce3c41563d00cfe65e6a76dbc00b37.nq.gz
│   ├── d74cadea33efea661ca4967ed70825dcb6f817c1.nq.gz
│   ├── f69d8403539380d92c51d9c69690ace4cb4cafdc.nq.gz
│   ├── f7f525f6f1a9ec675c49735e4979b6ee0c67ce64.nq.gz
│   ├── f9d02ae930350b1073c237b43d2f51ff0cb82361.nq.gz
│   └── fdff7cb4c89ce75d24aa86f97f252b88ad11c439.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 738e37148b2f7ecd86cbb8c271f9e033ae66eff8.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[agronholm/pythonfutures](https://github.com/agronholm/pythonfutures)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
