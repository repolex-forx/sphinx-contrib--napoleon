# Repolex Knowledge Graph of sphinx-contrib/napoleon

RDF knowledge graph data for [sphinx-contrib/napoleon](https://github.com/sphinx-contrib/napoleon), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/napoleon
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── dce30797b7a229ccebda4030f65482d501427794
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── dce30797b7a229ccebda4030f65482d501427794
│           └── chunk-001.nq.gz
├── blob
│   ├── 000c8b09cebf9d05948949de8465ec827e3afb59.nq.gz
│   ├── 041dff40bbc5fb0a82c09527a0de09d69d30c544.nq.gz
│   ├── 06508082c1e96eda6016e6d29621107ccf718ccb.nq.gz
│   ├── 0e71008e1380bb4cb9b3545bf9c010b11273360d.nq.gz
│   ├── 1b1c95e0b2570264e7e59945cfbf19baeda8500b.nq.gz
│   ├── 28824ae8432d2bb50b7b517af154b93a2d361a95.nq.gz
│   ├── 37d5ac8464079584cf0f091d3c22faeee3ace617.nq.gz
│   ├── 419f381aa2562ccdf3cfba7ec65e736438067d8e.nq.gz
│   ├── 48fa49b53ca6878bcad2a57e659823f1dc76b6cb.nq.gz
│   ├── 4bdeb57a37714f5822be318d6d2b7f9b0ba68b0d.nq.gz
│   ├── 52e49e72059ace55b8aa7e52199e86efea890057.nq.gz
│   ├── 5a76e06cdbab7c07bdc16465c28fa9732c71a2e3.nq.gz
│   ├── 5e467a6f8a5f1c29d37e397c714a57dcb6a6c744.nq.gz
│   ├── 664c8b178598ba403561e143ef446922b5d67d23.nq.gz
│   ├── 749140cddf1971e0ca78f0cb13a21de7014918cc.nq.gz
│   ├── 79bf786ebc8b2b3a47cf2366156e25f1aa87f053.nq.gz
│   ├── 842cd36bcda3d664af5ce845d81e7513ae3755e1.nq.gz
│   ├── 8529a1d56d456dd316839ab6e23e4e619321899c.nq.gz
│   ├── 8937d87b80e49dc14b7022bc6c3107b7fc45c43b.nq.gz
│   ├── 8b8421fedaf4aecc80c24e81d0246dcdce1df618.nq.gz
│   ├── 95ba8d0916f83251422ce6e3ca53452099524ee3.nq.gz
│   ├── a3b41613ecb17f32b7724203d1a5358f394e8671.nq.gz
│   ├── a61cc0e83a2cf0060cedc643419052de1cee0695.nq.gz
│   ├── c3ba273b8e9ce4e919c22514500779b573a53c1d.nq.gz
│   ├── c4937207d7ac3fd93e66fdfaebd9d1ada128c1df.nq.gz
│   ├── c4c7b17358a6868b4b450ef1642903da40557e46.nq.gz
│   ├── c8d2b48ad9293204c2cb9a77a8fa81cf7effdd04.nq.gz
│   ├── dd2a098fa919d00b8155b9117890e926107600a2.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e7138211e4715a03ec6e7f0637b3b31e905b5fe6.nq.gz
│   ├── eae91d1acc97ae0da2a54a7a546272700479cb0e.nq.gz
│   ├── ec23a65d153f9454d9cbfa4afef7d5720244d9cf.nq.gz
│   └── ed29d550754ddfe277e313934bbb63217846c5d2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── dce30797b7a229ccebda4030f65482d501427794.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 41 files
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

[sphinx-contrib/napoleon](https://github.com/sphinx-contrib/napoleon)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
