# WARP Docs

---

# Command Entry

Warp's main features for Command Entry and History:

- 1.
    

    ​[A.I. Command Search](https://docs.warp.dev/features/entry/ai-command-search) (`` CTRL-` ``) converts natural language descriptions into shell commands that can be executed.

    

- 2.
    

    ​[Workflows](https://docs.warp.dev/features/entry/workflows) (`CTRL-SHIFT-R`) are an easier way to execute and share parameterized and searchable commands within Warp.

    

- 3.
    

    ​[Command Search](https://docs.warp.dev/features/entry/command-search) (`CTRL-R`) is a 3-in-1 panel that allows you to search across Command History, Workflows, Notebooks, and A.I. Command Search all at once.

    

- 4.
    

    ​[Command History](https://docs.warp.dev/features/entry/command-history) (`UP`) allows Warp to isolate the history of each shell session to make previously run commands easily accessible.

---

# A.I. Command Search

## What is it

AI Command Search converts natural language descriptions into shell commands that can be executed. Currently, you need to be online to use this feature. The feature is backed by [OpenAI’s codex engine](https://openai.com/blog/openai-codex/). *Note*: If this feature doesn't work, it is possible that your ISP or Firewall is blocking the calls to `app.warp.dev`

## How to Access it

- 1.
    

    Press `` CTRL- `` or type `#` into the Text Input Editor to open the AI Command Search panel.

    

- 2.
    

    Type in the input box what you'd like to do and press `ENTER` to generate the command.

    

- 3.
    

    Once the result shows up, press `CMD-ENTER` to input the generated command directly into Warp's Input Editor.

    

---

# Workflows

## What is it

Workflows are an easier way to execute and share commands within Warp. They are easily parameterized and searchable by name, description, or command arguments. [Common workflows](https://github.com/warpdotdev/workflows) sourced by the Warp team and community are readily available within the app. Additionally, you can create and scope workflows locally or to a git repository.

## How to Use it

- Press `CTRL-SHIFT-R` to open the Workflow menu or through the Command Palette `CMD-P`.
    

- Once inside the menu, start typing in the search bar to filter the existing workflows or browse by category. (e.g. git, android, npm, etc.)
    

- When a Workflow is selected, you can use `SHIFT-TAB` to cycle thru the parameters.
    

### How is This Different From Aliases?[](https://docs.warp.dev/features/entry/workflows#how-is-this-different-from-aliases)

Workflows solve some major pain points with aliases, specifically the:

- 1.
    

    need to context switch

    
    - 1.
        

        leave vim, source dotfiles, or reset shell

        
    

- 2.
    

    difficulty with attaching documentation

    

- 3.
    

    inability to easily search or share

    

- 4.
    

    inability to easily parameterize

    

---

## Creating Custom Workflows

### How to Create a Workflow

Workflows can easily be shared with your team by saving a workflow's YAML file to `~/.warp/workflows/` or `.warp/workflows/` in the top level of a repository. Local and Repository workflows can be accessed under the "My Workflows" and "Repository Workflows" tab of the Workflows menu, respectively.

See the existing workflows spec within the [Workflows repo](https://github.com/warpdotdev/Workflows/tree/main/specs) for examples. Additionally, we outline the file format below:

---

# Workflows File Format

The workflow file format is a [yaml](https://yaml.org/) file and must have either a `.yml` or `yaml` extension. If you're new to YAML and want to learn more, see "[Learn YAML in Y minutes](https://learnxinyminutes.com/docs/yaml/)."

*Compatibility Note*: Warp is still in Beta and this format is subject to change.

## `name`

---

The name of the Workflow. Required.

## `command`

---

The command that is executed when the Workflow is selected. Required.

## `tags`

---

An array of tags that are useful to categorize the Workflow. Optional.

```yaml
tags: ["git", "GitHub"]
```

## `description`

---

The description of the Workflow and what it does. Optional.

## `source_url`

---

The URL from where the Workflow was originally generated from. This is surfaced in [commands.dev](https://www.commands.dev/) for attribution purposes. Optional.

## `author`

---

The original author of the Workflow. For example, if this workflow was generated from StackOverflow, the `author` would be the `author` of the StackOverflow post. This is surfaced in [commands.dev](https://www.commands.dev/) for attribution purposes. Optional.

## `author_url`

---

The URL of original author of the Workflow. For example, if this workflow was generated from StackOverflow, the `author_url` would be the StackOverflow author's profile page. This is surfaced in [commands.dev](https://www.commands.dev/) for attribution purposes. Optional.

## `shells`

---

The list of shells where this Workflow is valid. If not specified, the Workflow is assumed to be valid in all shells. This must be one of `zsh`, `bash`, or `fish`.

## `arguments`

---

A Workflow can have parameterized arguments to specify pieces of the Workflow that need to be filled in by the user.

You can specify which part of the Workflow command maps to an argument by surrounding it with two curly braces (`{{<argument>}}`).

For example the workflow command:

```shell
for {{variable}} in {{sequence}}; do
  {{command}}
done
```

Includes 3 arguments: `variable`, `sequence`, and `command`.

## `arguments.name`

---

The name of the argument. The argument name is used within the command to specify the ranges of the argument. Required.

```yaml
name: Example workflow
command: echo {{string}}
arguments:
  - name: string
    description: The value to echo
```

## `arguments.description`

---

The description of the argument. This is surfaced in both commands.dev and Warp to help users fill in Workflow arguments. Optional

## `arguments.default_value`

---

The default value for the argument. If specified, the `default_value` replaces the argument name within the command. Optional

The workflow file format is a [yaml](https://yaml.org/) file and must have either a `.yml ` or `yaml` extension. If you're new to YAML and want to learn more, see [Learn YAML in Y minutes](https://learnxinyminutes.com/docs/yaml/). *Compatibility Note*: Warp is still in Beta and this format is subject to change.

**`name`**

The name of the Workflow. Required.

**`command`**

The command that is executed when the Workflow is selected. Required.

**`tags`**

An array of tags that are useful to categorize the Workflow. Optional.

tags: ["git", "GitHub"]

**`description`**

The description of the Workflow and what it does. Optional.

**`source_url`**

The URL from where the Workflow was originally generated from. This is surfaced in [commands.dev](https://www.commands.dev/) for attribution purposes. Optional.

**`author`**

The original author of the Workflow. For example, if this workflow was generated from StackOverflow, the `author` would be the `author` of the StackOverflow post. This is surfaced in [commands.dev](https://www.commands.dev/) for attribution purposes. Optional.

**`author_url`**

The URL of original author of the Workflow. For example, if this workflow was generated from StackOverflow, the `author_url` would be the StackOverflow author's profile page. This is surfaced in [commands.dev](https://www.commands.dev/) for attribution purposes. Optional.

**`shells`**

The list of shells where this Workflow is valid. If not specified, the Workflow is assumed to be valid in all shells. This must be one of `zsh`, `bash`, or `fish`.

**`arguments`**

A Workflow can have parameterized arguments to specify pieces of the Workflow that need to be filled in by the user.

You can specify which part of the Workflow command maps to an argument by surrounding it with two curly braces (`{{<argument>}}`).

For example the workflow command:

```
for {{variable}} in {{sequence}}; do

{{command}}

done
```

Includes 3 arguments: `variable`, `sequence`, and `command`.

**`arguments.name`**

The name of the argument. The argument name is used within the command to specify the ranges of the argument. Required.

```
name: Example workflow

command: echo {{string}}

arguments:

- name: string
```

description: The value to echo

**`arguments.description`**

The description of the argument. This is surfaced in both [commands.dev](https://www.commands.dev/) and Warp to help users fill in Workflow arguments. Optional

**`arguments.default_value`**

The default value for the argument. If specified, the `default_value` replaces the argument name within the command. Optional

# Where to Save Workflows

Local workflows are scoped to your machine. Repository workflows are scoped to a git repository and can be accessed by anyone who has cloned the repo. *Note:* Repository workflows will not appear if you are ssh'd into a remote machine.

Local Workflow Path: `~/.warp/workflows`

Repository Workflow Path: `{{path_to_git_repo}}/.warp/workflows`

## Adding a Local Workflow

To start, create a workflows subdirectory within your `.warp` folder

`mkdir -p ~/.warp/workflows`

Add your workflow’s `.yaml` file to this directory; if the file format is valid Warp should automatically load it into the Workflows menu.

`cp ~/path/to/my_awesome_workflow.yaml ~/.warp/workflows`

## Adding a Repository Workflow

You can add a repository workflow similarly to how you added a local workflow. Create a workflows folder in a repository’s root directory and save your `.yaml` file like so:

```
cd {{repository_path}}

mkdir -p .warp/workflows/

cp ~/path/to/my_awesome_workflow.yaml .warp/workflows
```

---

# Command Search

## What is it

Command Search panel allows you to search across Command History, Workflows, Notebooks (**Coming Soon**), and A.I. Command Search all at once. Warp supports fuzzy search and tries to rank more relevant search queries.

## How to Access it

- 1.
    

    Press `CTRL-R` to open the Command Search Panel. You’ll be greeted with a landing page, where you can click through different filters to get started.

    

![](https://848020679-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MbqIgTw17KQvq_DQuRr%2Fuploads%2Fgit-blob-d05964a8547bccec07191bf2509a8461fea5b4dc%2Fcommand-search.png?alt=media)

---

Command Search Panel

- 1.
    

    Type into the input box what your search query is. The results will be a mix of command history, saved workflows, and A.I. Command Search.

        
        ![curly brackets](https://848020679-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MbqIgTw17KQvq_DQuRr%2Fuploads%2Fgit-blob-1d87ef1fddcb49ad7719aaa9ba7e92245bf414ee%2Fworkflow.png?alt=media)
        
        Curly Brackets icon signifies that the result is a [Workflow](https://docs.warp.dev/features/entry/workflows).
        
        
        ![rewind time clock](https://848020679-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MbqIgTw17KQvq_DQuRr%2Fuploads%2Fgit-blob-3f722048a6ffb5bf2c61f7924edc6f2c06afec96%2Fhistory.png?alt=media)
        
        Rewind Time Clock icon signifies that the result is a [Command History](https://docs.warp.dev/features/entry/command-history).
        
        
        ![earmarked page](https://848020679-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MbqIgTw17KQvq_DQuRr%2Fuploads%2Fgit-blob-df0fa7be01eb32d7fa0aaee9b2db92160a082570%2Fnotebook.png?alt=media)
        
        Earmarked Page icon signifies that the result is a Notebook (**Coming Soon**).
        
        
        ![sparkle](https://848020679-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MbqIgTw17KQvq_DQuRr%2Fuploads%2Fgit-blob-91ccf3f2a2c1de35174b3a29e8eb87048035cb85%2Fai-sparkle.png?alt=media)
        
        Sparkle icon signifies piping that search query into [A.I. Command Search](https://docs.warp.dev/features/entry/ai-command-search)
        
    

- 2.
    

    Activate a specific filter, by prepending your search term with:

    
    - `workflows:` will activate the workflows filter. You can also use the shortcuts `w:` or `W+TAB`.
        
    
    - `history:` will activate the history filter. You can also use the shortcuts `h:` or `H+TAB`.
        
    
    - `#:` will activate the A.I. Command Search filter. Once the filter is activated, it will be bolded and italicized.
        
    

- 3.
    

    Once the result shows up, press ENTER to input the command directly into Warp's Input Editor. For history results, `CMD-ENTER` will directly execute the command.

---

# Command History

## What is it

While running, Warp isolates the history of each shell session e.g. if you have two Split Panes open, commands created in one pane do not populate the history of the other. Warp combines the history upon closing.

## How to Access it

- Hitting `↑` (UP) in the [Input Editor](https://github.com/warpdotdev/docs/blob/main/features/entry/editor/README.md) brings up your history and performs a prefix search based on input.
    

- Pressing `CTRL-R` opens the [Command Search](https://docs.warp.dev/features/entry/command-search) panel and initiates a search of your Command History. To navigate the Command Search panel:
    
    - Start typing and Warp will automatically filter using fuzzy search. Warp bolds matching text when filtering with fuzzy search.

---

# Launch Configurations

## What is it[](https://docs.warp.dev/features/entry/workflows#workflow-file-format#what-is-it)

Launch Configurations enables you to save your configuration of windows, tab, and panes, so that you can reopen the same set of windows, tab, and panes per project quickly. You can save this via the app, or by adding a yaml file.

## How it works[](https://docs.warp.dev/features/entry/workflows#workflow-file-format#how-it-works)

- 1.
    

    Set up the configuration of windows, tabs, and panes you would like to save.

    

- 2.
    

    From the Command Palette `CMD-P`, enter `#` to open the Launch Configuration Palette, then click plus **+**.

    

- 3.
    

    Name the configuration file.

    

- 4.
    

    Click the save configuration button.

    

- 5.
    

    Then, toggle the Launch Configuration Palette like in step 2 from above, with the keyboard shortcut `CTRL-CMD-L`, or from the Mac Menu: `File > Launch Configurations`, where you can search through and open your saved configurations.

---

## YAML Format[](https://docs.warp.dev/features/entry/workflows#workflow-file-format#yaml-format)

All yaml files are stored in `~/.warp/launch_configurations/`. *Note:* The `cwd:` value in the yaml code must contain an absolute path or `""`. Note that `~` or empty paths will result in the file not being visible on the list of options for Launch Configurations.

### Windows[](https://docs.warp.dev/features/entry/workflows#workflow-file-format#windows)

Here's a sample configuration that shows how windows are structured.

```
# Warp Launch Configuration
#
#
# Use this to start a certain configuration of windows, tabs, and panes.
# Open the launch configuration palette with ctrl-cmd-L to access 
# and open any launch configuration.
#
# This configuration has two windows, each with one tab in different starting directories.

---
name: Example Configuration With Two Windows
windows:
  - tabs:
      - title: documents
        layout:
          cwd: /Users/warp-user/Documents
        color: blue
  - tabs:
      - title: warp user
        layout:
          cwd: /Users/warp-user
        color: green
```
```

### Tabs[](https://docs.warp.dev/features/entry/workflows#workflow-file-format#tabs)

Here's a sample configuration that shows how tabs are structured.

```
# Warp Launch Configuration
#
# This configuration has two windows.
# The first window executes two commands on start.
# The second window has a split pane that executes a command on start.

---
name: Example Configuration With Starting Commands
windows:
  - tabs:
      - title: documents
        layout:
          cwd: /Users/warp-user/Documents
          commands:
            - exec: ls
            - exec: code .
        color: blue
  - tabs:
      - title: downloads
        layout:
          split_direction: vertical
          panes:
            - cwd: /Users/warp-user/Downloads
              commands:
                - exec: curl http://example.com -o my.file
            - cwd: /Users/warp-user
              commands:
                - exec: ssh user@remote.server.com
        color: green
```

### 

Panes[](https://docs.warp.dev/features/entry/workflows#workflow-file-format#panes)

Launch Configurations support setting split panes in each tab. Note that Warp also supports nesting split panes.

# Warp Launch Configuration

#

# This configuration is two windows, each with split panes.

# The first window contains a vertically split tab with two panes.

# The second window contains a horizontally split tab,

# with a vertically split tab on the right.



---

name: Example Configuration With Split Panes

windows:

- tabs:

- title: downloads and warp user

layout:

split_direction: vertical

panes:

- cwd: /Users/warp-user/Downloads

- cwd: /Users/warp-user

color: blue

- tabs:

- title: desktop, documents, and warp user

layout:

split_direction: horizontal

panes:

- cwd: /Users/warp-user/Desktop

- split_direction: vertical

panes:

- cwd: /Users/warp-user/Documents

- cwd: /Users/warp-user

color: green

### 

Commands[](https://docs.warp.dev/features/entry/workflows#workflow-file-format#commands)

Use the `commands` field to define a set of commands to run when a configuration is launched.

# Warp Launch Configuration

#

# This configuration has two windows.

# The first window executes two commands on start.

# The second window has a split pane that executes a command on start.



---

name: Example Configuration With Starting Commands

windows:

- tabs:

- title: documents

layout:

cwd: /Users/warp-user/Documents

commands:

- exec: ls

- exec: code .

color: blue

- tabs:

- title: downloads

layout:

split_direction: vertical

panes:

- cwd: /Users/warp-user/Downloads

commands:

- exec: curl http://example.com -o my.file

- cwd: /Users/warp-user

commands:

- exec: ssh user@remote.server.com

color: green