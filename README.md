# Repolex Knowledge Graph of dtolnay/dissimilar

RDF knowledge graph data for [dtolnay/dissimilar](https://github.com/dtolnay/dissimilar), parsed by [repolex](https://repolex.ai).

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
rlex download dtolnay/dissimilar
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a4e3cb224d9099ec92d7c94b1204a1ccb69795da
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── a4e3cb224d9099ec92d7c94b1204a1ccb69795da.nq.gz
│   └── repolex
│       └── a4e3cb224d9099ec92d7c94b1204a1ccb69795da
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c41d7072681891b306aaf6bead6a41850a18730.nq.gz
│   ├── 1b5ec8b78e237b5c3b3d812a7c0a6589d0f7161d.nq.gz
│   ├── 22c05d4079575317ad4eaf6f97d4bf646139fa81.nq.gz
│   ├── 2ae0eefe627f45dfe4d5677f09420bee0b7c27aa.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 3dde82a4e642c5bc41be8914a3717a2b0879cc29.nq.gz
│   ├── 4bc31dc394135fc1aa166b499d5f346bc0abfc2d.nq.gz
│   ├── 54b438fd795affa08849b1cbd84d53cf44e002a5.nq.gz
│   ├── 54c09bcc8eafc1110866d6717e5364013b645bfe.nq.gz
│   ├── 750707701cdae985156601cc906195021ba6a6e5.nq.gz
│   ├── 7debb0593ae4b939acd5edbb95ed60dcef81cf86.nq.gz
│   ├── 83fccc4e540d609c0651cee4d00882614e519bd4.nq.gz
│   ├── 8f25a80fff35db89d7f3d9126c73335b6e6f31cd.nq.gz
│   ├── add1d89288d3ed87e511604dead687e00ba0ea5c.nq.gz
│   ├── b1b61ba928f40ac8e64c6afced36adc54f855d68.nq.gz
│   ├── dde878844b8582f806063068fd692a689bc59b16.nq.gz
│   ├── e9e21997b1aca0707f8749ea13c09aec66c899d2.nq.gz
│   └── fc0ca3fbaa76ebc68d49c68cc8491070386a8cf5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── a4e3cb224d9099ec92d7c94b1204a1ccb69795da.nq.gz
├── filetree
│   └── a4e3cb224d9099ec92d7c94b1204a1ccb69795da.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 28 files
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

[dtolnay/dissimilar](https://github.com/dtolnay/dissimilar)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
