# Repolex Knowledge Graph of jaraco/jaraco.modb

RDF knowledge graph data for [jaraco/jaraco.modb](https://github.com/jaraco/jaraco.modb), parsed by [repolex](https://repolex.ai).

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
rlex download jaraco/jaraco.modb
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 66cebd9b315631341b0c66d308cc18ee643f50e2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 66cebd9b315631341b0c66d308cc18ee643f50e2
│           └── chunk-001.nq.gz
├── blob
│   ├── 1f2aa7533b0423a8eb943f6f4ec02498e39581a0.nq.gz
│   ├── 2e3f4dd791a6372b427d618eb0baa8c4dc58e5f0.nq.gz
│   ├── 304196f81e11a168c9894f966e4a617ebf4ed53c.nq.gz
│   ├── 3c03fccda18b7ad99e97b1735e9598614527d7a5.nq.gz
│   ├── 54c9000ec94341dd65c2053251b85b124017b9b5.nq.gz
│   ├── 54cc8303b22089e12053e552d4e6cb852a865b8a.nq.gz
│   ├── 577e87a793a20e413f7321f4f17ec1eba2ea1962.nq.gz
│   ├── 5bdc232005af9be104a00437ae9bc64417a4c1cc.nq.gz
│   ├── 5c05f9e27d57a4b7a3c3a9fdfecf8cddb8be499f.nq.gz
│   ├── 6f57ca775a4517e8a5bb88b99099c208a2db66e2.nq.gz
│   ├── 700235be57c1b2872455c0be5333f59cf568e252.nq.gz
│   ├── 724370638fc188317bbc7dc868f1a571995fd796.nq.gz
│   ├── 9a0f3bce1395ae3819030b822e5d9076c85068ea.nq.gz
│   ├── a65dd4e7ba3d101c712be600d8f668cafd7b6f43.nq.gz
│   ├── aedde4c218e102d1b2d6b9bc28b20971e4e14d15.nq.gz
│   ├── c8f371adba2440dda41e9221ec7c32f930b8f1c3.nq.gz
│   ├── dde60f3e9280073396887bdafe46490f410988f9.nq.gz
│   ├── e05a3d4a2ab888e32952006d8cd380864368db5f.nq.gz
│   ├── e39da214382264e80cd25238bcae3ff4e7d946bf.nq.gz
│   ├── e3a8059e486dc325453610a185cd3a466debb4b7.nq.gz
│   ├── eeeba182951ef25e9007070788091a8ac737829b.nq.gz
│   └── efcb8cbc2043faa7caf4f92fc7488bd6914c934c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 66cebd9b315631341b0c66d308cc18ee643f50e2.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 29 files
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

[jaraco/jaraco.modb](https://github.com/jaraco/jaraco.modb)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
