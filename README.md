# DUP Protocol v2 — unified polygon (DUP Labs)

**Brand:** [DUP Labs](docs/BRAND.md) · **DUP Protocol** · Uladzimir Dabranski (D.U.P.)

This folder is a **local merge check**: one working tree built from the two frozen lines **without modifying them**.

| Line | GitHub | Role |
|------|--------|------|
| Industrial pin | [`dup-protocol`](https://github.com/Gruver87/dup-protocol) | Audit freeze · TCP+TLS · tag `v1.3.1339-tip-v2-industrial` |
| Experimental | [`dup-protocol-experimental`](https://github.com/Gruver87/dup-protocol-experimental) | R&D · libp2p · money/honesty waves |

**How it was assembled:** [V2_POLYGON.md](docs/V2_POLYGON.md)

**Not claimed:** public audited mainnet · firm pen-test PASS · 48h soak on *this* copy (soaks stay on the source trees).

---

## Layout (keep it this way)

```
api/ consensus/ crypto/ network/ storage/ sync/ native/ bridge/  # L1
docs/            # SHOWCASE, ADRs, diligence, V2_POLYGON
docker/          # node JSON (prod sprouts OFF except Experimental libp2p mesh)
scripts/         # operator + gates
tests/           # units
sdk/             # thin operator client (lab)
```

**Do not mix** pin TCP+TLS and Experimental libp2p in the same node JSON.

---

## Start (code only — no live mesh steal)

```powershell
cd C:\Users\vovun\Desktop\dup-protocol-v2
copy .env.example .env
pip install -r requirements.txt
python -c "import main; print('import ok')"
```

Native (when you intend to run a node): `.\scripts\build_native.ps1`

**Mesh:** do **not** bind `:18180–18182` while Experimental soak is ALIVE. Use pin-style TLS compose or wait.

| Intent | Compose |
|--------|---------|
| Pin-like 3-node TLS | `docker-compose.prod.3node.p2ptls.yml` |
| Experimental libp2p mesh | `docker-compose.prod.3node.yml` |

---

## Diligence (same honesty as sources)

- [SHOWCASE](docs/SHOWCASE.md) · [DILIGENCE_BRIEF](docs/DILIGENCE_BRIEF.md) · [FUND_READINESS](docs/FUND_READINESS.md)
- Pin vision: [VISION](docs/VISION.md) · pin demo: [DEMO_RUNBOOK_PIN](docs/DEMO_RUNBOOK_PIN.md)
- Fund operator pack: [FUND_DEMO_OPERATOR_PACK](docs/FUND_DEMO_OPERATOR_PACK.md)

Until this polygon has its **own** packaged 48h, cite soak packs on the **source** repos, not as “v2 soak PASS”.

---

## License

MIT — see [LICENSE](LICENSE).
