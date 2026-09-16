# `.github`

Organization-level community health files for
[Estamora Soroban Layers](https://github.com/Estamora-Soroban-Layers).

This repository holds no product code. It holds the things that must be true of the
organization rather than of any single repository.

## What is here

| Path | Purpose |
| --- | --- |
| [`profile/README.md`](profile/README.md) | The organization profile. GitHub renders this file on the [organization landing page](https://github.com/Estamora-Soroban-Layers). |
| [`SECURITY.md`](SECURITY.md) | The organization-wide security policy. Applies to every repository that does not declare its own. |

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
