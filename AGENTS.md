# AGENTS.md

This is the repo-level operating contract for agents working in OWASP Developer Guide.
***These rules are requirements, not suggestions.***

## Project Goals

The OWASP Developer Guide is a free, open-source OWASP threat modeling tool.
It is a documentation project that provides software developers and development teams with insights into software security.

## Operating Contracts

### Agents

This is the repo-level operating contract for non-human OWASP Developer Guide contributors.
These rules are requirements, ***not suggestions***.

### Contributing

The [contributing.md](./contributing.md) file is the operating contract for our human contributors.
Non-human contributors must read, understand, and respect these contracts.

### Code of Conduct

The [code_of_conduct.md](./code_of_conduct.md) applies to all contributors -
regardless of whether the contributor is carbon-based, silicon-based, or legally ambiguous.

## Explicit Boundaries

1. Humans are responsible for all contributions, regardless of tooling.
2. AI should explicitly refuse to take action clearly prohibited by this AGENTS file
3. Humans write public product docs under `docs/`. Agents must not author docs pages
4. Humans create issues, comment on issues, submit pull requests, approve releases, publish artifacts
5. Humans decide roadmap or product policy
6. Agents may point out docs gaps, but a human must write the final docs text.
7. Agents may test docs with markdown linting, spellcheck, link checks, and local docs builds
8. Agents may edit code, tests, configuration, workflows, and maintainer scripts when explicitly asked
9. Agents must not open issues, comment on GitHub, open pull requests, approve pull requests
10. Agents must not commit, merge, push, release, or publish
11. Do not mix unrelated cleanup, dependency updates, formatting churn, or opportunistic refactors into task work

## Supply Chain / Dependencies

- ALL dependencies must have a minimum release age of 10 days
- No updates to lock-files unless intentionally doing dependency work
- GitHub Actions must be pinned to a full commit SHA with an inline version comment for Dependabot
- GitHub Actions have the same 10 day minimum release age requirement
- Prefer small helper scripts over new dependencies when reasonable

### docs

- Docs checks are for validation only: markdown lint, spellcheck, link check, and docs build where available

### Root level checks

- `npm run markdown:lint`
- Spellcheck is not available as an npm command. You can run it if:
  - the user has or approves installing pyspelling
  - the `en` dictionary is installed
  - `pyspelling -c .spellcheck.yaml`

## Directory Specific Context

### `docs/`

- Agents do not write public documentation pages.
- Agents may validate human-authored docs with markdown formatting, spellcheck, link checks, and local docs builds.
