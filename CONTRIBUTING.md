# Contributing to Estamora

Welcome to the Estamora organization! Estamora is an open-source, policy-guarded payments, milestone escrow, and pre-flight simulation protocol built on Stellar (Soroban).

## The Estamora Stack

| Repository | Role | Technology |
| :--- | :--- | :--- |
| [**`estamora-contracts`**](https://github.com/Estamora-Soroban-Layers/estamora-contracts) | Soroban smart contracts | Rust, Soroban SDK v22.0.8, WebAssembly |
| [**`estamora-sdk`**](https://github.com/Estamora-Soroban-Layers/estamora-sdk) | Client SDK & Pre-flight simulation engine | TypeScript, `@stellar/stellar-sdk` |
| [**`estamora-app`**](https://github.com/Estamora-Soroban-Layers/estamora-app) | Merchant & Buyer Web Console | React 19, Vite, Freighter Wallet |
| [**`estamora-docs`**](https://github.com/Estamora-Soroban-Layers/estamora-docs) | Documentation & Architecture Hub | MkDocs Material |

## How to Contribute

1. **Pick an Issue**: Check out issues across the ecosystem repositories.
2. **Submit PRs**: Follow the PR guidelines in each respective repository:
   - Run `cargo test` on `estamora-contracts`.
   - Run `npm test` and `npm run typecheck` on `estamora-sdk`.
   - Run `npm run build` on `estamora-app`.
   - Run `mkdocs build --strict` on `estamora-docs`.
3. **Commit Sign-off**: Keep commit messages descriptive and concise.
