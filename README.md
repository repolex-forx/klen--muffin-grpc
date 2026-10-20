# Repolex Knowledge Graph of klen/muffin-grpc

RDF knowledge graph data for [klen/muffin-grpc](https://github.com/klen/muffin-grpc), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-grpc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 790afb3a6fb9d911690c3f675354654e6551a4a2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 790afb3a6fb9d911690c3f675354654e6551a4a2
│           └── chunk-001.nq.gz
├── blob
│   ├── 002cc431c48c47da5dc7b8b1dc67f452ff9a3c6b.nq.gz
│   ├── 009ac688ebc285205a7871dfc498c54be9085e3a.nq.gz
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 0ae4be31e56fab8f3028a8b100f431e14a4e71c1.nq.gz
│   ├── 1d456a85e86868d785ba266239ba14600dfe14e6.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 282f5db81bd684d71f4c6f081978aa66a33882af.nq.gz
│   ├── 33f5113d441e87ff212355dc10a50b9e6013ef77.nq.gz
│   ├── 3a751292ad6602c8a11a7e130e47c11901c02f7a.nq.gz
│   ├── 3e1f83d9eec59bc7ec81d088d67c9efda34bb17e.nq.gz
│   ├── 4e215e0461a3f5854a9ff525806f4ef93d3b7af9.nq.gz
│   ├── 501c7f8502bee42066313f97417ae1e5d6dbf984.nq.gz
│   ├── 5316948220ba6dde914372b4fd12531edf8ec730.nq.gz
│   ├── 5372630f9d3d1be0abc995befeee80d99906a9df.nq.gz
│   ├── 5453b8298b4f4c98cc8ad661c9119e85f3d23dbd.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 8588ca0816775ba2a2df04a64aa3ba3e94d51b7f.nq.gz
│   ├── ac1f9371430b81a5b5f19821d657ee68306bf45f.nq.gz
│   ├── afecd4cee9c3c3d69a85dd2b9f31a98c7dd08773.nq.gz
│   ├── be878ce25fffc1a751c1b4b934002677444859f1.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── cf54c6346190a213a2f99749c135ca2e21aade5b.nq.gz
│   ├── d8d532002dd814d1f43acb80e7a2ffe6fcfa4f0a.nq.gz
│   ├── e3573ae83dcbe739a1723fe6a4063ab9f490a696.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
│   ├── ef23051ba28a3e87238a94de1f097f9bbd894ac8.nq.gz
│   └── f7fad52f505ba27c06fe0dbd7581052e9542c4bd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 790afb3a6fb9d911690c3f675354654e6551a4a2.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 38 files
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

[klen/muffin-grpc](https://github.com/klen/muffin-grpc)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
