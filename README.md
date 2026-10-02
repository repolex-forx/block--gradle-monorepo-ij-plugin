# Repolex Knowledge Graph of block/gradle-monorepo-ij-plugin

RDF knowledge graph data for [block/gradle-monorepo-ij-plugin](https://github.com/block/gradle-monorepo-ij-plugin), parsed by [repolex](https://repolex.ai).

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
rlex download block/gradle-monorepo-ij-plugin
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a485c87aff20d3a9bb1799559ae3d94f3142aa36
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── a485c87aff20d3a9bb1799559ae3d94f3142aa36.nq.gz
│   └── repolex
│       └── a485c87aff20d3a9bb1799559ae3d94f3142aa36
│           └── chunk-001.nq.gz
├── blob
│   ├── 0367d2331a2cbfb3dadb43da08affe106a235c28.nq.gz
│   ├── 081cbe83449cf8e625a3e2e79b6b35415c4e1503.nq.gz
│   ├── 1126981a3ffba6ffe655b5a837bfd43c9fac2231.nq.gz
│   ├── 11d81a5a7d6dc067ed2a3d3c88d4eb7cd4a04772.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2d21bb477db924bedc297d40817324edf7a8ca15.nq.gz
│   ├── 311345006807b6e17d4a0af2f16c3fe7468a4e82.nq.gz
│   ├── 31559b7d115e3c105b328cce9b9dcd9774025061.nq.gz
│   ├── 3440ffd4406a4c1b1719c8f0219427570668a89c.nq.gz
│   ├── 364f4b0b8d1625f76d6b1ab8c73189d9c99e9e06.nq.gz
│   ├── 383f4511d444516caed0fd113ee8a2b640cd2290.nq.gz
│   ├── 386590922afdb02b216a0d12a0d6947b101c11ba.nq.gz
│   ├── 4b56c9448ef02d2dbbb9e8293845d230ff88f009.nq.gz
│   ├── 56880e5036201884a32034bc96225cd39cadbc3a.nq.gz
│   ├── 58d016aae9ccfd9bd5141399c14865fb00949fbf.nq.gz
│   ├── 5a429731a9b8e026bf99b93391769ea9fecbe1f1.nq.gz
│   ├── 61e1f1ac617691a41ba458dbb919a8430501fa99.nq.gz
│   ├── 6bccf43368fd7c96d9c659562a5142b8b8cb98a1.nq.gz
│   ├── 739907dfd15937f032b5a46390e9d63709e87f7a.nq.gz
│   ├── 81bce670dbc21b735f43809e99d5604f50431050.nq.gz
│   ├── 9fd327e7bfc6c91b27b8d70092990dbf7135c037.nq.gz
│   ├── a79576a8d6827a9b9dfae46baacf87b316b8c479.nq.gz
│   ├── c3f25d810a01168cfe63cfac172f41f2d1159c58.nq.gz
│   ├── c54b4795c7e9073573cd337798156c37095579ae.nq.gz
│   ├── c61a118f7ddb21223f1a2fdd05f6aec1b9863aec.nq.gz
│   ├── c97c2b88980d286ed7d287a5cdf6ffa467ca01bf.nq.gz
│   ├── cd0a80988307477eda75700f6a5943cf7394f1d4.nq.gz
│   ├── cf4188aa98ce0df2808cd92e10156e69ba5d737e.nq.gz
│   ├── d997cfc60f4cff0e7451d19d49a82fa986695d07.nq.gz
│   ├── db879f914599dfc1c93c276ac08619a6baeef437.nq.gz
│   ├── e509b2dd8fe5579a5954a2c28633ad914cd1c225.nq.gz
│   ├── e889550ba4cbc92a720527042e5f6e7a303bfcbc.nq.gz
│   ├── f7766a37dc3382050c4b99f2da2946bc1477a208.nq.gz
│   └── fe28214d3352b0ed40820a4999317694c8b1ef57.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a485c87aff20d3a9bb1799559ae3d94f3142aa36.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 43 files
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

[block/gradle-monorepo-ij-plugin](https://github.com/block/gradle-monorepo-ij-plugin)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
