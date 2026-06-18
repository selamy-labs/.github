# Selamy Labs

**Autonomous agent systems that do real engineering and operations work — in public.**

We build and run a live multi-agent fleet: agents that claim work from a priority queue, ship merged pull requests, and recover from their own failures — kept honest by evals, OpenTelemetry, and infrastructure-as-code. The repositories here are the open-source pieces of that system.

### Open source

- **[laneq](https://github.com/selamy-labs/laneq)** — a tiny lease-based priority queue for coordinating parallel agents without collisions.
- **[agent-skills](https://github.com/selamy-labs/agent-skills)** — reusable `SKILL.md` workflows that give agents judgment, not just tools.
- **MCP servers** (capabilities for agents): [agent-mcp](https://github.com/selamy-labs/agent-mcp) · [telemetry-mcp](https://github.com/selamy-labs/telemetry-mcp) · [memory-mcp](https://github.com/selamy-labs/memory-mcp) · [dispatch-mcp](https://github.com/selamy-labs/dispatch-mcp) · [reddit-mcp](https://github.com/selamy-labs/reddit-mcp) · [dns-mcp](https://github.com/selamy-labs/dns-mcp)
- **[terraform-modules](https://github.com/selamy-labs/terraform-modules)** — reusable OpenTofu modules for cloud/provider resources.
- **[python-repo-template](https://github.com/selamy-labs/python-repo-template)** — the scaffold our public repos start from.

### How we build

- **Done means evidence** — a merged PR, a loaded page, a green run — not "the model said so."
- **Declarative everything** — IaC/GitOps; no hand-mutated live state.
- **Evals + observability first** — agent work is measured (OpenTelemetry traces) and gated, not hoped for.
- **Public-first** — share the framework openly; keep only what must be private, private.

---

Built by **[Patrick Selamy](https://github.com/pselamy)** · [selamy.dev](https://selamy.dev)
