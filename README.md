# Repolex Knowledge Graph of python-lsp/pylsp-mypy

RDF knowledge graph data for [python-lsp/pylsp-mypy](https://github.com/python-lsp/pylsp-mypy), parsed by [repolex](https://repolex.ai).

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
rlex download python-lsp/pylsp-mypy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 738aed026f3d9e48907e22028dd97ecacedcbff0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 738aed026f3d9e48907e22028dd97ecacedcbff0
│           └── chunk-001.nq.gz
├── blob
│   ├── 075be7773999fbd05b3323bfb0341396ef006509.nq.gz
│   ├── 1b41d0a1adeac14aee2e8af8250b96fac4a1d5b4.nq.gz
│   ├── 25246b1404c4ad1edfd079530e0b32bb45d39fb7.nq.gz
│   ├── 37451c3853a6837150c31b0b422d69c841c75ddb.nq.gz
│   ├── 49e0fc1e09447ed8f5dd92db74c9d289f547a1a3.nq.gz
│   ├── 4e9c09c2aa96a20173f0cae8fc237cc6b817cdd9.nq.gz
│   ├── 5affa0ee6bc34e7b57451df31722c78aa8463d37.nq.gz
│   ├── 634e22d377d20b537f67b53211dc13b156c2f360.nq.gz
│   ├── 7bbc71c09205c78d790739d246bbe4f9f1881c17.nq.gz
│   ├── 8528df33ea343e390d9fad522d1ba6e6c26ab6af.nq.gz
│   ├── 9561fb1061f6de114633c70871232a6896dcbe8a.nq.gz
│   ├── 99a17a770a806a5c2e4d5d488ea26cee842d69a0.nq.gz
│   ├── d35466800681df49285cb2204b316b5a56f61ac7.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── faa83ca4ad5286cf016a441bf48ef7b85f8052db.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 738aed026f3d9e48907e22028dd97ecacedcbff0.nq.gz
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

[python-lsp/pylsp-mypy](https://github.com/python-lsp/pylsp-mypy)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
