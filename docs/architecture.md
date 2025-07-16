\# Protocol Architecture: Tokenized RWAs in DeFi



This document outlines the technical architecture of protocols that tokenize real-world assets (RWAs) such as Centrifuge, Goldfinch, and others.



\## Core Components



| Component          | Description                                                                 |

|-------------------|-----------------------------------------------------------------------------|

| \*\*Borrower Pools\*\* | Smart contract vaults created by asset originators (borrowers)              |

| \*\*Tranching System\*\* | Splits capital into senior (low risk) and junior (high risk) tranches       |

| \*\*Drop / Tin Tokens\*\* | ERC-20 tokens representing senior/junior tranches (e.g., DROP, TIN)       |

| \*\*NAV Feed\*\*       | Oracles or internal logic that calculate Net Asset Value of pools           |

| \*\*Repayment Module\*\* | Handles repayment flows from borrowers to investors                        |

| \*\*SPV Integration\*\* | Ties on-chain activity to off-chain legal contracts via special entities    |

| \*\*Governance\*\*     | DAO or multisig control over protocol parameters and pool approvals         |



\## Capital Lifecycle



1\. \*\*Investor deposits USDC\*\* into a senior or junior tranche.

2\. \*\*Borrower requests financing\*\* and posts off-chain collateral (e.g., invoice, property).

3\. \*\*SPV mints an NFT\*\* or debt token representing the asset on-chain.

4\. \*\*Loan is issued\*\* through the pool contract, deducting fees.

5\. \*\*Repayments\*\* are made over time and split across tranches.

6\. \*\*Investors redeem\*\* their yield + principal after lockup or maturity.



\## Key Smart Contract Roles



\- `PoolManager`: Approves new asset originators

\- `Tranche`: Manages risk-layered capital

\- `NAVOracle`: Tracks value of the underlying assets

\- `Assessor`: Determines pricing and payout conditions

\- `Coordinator`: Handles batch operations like epoch rolling or reward calculation



\## Data Flow (Simplified)

User → Frontend → Vault Contract → Tranche → Asset NFT → NAV Oracle → Repayment Flow → Token Holder

## External Integrations



\- \*\*Chainlink / Pyth\*\*: Price oracles

\- \*\*IPFS / Arweave\*\*: Document storage

\- \*\*KYC Providers\*\*: Whitelisting investors

\- \*\*Legal SPVs\*\*: Contractual asset backing



\## Security Considerations



\- Tranche configuration errors can misprice risk

\- NAV oracle manipulation may cause misallocated redemptions

\- Front-running pool operations (e.g., mid-epoch deposits)

