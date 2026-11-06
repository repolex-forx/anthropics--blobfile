# Repolex Knowledge Graph of anthropics/blobfile

RDF knowledge graph data for [anthropics/blobfile](https://github.com/anthropics/blobfile), parsed by [repolex](https://repolex.ai).

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
rlex download anthropics/blobfile
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e8d35f07e4fcc40206a69f4cbf0765da9f66c920
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e8d35f07e4fcc40206a69f4cbf0765da9f66c920
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b398eade1db59148cf99766448b62e421e8cb66.nq.gz
│   ├── 2d926d3ca0daba4e59d898ade49bf212ab12fcc3.nq.gz
│   ├── 2eee8595ba2ce41a6ce0d69ddacf3f4303b73373.nq.gz
│   ├── 2f4de62820b5e7d163a327581e7649587bb57380.nq.gz
│   ├── 3e3c2f1e5edb083aab93646ac7b076daa38516dd.nq.gz
│   ├── 448c201d8f7a61f168e23023e12e57649b9138f8.nq.gz
│   ├── 546d278e3ae8bd9f6cfdfa7215b9662ff099cf22.nq.gz
│   ├── 5b3ba1d58f9a9c50c24dde10e0581040c09c9576.nq.gz
│   ├── 6e01f088149392f281df35d8841ce97d85220bfd.nq.gz
│   ├── 7623d6621d43f055ea4e13b2eb8c4aef45a54cd1.nq.gz
│   ├── 8b21d1d821bba0c3e2231b0da5891b78f60ef5f2.nq.gz
│   ├── 91ad5f2e369001d32852a4d861eca72efbecb7c6.nq.gz
│   ├── 939ebf6fe449aebff033887a9b3cb27e1ea191c9.nq.gz
│   ├── 9fad81c85097ba61d262f705cf05224d8962c307.nq.gz
│   ├── a237f2546a5685a4f2d2f6d9e705706d23124946.nq.gz
│   ├── a4260b11482fae59a9032f8803a2241338879282.nq.gz
│   ├── c580070b280eee454fa37548cca121860909e331.nq.gz
│   ├── c931d8f68e594d54c151307fecadb03d245a3bc4.nq.gz
│   ├── cdbf451db45e41954a15baeaedd574f78c105c95.nq.gz
│   ├── d110d0783ad0847c6fc1422b751c931cba6b8202.nq.gz
│   ├── d29098c2c191d2a3e16545e47177346e11d18454.nq.gz
│   ├── e309c2b3dcfe59f587c85b1bbac57a620a9edde9.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e827daa176e3755778b54fe453f6d960871b5e48.nq.gz
│   ├── e8eb80b512a243abc5906f26e8d745d017d3a5e5.nq.gz
│   └── fe9a1054cad68057eeb96d02414ae8d333f0cf2f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e8d35f07e4fcc40206a69f4cbf0765da9f66c920.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 33 files
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

[anthropics/blobfile](https://github.com/anthropics/blobfile)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
