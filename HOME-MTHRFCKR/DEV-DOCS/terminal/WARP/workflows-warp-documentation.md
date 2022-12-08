---
created: 2022-07-16T16:00:47 (UTC -04:00)
tags: []
source: https://docs.warp.dev/features/integrations-and-plugins
author: 
---

# Workflows - Warp Documentation

> ## Excerpt
> Workflows are an easier way to execute and share commands within Warp. They are searchable by name, description, or command and are easily parameterized. A global list of commands sourced by the Warp team and community are readily available within the app. Additionally, you can create and manage local workflows specific to you or associated with a particular git repository.

---
Workflows are an easier way to execute and share commands within Warp. They are searchable by name, description, or command and are easily parameterized. A [global list](https://github.com/warpdotdev/workflows) of commands sourced by the Warp team and community are readily available within the app. Additionally, you can create and manage local workflows specific to you or associated with a particular git repository.

The in app Workflows menu can be accessed through the Command Palette or by pressing `SHIFT-CTRL-R`. Once inside the menu, filter the existing commands by typing in the search bar or click on any of the sections in the side panel to browse by category.

![](https://848020679-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MbqIgTw17KQvq_DQuRr%2Fuploads%2FgndxsTAKA636Lre5bTRU%2Fworkflows-original.gif?alt=media&token=caf7dcb9-58a9-4c42-bdbd-8454f1405fa6)

Press SHIFT-CTRL-R to open the Workflows menu.

## 

How is this Different from Aliases?

Power users tend to save aliases, create shell functions, and leverage CLI tools that streamline this. Aliases, however, have major pain points:

-   1.
    
    -   1.
        
        leave vim, source dotfiles, or reset shell
        
    

-   2.
    
    it’s difficult to attach documentation
    

-   3.
    
    are not easily searchable or sharable
    

-   4.
    
    are not easily parameterized
    

Getting aliases and functions to a productive state requires an upfront investment that’s justifiable for devs who spend most of their workday in the terminal but less so for beginners and casual users.

## 

Creating Custom Workflows

In addition to the globally sourced commands, Workflows supports the ability to save commonly used commands specific to you or your team by adding workflows defined in YAML files directly to the `~/.warp/workflows` directory or the `.warp/workflows` in the top level of a repository. Local and Repository workflows can be accessed under the "My Workflows" and "Repository Workflows" tab of the workflows menu, respectively.

## 

Local vs Repository Workflows

Local workflows are specific to a single developer. Repository workflows are instead associated with a specific git repository and can be accessed by anyone who has cloned the repo. **Currently, Repository workflows will not appear if you are SSH’d into a remote machine**.

Local Workflows: `~/.warp/workflows`

Repository Workflows `{{path_to_git_repo}}/.warp/workflows`

## 

Workflows File Format

The existing workflows specs within the [Workflows repo](https://github.com/warpdotdev/workflows) should serve as an example for the format. Additionally, a more comprehensive file format is available in [FORMAT.md](https://github.com/warpdotdev/workflows/blob/main/FORMAT.md).

## 

Adding a Local Workflow

To start, create a workflows subdirectory within your .warp folder

`mkdir -p ~/.warp/workflows`

Then, add your command’s yaml file to this directory and Warp should automatically load it into the workflows menu.

`cp ~/path/to/my_awesome_workflow.yaml ~/.warp/workflows`

## 

Adding a Repository Workflow

You can add a repository workflow exactly like you add a local workflow except now the yaml file should live within the _repo’s_. `.warp` directory. While cd’d into the repo’s root directory run

cp ~/path/to/my\_awesome\_workflow.yaml .warp/workflows

## 

Contributing to Global Workflows

You can add workflows that all Warp users can use by contributing directly to the [Workflows repo](https://github.com/warpdotdev/workflows/tree/main/specs). See the [Contributing](https://github.com/warpdotdev/workflows#contributing) section for more details.
