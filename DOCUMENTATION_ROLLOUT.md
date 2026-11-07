# Cross-repository documentation rollout

**Inventory snapshot:** November 6, 2026 (UTC). The connected inventory included **46 accessible repositories**, comprising **35 public** and **11 private** repositories in the VizHub organization. This public plan lists only public repositories.

## Delivery model

One **documentation-only PR per writable repository**, following [DOCUMENTATION_STANDARDS.md](./DOCUMENTATION_STANDARDS.md). Each PR is reviewed and merged independently. Avoid touching application code, CI configuration, package manifests, dependencies, or production infrastructure in the same PR.

| Wave | Scope | Exit criteria |
| --- | --- | --- |
| **0 — Foundation** | This `.github` repository: shared standards, public catalog, organization profile | Review and merge the foundation PR |
| **1 — Core** | Main user-facing platforms, editor and operations documentation | Current-vs-legacy product descriptions and onboarding reconciled |
| **2 — Components** | Runtime, editor libraries, SDKs, templates, benchmarking and examples | Commands, interfaces, and cross-links checked against source |
| **3 — Historical** | Earlier platform generations, prototypes, experiments and historical community support | Clear historical context and accurate links |
| **Exception — Archived** | `vizhub-libraries` | Keep read-only unless an authorized maintainer temporarily unarchives for a docs PR |

The [public repository catalog](./REPOSITORY_CATALOG.md) assigns a proposed wave and repository-specific focus to each public repository. These are planning categories, not verified maintenance labels.

## Suggested PR order

1. Merge Wave 0 before rolling its conventions into other repositories.
2. Prioritize repositories with outdated product identity, incorrect active/deployed claims, or broken onboarding.
3. Batch subsequent PRs by wave, but keep changes independently reviewable. Do not blindly apply one README template to every repository.
4. Use the common [PR checklist](./DOCUMENTATION_STANDARDS.md#documentation-only-pr-checklist) and record the evidence used for setup and API claims.
5. Record per-repository PR URLs, merged state, blockers, and review notes as work proceeds. Update the catalog snapshot when inventory changes, not just when a repository is pushed.
6. For private repositories, keep the detailed tracker and PR links in an access-controlled project repository. Do not mirror private names, metadata, or internal descriptions into this public catalog.

## PR description template

~~~markdown
## Documentation scope
- Repository purpose and doc entry points updated
- Verified facts and paths against the current default branch
- Documentation-only; no code, dependencies, infrastructure, or deployment changes

## Verification
- Commands/scripts checked against: ...
- Local links/assets/anchors checked: ...
- Docs checks executed (or unavailable): ...

## Historical and unresolved claims
- Legacy instructions retained or labeled: ...
- Claims intentionally not verified: ...

## Follow-ups
- ...
~~~

## Important exceptions

- **Archive:** `vizhub-libraries` is archived. Do not alter its archive state just to satisfy a numerical PR target without approval.
- **Private repositories:** The public count is not the whole organizational scope. Internal planning must use equivalent access controls before adding private repo entries.
- **Activity dates:** GitHub `pushed_at` timestamps may reflect any branch and do not establish last default-branch change or current operational status.
- **Products:** The technical GitHub repository names do not determine the user-facing VizHub branding or production deployment state.
