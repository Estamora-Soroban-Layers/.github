# `.github`

[![Specification CI](https://github.com/Estamora-Soroban-Layers/estamora-conformance-spec/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-conformance-spec/actions/workflows/ci.yml)
[![Runner CI](https://github.com/Estamora-Soroban-Layers/estamora-conformance-runner/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-conformance-runner/actions/workflows/ci.yml)
[![Docs CI](https://github.com/Estamora-Soroban-Layers/estamora-docs/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-docs/actions/workflows/ci.yml)
[![Documentation](https://img.shields.io/badge/docs-estamora--docs.vercel.app-blue)](https://estamora-docs.vercel.app)
[![Application](https://img.shields.io/badge/app-estamora--app.vercel.app-black?logo=vercel)](https://estamora-app.vercel.app)
[![License: Apache-2.0](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](LICENSE)

Organization-level community health files for
[Estamora Soroban Layers](https://github.com/Estamora-Soroban-Layers).

This repository holds no product code. It holds the things that must be true of the
organization rather than of any single repository.

## What is here

| Path | Purpose |
| --- | --- |
| [`profile/README.md`](profile/README.md) | The organization profile. GitHub renders this file on the [organization landing page](https://github.com/Estamora-Soroban-Layers). |
| [`SECURITY.md`](SECURITY.md) | The organization-wide security policy. Applies to every repository that does not declare its own. |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Where a change belongs. Routes each repository's subject matter to the repository that owns it, then states the conventions that hold in all four. |
| [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) | The Contributor Covenant, with the clause that is specific to this repository: describe what the other four do, and no more than that. |
| [`LICENSE`](LICENSE) | Apache-2.0, byte-identical to the copy in each of the four repositories. |
| [`.coderabbit.yaml`](.coderabbit.yaml) | The organization default for review configuration: how a change should be argued, and the secret scanning no repository can switch off by accident. |

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
its own, and that applies to `SECURITY.md`, `CONTRIBUTING.md` and `CODE_OF_CONDUCT.md`
alike. All four Estamora repositories declare their own, so the files here are *defaults
for future repositories* rather than overrides of the existing ones. Keeping both is
intentional, and the reason is the same in every case: a new repository is never left
without a reporting channel, a contribution guide or a code of conduct, which are exactly
the failures these files exist to prevent.

`LICENSE` is the exception, and it is worth knowing why: GitHub does **not** use it as a
default for other repositories. A license is per-repository and cannot be inherited, which
is why the same text is committed to all five. It is kept byte-identical so that a reader
comparing two repositories cannot find a difference that is not there.

## License

Apache-2.0. [`LICENSE`](LICENSE) here is byte-identical to the copy in each of the four
other repositories, so there is no second version of the license to compare and no
ambiguity about which one applies to what.
