<div align="center">

# Estamora Payment Protocol

**Policy-guarded milestone escrow, dispute arbitration, and spend-cap micro-payments on Stellar (Soroban).**

[![Contracts CI](https://github.com/Estamora-Soroban-Layers/estamora-contracts/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-contracts/actions/workflows/ci.yml)
[![SDK CI](https://github.com/Estamora-Soroban-Layers/estamora-sdk/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-sdk/actions/workflows/ci.yml)
[![App CI](https://github.com/Estamora-Soroban-Layers/estamora-app/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-app/actions/workflows/ci.yml)
[![Docs CI](https://github.com/Estamora-Soroban-Layers/estamora-docs/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-docs/actions/workflows/ci.yml)
[![Documentation site](https://img.shields.io/badge/docs-estamora--docs.vercel.app-blue)](https://estamora-docs.vercel.app)
[![Application](https://img.shields.io/badge/app-estamora--app.vercel.app-black?logo=vercel)](https://estamora-app.vercel.app)
[![License: Apache-2.0](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](LICENSE)

</div>

---

## Overview

**Estamora** brings programmable trustless payments and non-custodial milestone escrow to the Stellar network. Built natively on **Soroban**, the protocol provides:

1. **Milestone & Time-Locked Escrows**: Buyer funds are locked safely in contract custody and released upon verified delivery, with automatic timeout refunds to buyers if orders expire unfulfilled.
2. **Dispute Resolution & Fair Splits**: Neutral arbitration mechanism for fair percentage settlements between buyers and sellers.
3. **Delegated Spend Caps (AI Agent Firewall)**: Account owners grant secondary accounts (AI agents, automated daemons) controlled spending permissions with strict per-transaction and 24-hour rolling window caps.
4. **Zero-Broadcast Pre-Flight Simulation**: `@estamora/sdk` estimates resource fees and CPU budgets via RPC before requesting wallet signatures.

---

## Live Product In Action

### Decentralized Application Console
Live non-custodial dashboard connecting directly to Freighter wallet and Stellar Testnet.

![Estamora Dashboard Console](profile/assets/screenshots/estamora-dashboard.png)

### Developer Documentation Portal
Comprehensive architectural guides, smart contract references, and integration tutorials.

![Estamora Documentation Portal](profile/assets/screenshots/estamora-docs.png)

---

## Repositories & Architecture

| Repository | Role | Technology | Live Links |
| :--- | :--- | :--- | :--- |
| [**`estamora-contracts`**](https://github.com/Estamora-Soroban-Layers/estamora-contracts) | Soroban smart contracts: milestone escrow, dispute split arbitration, and delegated spend limits. | Rust, Soroban SDK v22 | [Contracts](https://github.com/Estamora-Soroban-Layers/estamora-contracts) |
| [**`estamora-sdk`**](https://github.com/Estamora-Soroban-Layers/estamora-sdk) | Client SDK, pre-flight simulation engine, transaction builders, and structured error decoders. | TypeScript, `@stellar/stellar-sdk` | [Client SDK](https://github.com/Estamora-Soroban-Layers/estamora-sdk) |
| [**`estamora-app`**](https://github.com/Estamora-Soroban-Layers/estamora-app) | Interactive merchant dashboard, checkout simulator, and Freighter wallet operator console. | React 19, Vite, TypeScript | [Live DApp](https://estamora-app.vercel.app) |
| [**`estamora-docs`**](https://github.com/Estamora-Soroban-Layers/estamora-docs) | Documentation hub, technical guides, contract references, and architecture maps. | MkDocs Material | [Live Docs](https://estamora-docs.vercel.app) |

---

## Testnet Deployment

- **Contract ID**: `CADQOBYHA4DQOBYHA4DQOBYHA4DQOBYHA4DQP5KR`
- **Network**: Stellar Testnet
- **WASM Size**: `26,247 B (26.2 KB)`
- **RPC**: `https://soroban-testnet.stellar.org`

---

## Community & Contributing

We actively welcome contributors from the Stellar ecosystem:

- 💬 **Telegram**: [Estamora Community](https://t.me/estamora_stellar)
- 👾 **Discord**: [Estamora Developers](https://discord.gg/estamora-dev)
- 👤 **Maintainer**: [@winningtalker-commits](https://github.com/winningtalker-commits)
