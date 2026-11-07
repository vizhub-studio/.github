# VizHub documentation standards

> **Scope:** Documentation in repositories maintained by the VizHub organization. These are editorial and verification standards, not requirements to adopt a particular framework or application architecture.
>
> **Maintainer note:** This public repository must not disclose the names, source contents, credentials, operations, or roadmaps of private repositories.

## Goals

Documentation should let a new reader answer five questions without guessing:

1. **What is this repository?** State its purpose, intended audience, and relation to VizHub.
2. **What is its actual status?** Distinguish active, maintenance-only, experimental, historical, and archived work based on verified evidence.
3. **How do I use or develop it?** Provide commands and examples that correspond to checked-in scripts and actual exported interfaces.
4. **Where do I find deeper information?** Use a small, accurate navigation structure and canonical links.
5. **What are its limitations?** Clearly separate supported behavior from proposals, experiments, and legacy instructions.

Use the most complete, accurate, maintained documentation as a quality reference, **not** as text to copy indiscriminately. The appropriate size of the documentation depends on the repository.

## Required README structure

Use these sections as a checklist, not as a rigid template. A small library may need only a short README; a deployed application may need a separate documentation index.

- **Title and one-paragraph summary:** Explain what the project does; avoid aspirational feature claims.
- **Status and scope:** Explicitly label historical or experimental repositories; verify active support rather than inferring it from recent push dates.
- **Quick start or usage:** Show the minimum reproducible workflow, with prerequisites and environment assumptions.
- **Key features / API:** Only describe functionality confirmed by source, tests, or a maintained example.
- **Development and verification:** List commands actually present in the package manifest or tooling configuration, and warn about destructive commands.
- **Architecture / design:** Link to deeper documentation when necessary; avoid duplicating implementation details.
- **Related projects:** Link to relevant public repositories and the [public repository catalog](./REPOSITORY_CATALOG.md).
- **Contributing and license:** Link to actual contribution and license files, if present; do not invent a license or contribution policy.

Avoid adding placeholder sections. When functionality is not verified, omit it or mark it as unverified and explain what needs checking.

## Source of truth and technical claims

1. Read the default branch's README, relevant package manifests, scripts, exports, routes, configuration, tests, and existing documents before editing.
2. **Code, tests, and checked-in configuration win** when a README disagrees with them. Record unresolved discrepancies in the PR rather than guessing.
3. Validate example commands against the repository's scripts, expected working directory, and required tooling. A `README` example is not verified merely because it looks plausible.
4. Do not claim a feature is deployed, enabled, or available to customers simply because its code exists or a PR merged. Document source state, deployment evidence, configuration/feature flags, and rollout state separately where relevant.
5. Do not copy dates, version numbers, benchmark results, pricing, uptime, API endpoints, or feature matrices from older documents without verification.
6. If evidence is unavailable, write **“not verified”** rather than inventing an assertion.
7. Use **last pushed** only as repository activity metadata. It is not proof of active maintenance, a default-branch merge, or a production deployment.

## Naming and cross-repository relationships

- **VizHub** is the user-facing product name at [vizhub.com](https://vizhub.com/). Keep existing technical repository identifiers intact; they are not necessarily product brands.
- **VizHub Cloud** identifies a legacy product/system. Historical documents should distinguish it from the current VizHub product; do not silently rewrite historical design descriptions.
- **VZCode** is a separately named editor project. Use its published/project-specific name when referring to that editor.
- Refer to old products, infrastructure, domains, and screenshots in historical context, not as default onboarding or active deployment instructions.
- Prefer links to the actual current GitHub repository. Existing redirects can be retained when verified as intentional; broken or relocated `vizhub-core`, `datavis-tech`, or other legacy links should be assessed individually.
- Cross-reference public components through [REPOSITORY_CATALOG.md](./REPOSITORY_CATALOG.md); never imply that every component is currently incorporated into the active product.

## Security, privacy, and operations

- Do not commit credentials, API keys, tokens, internal hostnames, private customer data, billing details, or nonpublic deployment instructions to public documentation.
- Do not reveal or enumerate private repository names in this organization's public documentation. Track private-repository documentation work in a repository with equivalent access controls.
- Use placeholder environment variables, redact sensitive output, and explicitly identify secret-bearing files that must remain uncommitted.
- Tag destructive or production-affecting commands, such as database resets, credential rotation, migrations, and deployments. Never present them as routine setup commands without context and safety checks.
- Avoid source-code, dependency, build, or deployment changes in documentation-only PRs, unless separately approved.

## Navigation and document lifecycle

- Keep the README a compact, reliable entry point. Move long-form reference material into well-named documents when it improves findability.
- If a repository already has documentation indexes or `AGENTS.md` instructions, link to them rather than creating competing indexes.
- Prefer relative links inside the same repository and canonical GitHub links across repositories.
- Fix broken anchors, paths, and links. Do not delete useful historical design notes merely because they are old: label and relocate them where appropriate.
- Treat plans and proposals as plans, not confirmed behavior. Include a date or version/context when claims are time-sensitive.
- Avoid unmaintained counts and manually numbered “complete” inventories that will drift unless a clear maintenance process exists.

## Documentation-only PR checklist

Every Wave 1–3 documentation PR should address the applicable checks:

- [ ] Changes are confined to documentation and necessary documentation assets.
- [ ] README identifies the repository's purpose, audience, and verified status.
- [ ] Installation, test, and development commands match the checked-in scripts/configuration, or are clearly marked unverified.
- [ ] Technical assertions are supported by implementation, tests, or other explicit evidence.
- [ ] User-facing product terminology and cross-repository links are consistent.
- [ ] Historical features and old deployment endpoints are not described as current.
- [ ] New and changed relative links, image references, and Markdown anchors are checked.
- [ ] No secrets, private repo names, private infrastructure details, or sensitive customer information are disclosed.
- [ ] Any available documentation validation is run; unavailable checks are explicitly noted.
- [ ] The PR describes changes, evidence, limitations, and any follow-on documentation-only work.

## Right-sizing guide

| Repository type | Typical documentation |
| --- | --- |
| Small library / theme | README with installation, usage, API, examples, status |
| Editor / SDK / runtime | README plus API/architecture or integration docs as needed |
| App / service | README, environment/setup, architecture, testing, operations docs separated by access level |
| Template / example | README with reproducible starting point, prerequisites, customization, examples |
| Historical / abandoned experiment | README explaining purpose, historical period, reproducibility if possible, and current alternatives |
| Archived repository | Preserve archived state; catalog it here. A documentation PR requires unarchiving by an authorized maintainer |

See [Documentation rollout](./DOCUMENTATION_ROLLOUT.md) for the sequence and review process.
