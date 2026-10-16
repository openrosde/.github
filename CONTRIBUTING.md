# Contributing to OpenRoSDE

Thank you for your interest in contributing to OpenRoSDE!
This guide applies to every repository of [https://github.com/openrosde](https://github.com/openrosde) that has no contributing guide of its own.

## 📖 Where to Start

- Read the `CONTRIBUTING.md` of the repository you contribute to, which takes precedence over this file.
- Read the contributing guide of the core, [https://github.com/openrosde/openrosde/blob/main/CONTRIBUTING.md](https://github.com/openrosde/openrosde/blob/main/CONTRIBUTING.md), which describes the workflow of the project and how to add a new robot platform.
- Browse the documentation at [https://openrosde.org/](https://openrosde.org/), starting with [https://openrosde.org/docs/project/contributing](https://openrosde.org/docs/project/contributing).

## 🤝 In Short

- Open an issue before starting non-trivial work, so the maintainers can give early feedback.
- Report an issue of a platform or a device in its own repository, and an issue of the scripts, the images, or the CI in the core.
- Write commit messages and pull request titles as [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).
- Submit changes through a pull request from a feature branch named `<type>/<slug>` after the Conventional Commit type, into the branch that the guide of the repository names, which is `dev` for the core and `main` for the website, the platforms, and the devices.
- Describe the pull request with the sections of the template: Summary, Changes, Testing, Related, and Changelog.
- Add a one-line entry under `## [Unreleased]` of `CHANGELOG.md` in a repository that keeps one, such as the core, and write `None` under Changelog in one that does not.
- Use backticks for code identifiers, and no semicolons, en dashes, or em dashes, in issues and pull requests.
- Report a security vulnerability privately, with **Report a vulnerability** in the **Security** tab of the repository, as [`SECURITY.md`](SECURITY.md) describes.

Everyone who takes part in the project follows the [Code of Conduct](CODE_OF_CONDUCT.md).

## ⚖️ License of Contributions

The repositories of OpenRoSDE are licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0), unless their `LICENSE` says otherwise.
Unless you state otherwise, a contribution you submit is licensed under the same terms, as section 5 of the license provides.
