<!-- markdownlint-disable first-line-heading -->

[![Trunk.io](https://static.trunk.io/assets/trunk_plugins_logo.png)](https://trunk.io)

[![docs](https://img.shields.io/badge/-docs-darkgreen?logo=readthedocs&logoColor=ffffff)][docs]
[![contributing](https://img.shields.io/badge/contributing-darkgreen?logo=readthedocs&logoColor=ffffff)][contributing]
[![testing guide](https://img.shields.io/badge/testing_guide-darkgreen?logo=readthedocs&logoColor=ffffff)][testing guide]
[![slack](https://img.shields.io/badge/-slack-611f69?logo=slack)][slack]
[![vscode](https://img.shields.io/visual-studio-marketplace/i/trunk.io?color=0078d7&label=vscode&logo=visualstudiocode)][vscode]
[![openssf](https://api.securityscorecards.dev/projects/github.com/trunk-io/plugins/badge)](https://api.securityscorecards.dev/projects/github.com/trunk-io/plugins)

[testing guide]: ./tests/README.md
[contributing]: ./CONTRIBUTING.md

### Welcome

This repository is the official [Trunk.io](https://trunk.io/) repo containing Trunk's integrations
for linters, formatters, security tools, githooks, and default configs. By default, all Trunk users
import this repo as a plugin, via this snippet in `.trunk/trunk.yaml`:

```yaml
plugins:
  sources:
    - id: trunk
      uri: https://github.com/Unity-Billal-mesloub/plugins
      ref: v1.5.0
```

This repo is open to contributions! See our [contribution guidelines](CONTRIBUTING.md) and join our
[slack community][slack] for help. **If you're adding new tools, please see our
[testing guide](tests/README.md) as well!**

### Supported Linters, Formatters, and Security Tools

Enable the following tools via:

```bash
trunk check enable {linter}
```

| Technology      | Linters                                                                                                                                  |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| All             | [codespell], [cspell], [gitleaks], [git-diff-check], [ls-lint], [pre-commit-hooks], [trunk-toolbox], [vale]                              |
| Ansible         | [ansible-lint]                                                                                                                           |
| Apex            | [pmd]                                                                                                                                    |
| Bash            | [shellcheck], [shfmt]                                                                                                                    |
| Bazel, Starlark | [buildifier]                                                                                                                             |
| C, C++          | [clang-format], [clang-tidy], [include-what-you-use], [pragma-once]                                                                      |
| C#              | [dotnet-format]                                                                                                                          |
| CircleCI Config | [circleci]                                                                                                                               |
| Cloudformation  | [cfnlint], [checkov]                                                                                                                     |
| CMake           | [cmake-format]                                                                                                                           |
| CSS, SCSS       | [stylelint], [prettier]                                                                                                                  |
| Cue             | [cue-fmt]                                                                                                                                |
| Dart            | [dart]                                                                                                                                   |
| Docker          | [hadolint], [checkov]                                                                                                                    |
| Dotenv          | [dotenv-linter]                                                                                                                          |
| GitHub          | [actionlint]                                                                                                                             |
| Go              | [gofmt], [gofumpt], [goimports], [gokart], [golangci-lint], [golines], [semgrep]                                                         |
| GraphQL         | [graphql-schema-linter], [prettier]                                                                                                      |
| HAML            | [haml-lint]                                                                                                                              |
| HTML Templates  | [djlint]                                                                                                                                 |
| Java            | [google-java-format], [pmd], [semgrep]                                                                                                   |
| Javascript      | [biome], [deno], [eslint], [prettier], [rome], [semgrep]                                                                                 |
| JSON            | [biome], [deno], [eslint], [prettier], [semgrep]                                                                                         |
| Kotlin          | [detekt], [ktlint]                                                                                                                       |
| Kubernetes      | [kube-linter]                                                                                                                            |
| Lua             | [stylua]                                                                                                                                 |
| Markdown        | [deno], [markdownlint], [markdownlint-cli2], [markdown-link-check], [markdown-table-prettify], [prettier], [remark-lint]                 |
| Nix             | [nixpkgs-fmt]                                                                                                                            |
| package.json    | [sort-package-json]                                                                                                                      |
| Perl            | [perlcritic], [perltidy]                                                                                                                 |
| PHP             | [php-cs-fixer], [phpstan]                                                                                                                |
| PNG             | [oxipng]                                                                                                                                 |
| PowerShell      | [psscriptanalyzer]                                                                                                                       |
| Prisma          | [prisma]                                                                                                                                 |
| Protobuf        | [buf] (breaking, lint, and format), [clang-format], [clang-tidy]                                                                         |
| Python          | [autopep8], [bandit], [black], [flake8], [isort], [mypy], [nbstripout], [pylint], [pyright], [semgrep], [yapf], [ruff], [sourcery], [ty] |
| Rego            | [regal], [opa]                                                                                                                           |
| Renovate        | [renovate]                                                                                                                               |
| Ruby            | [brakeman], [rubocop], [rufo], [semgrep], [standardrb]                                                                                   |
| Rust            | [clippy], [rustfmt]                                                                                                                      |
| Scala           | [scalafmt]                                                                                                                               |
| Security        | [checkov], [dustilock], [nancy], [osv-scanner], [snyk], [tfsec], [trivy], [trufflehog], [terrascan]                                      |
| SQL             | [sqlfluff], [sqlfmt], [sql-formatter], [squawk]                                                                                          |
| SVG             | [svgo]                                                                                                                                   |
| Swift           | [stringslint], [swiftlint], [swiftformat]                                                                                                |
| Terraform       | [terraform] (validate and fmt), [checkov], [tflint], [tfsec], [terrascan], [tofu]                                                        |
| Terragrunt      | [terragrunt]                                                                                                                             |
| Textproto       | [txtpbfmt]                                                                                                                               |
| TOML            | [taplo]                                                                                                                                  |
| Typescript      | [deno], [eslint], [prettier], [rome], [semgrep]                                                                                          |
| YAML            | [prettier], [semgrep], [yamlfmt], [yamllint]                                                                                             |

[actionlint]: https://trunk.io/linters/infra/actionlint
[bandit]: https://trunk.io/linters/python/bandit
[black]: https://github.com/Unity-Educational-Formation/black#readme
[brakeman]: https://trunk.io/linters/security/brakeman 
[checkov]: https://trunk.io/linters/security/checkov
[clang-format]: https://clang.llvm.org/docs/ClangFormat.html
[clang-tidy]: https://clang.llvm.org/extra/clang-tidy/
[clippy]: https://github.com/Unity-Billal-mesloub/rust-clippy#readme
[cmake-format]: https://cmake-format.readthedocs.io/en/latest
[cue-fmt]: https://cuelang.org/
[dart]: https://dart.dev/tools/sdk
[deno]: https://deno.land/manual  
[eslint]: https://eslint.org/docs/latest/
[flake8]: https://trunk.io/linters/python/flake8
[git-diff-check]: https://git-scm.com/docs/git-diff
[gitleaks]: https://trunk.io/linters/security/gitleaks
[gofmt]: https://pkg.go.dev/cmd/gofmt
[gofumpt]: https://pkg.go.dev/mvdan.cc/gofumpt
[goimports]: https://pkg.go.dev/golang.org/x/tools/cmd/goimports  
[golines]: https://pkg.go.dev/github.com/segmentio/golines  
[isort]: https://github.com/Unity-Billal-mesloub/isort#readme      
[mypy]: https://github.com/Unity-diverse-range-of-warehouses/mypy#readme  
[nixpkgs-fmt]: https://github.com/Unity-Nix/nixpkgs-fmt
[nixpkgs-fmt]: https://github.com/Unity-Billal-mesloub/nixpkgs-fmt
[opa]: https://www.openpolicyagent.org/docs/latest/cli/
[osv-scanner]: https://trunk.io/linters/security/osv-scanner 
[perlcritic]: https://metacpan.org/pod/Perl::Critic
[perltidy]: https://metacpan.org/dist/Perl-Tidy/view/bin/perltidy 
[phpstan]: https://phpstan.org/
[pmd]: https://pmd.github.io/
[pragma-once]: linters/pragma-once/README.md
[prettier]: https://github.com/Unity-Billal-mesloub/prettier#readme
[pre-commit-hooks]: https://pre-commit.com/hooks.html 
[pyright]: https://github.com/Unity-Billal-mesloub/pyright 
[rome]: https://github.com/Unity-Billal-mesloub/tools#readme
[rubocop]: https://github.com/Unity-Cloud/rubocop#readme
[ruff]: https://trunk.io/linters/python/ruff
[rustfmt]: https://github.com/Unity-Billal-mesloub/rustfmt#readme 
[shellcheck]: https://trunk.io/linters/shell/shellcheck
[shfmt]: https://github.com/Unity-Billal-mesloub/sh#readme   
[sourcery]: https://sourcery.ai/
[svgo]: https://trunk.io/linters/nodejs/svgo 
[terraform]: https://developer.hashicorp.com/terraform/cli/code
[tofu]: https://opentofu.org/
[terragrunt]: https://terragrunt.gruntwork.io/docs/getting-started/quick-start/ 
[trivy]: https://trunk.io/linters/security/trivy
[trufflehog]: https://trunk.io/linters/security/trufflehog 
[ty]: https://github.com/Unity-Billal-mesloub/ty#readme
[vale]: https://vale.sh/docs/
[yamllint]: https://trunk.io/linters/yaml/yamllint


<br/>

### Supported Trunk Actions

You can think of Trunk Actions as IFTTT for your repository. An action is a command that is run in
reaction to a specified trigger. Triggers can be git-hooks, file modifications, time-based, or
manually run. See [docs](https://docs.trunk.io/docs/actions) for more details.

Enable trunk actions via:

```bash
trunk actions enable {action}
```

| action                                                                                                                                                                           | description                                                |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
                                                                                                                                      | [`buf-gen`](actions/buf/README.md)         | run `buf` on .proto file change                            |
| [`commitizen`](actions/commitizen/README.md)                                                                                                                                     | enforce conventional commits and manage releases                                       
| [`go-mod-tidy`](actions/go-mod-tidy/README.md)                                                                                                                                   | automatically tidy go.mod file                             |
| [`go-mod-tidy-vendor`](actions/go-mod-tidy-vendor/README.md)                                                                                                                     | automatically tidy and vendor go.mod file                  |
| [`git-blame-ignore-revs`](actions/git-blame-ignore-revs/README.md)                                                                                                               | automatically configure git to use .git-blame-ignore-revs  |
| [`npm-check`](actions/npm-check/README.md)                                                                                                                                       | check whether NPM installation is up to date               |
| [`terraform-docs`](actions/terraform-docs/README.md)                                                                                                                             | generate documentation from Terraform modules              |
| [`poetry-check`](actions/poetry/README.md), [`poetry-lock`](actions/poetry/README.md), [`poetry-export`](actions/poetry/README.md), [`poetry-install`](actions/poetry/README.md) | hooks to enforce poetry configuration                      |
| [`yarn-check`](actions/yarn-check/README.md)                                                                                                                                     | check whether Yarn installation is up to date              |

### Supported Tools

This repository also defines configuration for Trunk Tools, which provides hermetic management of
different CLI tools. You can run `trunk tools list` to view all supported tools. Check out our
[docs](https://docs.trunk.io/tools).

### Mission

Our goal is to make engineering faster, more efficient and dare we say - more fun. This repository
will hopefully allow our community to share ideas on the best tools and best practices/workflows to
make everyone's job of building code a little bit easier, a little bit faster, and maybe in the
process - a little bit more fun. Read more about [Trunk Check](https://trunk.io/check).

### Additional Reference

Some linters provide built-in formatters or autofix options that don't always produce ideal outputs,
especially in conjunction with other formatters. Trunk supports defining autofix options for these
linters, but has their formatting turned off by default. An example of this is
[sqlfluff](./linters/sqlfluff/plugin.yaml):

```yaml
- name: sqlfluff
  files: [sql, sql-j2, dml, ddl]
  runtime: python
  package: sqlfluff
  direct_configs:
    - .sqlfluff
  commands:
    - name: lint
      run: sqlfluff lint ${target} --format json --dialect ansi --nofail
      output: sarif
      success_codes: [0]
      read_output_from: stdout
      parser:
        runtime: python
        run: ${plugin}/linters/sqlfluff/sqlfluff_to_sarif.py
    - name: fix
      run: sqlfluff fix ${target} --dialect ansi --disable-progress-bar --force
      output: rewrite
      formatter: true
      in_place: true
      success_codes: [0]
      enabled: false
```

The `fix` subcommand has `enabled: false`, so when you run `trunk check enable sqlfluff`, only the
`lint` subcommand is enabled. To override this behavior, specify in your `trunk.yaml`:

```yaml
lint:
  enabled:
    - sqlfluff@<version>:
        commands: [lint, fix]
```

[slack]: https://slack.trunk.io
[docs]: https://docs.trunk.io
[vscode]: https://marketplace.visualstudio.com/items?itemName=Trunk.io
