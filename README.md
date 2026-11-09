# Repolex Knowledge Graph of MojoJolo/textteaser

RDF knowledge graph data for [MojoJolo/textteaser](https://github.com/MojoJolo/textteaser), parsed by [repolex](https://repolex.ai).

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
rlex download MojoJolo/textteaser
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f96cc7422e9a175977a2935bb2fe571aadf0293e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f96cc7422e9a175977a2935bb2fe571aadf0293e
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f4177bbed97995a612c3668465690f3a0ac65ac.nq.gz
│   ├── 1260ce8a4fa620c8f4752bfd581a27131ad14de4.nq.gz
│   ├── 1bd04a57f825bfc7121aa308c6a3e8e2d232c29d.nq.gz
│   ├── 1da09557844243f8259257f18dce6d12070b8626.nq.gz
│   ├── 23ef9607a5ced58b32332751a07a50803cb4a074.nq.gz
│   ├── 2f6062552a27e70c3012665837a8ad80b22b4304.nq.gz
│   ├── 387753a1a331d3d07204fc652c09d1c6b67b19ba.nq.gz
│   ├── 3f697860f8833d6107c14f0262f8c6b3a02e551b.nq.gz
│   ├── 3fc3108b5ee81a53a08e7f53dfb1168cc1bf5680.nq.gz
│   ├── 4a4533e931f59e8a755fcc6d054714fbaf6ef102.nq.gz
│   ├── 4a6669efa3a66b5a8c69bb82ce3bb23a9d0f0555.nq.gz
│   ├── 5b97c305d88f0020ca73064b81f94bda2679be10.nq.gz
│   ├── 603bc274a9776657748cc184c026685bfcb350a1.nq.gz
│   ├── 6374b2fa036794b09a5af751497e9edb82311f69.nq.gz
│   ├── 64abd373f7fe1e4d14201d28ffa7627d5aeda222.nq.gz
│   ├── 6fb83d58b54bf6f3a1c366c76f2514bf5d424e30.nq.gz
│   ├── 79299048057257cc8cd7f01aa82d507678ee5db6.nq.gz
│   ├── 83a8927897f2dd98c64d302c41104c1025749408.nq.gz
│   ├── 99f904de8c9184dce02e637172fe0c05c84ba944.nq.gz
│   ├── b33e79934361569f29a036a5cf5c28251d6e7636.nq.gz
│   ├── b76f154ddb7cc42239f97eba200d1f7b831f5ca7.nq.gz
│   ├── c60984289a8e336ab85cfb2dc18684921b9e3c2c.nq.gz
│   ├── e28298729c515ad3196eff1a02961e2b92e164f8.nq.gz
│   ├── e89076be5ab24adc12ad9cdf14fe1299c4ff5e00.nq.gz
│   ├── f34ac5e29b6051a619636552f935d2e6dfade5cc.nq.gz
│   └── fbd27abd63875e0b8788c82c968bfa4da7cfae5b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f96cc7422e9a175977a2935bb2fe571aadf0293e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[MojoJolo/textteaser](https://github.com/MojoJolo/textteaser)

---
*Parsed on 2026-11-09 by [repolex](https://repolex.ai)*
