---
created: 2022-07-16T16:02:14 (UTC -04:00)
tags: []
source: https://docs.warp.dev/features/integrations-and-plugins
author: 
---

# SSH - Warp Documentation

> ## Excerpt
> When you SSH into a remote box, you get all the features of Warp without any configuration on your part. The input editor, autocompletions, and history search work the same, regardless of machine.

---
When you SSH into a remote box, you get all the features of Warp without any configuration on your part. The input editor, autocompletions, and history search work the same, regardless of machine.

-   Warp specific features like Blocks are currently supported only for bash or zsh.
    

-   If you're using a different shell, you'll want to use `/usr/bin/ssh` directly (see below for more details).
    

-   For zsh, xxd is required to bootstrap warp.
    

If you're using zsh on the remote host, we create a temp folder to act as the ZDOTDIR during the bootstrapping process and remove it when the shell is setup.

![](https://848020679-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MbqIgTw17KQvq_DQuRr%2Fuploads%2Fgit-blob-d1dfbe0032fc3388c17b2ecb4eaff36a7a2b5d6c%2Fssh.png?alt=media)

## 

Implementation

We create a wrapper (around `/usr/bin/ssh`) to setup the shell for Warp's feature set. We authenticate normally using `/usr/bin/ssh`, and bootstrap the remote shell to work with Warp Blocks and the Input Editor. You can opt-out of this functionality by invoking `/usr/bin/ssh` directly.

-   Warp takes over the prompt which enables us to build a modern input editor.
    

-   Warp configures histcontrol to ignore commands with leading spaces. We do this so our bootstrapping code does not clutter the history.
    

You can see the SSH wrapper by using `which warp_ssh_helper` in Zsh, `type warp_ssh_helper` in Bash.

## 

Troubleshooting

## 

channel 2: open failed: connect failed: open failed

If you're seeing these errors, you may have some config on your server (usually in `/etc/ssh/sshd_config`) preventing Warp's ControlMaster connection from working. In this state, completions that require information from your remote host won't work and your history also won't work.

You should ensure that `MaxSessions` is either commented out or is at least `2`.

Write access in `/etc/ssh/` typically requires sudo access. After any edits, you'd also need to restart the `sshd` daemon.
