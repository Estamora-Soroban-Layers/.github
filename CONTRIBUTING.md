# Contributing to Estamora

Four repositories, one project. This file does one job: it says **which repository owns what**, so
that a change lands somewhere a reviewer can actually judge it.

It deliberately does not repeat the rules. Each repository documents its own process, in more
detail than an organization-wide file could, and where this file and a repository's own
`CONTRIBUTING.md` disagree, **the repository's own wins**. That is not a courtesy — the
documentation site's second rule is that a normative statement is never restated, and a
contribution guide has no exemption from the principles it exists to route.

## What each repository owns

| Repository | Owns | Its own rules |
| --- | --- | --- |
| [`estamora-conformance-spec`](https://github.com/Estamora-Soroban-Layers/estamora-conformance-spec) | What conformance **means**: profiles, vectors, schemas, and the tooling that keeps them consistent | Four review questions — cited, checkable, falsifiable, scoped |
| [`estamora-conformance-runner`](https://github.com/Estamora-Soroban-Layers/estamora-conformance-runner) | **Measuring** a deployed contract against those requirements | What a change has to satisfy; the exit-code contract |
| [`estamora-docs`](https://github.com/Estamora-Soroban-Layers/estamora-docs) | **Explaining** both, assembled from pinned revisions rather than restated | A document lives in the repository that owns it; a normative statement is never restated |
| [`estamora-app`](https://github.com/Estamora-Soroban-Layers/estamora-app) | **Showing** conformance evidence for live testnet contracts | A claim about the format is a rule, not a sentence; never make a value look more complete than it is; no code path signs or submits |
| [`.github`](https://github.com/Estamora-Soroban-Layers/.github) | The organization profile and the policies that must hold across all four | This file |

## Where a change belongs

One rule settles almost everything: **a change is made in the repository that owns the fact, never
in one that restates it.** A fix applied where the fact is displayed rather than where it is owned
is a fix that will be undone by the next assembly.

| The thing you want to change | The repository |
| --- | --- |
| A requirement, a profile identity, a vector, a schema | `estamora-conformance-spec` |
| A measurement, an assertion kind, an exit code, a report format | `estamora-conformance-runner` |
| A curated page — the guides, the concepts, the reference that explains the other two | `estamora-docs` |
| A page under `runner/` or `spec/` on the documentation site | Not `estamora-docs` — those are assembled from the repositories above, so the fix is upstream and the site picks it up when the pin moves |
| A view, an audit rule, a live contract read, a badge or figure the application displays | `estamora-app` |
| The organization profile, the security policy, this file | `.github` |

Two cases are worth stating because they look like exceptions and are not. A **curated** page on
the documentation site that contradicts a document it assembles is a defect *there*, not upstream —
that is what the site's `pins` and `video` jobs exist to catch. And a contract that fails a profile
is not a defect anywhere in this organization: it is the result the profile exists to produce.

## The conventions that hold across all four

**One commit per improvement.** The message explains the *why* — which defect the change makes
impossible, or which requirement it pins. This is not a style preference: the history of a project
like this is part of what makes it reviewable, and a commit that bundles a requirement change with
a formatting change cannot be reviewed at all.

**A figure in prose is a claim.** Counts, coverage percentages, durations, ledger numbers and
measurements go stale, and no linter reads English. State it where an artefact owns it, or say
which check fails when the two disagree. The documentation site and the runner both have jobs that
exist because a restated figure had quietly stopped being true.

**Evidence has to be reproducible.** A measurement names the revision it was taken from and the
artefact it measured. That is why the runner refuses to record a testnet report whose recorded
code hash is not the hash of the artifact the repository commits: evidence tied to bytes that have
moved on says nothing about what a reader will build.

**A pinned reference is part of what a result means.** The documentation site names the tag each
assembled page came from, and the runner pins the specification. Moving a pin to make a page read
better silently changes what somebody else already cited.

**Conformance is not security.** No repository, at any layer, may present a passing result as
making a contract safe. It is the one claim the whole project is built to avoid making, and it is
enforced by the absence of code as much as by anything a test can check.

## Getting a checkout working

Locally, each repository runs the same chain its CI runs, so a green local run means a green pull
request. The exact commands are in each repository's own guide; these are the entry points.

| Repository | Set up | The chain |
| --- | --- | --- |
| `estamora-conformance-spec` | `npm ci` | `npm run ci` |
| `estamora-conformance-runner` | `./scripts/install.sh` | `./scripts/run-ci.sh` |
| `estamora-docs` | `python3 -m venv .venv && . .venv/bin/activate` | the `scripts/check-*.py` checks, then `./scripts/build-site.sh` |
| `estamora-app` | `npm ci` | `npm run ci` |

## Review

`main` is protected in every repository and requires that repository's checks, so a pull request
cannot merge red. Beyond that, a reviewer will ask for the reasoning rather than the diff, and each
repository states the questions it reviews against — the specification's four questions, the
runner's requirements for what a change has to satisfy, the application's three rules, the
documentation site's two. Read the one that applies before opening the pull request; it is
considerably shorter than the review round it replaces.

## Licensing and conduct

Everything here is [Apache-2.0](LICENSE). By contributing, you agree your contribution is licensed
under the same terms.

Participation is covered by the [code of conduct](CODE_OF_CONDUCT.md). Security issues should not
be filed as public issues — see [SECURITY.md](SECURITY.md).
