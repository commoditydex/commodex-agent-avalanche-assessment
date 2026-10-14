# commodex-agent-avalanche-assessment

Avalanche assessment agent for the Commodex Avalanche C-Chain setup. Commodex: https://commodex.xyz/

- Production: https://commodex.xyz
- Testnet UI: https://wedevnext.commodex.xyz
- Fuji evidence page on the testnet UI: https://wedevnext.commodex.xyz/fuji
- Network: Avalanche Fuji C-Chain (EVM), chain id `43113`

## Agent

| | |
|---|---|
| Person | Ewa Kamińska |
| Role | Avalanche assessment — keeps the evidence register and reports actual test results |
| FR scope | FR-01, FR-03 |
| Squad page | https://team.impactcapital.ltd/showcase/commodex/ |

## Status — 11 October 2026

**FR-01 demonstrated on Fuji on 11 Oct 2026 (CommodexAnchor deployed and first hash anchored). FR-02 to FR-04 not yet.**

The single source of truth for every on-chain claim Commodex makes is [EVIDENCE.md](EVIDENCE.md).
A claim that has no row there with an explorer link is not made — in a presentation, on the site or in any application.

## Commands

Re-check every row of EVIDENCE.md against the public Fuji RPC (no install, no key, Node 18 or newer):

```bash
git clone https://github.com/Impact-Capital-Management/commodex-agent-contract-assurance
node commodex-agent-contract-assurance/checks/verify-fuji.mjs     # 10/10 PASS on 14 Oct 2026
```

Read one receipt by hand (status `0x1` = success):

```bash
curl -s -X POST https://api.avax-test.network/ext/bc/C/rpc -H 'content-type: application/json'   -d '{"jsonrpc":"2.0","id":1,"method":"eth_getTransactionReceipt","params":["0x3a1c5d0093de40c15deed22f9a568c0a1b2ad04f66f5ae084771583c69e45ac9"]}'
```

The same evidence, grouped by agent role, is on the testnet UI: https://wedevnext.commodex.xyz/fuji

## License

MIT — see [LICENSE](LICENSE).
