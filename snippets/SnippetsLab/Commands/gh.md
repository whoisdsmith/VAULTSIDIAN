---
created: 2022-07-03T05:16:22Z
folder: Commands
modified: 2022-07-03T05:16:25Z
title: gh
---

# Gh

Work seamlessly with GitHub from the command line.

USAGE  
  gh <command> <subcommand> [flags]

CORE COMMANDS  
  auth: Authenticate gh and git with GitHub  
  browse: Open the repository in the browser  
  codespace: Connect to and manage codespaces  
  gist: Manage gists  
  issue: Manage issues  
  pr: Manage pull requests  
  release: Manage releases  
  repo: Manage repositories

ACTIONS COMMANDS  
  run: View details about workflow runs  
  workflow: View details about GitHub Actions workflows

ADDITIONAL COMMANDS  
  alias: Create command shortcuts  
  api: Make an authenticated GitHub API request  
  completion: Generate shell completion scripts  
  config: Manage configuration for gh  
  extension: Manage gh extensions  
  gpg-key: Manage GPG keys  
  help: Help about any command  
  label: Manage labels  
  search: Search for repositories, issues, and pull requests  
  secret: Manage GitHub secrets  
  ssh-key: Manage SSH keys  
  status: Print information about relevant issues, pull requests, and notifications across repositories

HELP TOPICS  
  actions: Learn about working with GitHub Actions  
  environment: Environment variables that can be used with gh  
  formatting: Formatting options for JSON data exported from gh  
  mintty: Information about using gh with MinTTY  
  reference: A comprehensive reference of all gh commands

FLAGS  
  --help Show help for command  
  --version Show gh version

EXAMPLES  
  $ gh issue create  
  $ gh repo clone cli/cli  
  $ gh pr checkout 321

LEARN MORE  
  Use 'gh <command> <subcommand> --help' for more information about a command.  
  Read the manual at https://cli.github.com/manual

FEEDBACK  
  Open an issue using 'gh issue create -R github.com/cli/cli'
