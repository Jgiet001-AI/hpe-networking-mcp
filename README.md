# Knowledge Graph — `hpe-networking-mcp`

This branch holds an auto-generated **[Understand-Anything](https://github.com/Egonex-AI/Understand-Anything)**
knowledge graph for [`Jgiet001-AI/hpe-networking-mcp`](https://github.com/Jgiet001-AI/hpe-networking-mcp)
(a fork of `nowireless4u/hpe-networking-mcp`). It is an interactive map of the codebase —
files, functions, classes, imports, call edges, architectural layers, and a guided tour —
that you explore in a local web dashboard.

> **Do not edit by hand.** Local automation refreshes `.understand-anything/` after each
> upstream sync. The `main` branch mirrors upstream; this `knowledge-graph` branch only
> carries the graph artifacts below.

**What's here**
```
.understand-anything/
├── knowledge-graph.json   # the graph the dashboard renders (nodes, edges, layers, tour)
├── fingerprints.json      # per-file structural hashes (used for incremental updates)
└── meta.json              # which upstream commit this graph was built from
```

---

## View the graph at http://127.0.0.1:5173/

> ⚠️ **You must open the full URL the server prints, including `?token=…`.**
> The bare `http://127.0.0.1:5173/` will show an "Access Token Required" gate.

You need [Node.js **≥ 22**](https://nodejs.org). Pick one of the two paths below.

### Path A — Claude Code users (easiest)

If you use [Claude Code](https://claude.com/claude-code), the dashboard ships with the
Understand-Anything plugin and launches itself.

```bash
# 1. Clone just this branch (the graph), into a folder of its own
git clone --branch knowledge-graph --single-branch \
  https://github.com/Jgiet001-AI/hpe-networking-mcp.git hpe-graph
cd hpe-graph
```

```text
# 2. In Claude Code: install the plugin once, then launch the dashboard on this folder
/plugin marketplace add Egonex-AI/Understand-Anything
/plugin install understand-anything
/understand-dashboard .
```

Claude builds the dashboard (first run only) and prints a line like:

```
🔑  Dashboard URL: http://127.0.0.1:5173/?token=<your-token>
```

Open that exact URL in your browser.

### Path B — Manual (no Claude Code)

Run the open-source dashboard directly against the cloned graph.

```bash
# 1. Clone this branch (the graph) and the dashboard source
git clone --branch knowledge-graph --single-branch \
  https://github.com/Jgiet001-AI/hpe-networking-mcp.git hpe-graph
git clone https://github.com/Egonex-AI/Understand-Anything.git ua
cd ua

# 2. Build the plugin (pnpm via corepack; allow the native tree-sitter build scripts)
corepack pnpm install --config.dangerouslyAllowAllBuilds=true
corepack pnpm --filter @understand-anything/core build

# 3. Serve the dashboard, pointed at the cloned graph folder
cd packages/dashboard
GRAPH_DIR="$(cd ../../../hpe-graph && pwd)" npx vite --host 127.0.0.1
```

The server prints the tokenized URL — open it:

```
🔑  Dashboard URL: http://127.0.0.1:5173/?token=<your-token>
```

> `GRAPH_DIR` must be the folder that contains `.understand-anything/knowledge-graph.json`
> (i.e. the root of the `hpe-graph` clone). If port `5173` is busy, Vite picks the next free
> port — use whatever it prints. Stop the server with `Ctrl+C`.

---

## What you can do in the dashboard

- **Graph view** — pan/zoom the dependency graph; the most-depended-on hubs stand out
  (e.g. `platforms/_common/annotations.py`, the per-platform `_client`/`_registry` modules).
- **Layers** — browse the codebase by architectural layer (Server Core, Middleware,
  Platform Integrations, Platform Tool Wrappers, Redaction & Translation Engines, Skills,
  Tests, Infrastructure).
- **Tour** — a guided, ordered walkthrough from the entry point through the 9 platform
  integrations and supporting subsystems.
- **Impact / relationships** — follow `imports`, `calls`, and `tested_by` edges to see what a
  change touches.

## Freshness

Check `.understand-anything/meta.json` → `gitCommitHash` to see which upstream commit the graph
reflects. The graph is rebuilt automatically as upstream advances.
