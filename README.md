# OSS Guidelines

**Archived**: I still follow the patterns described here, but the idea of documenting
and (automatically) enforcing them has not taken off.

Practices and standards for authoring and maintaining Open Source Software.

## Contents

- [Terminology](#terminology)
- [Status](#status)
- [Files](#files)
- [Versioning](#versioning)
- [Documentation](#documentation)
- [Testing](#testing)

## Terminology

| Term          | Definition |
| ---           | ---        |
| Project       | Space and materials allowing collaboration on a piece of software |
| Author        | Original creator(s) of the project |
| Maintainer    | Anyone with ownership of the project (including Author(s)) |
| Collaborator  | Anyone involved in the project (including Maintainers and Author(s)) |
| Pull Request  | A request by a collaborator to incorporate changes, and any ensuing discussion |
| Issue         | Information reported about the project (without proposed changes), usually about a bug or proposed feature |

## Status

Projects are in one of three statuses: `active`, `maintenance`, or `abandoned`.

### Active

Maintainers are currently engaged and working on this project.

Projects which do not specify a status can be assumed `active`. Projects which
are not `active` MUST include their status at the top of the project `README`.

### Maintenance

Maintainers are not currently engaged, but are available to perform maintenance
activities in a timely manner. Such activities include, but are not limited to,
Pull Request review, Issue triage, and fixing *critical* bugs.

No new versions should be expected, and the project may not build or run.

### Abandoned

No one is currently maintaining this project. Pull Requests or Issues may go
ignored. No new versions will be released, existing deployments will not be
managed.

## Files

Projects MUST have and maintain the following files:

- `README` (in any format, e.g. `README.md`)
- `CHANGELOG` (in any format, e.g. `CHANGELOG.md`)
- `LICENSE`
- `Makefile`

Templates are available in [./templates](./templates).

### README

Projects MUST have a `README` with the following sections in the following
order:

- *Description*
- *Installation* (if applicable)
- *Usage* (if applicable)
- *Development & Testing*
- Any other, project-specific sections
- A link to the `CHANGELOG`
- A link to the `LICENSE`

### CHANGELOG

Projects MUST keep a `CHANGELOG` of important changes occurring in each version
of the software released. Content SHOULD be edited (i.e. not just `git log`). A
section for unreleased changes SHOULD be present. Headers SHOULD link to online
diffs when available.

### LICENSE

Projects MUST have a `LICENSE` that clearly states the terms by which this
software can be used and/or shared. [MIT][] is recommended.

[MIT]: https://opensource.org/licenses/MIT

### Makefile

Projects MUST have a `Makefile` with at least one target: `make test`. All
project-related tasks (e.g. build, release, deploy) SHOULD be accomplished
through `make` targets.

## Versioning

Projects *on which others may depend* MUST follow [Semantic
Versioning][semantic-versioning].

[semantic-versioning]: http://semver.org/#summary

## Documentation

Projects MUST be documented.

Command-line applications MUST have a help message printed on invalid input
and/or an explicit `--help` flag. Command-line applications SHOULD have
man-pages installed with the application.

Libraries SHOULD use language-specific tools (e.g. Haddock, RDoc, etc) and their
output SHOULD be generated and made available online.

## Testing

Projects MUST have automated tests that run for every Pull Request.

---

[CHANGELOG](./CHANGELOG.md) | [LICENSE](./LICENSE)
