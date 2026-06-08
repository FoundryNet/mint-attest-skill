# mint-attest — Claude Code plugin

Attest completed work on **MINT Protocol**. After Claude finishes a substantive
deliverable (code review, refactor, research, report, audit, tests…), it records
a **tamper-evident, on-chain proof** of the work — what was done, when, and by
whom — and returns a public Solscan verify URL.

Settled on Solana. Free to register, free to verify, $0.02 per attestation.
Skips silently when `MINT_API_KEY` is unset, so it never blocks a task.

## Install

```bash
claude plugin marketplace add FoundryNet/mint-attest-skill
claude plugin install mint-attest@foundrynet
```

(or add a local checkout: `claude plugin marketplace add /path/to/mint-attest-skill`)

## Configure

```bash
export MINT_API_KEY=fnet_…        # free key at https://foundrynet.io
export MINT_AGENT_NAME="Claude Code"   # optional; the attesting agent's name
```

The skill installs the [`mint-attest`](https://pypi.org/project/mint-attest) PyPI
SDK on first use; there is no Solana/wallet dependency on your side — the MINT
server handles all on-chain interaction.

## What gets recorded

Input/output are hashed locally (SHA-256) — your data never leaves, only the
hash does. The record carries the work type, a summary, the duration, and the
hashes, settled on Solana mainnet. Browse it at https://mint.foundrynet.io.

## Links

- Explorer: https://mint.foundrynet.io
- SDK: https://pypi.org/project/mint-attest
- Protocol: https://foundrynet.io

MIT licensed.
