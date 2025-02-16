# Repositories

This document describes the lifecycle of repositories under the [falcosecurity](https://github.com/falcosecurity) along with their criteria, structure, scope, and status.

**Table of Contents**

  - [Criteria](#criteria)
  - [Owners](#owners)
  - [License](#license)
  - [Status](#status)
  - [Lifecycle](#lifecycle)
    * [Addition](#addition)
    * [Change of Status](#change-of-status)
    * [Archiviation](#archiviation)
    * [Unarchiviation](#unarchiviation)
    * [Removal](#removal)
    * [Core Maintainers duties and privileges](#core-maintainers-duties-and-privileges)

**Resources**
<!-- NAVIGATION_LINKS -->
 - [Governance](https://github.com/falcosecurity/evolution/blob/main/GOVERNANCE.md)
 - [Code Of Conduct](https://github.com/falcosecurity/evolution/blob/main/CODE_OF_CONDUCT.md)
 - [Maintainers Guidelines](https://github.com/falcosecurity/evolution/blob/main/MAINTAINERS_GUIDELINES.md)
 - [Maintainers List](https://github.com/falcosecurity/evolution/blob/main/MAINTAINERS.md)
 - [Repositories Guidelines](https://github.com/falcosecurity/evolution/blob/main/REPOSITORIES.md)
 - [Repositories List](https://github.com/falcosecurity/evolution/blob/main/README.md#repositories)
 - [Adopters List](https://github.com/falcosecurity/falco/blob/master/ADOPTERS.md)
 - [Contributing](https://github.com/falcosecurity/.github/blob/main/CONTRIBUTING.md)
 - [Security policy](https://github.com/falcosecurity/.github/blob/main/SECURITY.md)
 - [Join the Community](https://github.com/falcosecurity/community)
<!-- /NAVIGATION_LINKS -->

## Criteria

Repositories host specific parts of The Falco Project such as core codebase components, documentation, tools, libraries, or subprojects. The [falcosecurity](https://github.com/falcosecurity) GitHub organization owns repositories exclusively related to The Falco Project or its ecosystem.

## Owners

Repositories must contain [OWNERS](https://www.kubernetes.dev/docs/guide/owners/) files following the Kubernetes specification. OWNERS files are used to designate responsibility over different parts of the repository codebase and serve as the implementation mechanism for the two-phase code review process used by each project. 

Each repository must have an `OWNERS` file in the root directory. Each sub-directory that contains a unit of independent code or content may also contain an OWNERS file. This file applies to everything within its directory, including the OWNERS file itself, sibling files, and child directories. There must be only one OWNERS file per directory.

As for the [Kubernetes specification](https://www.kubernetes.dev/docs/guide/owners/), OWNERS files are in YAML format and support a given set of keys, of which The Falco Project observes the following:

- `approvers`: Users that can `/approve` or `/lgtm` PRs. See [GOVERNANCE.md](GOVERNANCE.md#maintainers) for more details.
- `reviewers`: Users that are good candidates to `/lgtm` PRs. See [GOVERNANCE.md](GOVERNANCE.md#reviewers) for more details.
- `emeritus_approvers`: Users that used to be in `approvers` but can no longer dedicate the time needed to handle the responsibilities of reviewing and approving changes. See [GOVERNANCE.md](GOVERNANCE.md#emeritus-maintainers) for more details.

In OWNERS files, users are referenced by their GitHub usernames or aliases. In a given OWNERS file, a given user can't be listed in more than one of `approvers`, `reviewers`, and `emeritus_approvers`.

## License

Refer to [GOVERNANCE.md](GOVERNANCE.md#license).

## Status

Repositories get assigned a status that describes their scope and responsibilties inside The Falco Project.

- **Official**: [Core repositories](GOVERNANCE.md#core-repositories) of The Falco Project.
- **Incubating**: Repositories that contain non-core components or any subprojects that don't yet have an adequate level of maturity.
- **Sandbox**: Intended only for the [falcosecurity/contrib](https://github.com/falcosecurity/contrib) repository.
- **Special**: Repositories with a special function or a particular purpose for The Falco Project as a whole or the [falcosecurity](https://github.com/falcosecurity) GitHub organization, including but not limited to [this repository](https://github.com/falcosecurity/evolution), the [community](https://github.com/falcosecurity/community), the [.github](https://github.com/falcosecurity/.github) repository, and other particular ones like the [template repositories](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-template-repository).

The status of each repository is tracked in the [README.md](README.md) file of the [falcosecurity/evolution](https://github.com/falcosecurity/evolution) repository.

## Lifecycle

This section describes the lifecycle of the repositories hosted under the [falcosecurity](https://github.com/falcosecurity) GitHub organization.

Anyone can submit proposals regarding repositories' lifecycle by opening a GitHub issue in the
[falcosecurity/evolution](https://github.com/falcosecurity/evolution) repository (see below sections). The [Core Maintainers](GOVERNANCE.md#core-maintainers) will take into account the community feedback and decide on the proposal.

### Addition

New projects can be contributed to the falcosecurity organization by opening a GitHub issue in the
[falcosecurity/evolution](https://github.com/falcosecurity/evolution) repository.

If the decision is to add the proposed project, then one of the falcosecurity GitHub organization admins will assist the issue opener in transferring the repository to the falcosecurity organization and configuring it in [falcosecurity/test-infra](https://github.com/falcosecurity/test-infra). Upon addition, the repository must be reviewed to make sure it respects the [criteria](#criteria), [owners](#owners), and [license](#license) points of this document. In particular, when a repository is added, the proposed owners are reviewed as described by the [MAINTAINERS_GUIDELINES.md](MAINTAINERS_GUIDELINES.md) and eventually accepted.

Once the project is added to the falcosecurity GitHub organization, it will be owned and licensed by The Falco Project and will be subject to its [governance](GOVERNANCE.md).

When projects are first contributed to the [falcosecurity](https://github.com/falcosecurity) GitHub organization they are assigned the "Incubating" status, or the "Special" status if appropriate.

### Change of Status

Actively maintaining a repository might cause the evolution of its maturity, scope, and involvement, in The Falco Project. In those cases, the [Maintainers](GOVERNANCE.md#maintainers) of a given repository can propose changing its status by opening a GitHub issue in the [falcosecurity/evolution](https://github.com/falcosecurity/evolution) repository.

This is the path by which projects can be promoted from "Incubating" to "Official" status, or demoted from "Official" to "Incubating".

### Archiviation

Repositories showing little to no activity during the time span of a year can be proposed for archiviation by opening a GitHub issue in the [falcosecurity/evolution](https://github.com/falcosecurity/evolution) repository. [Archived repositories](https://docs.github.com/en/repositories/archiving-a-github-repository/archiving-repositories) will remain inside the falcosecurity GitHub organization but will be read-only and will not be maintained. As such, OWNERS files contained in archived repositories are not valid.

In some cases, a repository is archived to reserve its name for future use.

### Unarchiviation

Archived repositories can be proposed for unarchiviation by opening a GitHub issue in the [falcosecurity/evolution](https://github.com/falcosecurity/evolution) repository. If the decision is to unarchive the repository, then it must be reviewed to make sure it respects the [criteria](#criteria), [owners](#owners), and [license](#license) points of this document. In general, the same rules as for new repositories apply. The new proposed owners are reviewed as described by the [MAINTAINERS_GUIDELINES.md](MAINTAINERS_GUIDELINES.md) and eventually accepted.

### Removal

Repositories that show little relevance, are not maintained, or no longer have a purpose inside The Falco Project, can be proposed for removal by opening a GitHub issue in the [falcosecurity/evolution](https://github.com/falcosecurity/evolution) repository. Removed repositories will stop being maintained and will no longer be part of the falcosecurity GitHub organization. In such a case, one of the falcosecurity GitHub organization admins will assist the issue opener in transferring the repository to the [Falco Projects Retirement Home](https://github.com/falcosecurity-retire) GitHub organization and removing its configuration from [falcosecurity/test-infra](https://github.com/falcosecurity/test-infra).

### Core Maintainers duties and privileges

Since [Core Maintainers](GOVERNANCE.md#core-maintainers) as a team are responsible for the maintenance of the falcosecurity GitHub organization, they consequently have the following reserved powers:
 - decide on assigning or removing the "Official" status of a repository;
 - become maintainer of "Special" repositories;
 - become maintainer (or take control over) non-functioning or abandoned repositories (i.e., repositories with less than two active maintainers or disputed ones);
 - be the last escalation point for repositories disputes.

In all the above cases, [Core Maintainers](GOVERNANCE.md#core-maintainers) who volunteer to intervene must act with the spirit of serving the entire falcosecurity organization.