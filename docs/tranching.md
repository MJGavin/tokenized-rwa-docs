\# Tranching in Tokenized RWA Protocols



Tranching is a capital structure technique that divides investor funds into different risk/return layers. In RWA DeFi protocols, tranching enables differentiated exposure to underlying credit risk and optimizes capital efficiency.



\## Why Tranching?



\- \*\*Risk separation\*\*: Junior tranches absorb losses first, protecting senior investors

\- \*\*Yield differentiation\*\*: Junior investors earn higher returns to compensate for higher risk

\- \*\*Capital leverage\*\*: Small junior capital base can unlock larger senior investments



\## Common Tranche Types



| Tranche | Risk | Return | Characteristics |

|--------|------|--------|-----------------|

| \*\*Senior (e.g., DROP)\*\* | Low | Low | First to be repaid, protected by junior |

| \*\*Junior (e.g., TIN)\*\* | High | High | Last to be repaid, absorbs losses |



\## Flow Example



1\. Investors deposit stablecoins into a pool.

2\. Capital is split: 80% to \*\*senior\*\*, 20% to \*\*junior\*\* tranche.

3\. Borrower draws funds; repayment flows back through the tranches.

4\. If losses occur, junior absorbs them first.



\## Tranching in Practice



\### Centrifuge

\- DROP (senior) and TIN (junior) tokens

\- Real-world receivables as collateral

\- Overcollateralized pools with rolling maturity



\### Goldfinch

\- Senior pool auto-diversifies across borrowers

\- Backers manually stake into junior tranches

\- Protocol ensures senior liquidity first



\### Maple Finance

\- LPs deposit into single-sided lending pool

\- Manager structures risk within the pool via underwriting



\## Risks of Tranching



\- Junior tranche default wipes out that layer

\- Senior tranche overconfidence in protection

\- Liquidity lockups depending on repayment schedule

\- Poor underwriting can break protections



\## Why It Matters



Tranching is the credit primitive of RWA DeFi. It enables open access to yield while maintaining risk buffers and legal compliance mechanisms through on-chain vaults.

