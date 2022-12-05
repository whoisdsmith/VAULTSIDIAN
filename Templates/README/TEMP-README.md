# template-repo

[![Git Template Repository](https://img.shields.io/badge/Git-Template_Repo-9191E9?logo=git&logoColor=F05032&labelColor=343B42)](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template)
[![Test Workflow Status](https://github.com/ScribeMD/template-repo/workflows/Test/badge.svg)](https://github.com/ScribeMD/template-repo/actions/workflows/test.yaml)
[![Copy/Paste: 0%](https://img.shields.io/badge/Copy%2FPaste-0%25-B200B2?logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij48cGF0aCBmaWxsLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik03LjAyNCAzLjc1YzAtLjk2Ni43ODQtMS43NSAxLjc1LTEuNzVIMjAuMjVjLjk2NiAwIDEuNzUuNzg0IDEuNzUgMS43NXYxMS40OThhMS43NSAxLjc1IDAgMDEtMS43NSAxLjc1SDguNzc0YTEuNzUgMS43NSAwIDAxLTEuNzUtMS43NVYzLjc1em0xLjc1LS4yNWEuMjUuMjUgMCAwMC0uMjUuMjV2MTEuNDk4YzAgLjEzOS4xMTIuMjUuMjUuMjVIMjAuMjVhLjI1LjI1IDAgMDAuMjUtLjI1VjMuNzVhLjI1LjI1IDAgMDAtLjI1LS4yNUg4Ljc3NHoiLz48cGF0aCBkPSJNMS45OTUgMTAuNzQ5YTEuNzUgMS43NSAwIDAxMS43NS0xLjc1MUg1LjI1YS43NS43NSAwIDExMCAxLjVIMy43NDVhLjI1LjI1IDAgMDAtLjI1LjI1TDMuNSAyMC4yNWMwIC4xMzguMTExLjI1LjI1LjI1aDkuNWEuMjUuMjUgMCAwMC4yNS0uMjV2LTEuNTFhLjc1Ljc1IDAgMTExLjUgMHYxLjUxQTEuNzUgMS43NSAwIDAxMTMuMjUgMjJoLTkuNUExLjc1IDEuNzUgMCAwMTIgMjAuMjVsLS4wMDUtOS41MDF6Ii8+PC9zdmc+&labelColor=343B42)](https://github.com/kucherenko/jscpd)

[![Automated Updates: Renovate](https://img.shields.io/badge/Renovate-Automated_Updates-FF9F1C?logo=renovatebot&logoColor=1A1F6C&labelColor=666)](https://docs.renovatebot.com/)
[![Package Management: Poetry](https://img.shields.io/badge/Poetry-Package_Management-06BA63?logo=poetry&logoColor=60A5FA&labelColor=666)](https://python-poetry.org/)
[![Git Hooks: pre-commit](https://img.shields.io/badge/pre--commit-Git_Hooks-04E762?logo=precommit&logoColor=FAB040&labelColor=666)](https://pre-commit.com/)
[![Commit Style: Conventional Commits](https://img.shields.io/badge/Conventional_Commits-Commit_Style-090C9B?logo=conventionalcommits&logoColor=FE5196&labelColor=666)](https://conventionalcommits.org)
[![Releases: Semantic Versioning](https://img.shields.io/badge/SemVer-Releases-08A045?logo=semver&logoColor=3F4551&labelColor=666)](https://semver.org/)
[![Code Style: Prettier](https://img.shields.io/badge/Prettier-Code_Style-000?logo=prettier&logoColor=F7B93E&labelColor=666)](https://prettier.io/)
[![Code Style: EditorConfig](https://img.shields.io/badge/EditorConfig-Code_Style-FF69EB?logo=editorconfig&logoColor=FEFEFE&labelColor=666)](https://editorconfig.org/)
[![Editor: Visual Studio Code](https://img.shields.io/badge/VSCode-Editor-EE8434?logo=visualstudiocode&logoColor=007ACC&labelColor=666)](https://code.visualstudio.com/)

<!--TOC-->

- [template-repo](#template-repo)
  - [Usage](#usage)
  - [Changelog](#changelog)

<!--TOC-->

GitHub Template Repository for ScribeMD

## Usage

- As this is a
  [template repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-template-repository),
  please refer to
  [creating a repository from a template](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template).
  Only copy the default branch.
- Perform the following steps in the new repository:
  - Add any appropriate
    [starter workflows](https://docs.github.com/en/actions/using-workflows/using-starter-workflows).
  - Find and replace references to the repository name.
  - Add any file path patterns that should not be version controlled to
    [`.gitignore`](.gitignore), such as those created by tools. Not only
    [Git](https://git-scm.com/docs/gitignore), but most of our tools respect
    this list. However, you may occasionally find need to explicitly instruct
    particular tools to ignore particular files if they do not read from
    [`.gitignore`](.gitignore) or
    [do so incorrectly](https://github.com/kucherenko/jscpd/issues/466).
  - Add any needed development tools with an
    [available asdf plugin](https://github.com/asdf-vm/asdf-plugins) to
    [`.tool-versions`](.tool-versions).
  - Add any appropriate [pre-commit hooks](https://pre-commit.com/hooks.html)
    to [`.pre-commit-config.yaml`](.pre-commit-config.yaml), and update
    `default_install_hook_types` if introducing a new hook stage. In particular,
    include all of
    [our custom hooks](https://github.com/ScribeMD/pre-commit-hooks) that befit
    your toolchain.
  - Specify appropriate
    [MegaLinter flavor](https://oxsecurity.github.io/megalinter/latest/flavors/)
    in [`.pre-commit-config.yaml`](.pre-commit-config.yaml).
  - Adjust [MegaLinter](https://oxsecurity.github.io/megalinter/) configuration
    in [`.mega-linter.yaml`](.mega-linter.yaml) if necessary to match choices of
    language, formats, and tooling formats.
  - Add any needed [CSpell](https://cspell.org/) dictionaries to
    [`cspell.config.yaml`](cspell.config.yaml).
  - Update the [`../../../../../../../../../../LICENSE`](LICENSE) copyright year(s) if necessary.
  - Update the project name, description, and authors in
    [`pyproject.toml`](pyproject.toml).
  - Modif[`README.md`](TEMP-README.md)ME.md)/README.md`](README.md) to document the new repository.
  - [Classify your repository with topics](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/classifying-your-repository-with-topics),
    and set the repository description on GitHub.
  - [Disable merge commits and squash merging](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/about-merge-methods-on-github)
    since we use a
    [rebase-based workflow](https://git-scm.com/book/en/v2/Git-Branching-Rebasing).
  - [Configure automatic deletion of head branches when pull requests are merged](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-the-automatic-deletion-of-branches).
  - [Configure repository secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)
    if needed.
  - For private repositories only:
    - Configure
      [markdown-link-check](https://github.com/tcort/markdown-link-check/)
      to ignore URLs beginning with the repository's GitHub URL in
      [`.markdown-link-check.json`](.markdown-link-check.json) since it cannot
      log in with your GitHub credentials.

## Changelog

Please refer to [`CHANGELOG.md`](../../HOME-MTHRFCKR/DEV-DOCS/raindrop-io/dev-api/changelog.md).
