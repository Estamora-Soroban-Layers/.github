# Security Policy

**This file is the organization-wide default for
[Estamora Soroban Layers](https://github.com/Estamora-Soroban-Layers).** Every existing
Estamora repository declares its own `SECURITY.md`, and a repository-specific policy
always takes precedence over this one. This default exists so that a new repository is
never left without a reporting channel.

## Reporting a vulnerability

Use GitHub's **private vulnerability reporting** on the affected repository. It is
enabled on every Estamora repository:

`https://github.com/Estamora-Soroban-Layers/<repository>/security/advisories/new`

If you cannot use that form, email <danielwinningtalkerloba@gmail.com> with `[SECURITY]`
in the subject.

**Do not open a public issue for a vulnerability.**

Please include the repository and revision, what the impact is, and the smallest
reproduction you can produce. If you have a suggested fix, include it — but do not wait
for one before reporting.

## What to expect

| Stage | Target |
| --- | --- |
| Acknowledgement | 3 working days |
| Initial assessment, including whether we consider it in scope | 10 working days |
| Fix, or a written explanation of why we are not fixing it | 90 days from acknowledgement |

We will credit you in the advisory unless you ask us not to.

## In scope

The scope of a report depends on which repository it concerns, and each repository's own
`SECURITY.md` states it precisely. In general:

- **`estamora-conformance-runner`** — anything that lets a contract be reported
  `CONFORMANT` when it does not conform, or `NON_CONFORMANT` when it does; anything that
  makes a report non-reproducible; anything that lets executing an untrusted profile or
  vector escape the sandbox, read files it should not, or exhaust the machine.
- **`estamora-conformance-spec`** — a normative requirement that contradicts another one,
  a schema that does not constrain what the documentation says it constrains, or a
  published profile that does not implement the upstream specification it cites.
- **`estamora-docs` and `estamora-app`** — script injection, unsafe rendering of
  externally supplied data, or exposure of credentials.

## A finding in a contract measured by Estamora is not a finding in Estamora

If a contract fails conformance, or has a bug that Estamora did not detect, that is not a
vulnerability in Estamora — it is the expected behaviour of a tool that measures against
a written specification. Report it to the contract's maintainers.

The one exception is the case that *is* in scope: if Estamora reports `CONFORMANT` for a
contract that does not conform to the profile it was measured against, that is a defect
in Estamora. Report it here.

## Conformance is not security

Passing a profile means a contract behaves as that profile defines. Profiles are written
by people. A profile that does not state a failure mode does not detect it.

A `CONFORMANT` verdict is **not** an audit, and must not be presented as evidence that a
contract is safe. Estamora does not replace formal verification, economic analysis or
human review.

## Supported versions

The latest released minor of each artifact receives security fixes. Pre-release and
`draft` profiles receive fixes on a best-effort basis, and we may instead withdraw a
`draft` and publish a corrected version, because a change that alters what a profile
requires is a version change and never an edit.
