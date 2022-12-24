# CI Maven GitHub Workflows

A collection of GitHub Workflows composed of
[CI Maven Actions](https://github.com/Best-Quality-Engineering/ci-maven-actions) based on
the [CI Maven Plugin](https://github.com/Best-Quality-Engineering/ci-maven-plugin).

## `install-snapshot`

Executes the `install` goal on a Maven project using
[CI friendly properties](https://maven.apache.org/maven-ci-friendly.html).

| Dependent Actions                                                                                                 |
|-------------------------------------------------------------------------------------------------------------------|
| [`setup-runtime`](https://github.com/Best-Quality-Engineering/ci-maven-actions/blob/main/setup-runtime/README.md) |
| [`install`](https://github.com/Best-Quality-Engineering/ci-maven-actions/blob/main/install/README.md)             |

## `deploy-snapshot`

Executes the `deploy` goal using [CI friendly properties](https://maven.apache.org/maven-ci-friendly.html),
with support for signing and deploying snapshot artifacts to an artifact repository.

| Dependent Actions                                                                                                     |
|-----------------------------------------------------------------------------------------------------------------------|
| [`setup-runtime`](https://github.com/Best-Quality-Engineering/ci-maven-actions/blob/main/setup-runtime/README.md)     |
| [`deploy-snapshot`](https://github.com/Best-Quality-Engineering/ci-maven-actions/blob/main/deploy-snapshot/README.md) |

## `deploy-release`

Executes the `deploy` goal using [CI friendly properties](https://maven.apache.org/maven-ci-friendly.html),
with support for signing and deploying release artifacts to an artifact repository.

After deploying to the artifact repository, this workflow:

1. Creates a release branch
2. Increments the project `pom.xml` file, preparing the next development cycle.
3. Replaces version references in project documentation (i.e. `README.md`)
4. Commits all changes to the release branch
5. Merges the release branch to the base branch

| Dependent Actions                                                                                                               |
|---------------------------------------------------------------------------------------------------------------------------------|
| [`setup-runtime`](https://github.com/Best-Quality-Engineering/ci-maven-actions/blob/main/setup-runtime/README.md)               |
| [`export-revision`](https://github.com/Best-Quality-Engineering/ci-maven-actions/blob/main/export-revision/README.md)           |
| [`deploy-release`](https://github.com/Best-Quality-Engineering/ci-maven-actions/blob/main/deploy-release/README.md)             |
| [`git-user`](https://github.com/Best-Quality-Engineering/ci-maven-actions/blob/main/git-user/README.md)                         |
| [`create-branch`](https://github.com/Best-Quality-Engineering/ci-maven-actions/blob/main/create-branch/README.md)               |
| [`increment-pom`](https://github.com/Best-Quality-Engineering/ci-maven-actions/blob/main/increment-pom/README.md)               |
| [`replace-content`](https://github.com/Best-Quality-Engineering/ci-maven-actions/blob/main/replace-content/README.md)           |
| [`merge-release-branch`](https://github.com/Best-Quality-Engineering/ci-maven-actions/blob/main/merge-release-branch/README.md) |
