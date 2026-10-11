# Evidence register — Avalanche Fuji (chain id 43113)

Newest first. A row is added only after the transaction is mined and opened on the explorer.

| Date (UTC) | Step | Requirement | Block | Explorer | What it proves |
|---|---|---|---|---|---|
| 2026-10-11 | Contract source verified on the explorer | FR-03 | — | https://testnet.snowtrace.io/address/0xe274C452dFb0D259FA413EEd3a830197a4Fd50ef/contract/43113/code | Anyone can read the deployed code; it matches the source in commodex-agent-avalanche-contracts |
| 2026-10-11 14:08 | First anchor, kind `TEST` | FR-01 | 59306896 | https://testnet.snowtrace.io/tx/0x2384d975b453a523524346ce7cd00e8d039bd8c4b6e7ec2ea73e1f5970077bef | The Commodex operator wallet records a hash on Fuji with no participant wallet; `Anchored` event emitted |
| 2026-10-11 14:07 | CommodexAnchor v0 deployed at `0xe274C452dFb0D259FA413EEd3a830197a4Fd50ef` | FR-03 | 59306874 | https://testnet.snowtrace.io/tx/0x24efb4ba147d4dab9cd9ae98a11edddd53b4ae4dc1cd861f5a8b44a66a3673a4 | Gate M0 / milestone M2.2: the hash-anchor contract is live on Fuji; deploy input equals the published build |
| 2026-10-11 | CommodexAnchor v0 built | FR-03 | — | — | Contract and 7 local tests; reviewed by contract assurance (one medium finding, fixed before deploy) |

How each row was checked on 2026-10-11: transaction receipts read from the public Fuji RPC
(`https://api.avax-test.network/ext/bc/C/rpc`, `eth_chainId` = `0xa869`), status `0x1`, sender
`0xa6547c2812140c0495113d4490eb0f2805A67ecD`; `anchoredAtBlock(0x8b8d8a98…eae3fc00)` returns 59306896.

## Acceptance status

| Req. | Evidence required | Status |
|---|---|---|
| FR-01 | Operator submits on Fuji 43113 (no participant wallet) | **demonstrated 2026-10-11** (block 59306896) |
| FR-02 | Rehearsal PO on staging with document SHA-256s | not yet demonstrated |
| FR-03 | Document-hash tx recorded on Fuji against the PO | contract live; PO document hash not yet recorded |
| FR-04 | Each contribution traced to a full commit | not yet demonstrated |
