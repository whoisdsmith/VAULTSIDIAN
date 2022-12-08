---
created: 2022-08-05T11:16:24 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/knowledge-base/web-services/guide-to-git-how-to-set-up-deployment/
author: 
---

# Guide to Git™ - How to Set Up Deployment | cPanel & WHM Documentation

---
## Guide to Git™ - How to Set Up Deployment

___

Last modified: _July 25, 2022_

## Overview

cPanel’s [_Git Version Control_](https://docs.cpanel.net/cpanel/files/git-version-control/) interface (_cPanel >> Home >> Files >> Git Version Control_) allows you to configure deployment for your cPanel-managed repositories. While many deployment configurations are possible, this document only outlines two types of deployment that you can configure.

### Push

**Push** deployment first pulls changes from a remote repository to your local computer. Then, you can push them to your cPanel-managed repository. The system will automatically deploy changes that you push to the cPanel-managed repository.

![[Guide to Git™ - How to Set Up Deployment  cPanel & WHM Documentation/git-push-deployment-workflow.png]] _Push deployment._

### Pull

**Pull** deployment pulls changes from a remote repository to your local computer and pushes new changes from your local computer to the remote repository. You can then use the [_Git Version Control_](https://docs.cpanel.net/cpanel/files/git-version-control/) interface (_cPanel >> Home >> Files >> Git Version Control_) to manually deploy changes that you pull from the remote repository.

![[Guide to Git™ - How to Set Up Deployment  cPanel & WHM Documentation/git-pull-deployment-workflow.png]]

_Pull deployment._

Note:

If you experience issues when you configure Git deployment, read the following documents:

-   [Guide to Git - Set Up Access to Private Repositories](https://docs.cpanel.net/knowledge-base/web-services/guide-to-git-set-up-access-to-private-repositories)
    
-   [Git Version Control Series: Git Problems and How to Fix Them](https://blog.cpanel.com/git-version-control-series-git-problems-and-how-to-fix-them/)
    

## Set up push deployment

Note:

We recommend that you use this type of deployment.

### Create an empty repository on your cPanel account.

If the repository that you wish to deploy does not already exist on your cPanel account, use cPanel’s [_Git Version Control_](https://docs.cpanel.net/cpanel/files/git-version-control/) interface (_cPanel >> Home >> Files >> Git Version Control_) to create one.

Note:

For this type of deployment, do **not** clone a remote repository during this step. Instead, create an empty repository.

### Clone the remote repository to your local computer.

If you have not already cloned it, clone the remote repository. For example, run the following command to clone a repository, where `URL` represents the remote repository’s clone URL:

```bash
git clone URL
```

Important:

To clone private repositories, you must perform additional steps. If you do not perform these steps, you will experience errors when you attempt to use Git. For more information, read our [Guide to Git - Set Up Access to Private Repositories](https://docs.cpanel.net/knowledge-base/web-services/guide-to-git-set-up-access-to-private-repositories) documentation.

Note:

You can find the repository’s clone URL by performing the following steps:

1.  Navigate to cPanel’s [_Git Version Control_](https://docs.cpanel.net/cpanel/files/git-version-control/) interface (_cPanel >> Home >> Files >> Git Version Control_)
    
2.  Locate the desired repository in the list of repositories and click _Manage_.
    
3.  The URL appears under the _Clone URL_ heading.
    

### Create the .cpanel.yml file.

In order to deploy changes from a cPanel-managed repository, you **must** check a `.cpanel.yml` file in to the top-level directory of your repository. You can create and commit this file to your local computer’s copy of the repository, or you can create and commit it on the remote repository.

-   If you use the remote repository, you will require read-write access or can submit a pull request to the remote repository.
    
-   This tutorial uses changes from the local computer rather than the remote repository.
    

For example, a `.cpanel.yml` file may resemble the following example:

<table style="border-spacing:0;padding:0;margin:0;border:0;width:auto;overflow:auto;display:block;"><tbody><tr><td style="vertical-align:top;padding:0;margin:0;border:0;"><pre style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4" class=" language-bash"><code class=" language-bash" data-lang="bash">1
2
3
4
5
6
</code></pre></td><td style="vertical-align:top;padding:0;margin:0;border:0;;width:100%"><pre style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4" class=" language-bash"><code class=" language-bash" data-lang="bash">---
deployment:
 tasks:
 - <span class="token function">export</span> DEPLOYPATH<span class="token operator">=</span>/home/user/public_html/
 - /bin/cp index.html <span class="token variable">$DEPLOYPATH</span>
 - /bin/cp style.css <span class="token variable">$DEPLOYPATH</span></code></pre></td></tr></tbody></table>

More:

For more information about the `.cpanel.yml` file, read our [Guide to Git - Deployment](https://docs.cpanel.net/knowledge-base/web-services/guide-to-git-deployment) documentation.

### Add the cPanel-managed repository as a remote.

From your local computer, run the following command to add the cPanel-managed repository as the local computer’s remote:

```bash
git remote add origin URL
```

In this command, `URL` represents the cPanel-managed repository’s clone URL.

### Push changes to the cPanel-managed repository.

From your local computer, run the following command to push the changes from your local computer to the cPanel-managed repository:

```bash
git push -u origin HEAD
```

After the cPanel-managed repository contains the `.cpanel.yml` file, the system will automatically deploy any changes that you push to it.

Important:

-   If you experience errors when you attempt to push your changes, the repository may be private and require SSH access. For more information, read our [Guide to Git - Set Up Access to Private Repositories](https://docs.cpanel.net/knowledge-base/web-services/guide-to-git-set-up-access-to-private-repositories) documentation.

## Set up pull deployment

### Clone the remote repository to your cPanel account.

If the repository that you wish to deploy does not already exist on your cPanel account, use cPanel’s [_Git Version Control_](https://docs.cpanel.net/cpanel/files/git-version-control/) interface (_cPanel >> Home >> Files >> Git Version Control_) to clone the desired remote repository.

Note:

This feature enforces several restrictions on clone URLs, and it verifies the remote host’s public SSH keys for `ssh://` clone URLs.

### Clone the remote repository to your local computer.

If you have **not** already cloned the remote repository, use the terminal on your local computer to clone the remote repository.

For example, run the following command to clone a repository, where URL represents the remote repository’s clone URL:

```bash
git clone URL
```

### Create the .cpanel.yml file.

In order to deploy changes from a cPanel-managed repository, you **must** check a `.cpanel.yml` file in to the top-level directory of your repository. You can create and commit this file to your local computer’s copy of the repository, or you can create and commit it on the remote repository.

If you use the remote repository, you will **require** read-write access or can submit a pull request to the remote repository. This tutorial uses changes from the local computer rather than the remote repository.

<table style="border-spacing:0;padding:0;margin:0;border:0;width:auto;overflow:auto;display:block;"><tbody><tr><td style="vertical-align:top;padding:0;margin:0;border:0;"><pre style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4" class=" language-bash"><code class=" language-bash" data-lang="bash">1
2
3
4
5
6
</code></pre></td><td style="vertical-align:top;padding:0;margin:0;border:0;;width:100%"><pre style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4" class=" language-bash"><code class=" language-bash" data-lang="bash">---
deployment:
 tasks:
 - <span class="token function">export</span> DEPLOYPATH<span class="token operator">=</span>/home/user/public_html/
 - /bin/cp index.html <span class="token variable">$DEPLOYPATH</span>
 - /bin/cp style.css <span class="token variable">$DEPLOYPATH</span></code></pre></td></tr></tbody></table>

More:

For more information about the `.cpanel.yml` file, read our [Guide to Git - Deployment](https://docs.cpanel.net/knowledge-base/web-services/guide-to-git-deployment) documentation.

### Push changes to the remote repository.

From your local computer, run the following command to push the changes from your local computer to the remote repository:

```bash
git push origin HEAD
```

### Pull and deploy changes from the cPanel interface.

To pull the changes from the remote repository and then manually deploy them, perform the following steps:

1.  Navigate to cPanel’s [_Git Version Control_](https://docs.cpanel.net/cpanel/files/git-version-control/) interface (_cPanel >> Home >> Files >> Git Version Control_).
    
2.  Locate the desired repository in the list of repositories and click _Manage_.
    
3.  Click the _Pull or Deploy_ tab.
    
4.  Click _Update from Remote_ to pull changes from the remote repository.
    
5.  Click _Deploy HEAD Commit_ to deploy your changes.
    

Repeat these steps each time that you wish to pull and deploy changes. The system will **not** deploy changes for this deployment type automatically.
