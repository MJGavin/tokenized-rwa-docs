# Protocol Design

This document outlines the design architecture of the tokenized RWA protocol, emphasizing modularity, compliance, and lifecycle flexibility for regulated assets.

## Objectives

- Represent real-world assets (RWAs) on-chain in a secure, compliant manner
- Ensure investor protection and enforceable rights
- Enable modular compliance checks and jurisdictional adaptability
- Allow upgrades without contract redeployment

## Key Components

### 1. Identity and Compliance Layer

- **Identity Registry**: A smart contract storing whitelisted investor wallet addresses mapped to their off-chain identity verification (KYC/AML).
- **Compliance Module**: Customizable logic for validating transfers, including:
  - Jurisdictional restrictions
  - Investor caps
  - Holding periods
  - Transfer locks (manual or rule-based)

> Modeled on Tokeny’s “OnchainID” and compliance extensions.

### 2. Token Contract (ERC-3643 Compatible)

- **Modular ERC-3643 (T-REX) standard** or upgradeable ERC-20 derivative
- Integrated with identity and compliance layers
- Roles:
  - **Controller**: Override transfer restrictions in emergencies
  - **Issuer**: Mint and burn tokens as needed
  - **Agent**: Perform operational actions on behalf of issuer (e.g., forced transfers)

### 3. Asset Vault / Off-chain Representation

- RWA tokens reference an off-chain asset custodied by a regulated SPV or trustee
- Legal agreement binds token ownership to asset claims
- Transparency ensured via:
  - Public audit trails
  - On-chain attestation to off-chain events

### 4. Transfer Mechanics

- Transfers validated via:
  - Compliance module
  - Identity registry
  - Transfer rules (e.g., time-based lockups)
- Forced transfers possible by issuer in extreme cases (e.g., lost keys, court order)

### 5. Upgradeability

- Proxy-based architecture (e.g., OpenZeppelin Transparent Proxy)
- Enables upgradable business logic while preserving state and addresses

---

## Lifecycle Overview

1. **Token Issuance**: Issuer mints tokens to verified investors
2. **Secondary Trading**: Compliant transfers validated at each hop
3. **Redemption**: Investor returns tokens; off-chain asset claim is fulfilled
4. **Upgrade Path**: Contracts upgradable via governance or multi-sig

---

## Governance & Controls

- **Multi-signature controls** over minting, burning, and upgrades
- Optional DAO for community governance
- Emergency pause functionality

---

## Interoperability

- Compatible with institutional custody providers (e.g., Fireblocks, Anchorage)
- Can integrate with permissioned DeFi protocols

---

## Next Steps

- Finalize smart contract templates
- Engage with legal counsel on enforceability
- Launch MVP with test asset class (e.g., tokenized Treasury bills)