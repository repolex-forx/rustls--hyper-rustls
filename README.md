# Repolex Knowledge Graph of rustls/hyper-rustls

RDF knowledge graph data for [rustls/hyper-rustls](https://github.com/rustls/hyper-rustls), parsed by [repolex](https://repolex.ai).

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
rlex download rustls/hyper-rustls
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9741534153d47277d754a3254759360b36ee58fd
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 9741534153d47277d754a3254759360b36ee58fd.nq.gz
│   └── repolex
│       └── 9741534153d47277d754a3254759360b36ee58fd
│           └── chunk-001.nq.gz
├── blob
│   ├── 01de0fb683f0e98f1408624ff77c1a8f08aa2269.nq.gz
│   ├── 03acf1bd2c44c9c10429d0ee4d05ee1e92f9e3f9.nq.gz
│   ├── 047c19ec9b973c96152f1e1fbd790b7a76e16b56.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 1e10e1bcb197ac42876acdf4fbf24bc54b8ca790.nq.gz
│   ├── 259b3f1141a8b6721206857ce77e10984c8c975d.nq.gz
│   ├── 50b24b45db2f8f436a22d5b7b443f42b82f965b6.nq.gz
│   ├── 58f1746e06bf6471cb515e5aa5dfcbd7053eb41f.nq.gz
│   ├── 713d48106e809e587d7cc7836f481b205ff24f39.nq.gz
│   ├── 79061cd183981ef1353a3fb9954755b1538efab4.nq.gz
│   ├── 89e355aebe8b0b16c1ba6c04b1a0032667fa0382.nq.gz
│   ├── 96d97b49002d5f49ef18656527317b015d99a807.nq.gz
│   ├── aec534728c823b3a0278abeaa856917fe4bb164c.nq.gz
│   ├── bcc0a699821d38a31855e3e9ffd56e46f2b6443a.nq.gz
│   ├── bde294893716d46914cdfd54e69ac12030156c4d.nq.gz
│   ├── c7b634c988d1107b4de3414f4267d205a85a0be5.nq.gz
│   ├── cda95b5a9e7da50d2df4f0e9d82a0a7514c8b27b.nq.gz
│   ├── d19fdf92ca14522e488ed61aed3cc11a5dc2f8e7.nq.gz
│   ├── db911b7b060cce924c951d6ff2adb3e675894998.nq.gz
│   ├── db98af7350105751f112120f73bec448f9efd962.nq.gz
│   ├── e70b64a4ae985e54cdc4c8e2785bc9f0557d75e6.nq.gz
│   ├── ef480e6f0936ef5d006d6e3ce9ea8536232b3c88.nq.gz
│   ├── f08e7b1b38625679361162710dcbb8dfed884b9f.nq.gz
│   └── fbd21f4d0aa4fbd31ce6a99353b2ca0c7771d493.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 9741534153d47277d754a3254759360b36ee58fd.nq.gz
├── filetree
│   └── 9741534153d47277d754a3254759360b36ee58fd.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 34 files
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

[rustls/hyper-rustls](https://github.com/rustls/hyper-rustls)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
