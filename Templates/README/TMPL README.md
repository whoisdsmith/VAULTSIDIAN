<p align="center"><img src="https://raw.githubusercontent.com/svengreb/tmpl/main/assets/images/repository-hero.svg?sanitize=true"/></p>

<p align="center"><a href="https://github.com/svengreb/tmpl/releases/latest" target="_blank" rel="noreferrer"><img src="https://img.shields.io/github/release/svengreb/tmpl.svg?style=flat-square&label=Release&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0"/></a> <a href="https://github.com/svengreb/tmpl/blob/master/CHANGELOG.md" target="_blank" rel="noreferrer"><img src="https://img.shields.io/github/release/svengreb/tmpl.svg?style=flat-square&label=Changelog&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0"/></a></p>

<p align="center"><a href="https://github.com/svengreb/tmpl/actions?query=workflow%3Aci-node" target="_blank" rel="noreferrer"><img src="https://img.shields.io/github/workflow/status/svengreb/tmpl/ci-node.svg?style=flat-square&label=CI%20Node&logo=github&logoColor=eceff4&colorA=4c566a"/></a></p>

<p align="center"><a href="https://github.com/arcticicestudio/styleguide-markdown/releases/latest" target="_blank" rel="noreferrer"><img src="https://img.shields.io/github/release/arcticicestudio/styleguide-markdown.svg?style=flat-square&label=Markdown%20Style%20Guide&logoColor=eceff4&colorA=4c566a&colorB=88c0d0&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzOSIgaGVpZ2h0PSIzOSIgdmlld0JveD0iMCAwIDM5IDM5Ij48cGF0aCBmaWxsPSJub25lIiBzdHJva2U9IiNEOERFRTkiIHN0cm9rZS13aWR0aD0iMyIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBkPSJNMS41IDEuNWgzNnYzNmgtMzZ6Ii8%2BPHBhdGggZmlsbD0iI0Q4REVFOSIgZD0iTTIwLjY4MyAyNS42NTVsNS44NzItMTMuNDhoLjU2Nmw1Ljg3MyAxMy40OGgtMS45OTZsLTQuMTU5LTEwLjA1Ni00LjE2MSAxMC4wNTZoLTEuOTk1em0tMi42OTYgMGwtMTMuNDgtNS44NzJ2LS41NjZsMTMuNDgtNS44NzJ2MS45OTVMNy45MzEgMTkuNWwxMC4wNTYgNC4xNnoiLz48L3N2Zz4%3D"/></a> <a href="https://github.com/arcticicestudio/styleguide-git/releases/latest" target="_blank" rel="noreferrer"><img src="https://img.shields.io/github/release/arcticicestudio/styleguide-git.svg?style=flat-square&label=Git%20Style%20Guide&logoColor=eceff4&colorA=4c566a&colorB=88c0d0&logo=git"/></a></p>

<p align="center">A collection of <a href="https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-template-repository" target="_blank" rel="noreferrer">template repositories</a> for new projects.</p>

Starting a new project repository means to spend a lot of time first for setting up the basic structure and configuration for the used technology stack over and over again. It is a repetitive task since the same tools are often used across many projects, like linters and code formatters, and therefore often just copied over. This has the disadvantage that the configuration or documentation may differ between different projects or common changes and configurations are not synchronize at all. Many tools provide a way to created so called “shared configurations“ that can be used as base and dynamically composed with project-specific configurations, however, this does not apply to all.
To prevent such problems a central place, so called “template repository“, for basic configurations and documentations as well as focus on different use cases, project structures and programming languages is a good solution to act as a single-source-of-truth™️.

_tmpl_, the imaginative abbreviation for “template“, is my solution to enable a smooth project start and ensure that a project stays healthy, stable and up-to-date over time. It is separated into context, layout and/or language specific templates where each lives in its own repository.
Please note that _tmpl_ has mainly been created for my personal use in mind. The default configurations of these templates might not fit your needs, but they were designed to be flexible and can be adapted to different use cases and environments.

## Overview

This repository serves as the base template repository of _tmpl_ that provides essential features for every project.

