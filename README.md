# Repolex Knowledge Graph of smol-rs/atomic-waker

RDF knowledge graph data for [smol-rs/atomic-waker](https://github.com/smol-rs/atomic-waker), parsed by [repolex](https://repolex.ai).

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
rlex download smol-rs/atomic-waker
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9969a29ccd1fe298e2df7346849c0095ba303a64
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 9969a29ccd1fe298e2df7346849c0095ba303a64.nq.gz
│   └── repolex
│       └── 9969a29ccd1fe298e2df7346849c0095ba303a64
│           └── chunk-001.nq.gz
├── blob
│   ├── 09c3f9292eea39886b723a2fd6b626c017a043ce.nq.gz
│   ├── 0dd339f02a6f580270ac63e6325474045167a678.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 199d82dea00277f6ca7e0e942aebfdaf173bb708.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 52f79451880d0933ff64b9b54db861955d744dfc.nq.gz
│   ├── 574cf1f658284616513d22dc42f5401e847f75f3.nq.gz
│   ├── 59fad1f971b51f3884f8b6b71f1c02b81a3ae4d1.nq.gz
│   ├── 96ef6c0b944e24fc22f51f18136cd62ffd5b0b8f.nq.gz
│   ├── aa77d251aad59f301d94870e115505d54db9eb69.nq.gz
│   ├── d305121efc97bf77c8898aaa8daf211155218c8f.nq.gz
│   ├── df055fb9a4e31c9d2c4094ac71d4f080e4bd23a7.nq.gz
│   └── fb48c9191b3bb0f5831c6c52dfbc3cf3e9806c21.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 9969a29ccd1fe298e2df7346849c0095ba303a64.nq.gz
├── filetree
│   └── 9969a29ccd1fe298e2df7346849c0095ba303a64.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 23 files
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

[smol-rs/atomic-waker](https://github.com/smol-rs/atomic-waker)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
