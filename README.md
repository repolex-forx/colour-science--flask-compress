# Repolex Knowledge Graph of colour-science/flask-compress

RDF knowledge graph data for [colour-science/flask-compress](https://github.com/colour-science/flask-compress), parsed by [repolex](https://repolex.ai).

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
rlex download colour-science/flask-compress
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 33ff4e5ebe91ddc31d83d0be87ade25c1ad6f30b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 33ff4e5ebe91ddc31d83d0be87ade25c1ad6f30b
│           └── chunk-001.nq.gz
├── blob
│   ├── 12a03d70dec746f2921642f3f5c820d27526c127.nq.gz
│   ├── 20f00676ddbb8fc9a227835113d1cc50399e44dc.nq.gz
│   ├── 2390d8c809eea1d6587357cdad25ed4af134db32.nq.gz
│   ├── 2b424e236c6232da1721ed96b2071478e4fa07be.nq.gz
│   ├── 2dbd8537045f8bd8396e9e0241588e635acdea4a.nq.gz
│   ├── 3248ee057054e7f84839e9170b855cd021f49ccf.nq.gz
│   ├── 41ac0dc16f15991dad47800a0b104ef1d8716ca7.nq.gz
│   ├── 5e64191c10921ebc6f2850b32b1f8ca9f35b361f.nq.gz
│   ├── 67eea73f6c03eefa3b89d74f736a0850ca5b2edc.nq.gz
│   ├── 9a6c841fc5aa69a46ff964ac67b41412f95d7909.nq.gz
│   ├── 9c34de84d75ebe2c1e360a6e104186ef00542ef4.nq.gz
│   ├── a924a670ff5ca4a96645d83e3e7179ae0bf56fd1.nq.gz
│   ├── b5dcd564cd950a7a820b5fbfd799d771e7a65ae3.nq.gz
│   ├── c107b93706c56ff39e970165a1bde83db751435d.nq.gz
│   ├── dbd44550f3be0fad401040605e1ea9ef8230aaf5.nq.gz
│   ├── dd08a8bed3230bb42da6f47436f90dba06ad7a5b.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 33ff4e5ebe91ddc31d83d0be87ade25c1ad6f30b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[colour-science/flask-compress](https://github.com/colour-science/flask-compress)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
