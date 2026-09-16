# `.github`

[![Specification CI](https://github.com/Estamora-Soroban-Layers/estamora-conformance-spec/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-conformance-spec/actions/workflows/ci.yml)
[![Runner CI](https://github.com/Estamora-Soroban-Layers/estamora-conformance-runner/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-conformance-runner/actions/workflows/ci.yml)
[![Docs CI](https://github.com/Estamora-Soroban-Layers/estamora-docs/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-docs/actions/workflows/ci.yml)
[![Documentation](https://img.shields.io/badge/docs-estamora--docs.vercel.app-blue)](https://estamora-docs.vercel.app)
[![Application](https://img.shields.io/badge/app-estamora--app.vercel.app-black?logo=vercel)](https://estamora-app.vercel.app)
[![License: Apache-2.0](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](https://github.com/Estamora-Soroban-Layers/estamora-conformance-spec/blob/main/LICENSE)

Organization-level community health files for
[Estamora Soroban Layers](https://github.com/Estamora-Soroban-Layers).

This repository holds no product code. It holds the things that must be true of the
organization rather than of any single repository.

## What is here

| Path | Purpose |
| --- | --- |
| [`profile/README.md`](profile/README.md) | The organization profile. GitHub renders this file on the [organization landing page](https://github.com/Estamora-Soroban-Layers). |
| [`SECURITY.md`](SECURITY.md) | The organization-wide security policy. Applies to every repository that does not declare its own. |

## The organization this repository configures

| Repository | Owns | Live |
| --- | --- | --- |
| [`estamora-conformance-spec`](https://github.com/Estamora-Soroban-Layers/estamora-conformance-spec) | What conformance *means*: the profiles, vectors and schemas, and the tooling that keeps them consistent | [Reference set](https://estamora-soroban-layers.github.io/estamora-conformance-spec/) |
| [`estamora-conformance-runner`](https://github.com/Estamora-Soroban-Layers/estamora-conformance-runner) | *Measuring* a deployed contract against those requirements | [Documentation](https://estamora-docs.vercel.app) |
| [`estamora-docs`](https://github.com/Estamora-Soroban-Layers/estamora-docs) | *Explaining* both, assembled from pinned revisions of the two above | [estamora-docs.vercel.app](https://estamora-docs.vercel.app) |
| [`estamora-app`](https://github.com/Estamora-Soroban-Layers/estamora-app) | *Showing* conformance evidence for live testnet contracts | [estamora-app.vercel.app](https://estamora-app.vercel.app) |

None of those lives here. This repository holds the files that must be true of all of them,
which is why a change to one of them is a change in the repository that owns it — never an
edit here.

## How the profile README works

GitHub renders `profile/README.md` from the repository named `.github` — the literal
name, including the leading dot — as the public landing page for the organization. It is
rendered from `main`, so a change to it takes effect on merge.

## Repository-specific files win

GitHub falls back to the files in this repository only when a repository does not define
its own. Every Estamora repository declares its own `SECURITY.md`, so the file here is a
*default for future repositories*, not an override of the existing ones. Keeping both is
intentional: the default means a new repository is never left without a reporting
channel, which is the failure this file specifically exists to prevent.

## License

Apache-2.0. The license text lives in
[`estamora-conformance-spec/LICENSE`](https://github.com/Estamora-Soroban-Layers/estamora-conformance-spec/blob/main/LICENSE)
and is the same across every Estamora repository.