- [GitHub specific features](#github) like…
  - …definitions for [code owners](#code-owners)
  - …individual [issue templates](#issue-templates)
  - …a extensive [pull request template](#pull-request-template)
  - …basic [CI/CD action workflows](#cicd-action-workflows)
  - …[automated updates and security vulnerability alerts](#automated-dependency-updates) for dependencies through the native [Dependabot][14] integration
- Configurations for [npm and Yarn](#nodejs-npm-and-yarn)
- Basic configurations for [Git](#git)
- A [MIT license](#license)
- [EditorConfig](#editorconfig) integration
- [Prettier][76] for [“auto-magical“ code& text formatting](#automatic-code-and-text-formatter)
- [remark-lint][79] to [lint Markdown](#markdown-linting)
- [lint-staged][63] for [Automatic pre-commit linting](#automatic-pre-commit-linting)
- [husky][58] to [manage and run Git Hooks](#git-hook-manager-&-runner)

See the [“Features“](#features) section below for more details.

## Template Repositories

Like mentioned in the introduction above, _tmpl_ is separated into multiple scalable _tmpl_ repositories based on different project layouts, languages and/or context. See the documentations of the specific repository for more details about the use case(s) and how to use it as template:

- [tmpl-go][81] — A template repository for [Go][54] projects.

## Directory Structure

```raw
tmpl
├─ .github
│   ├─ ISSUE_TEMPLATE
│   └─ workflows
└─ assets
    └─ images
```

The current directory structure consists of basic directories mainly targeted for repositories hosted on GitHub, but the contained files can also be simply adjusted for usage with other platforms. Please see the [GitHub Features](#github-features) section below for more details about the provided files.

- `.github` — The base directory for configurations and documentations of [GitHub features][44] like [action][29] workflows and [issue/pull request templates][32].
  - `.github/ISSUE_TEMPLATE` — The directory for [individual issue template files][34].
  - `.github/workflows` — The directory for [action workflow files][28].
- `.assets` — A common base directory for (binary) projects assets like media or tool specific files that is independent of the repository hosting platform.
  - `.assets/images` — The sub-directory for project and/or repository specific images like [SVG][86] or [raster graphics][85].

## Features

This repository serves as the base template repository of _tmpl_ that provides essential features for every project.

The sections below contain more detailed information about each feature, the sane default configurations and their files in the repository as well as ways to customize and adjust them to adapt to other use cases and projects. They provide details about files in this repository and the overall directory structure.

### GitHub

This template repository has partially been designed for repositories hosted on GitHub and makes use of many of [its fantastic features][44].

#### Code Owners

The [`.github/CODEOWNERS`][31] file defines individuals or teams that are responsible for code in a repository and automatically requested for review when a contributor opens a pull request that modifies files that they own.

#### Issue Templates

The [individual issue template files][34] in the `.github/ISSUE_TEMPLATE` directory are automatically used as content when a contributor creates a new issue where each file will be available as template in the [issue template chooser][33].
Note that the [`.github/ISSUE_TEMPLATE.md` file][38] is still included in this repository, but has been official deprecated by GitHub in favor of these individual issue template files.

#### Pull Request Template

The [`.github/PULL_REQUEST_TEMPLATE.md`][35] file is automatically used as content when a contributor creates a new pull request. It can also be used for automation and [as URL query parameter value][30] e.g. do directly link to it in documentations.

#### CI/CD Action Workflows

The [GitHub Actions][43] `.github/workflows` directory includes basic [CI/CD workflow files][28] that runs for changes in the Git `main` branch and `v*` tags. There is currently one job called `lint-node` that runs all linters that are included in this template repository. See sections like [“Automatic Code and Text Formatter“](#automatic-code-and-text-formatter), [“Markdown Linting“](#markdown-linting) and [“Automatic Pre-Commit Linting“](#automatic-pre-commit-linting) below for more details.
To skip a workflow, include a [supported keyword like `[skip actions]`][26] in a commit message.

#### Automated Dependency Updates

To ensure dependencies of various package ecosystems are up-to-date, [Dependabot][14] has been [natively integrated into GitHub][27]. It creates [automated updates][37] and [security vulnerability alerts][41] for dependencies.
The basic [`dependabot.yml` file][21] in this template repository contains [the configuration][37] for [GitHub Action workflows](#cicd-action-workflows) and [Node.js dependencies](#nodejs-npm-and-yarn).

Note that you must manually enable or disable [version][36] and [security][42] Dependabot updates per repository!

### Node.js: npm and Yarn

Since most of the tools included in this template repository like…

- Prettier for [“auto-magical“ code & text formatting](#automatic-code-and-text-formatter)
- remark-lint for [linting of Markdown source files](#markdown-linting)
- lint-staged for [automatic pre-commit linting](#automatic-pre-commit-linting)
- husky as [Git Hook manager & runner](#git-hook-manager-&-runner)

…are (unfortunately) written in JavaScript for [Node][65], [npm][74]/[Yarn][89] is required to manage these packages.

The [`package.json`][70] and [`.npmrc`][71] files declare [Node][65] specific configurations like the development dependencies and the [`package-lock`][66], [`save-exact`][67] and [`save-prefix`][68] version resolution strategy. npm is the main package manager so Yarn‘s [`yarn.lock`][88] file should not be used and tracked in order to prevent conflicts with the [`package-lock.json`][69] file.

Note that as of [version `0.9.0`][45] the minimum versions for npm is [`>=7.7.0`][46], bundled with [Node `>=15.13.0`][64], in order to use the `run` and `exec` commands with [workspaces][72].

### Git

The [`.gitattributes`][50] and [`.gitignore`][51] configuration files define basic pattern. This includes pattern when using [git-crypt][49] to encrypt and store secrets within the repository as well as pattern for the fantastic [Jetbrains][60] products like [IntelliJ][59].

There is also the [`.mailmap`][52] file that…

1. …serves as a reference to involved project maintainers and teams and also allows contributors to send mails regarding security issues.
2. …prevents unnecessary overhead of updating all documentations when new core team members and contributors are added.
3. …fulfills it main purpose and functionality: Mapping commit authors when someone changed their email address or uses a different one.

### License

The _tmpl_ project and its repositories are licensed under the [MIT license][62] which is included as [`LICENSE` file][22].

### EditorConfig

The [`.editorconfig`][15] file allows to define and maintain consistent coding styles between different editors and IDEs. It is a well-known file that can, next to tools that are specialized to specific languages and formats, help to keep the style of source code and documentations healthy.

### Automatic Code and Text Formatter

A code formatter is a essential part of a project setup to ensure a good and consistent code style without requiring relatively time-consuming manual corrections found by a code linter. With code being automatically formatted on actions like saving a file the developer can focus entirely on the code instead of spending time and energy on indenting code line by line.

That‘s where one special project comes in: [Prettier][76], the opinionated code formatter with support for almost any language and integration with almost every popular editor. I‘ve been using it since the first version and I totally forgot about the fact that formatting is even a thing. That could also be because [Gophers][53] are already used to [`gofmt`][55] anyway.

_Prettier_ is a absolute must-have for every project setup and I‘m not aware of any other projects with such advanced parsers and language support. The only negative point is that it is written in _JavaScript_ instead of [Go][54] so it always pulls in [Node][65] as a development dependency. This is not a problem at all for web-based projects, but for Go or any other non Node.js project it inflates the setup unnecessarily.

Anyway, the fantastic developer experience and project benefits clearly outweigh the negative points. In addition many developers today already have _Node_ installed locally since its large ecosystem has already spread by far further than just the web but already powers many system, desktop and CLI applications.

One of the main features of Prettier is its configuration: It already provides the best and recommended style configurations of-out-the-box™.
The only option that was adjusted for this template repository is the [print width][75]. It is set to `80` by default which is not up-to-date for modern screens (might only be relevant when working in [TUI][87]s like e.g. [vim][83]). It has been changed to `120` like defined in [all of my style guides][16].
The `prettier.config.js` configuration file is placed in the project root as well as the `.prettierignore` file that defines ignore pattern.

To allow to format all sources a `format:pretty` npm package script is available that also runs in the main `format` script flow. The `lint:pretty` script allows to check if all supported files are formatted correctly and is also included in the main `lint` script flow.

### Markdown Linting

Ensuring that documentations and content written in [Markdown][84] are of great quality should be a continuous goal of any project. Persisting information is a consistent and extensive way helps tp keep a project healthy, no matter whether for long-time or new users ad well as maintainers and contributors. Linting Markdown results in better rendering with different markdown parsers and makes sure less refactoring is needed afterwards.

The best solution for this task would be a tool written in [Go][54], but the undisputed best tool is still [remark-lint][79] which is (unfortunately) written in JavaScript and used via [Node][65]. Of course there are fantastic projects written in Go like [goldmark][56] that provides a great way to _parse_ content, but linting is (currently) not a feature.
remark-lint on the other side is built on top of [remark][80], the powerful Markdown processor powered by plugins (such as remark-lint itself) and part of the [unified][82] collective. It comes with a really [large set of customizable rule][78] and ways to ensure Markdown will be consistent across any project.

Another decision point for remark-lint was the fact that Prettier (see section [“Automatic Code and Text Formatter“](#automatic-code-and-text-formatter)) so Node.js is already a development dependency anyway. This also allows to add other awesome projects that are (unfortunately) written in JavaScript and for which there is no comparable alternative.

remark-lint can be used via [remark-cli][73] and a rule preset. This preset is [remark-preset-lint-arcticicestudio][17], my custom preset that implements my [Markdown Style Guide][1].
Since the custom preset is still in major version `0` the version range is currently `>=0.x.x <1.0.0` to avoid the “SemVer Major Zero Caveat”. When defining package versions with the the carat `^` or tilde `~` range selector it won‘t affect packages with a major version of `0`. npm will resolve these packages to their exact version until the major version is greater or equal to `1`.
To avoid this caveat the more detailed version range `>=0.x.x <1.0.0` is used to resolve all versions greater or equal to `0.x.x` but less than `1.0.0`. This will always use the latest `0.x.x` version and removes the need to increment the version manually on each new release.

The `.remarkrc.js` configuration file is placed in the project root as well as the `.remarkignore` file that defines ignore pattern.

To allow to run the Markdown linting separately the `lint:md` npm package script is available and included in the main `lint` script flow.

### Automatic Pre-Commit Linting

[Git Hooks][48] are a fantastic way to customize the development workflow of a project to simplify and automate specific tasks that are required when working on the code base. For example, formatting, linting and running tests before pushing a commit to ensure it conforms to the code style and works as expected.
Most Git Hooks are not that complex and fullfil a simple purpose while other solutions like [danger][13] can help to manage larger projects and projects that need to scale.

This template repository uses a Git Hook that automatically runs configured linters on all files that have been staged and that match the configured pattern like file extensions or names.
Like described in the [“Automatic Code and Text Formatter“](#automatic-code-and-text-formatter) section above, [Node][65] is already a development dependency anyway so the [lint-staged][63] NPM package is used for this goal. I‘ve used this package in almost any project and it is the most stable, production-proven and advanced tool that is currently out there with no comparable alternatives in other languages.

The configuration file `lint-staged.config.js` is placed in the project root and includes the command that should be run for matching file extensions. It currently contains entries for the following linters that run in the same order as listed here:

1. `prettier --list-different` - Runs [Prettier][76] (see section [“Automatic Code and Text Formatter“](#automatic-code-and-text-formatter)) to ensure all files are formatted correctly. The `--check` flag prints files that are not conform with the Prettier configuration.
2. `remark --no-stdout` - Runs [remark-lint][79] (see section [“Markdown Linting“](#markdown-linting)) against `*.md` to ensure all Markdown files are compliant to the style guide. The `--no-stdout` flag suppresses the output of the parsed file content.

### Git Hook Manager & Runner

In section [“Automatic Pre-Commit Linting“](#automatic-pre-commit-linting) the integration of [lint-staged][63], a [Git Hook][48] runner that runs linters against staged files, is described and how it is used in this template repository. To automatically run it and other Git Hooks the hook manager and runner [husky][58] is used.

Just like other already added tools described in the sections above, husky is (unfortunately) also written in JavaScript. Since [Node][65] is therefore already a development dependency it doesn‘t really matter that husky is another Node.js package too.
Unlike the other tools there are indeed alternatives written in [Go][54] like [lefthook][61] or [quickhook][77], but it requires time to test and evaluate them before actually replacing husky. Also a long as there are no comparable alternatives to the already used tools listed above, this template would be more complex by requiring both Node.js and Go as development dependency. Therefore husky took over the part as hook manager & runner for this template repository since it is a stable, production-proven and advanced project that I already use in almost any other project setup.

The `.huskyrc.js` configuration file is placed in the project root and includes the command to run for any [supported Git Hook][57]. It contains entries for the following hooks:

- `pre-commit` - Runs lint-staged (see section [“Automatic Pre-Commit Linting“](#automatic-pre-commit-linting)) before each commit to ensure all staged files are compliant to all style guides.

## Usage

There are multiple ways to use this template repository, either by [using GitHubs feature to create a repository from a template][40] or simply [cloning it][39]. No matter which method is used, there are a few manual steps to adjust some configurations and documentations for the individual target project. Note that these changes are only recommendations, but are common steps anyway.

1. Adjust the [`.github/CODEOWNERS`][20] and [`.mailmap`][23] files to use mappings for your project contributors and team members.
2. Adjust [files related to GitHub features](#github) like the [CI/CD action workflow](#cicd-action-workflow), [issue](#issue-templates) & [pull request](#pull-request-template) templates, [code owners](#code-owners) and any other file located in the [`github` directory][47] to match your project.
3. Adjust documentations like the [README][25], [changelog][18], [code of conduct][19] and [contribution guides][12] to match your project.
4. Adjust the [`package.json`][24] file to match your project.
5. Adjust the [`dependabot.yml`][21] file to match your project.
6. Adjust all copyright notices to match your project.

## Contributing

_tmpl_ is an open source project and contributions are always welcome!

There are many ways to contribute, from [writing- and improving documentation and tutorials][4], [reporting bugs][3], [submitting enhancement suggestions][5] that can be added to _tmpl_ by [submitting pull requests][9].

Please take a moment to read the [contributing guide][12] to learn about the development process, the [styleguides][10] to which this project adheres as well as the [branch organization][2] and [versioning][11] model.

The guide also includes information about [minimal, complete, and verifiable examples][8] and other ways to contribute to the project like [improving existing issues][7] and [giving feedback on issues and pull requests][6].

<p align="center">Copyright &copy; 2020-present <a href="https://www.svengreb.de" target="_blank" rel="noreferrer">Sven Greb</a></p>

<p align="center"><a href="https://github.com/svengreb/tmpl/blob/main/LICENSE" target="_blank" rel="noreferrer"><img src="https://img.shields.io/static/v1.svg?style=flat-square&label=License&message=MIT&logoColor=eceff4&logo=github&colorA=4c566a&colorB=88c0d0"/></a></p>

[1]: https://arcticicestudio.github.io/styleguide-markdown
[2]: https://github.com/svengreb/tmpl/blob/main/CONTRIBUTING.md#branch-organization
[3]: https://github.com/svengreb/tmpl/blob/main/CONTRIBUTING.md#bug-reports
[4]: https://github.com/svengreb/tmpl/blob/main/CONTRIBUTING.md#documentations
[5]: https://github.com/svengreb/tmpl/blob/main/CONTRIBUTING.md#enhancement-suggestions
[6]: https://github.com/svengreb/tmpl/blob/main/CONTRIBUTING.md#give-feedback-on-issues-and-pull-requests
[7]: https://github.com/svengreb/tmpl/blob/main/CONTRIBUTING.md#improve-issues
[8]: https://github.com/svengreb/tmpl/blob/main/CONTRIBUTING.md#mcve
[9]: https://github.com/svengreb/tmpl/blob/main/CONTRIBUTING.md#pull-requests
[10]: https://github.com/svengreb/tmpl/blob/main/CONTRIBUTING.md#style-guides
[11]: https://github.com/svengreb/tmpl/blob/main/CONTRIBUTING.md#versioning
[12]: https://github.com/svengreb/tmpl/blob/main/CONTRIBUTING.md
[13]: https://danger.systems
[14]: https://dependabot.com
[15]: https://editorconfig.org
[16]: https://github.com/arcticicestudio?tab=repositories&q=styleguide
[17]: https://github.com/arcticicestudio/remark-preset-lint-arcticicestudio
[18]: https://github.com/svengreb/tmpl/blob/main/CHANGELOG.md
[19]: https://github.com/svengreb/tmpl/blob/main/CODE_OF_CONDUCT.md
[20]: https://github.com/svengreb/tmpl/blob/main/.github/CODEOWNERS
[21]: https://github.com/svengreb/tmpl-go/blob/main/.github/dependabot.yml
[22]: https://github.com/svengreb/tmpl/blob/main/LICENSE
[23]: https://github.com/svengreb/tmpl/blob/main/.mailmap
[24]: https://github.com/svengreb/tmpl/blob/main/package.json
[25]: https://github.com/svengreb/tmpl/blob/main/README.md
[26]: https://github.blog/changelog/2021-02-08-github-actions-skip-pull-request-and-push-workflows-with-skip-ci
[27]: https://github.blog/2020-06-01-keep-all-your-packages-up-to-date-with-dependabot
[28]: https://docs.github.com/en/free-pro-team@latest/actions/reference/workflow-syntax-for-github-actions
[29]: https://docs.github.com/en/free-pro-team@latest/actions
[30]: https://docs.github.com/en/free-pro-team@latest/github/managing-your-work-on-github/about-automation-for-issues-and-pull-requests-with-query-parameters
[31]: https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/about-code-owners
[32]: https://docs.github.com/en/free-pro-team@latest/github/building-a-strong-community/about-issue-and-pull-request-templates
[33]: https://docs.github.com/en/free-pro-team@latest/github/building-a-strong-community/configuring-issue-templates-for-your-repository#configuring-the-template-chooser
[34]: https://docs.github.com/en/free-pro-team@latest/github/building-a-strong-community/configuring-issue-templates-for-your-repository
[35]: https://docs.github.com/en/free-pro-team@latest/github/building-a-strong-community/creating-a-pull-request-template-for-your-repository
[36]: https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/enabling-and-disabling-version-updates
[37]: https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/configuration-options-for-dependency-updates
[38]: https://docs.github.com/en/free-pro-team@latest/github/building-a-strong-community/manually-creating-a-single-issue-template-for-your-repository
[39]: https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/cloning-a-repository
[40]: https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template
[41]: https://docs.github.com/en/free-pro-team@latest/github/managing-security-vulnerabilities/about-alerts-for-vulnerable-dependencies
[42]: https://docs.github.com/en/free-pro-team@latest/github/managing-security-vulnerabilitiesconfiguring-dependabot-security-updates
[43]: https://github.com/features/actions
[44]: https://github.com/features
[45]: https://github.com/svengreb/tmpl/milestone/9
[46]: https://github.com/npm/cli/releases/tag/v7.7.0
[47]: https://github.com/svengreb/tmpl/tree/main/.github
[48]: https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks
[49]: https://github.com/AGWA/git-crypt
[50]: https://git-scm.com/docs/gitattributes
[51]: https://git-scm.com/docs/gitignore
[52]: https://git-scm.com/docs/git-shortlog#_mapping_authors
[53]: https://blog.golang.org/gopher
[54]: https://go.dev
[55]: https://golang.org/cmd/gofmt
[56]: https://github.com/yuin/goldmark
[57]: https://github.com/typicode/husky/blob/master/DOCS.md#supported-hooks
[58]: https://github.com/typicode/husky
[59]: https://www.jetbrains.com/idea
[60]: https://www.jetbrains.com
[61]: https://github.com/Arkweid/lefthook
[62]: https://opensource.org/licenses/MIT
[63]: https://github.com/okonet/lint-staged
[64]: https://nodejs.org/dist/v15.13.0
[65]: https://nodejs.org
[66]: https://docs.npmjs.com/cli/v6/using-npm/config#package-lock
[67]: https://docs.npmjs.com/cli/v6/using-npm/config#save-exact
[68]: https://docs.npmjs.com/cli/v6/using-npm/config#save-prefix
[69]: https://docs.npmjs.com/files/package-lock.json
[70]: https://docs.npmjs.com/files/package.json
[71]: https://docs.npmjs.com/cli/v7/configuring-npm/npmrc
[72]: https://docs.npmjs.com/cli/v7/using-npm/workspaces
[73]: https://www.npmjs.com/package/remark-cli
[74]: https://www.npmjs.com
[75]: https://prettier.io/docs/en/options.html#print-width
[76]: https://prettier.io
[77]: https://github.com/dirk/quickhook
[78]: https://github.com/remarkjs/remark-lint/blob/master/doc/rules.md
[79]: https://github.com/remarkjs/remark-lint
[80]: https://remark.js.org
[81]: https://github.com/svengreb/tmpl-go
[82]: https://unifiedjs.com
[83]: https://www.vim.org
[84]: https://en.wikipedia.org/wiki/Markdown
[85]: https://en.wikipedia.org/wiki/Raster_graphics
[86]: https://en.wikipedia.org/wiki/Scalable_Vector_Graphics
[87]: https://en.wikipedia.org/wiki/Text-based_user_interface
[88]: https://yarnpkg.com/lang/en/docs/yarn-lock
[89]: https://yarnpkg.com
