# Mike Bello — Smart Contract Security Researcher & Developer

Independent smart contract auditor from Mexico. Competitive audits on Code4rena, Sherlock and Cantina, former Nethermind security intern, and founder of [Seclat Security](https://x.com/SecLat_Security).

[X](https://x.com/mike_bello90) · [LinkedIn](https://www.linkedin.com/in/miguel-angel-valdez-bello-7294a768/) · [YouTube (Seclat)](https://www.youtube.com/@SecLat) · angelcap1990@gmail.com

## Summary

|                         |                                                                                                                                                               |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Valid findings          | **3 High · 8 Medium**                                                                                                                                         |
| Best result             | 🥈 **2nd place — Nudge.xyz** (Code4rena)                                                                                                                      |
| Protocols helped secure | Uniswap v4, Ethena, Wildcat, Ethereum Credit Guild, Revert Lend, Curves, Dopex, Nudge.xyz, GTE, Sentiment                                                     |
| Profiles                | [Code4rena](https://code4rena.com/@Mike_Bello90) · [Sherlock](https://audits.sherlock.xyz/watson/Mike_Bello90) · [Cantina](https://cantina.xyz/u/MikeBello90) |

## Findings

| Date     | Protocol                   | Platform            | Severity    | Finding                                                                                        | Link                                                                                                                                                                    |
| -------- | -------------------------- | ------------------- | ----------- | ---------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Oct 2026 | MPC protocol (undisclosed) | Bug bounty platform | Undisclosed | Two bugs in a multi-party computation (MPC) protocol                                           | Private (program rules)                                                                                                                                                 |
| Aug 2025 | GTE Perps and Launchpad    | Code4rena           | Medium      | Changing leverage refunds the margin that should back the account's unrealized loss            | [M-01](https://code4rena.com/reports/2025-08-gte-perps-and-launchpad) · [my submission](https://code4rena.com/audits/2025-08-gte-perps-and-launchpad/submissions/S-927) |
| Mar 2025 | Nudge.xyz 🥈               | Code4rena           | Medium      | Cross-chain reallocated tokens and rewards are lost for account abstraction wallet users       | [M-03](https://code4rena.com/reports/2025-03-nudgexyz)                                                                                                                  |
| Sep 2024 | Uniswap v4                 | Cantina             | Medium      | Gas check in `_fetchProtocolFee` blocks pool initialization on ZKsync and Arbitrum             | [#359](https://cantina.xyz/code/e2cf6906-ec8b-4c78-a585-74ac90615659/findings/359)                                                                                      |
| Aug 2024 | Sentiment V2               | Sherlock            | Medium      | Contracts cannot be paused correctly: pausable modifiers missing from main functions           | [#377](https://github.com/sherlock-audit/2024-08-sentiment-v2-judging/issues/377)                                                                                       |
| Mar 2024 | Revert Lend                | Code4rena           | Medium      | Dangerous use of deadline parameter                                                            | [M-21](https://code4rena.com/reports/2024-03-revert-lend)                                                                                                               |
| Jan 2024 | Curves                     | Code4rena           | High        | Unauthorized access to `setCurves` function                                                    | [H-04](https://code4rena.com/reports/2024-01-curves)                                                                                                                    |
| Jan 2024 | Curves                     | Code4rena           | Medium      | `onBalanceChange` clears previously unclaimed rewards                                          | [M-10](https://code4rena.com/reports/2024-01-curves)                                                                                                                    |
| Dec 2023 | Ethereum Credit Guild      | Code4rena           | Medium      | Malicious borrower can decrease Guild holders' rewards                                         | [M-11](https://code4rena.com/reports/2023-12-ethereumcreditguild)                                                                                                       |
| Oct 2023 | Ethena Labs                | Code4rena           | Medium      | Users still forced to follow the previous `cooldownDuration` after cooldown is turned off      | [M-03](https://code4rena.com/reports/2023-10-ethena)                                                                                                                    |
| Oct 2023 | The Wildcat Protocol       | Code4rena           | High        | Borrower has no way to update `maxTotalSupply` of a market or close it                         | [H-03](https://code4rena.com/reports/2023-10-wildcat)                                                                                                                   |
| Aug 2023 | Dopex                      | Code4rena           | High        | Settle feature breaks if an attacker transfers collateral tokens to `PerpetualAtlanticVaultLP` | [H-03](https://code4rena.com/reports/2023-08-dopex)                                                                                                                     |

Finding titles are the ones used in the official reports; my submission is credited in each.

### Featured: Uniswap v4 — pool initialization DoS on L2s

`_fetchProtocolFee` reserves 1% of `block.gaslimit` for the protocol fee controller call and reverts if `gasleft()` is lower. On chains where `block.gaslimit` doesn't mean what it means on Ethereum (ZKsync, Arbitrum), that 1% is larger than any transaction's available gas, so every `initialize` reverts with `ProtocolFeeCannotBeFetched`. I proved it with a Foundry test on forked ZKsync and Arbitrum. Lesson: "EVM-compatible" is not "EVM-equivalent".

## Other security work

- **Nethermind** — Smart Contract Security Internship (Jun–Aug 2024).
- **ERC-8003** — security review of the [ERC-20 Pre-Initialization Extension](https://ethereum-magicians.org/t/erc-8003-erc-20-pre-initialization-extension-sentinel-storage/24993) with its author.
- **Bug bounties** — active on Immunefi and HackenProof. Found two bugs in a multi-party computation (MPC) protocol on a bug bounty platform; details can't be disclosed under the program's rules.
- **Developer background** — designed, tested and deployed the smart contracts for Panoram Finance (Polygon); contracts in Cairo on Starknet.

## Open source contributions

New challenge levels submitted to [OpenZeppelin Ethernaut](https://github.com/OpenZeppelin/ethernaut) (under review):

- [GhostVault](https://github.com/OpenZeppelin/ethernaut/pull/861)
- [FrontRunner](https://github.com/OpenZeppelin/ethernaut/pull/862)
- [FlashQuorum](https://github.com/OpenZeppelin/ethernaut/pull/863)

## Talks & community

Security talks at **ETH Cinco de Mayo**, **Ethereum Mexico**, and **EVVM + FlashTalkCotorreo during Devconnect Argentina 2025**. Attended the DeFi Security Summit and was part of the **Invisible Garden** cohort (Argentina, Nov 2025). Through Seclat Security I teach smart contract security in Spanish to the Latin American community.

Talks and posts (links):

- https://x.com/SecLat_Security/status/1928130142351601925
- https://x.com/SecLat_Security/status/1914527672052367611
- https://x.com/mobil3_xyz/status/1988688179373961660
- https://x.com/Mike_Bello90/status/1850252634071965800
- https://x.com/SecLat_Security/status/1919522297742000466
- https://x.com/SecLat_Security/status/1917805634646405543
- https://x.com/Mike_Bello90/status/1988603600407560286
- https://x.com/SecLat_Security/status/1906012498488168914
- https://x.com/SecLat_Security/status/1996249626022907925
- https://x.com/Mike_Bello90/status/1962555898422784073
- https://x.com/Mike_Bello90/status/1919985027619684429
- https://x.com/Mike_Bello90/status/1906002574681022724

## Other submitted reports

Reports that were not rewarded, kept for transparency.

| Date     | Protocol                 | Platform | Report                                                                                                                                                           | Result       |
| -------- | ------------------------ | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ |
| Mar 2025 | Pinlink                  | Sherlock | [Oracle/market price mismatch can cause seller losses](https://github.com/sherlock-audit/2025-03-pinlink-rwa-tokenized-depin-marketplace-judging/issues/72)      | Not rewarded |
| Mar 2025 | Pinlink                  | Sherlock | [PIN token transfer limits can temporarily block trades](https://github.com/sherlock-audit/2025-03-pinlink-rwa-tokenized-depin-marketplace-judging/issues/80)    | Not rewarded |
| Mar 2025 | Pinlink                  | Sherlock | [Off-by-one in `enableAsset` supply check](https://github.com/sherlock-audit/2025-03-pinlink-rwa-tokenized-depin-marketplace-judging/issues/90)                  | Not rewarded |
| Aug 2024 | Sense Points Marketplace | Sherlock | [Upgradeable tokens becoming fee-on-transfer can make the vault insolvent](https://github.com/sherlock-audit/2024-07-sense-points-marketplace-judging/issues/88) | Won't fix    |
