# Repolex Knowledge Graph of simonw/condense-json

RDF knowledge graph data for [simonw/condense-json](https://github.com/simonw/condense-json), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/condense-json
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 27e812f0765c396eb9f21c7e5172667290c0a9c0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 27e812f0765c396eb9f21c7e5172667290c0a9c0
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c7715b8ee8dcfd39f5064f7916637fd7b1c4a9c.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 73af8722d78bd3e731e998eaad2f801603ee36b2.nq.gz
│   ├── 8945bd1f5e952902c06c843e14b13615f36788a5.nq.gz
│   ├── 8eef534a2cade6cf30a565ec8722775d55930845.nq.gz
│   ├── 91a9b8613fa39c5f518f3f7bac94e530c0783f1f.nq.gz
│   ├── c34f99089c038b4e14be43b69caa22f80ffbd46b.nq.gz
│   ├── c4ef7ce7500fe5e5699faf05ae4ce59efa14225e.nq.gz
│   ├── d64917c60fb90a5553676e17b6054ad15ec22341.nq.gz
│   ├── e4e129e53b908c5d1d557ff69fe36ad2fe07f966.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e79a3e743e2f481dcb565d841143553205133061.nq.gz
│   ├── eee2e1391bca184df7f641acae808de92719b978.nq.gz
│   ├── f8c24f1c78ee59299507241e6bc4414dab376a8f.nq.gz
│   └── fcf228abaca31891b16a32ed40f0d55aa5553a6e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 27e812f0765c396eb9f21c7e5172667290c0a9c0.nq.gz
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

[simonw/condense-json](https://github.com/simonw/condense-json)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
