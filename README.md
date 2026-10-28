# Repolex Knowledge Graph of scikit-hep/vegascope

RDF knowledge graph data for [scikit-hep/vegascope](https://github.com/scikit-hep/vegascope), parsed by [repolex](https://repolex.ai).

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
rlex download scikit-hep/vegascope
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 774b2a0fc4624fb38647f1681469ba73e7172c50
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 774b2a0fc4624fb38647f1681469ba73e7172c50
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b4d86835d54de6c046d9123ad65ac0328af2d6c.nq.gz
│   ├── 3b95243a246f46af71031efae567ae072a5d38b5.nq.gz
│   ├── 5100e5212b074db3b5cb81c1384731c8591ce178.nq.gz
│   ├── 70ce07a58ee368f0cd5b6a69a31ff3317e9414ac.nq.gz
│   ├── 7bbc71c09205c78d790739d246bbe4f9f1881c17.nq.gz
│   ├── 9916a766cc1cf164739cf127f1933d26d1f29e1e.nq.gz
│   ├── b6145f1050ba8b9bbc67dc2b43bbec903379b9fb.nq.gz
│   ├── bbee4c8876bb1d9d7005758f7339023f8a31d9bb.nq.gz
│   ├── bca44eff2f27b7d92c904678bb2a191b5285bce0.nq.gz
│   └── d9e709345d200bfa53063eab48d4a983bc285c51.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 774b2a0fc4624fb38647f1681469ba73e7172c50.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[scikit-hep/vegascope](https://github.com/scikit-hep/vegascope)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
