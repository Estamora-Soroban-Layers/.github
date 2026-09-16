# `.github`

[![Specification CI](https://github.com/Estamora-Soroban-Layers/estamora-conformance-spec/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-conformance-spec/actions/workflows/ci.yml)
[![Runner CI](https://github.com/Estamora-Soroban-Layers/estamora-conformance-runner/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-conformance-runner/actions/workflows/ci.yml)
[![Docs CI](https://github.com/Estamora-Soroban-Layers/estamora-docs/actions/workflows/ci.yml/badge.svg)](https://github.com/Estamora-Soroban-Layers/estamora-docs/actions/workflows/ci.yml)
[![Documentation](https://img.shields.io/badge/docs-estamora--docs.vercel.app-blue)](https://estamora-docs.vercel.app)
[![Application](https://img.shields.io/badge/app-estamora--app.vercel.app-black?logo=vercel)](https://estamora-app.vercel.app)
[![License: Apache-2.0](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](LICENSE)
[![Contributors](https://img.shields.io/github/contributors/Estamora-Soroban-Layers/.github)](https://github.com/Estamora-Soroban-Layers/.github/graphs/contributors)

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

## How a change reaches production, and what protects `main`

Everything here is deployed by a GitHub Actions job rather than by a Git integration, and that is
a decision rather than an omission.

| Step | Who does it |
| --- | --- |
| Build | CI builds the artefact and runs the repository's checks. The build output is what gets published. |
| Publish | The deploy job publishes the artefact CI built, with `vercel deploy --prebuilt --prod`. |
| Verify | That same job then asserts the published result — the published pages, and the pitch as `video/mp4` with byte-range support. |
| Vercel's Git integration | **Off.** Neither `estamora-docs` nor `estamora-app` is connected to its repository. |

Connecting Vercel's own Git integration would deploy every push before anything had checked it,
and would deploy the same commit a second time from a build Actions had already made. Two
deployments per push, one of them unverified, and the alias does not say which landed. Publishing
the artefact CI built keeps one property worth more than the convenience: **what is deployed is
what CI checked.** The cost is that a deployment now depends on a workflow — which is why the
deploy job asserts the result rather than trusting the exit code of a publish command.

### What protects `main`

Every repository protects `main`, with `strict` on, so a pull request must be up to date with the
branch before it can merge. The counts differ because the repositories do:

| Repository | Required checks | Required approvals |
| --- | ---: | ---: |
| `estamora-conformance-runner` | 20 | 0 |
| `estamora-docs` | 9 | 0 |
| `estamora-conformance-spec` | 8 | 0 |
| `estamora-app` | 7 | 0 |
| `.github` | 0 | 1 |

Nothing verifies the counts above, and that is worth saying in a project whose house rule is that a
figure with no check behind it goes stale. This repository runs no workflows — it holds nothing to
run them against — so the table is as current as the last edit to it. Each repository's own
protection settings remain the authoritative record; the table mirrors them because a reader of the
organization profile should not have to open five settings pages to find out what protects `main`.

This repository requires a review and no checks because it holds no code for a check to run. The
four code repositories require no review, which is deliberate for a project with one maintainer: a
review requirement the only person who can approve must also satisfy adds a step rather than a
check. What the required checks continue to do is block a merge that is red, and that is the part
that catches mistakes.

`enforce_admins` is **off** on all five, so an administrator can push past those checks. Worth
stating rather than leaving as an invisible property of the settings: it means a red `main` is
possible, GitHub prints the bypass in the push output when it happens, and the alternative —
enforcing the rules on administrators too — makes every commit a pull request, which for a
single-maintainer project trades a visible risk for a great deal of ceremony.

## License

Apache-2.0. [`LICENSE`](LICENSE) here is byte-identical to the copy in each of the four
other repositories, so there is no second version of the license to compare and no
ambiguity about which one applies to what.
