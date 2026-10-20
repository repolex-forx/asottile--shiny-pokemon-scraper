# Repolex Knowledge Graph of asottile/shiny-pokemon-scraper

RDF knowledge graph data for [asottile/shiny-pokemon-scraper](https://github.com/asottile/shiny-pokemon-scraper), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/shiny-pokemon-scraper
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f9f293a3ad7f98ba2df26180ef47fc5c0bfd1c47
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f9f293a3ad7f98ba2df26180ef47fc5c0bfd1c47
│           └── chunk-001.nq.gz
├── blob
│   ├── 06d6c09fce5095253b9bb6831e6f6809d837e51e.nq.gz
│   ├── 16f11d64923bcd236e717556d945a28d59d0aa97.nq.gz
│   ├── 23f570a6d1082e308a8ca9a8e06989599f8905e2.nq.gz
│   ├── a28a7e77e71bbe083cd8b951f655c8193873cc0f.nq.gz
│   ├── c1bbbc1ac43dfed49b5d7a7d903cdb24c2f32d4c.nq.gz
│   ├── c4be1b7014a184097d4e5c8d8654cd6fdba3b21d.nq.gz
│   ├── d4a907fc2943883158aa2c7560abdcd37c36001e.nq.gz
│   ├── e03e944532a11962fd394d18a60221fb9943e5f7.nq.gz
│   └── fff4c391980e69a85df00c2c8e61ea09b66be7b3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f9f293a3ad7f98ba2df26180ef47fc5c0bfd1c47.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 16 files
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

[asottile/shiny-pokemon-scraper](https://github.com/asottile/shiny-pokemon-scraper)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
