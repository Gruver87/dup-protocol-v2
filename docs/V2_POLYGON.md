# DUP Protocol v2 — merge polygon (local)

**This tree is a verification copy.** It does **not** replace:

- Industrial pin: [`dup-protocol`](https://github.com/Gruver87/dup-protocol) (local `Absolute_Blockchain_Ultimate_Hybrid`)
- R&D: [`dup-protocol-experimental`](https://github.com/Gruver87/dup-protocol-experimental) (local `Absolute_Blockchain_Experimental`)

**Not:** public audited mainnet · not a 48h soak claim · not Great Merge onto the pin.

## How this copy was built (2026-10-04)

| Step | What |
|------|------|
| 1 | Snapshot **Experimental HEAD** as the working codebase (money/honesty waves + mesh scripts) |
| 2 | Overlay **pin-only docs** that were missing (`DEMO_RUNBOOK_PIN.md`, `VISION.md`) |
| 3 | Drop tails: `.git`, `.env`, `data/`, `logs/`, wallets, caches, `RELEASE_NOTES_v1.2.*` / `v1.3.*` spam, social posts, unused `geth_*` porting dirs, evidence `*.log` |
| 4 | 2026-10-04 scan: drop empty dashboard, root HTML explorers, `rust_blockchain/`, `init_git.ps1`, unused `nft_core.py`, pin `sync-main-from-master.yml`, localhost screenshots |

Sources at copy time (operator disk):

- Experimental: `f3e93d8` (`dup-protocol-experimental`)
- Pin: `4b42165` (`dup-protocol`)

## Two profiles — do not mix in one JSON

| Profile | Transport | Use |
|---------|-----------|-----|
| **Industrial (pin-like)** | TCP+TLS | `docker-compose.prod.3node.p2ptls.yml` · `docs/DEMO_RUNBOOK_PIN.md` |
| **Experimental mesh** | rust-libp2p (ADR 0020) | `docker-compose.prod.3node.yml` · Experimental SHOWCASE |

`feature_long_range` stays **false** on prod JSON. Long-Range = lab compose only.

## Intentionally not copied

- Runtime DB / soak volumes (`data/`, `logs/`)
- Secrets (`.env`, `*.pem`, wallet dumps)
- Rust `target/` build artifacts
- Historical per-version `RELEASE_NOTES_v1.*` (see `CHANGELOG.md` + pin tag `v1.3.1339-tip-v2-industrial`)
- Unused pin `geth_*` trees (no imports on either live line)

## Pass bar for this polygon

1. `python -m compileall -q` on `main.py` / `runtime` / `consensus` (no mesh)
2. Later (operator, **not** while Experimental soak is ALIVE on :18180–182): own Docker mesh on **different ports** or after soak
3. Only then: GitHub `dup-protocol-v2` if the operator orders it
