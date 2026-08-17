<div align="center">

<img src="https://raw.githubusercontent.com/thinre/.github/main/profile/assets/thinre-mark.svg" alt="Thinre" width="76" height="76" />

# Thinre

### Manage the lifecycle of any agent or daemon across large customer fleets — without building a custom management stack for every application.

</div>

---

If you ship software that runs on machines you don't control — customer
servers, edge boxes, appliances — you know the pattern: every product
ends up growing its own updater, its own config pusher, its own fleet
dashboard.

**Thinre replaces that per-application stack with one.** Point it at an
agent or daemon you already have, describe its lifecycle in a small YAML
file, and it becomes a centrally managed application — installed,
upgraded, rolled back, configured, and health-checked across your whole
fleet from one control plane.

> **Turn any existing agent or daemon into a centrally managed application in hours, not weeks.**

## How it works

```
Thinre Cloud ── desired state ──▶ Supervisor ── download ▶ verify ▶ upgrade ▶ health ──▶ observed state
```

- A single open-source **Supervisor** binary runs on each machine. It
  dials out over one WebSocket (the **Thinre Link** protocol — no inbound
  ports), receives desired state, and reconciles the local software
  toward it.
- The managed software stays a **black box**: Thinre never links against
  or patches it. Everything goes through lifecycle hooks you declare in
  an integration manifest — scripts your software already has.
- **Thinre Cloud** is the control plane: fleets, staged rollouts with
  canary percentages and approval gates, atomic configuration revisions,
  multi-tenancy, and audit.

Fail-closed artifact verification, automatic rollback on failure, atomic
config, and crash-safe reconciliation come built in. Linux and Windows,
one binary each.

## Repositories

| Repository | What it is |
|---|---|
| [**thinre**](https://github.com/thinre/thinre) | Open source (Apache-2.0): the Supervisor, the integration contract, the `thinre` CLI, and the Link protocol. Everything that runs on **your** infrastructure. |
| **thinre-cloud** | The commercial control plane — fleet orchestration, rollouts, multi-tenancy, audit. Proprietary. |

## Get started

📖 **[Documentation](https://thinre.github.io/thinre/)** — begin with the
[quick start](https://thinre.github.io/thinre/quickstart): from a
downloaded binary to your first remote upgrade in about ten minutes.

- [Integration manifest](https://thinre.github.io/thinre/integration-manifest) — the contract between Thinre and your software
- [Link protocol](https://thinre.github.io/thinre/link-protocol) — the three-message wire protocol
- [CLI](https://thinre.github.io/thinre/cli) — publish manifests from your terminal

<div align="center">
<sub>Apache-2.0 edge · proprietary cloud · one control plane for every fleet</sub>
</div>
