---
created: 2022-08-05T11:26:49 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/files/gitweb/
author: 
---

# Gitweb | cPanel & WHM Documentation

---
## Gitweb

_Valid for versions 82 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/files/gitweb/)

___

Last modified: _July 8, 2022_

## Overview

Important:

-   cPanel, L.L.C. does **not** develop or own Gitweb. For more information, read Git’s [Gitweb](https://git-scm.com/docs/gitweb) documentation.
-   Your repository’s contents and organization determine how Gitweb displays many of its reports. Due to these variances, this document may not include everything that you see in Gitweb. If you see content that this document does not include, [submit a feature request](https://features.cpanel.net/).

Gitweb allows you to browse your repositories, view file contents, and review log, commit, and other information from within a simple interface. To access the _Gitweb_ interface for a repository, click _History_ for that repository in cPanel’s [_Git™ Version Control_](https://docs.cpanel.net/cpanel/files/git-version-control) interface (_cPanel >> Home >> Files >> Git™ Version Control_).

## The Gitweb interface

The _Gitweb_ interface displays the project’s summary report.

-   The breadcrumbs at the top of the interface display the current repository path and the current report’s name. Click a directory name to view Git repository information for that directory.
    
    -   cPanel’s [_Git™ Version Control_](https://docs.cpanel.net/cpanel/files/git-version-control) (_cPanel >> Home >> Files >> Git™ Version Control_) feature enforces several restrictions on repository paths.
    -   Repositories on your cPanel account that cPanel does **not** manage may appear in some lists within the _Gitweb_ interface.
    -   You may experience errors if you attempt to view information for repositories in restricted directories.
-   Throughout the interface, icons indicate the branches for which a commit is the HEAD commit:
    
    -   Green icons indicate local branches, grey icons indicate remote branches, and yellow icons indicate Git tags. For example, a green _master_ icon (![[Gitweb  cPanel & WHM Documentation/gitwebmaster.png]]) indicates the HEAD commit for the local _master_ branch.
    -   Click the branch names in green or yellow icons to view information in the context of that branch rather than the current branch.
-   Click the _Atom_ or _RSS_ icons in the bottom-right corner of some reports to access feeds for the repository’s activity.
    
-   Click the _TXT_ or _OPML_ icons in the bottom-right corner of some reports to access plaintext and XML versions of the data, respectively.
    

Note:

For information about Git commands, read our [Guide to Git™ - Common Git Commands](https://docs.cpanel.net/knowledge-base/web-services/guide-to-git-common-git-commands/) documentation.

## Gitweb reports

The _Gitweb_ interface displays repository information as a collection of reports. Gitweb displays links to other reports at the top of the interface **and** inline with report contents.

### blob

Click _blob_ to view the binary large object (blob) for a specific file. Git uses blobs to store the contents of a file at the time of a specific commit. This report displays the following information:

-   The name of the commit that contains the file or the `SHA-1` identifier for that version of the file, if you accessed this report via the [_commitdiff_](https://docs.cpanel.net/cpanel/files/gitweb//#commitdiff) report.
    
-   The path to the file within the repository.
    
    -   Click a directory name to view the [_tree_](https://docs.cpanel.net/cpanel/files/gitweb//#tree) report for that directory
    -   Click the filename or _raw_ to view a plaintext version of the file.
-   The contents of the file, by line number. Click a line number to navigate directly to that line.
    

Note:

Click _HEAD_ to view the _blob_ report for the `HEAD` commit’s version of that file.

#### Linked reports

-   [commit](https://docs.cpanel.net/cpanel/files/gitweb//#commit)
-   [commitdiff](https://docs.cpanel.net/cpanel/files/gitweb//#commitdiff)
-   [history](https://docs.cpanel.net/cpanel/files/gitweb//#history)
-   [log](https://docs.cpanel.net/cpanel/files/gitweb//#log)
-   [shortlog](https://docs.cpanel.net/cpanel/files/gitweb//#shortlog)
-   [summary](https://docs.cpanel.net/cpanel/files/gitweb//#summary)
-   [tree](https://docs.cpanel.net/cpanel/files/gitweb//#tree)

### commit

Click _commit_ to view all of the information for a specific commit. Each commit includes the following information:

-   The first line of the commit message, as a header. Click this line to view a [_commitdiff_](https://docs.cpanel.net/cpanel/files/gitweb//#commitdiff) report that compares this commit and its parent commit.
    
-   _author_ — The commit author’s name, their email address, and the date and time of the commit.
    
    -   Click the author’s name to view the results of a search for that author.
    -   Click the author’s email address to view the results of a search for that email address.
-   _committer_ — The commiter’s name, their email address, and the date and time of the commit.
    
    -   Click the commiter’s name to view the results of a search for that committer.
    -   Click the commiter’s email address to view the results of a search for that email address.
-   _commit_ — The commit’s `SHA-1` identifier.
    
-   _tree_ — The `SHA-1` identifier for the working tree. Click this identifier to view the [_tree_](https://docs.cpanel.net/cpanel/files/gitweb//#tree) report for the commit.
    
-   _parent_ — The `SHA-1` identifier for the parent commit. Click this identifier to view the [_commit_](https://docs.cpanel.net/cpanel/files/gitweb//#commit) report for the parent commit.
    
-   The full commit message.
    
-   A list of new, updated, moved, or deleted files. Click a filename to view the [_blob_](https://docs.cpanel.net/cpanel/files/gitweb//#blob) report for that file.
    
    -   New files display the filename and a _\[new file with mode: 0700\]_ message, where _0700_ represents the file’s [octal permissions](https://wikipedia.org/wiki/File_system_permissions).
    -   Updated files display the filename.
    -   Moved files display the filename and a _\[moved from path/name with n% similarity\]_ message, where _path/name_ represents the file’s previous location and _n%_ represents the percentage of the file that resembles its parent version.
    -   Deleted files display the filename and a _\[deleted file\]_ message.

Note:

-   Most commits list an identical committer and author.
-   Click _snapshot_ to download the repository’s data at the time of the commit.
-   Click _parent: SHA-1_, where _SHA-1_ represents a `SHA-1` identifier, to view the [_commit_](https://docs.cpanel.net/cpanel/files/gitweb//#commit) report for the parent commit.
-   Click _patch_ to view the commit diff in a plaintext email format. You can use this output when you run the [`git am`](https://git-scm.com/docs/git-am) command.

#### Linked reports

-   [blob](https://docs.cpanel.net/cpanel/files/gitweb//#blob)
-   [commitdiff](https://docs.cpanel.net/cpanel/files/gitweb//#commitdiff)
-   [log](https://docs.cpanel.net/cpanel/files/gitweb//#log)
-   [shortlog](https://docs.cpanel.net/cpanel/files/gitweb//#shortlog)
-   [summary](https://docs.cpanel.net/cpanel/files/gitweb//#summary)
-   [tree](https://docs.cpanel.net/cpanel/files/gitweb//#tree)

### commitdiff

Click _commitdiff_ (or, in some reports, _diff_ or _diff to current_) to view a comparison of two commits’ data in the unified diff format (a diff). When you access this report via a _commitdiff_ or _diff_ link, the diff compares the commit with its parent commit. When you access this report via a _diff_ to current link, the diff compares the commit with the `HEAD` commit.

This report includes the following information:

-   The first line of the commit message, as a header.
    
-   _author_ — The commit author’s name, their email address, and the date and time of the commit.
    
    -   Click the author name to view the results of a search for that commit’s author.
    -   Click the author email address to view the results of a search for that email address.
-   _committer_ — The commiter’s name, their email address, and the date and time of the commit.
    
    -   Click the commiter name to view the results of a search for that committer.
    -   Click the commiter email address to view the results of a search for that email address.
-   A list of new, updated, moved, or deleted files. Click a filename to view the [_blob_](https://docs.cpanel.net/cpanel/files/gitweb//#blob) report for that file.
    
    -   New files display the filename and a _\[new file with mode: 0700\]_ message, where _0700_ represents the file’s octal permissions.
        
    -   Updated files display the filename.
        
    -   Moved files display the filename and a _\[moved from path/name with n% similarity\]_ message, where _path/name_ represents the file’s previous location and _n%_ represents the percentage of lines that the commit changed within the file. Click the file’s previous location to view the [_blob_](https://docs.cpanel.net/cpanel/files/gitweb//#blob) report for the previous version of the file.
        
    -   Deleted files display the filename and a _\[deleted file\]_ message.
        
-   The specific `git diff` command for each file, as a header, and the diff for that file (the output of that command). Click a filename or the short `SHA-1` identifier for the file to view the [_blob_](https://docs.cpanel.net/cpanel/files/gitweb//#blob) report for that file.
    

Note:

Most commits list an identical committer and author.

In this report, you can also perform the following actions:

-   Click _inline_ to view each file’s diff as a list of line-by-line changes.
-   Click _parent: SHA-1_, where _SHA-1_ represents a `SHA-1` identifier, to view the commit report for the parent commit.
-   Click _patch_ to view the commit diff in a plaintext email format. You can use this output when you run the `git am` command.
-   Click _raw_ to view a plaintext version of the commit diff.
-   Click _side by side_ to view each file’s diff in two columns.

#### Linked reports

-   [blob](https://docs.cpanel.net/cpanel/files/gitweb//#blob)
-   [commit](https://docs.cpanel.net/cpanel/files/gitweb//#commit)
-   [history](https://docs.cpanel.net/cpanel/files/gitweb//#history)
-   [log](https://docs.cpanel.net/cpanel/files/gitweb//#log)
-   [shortlog](https://docs.cpanel.net/cpanel/files/gitweb//#shortlog)
-   [summary](https://docs.cpanel.net/cpanel/files/gitweb//#summary)
-   [tree](https://docs.cpanel.net/cpanel/files/gitweb//#tree)

### heads

Note:

This report does **not** display remote branches.

Click _heads_ to view information about each local branch’s `HEAD` commit. This report includes the following information:

-   The repository path. Click this path to view the _summary_ report for the repository.
    
-   A list of branches that includes the following information:
    
    -   The time since the most recent (`HEAD`) commit or the commit date.
    -   The branch name. Click the branch name to view the [_shortlog_ report](https://docs.cpanel.net/cpanel/files/gitweb//#shortlog) for that branch.

#### Linked reports

-   [commit](https://docs.cpanel.net/cpanel/files/gitweb//#commit)
-   [commitdiff](https://docs.cpanel.net/cpanel/files/gitweb//#commitdiff)
-   [log](https://docs.cpanel.net/cpanel/files/gitweb//#log)
-   [shortlog](https://docs.cpanel.net/cpanel/files/gitweb//#shortlog)
-   [summary](https://docs.cpanel.net/cpanel/files/gitweb//#summary)
-   [tags](https://docs.cpanel.net/cpanel/files/gitweb//#tags)
-   [tree](https://docs.cpanel.net/cpanel/files/gitweb//#tree)

### history

Click _history_ to view the change history for a specific file. This report includes the following information:

-   The first line of the commit message for the commit through which you accessed the report, as a header. Click the first line of the _commit_ message to view the commit report for that commit.
    
-   The file’s path. Click a directory name to view the [_tree_](https://docs.cpanel.net/cpanel/files/gitweb//#tree) report for that directory, or click the filename to view the [_blob_](https://docs.cpanel.net/cpanel/files/gitweb//#blob) report for that file.
    
-   A list of commits that included changes to that file. This list displays the following information:
    
    -   The amount of time since that commit or the commit date.
    -   The commit author’s name. Click the author’s name to view the results of a search for that commit author.
    -   The first line of the commit message. Click the first line of the _commit_ message to view the [_commit_](https://docs.cpanel.net/cpanel/files/gitweb//#commit) report for that commit.

Note:

Click _raw_ to view a plaintext version of the file.

#### Linked reports

-   [blob](https://docs.cpanel.net/cpanel/files/gitweb//#blob)
-   [commit](https://docs.cpanel.net/cpanel/files/gitweb//#commit)
-   [commitdiff](https://docs.cpanel.net/cpanel/files/gitweb//#commitdiff) (diff to current)
-   [log](https://docs.cpanel.net/cpanel/files/gitweb//#log)
-   [shortlog](https://docs.cpanel.net/cpanel/files/gitweb//#shortlog)
-   [summary](https://docs.cpanel.net/cpanel/files/gitweb//#summary)
-   [tree](https://docs.cpanel.net/cpanel/files/gitweb//#tree)

### log

Click _log_ to view each commit’s log information. This report includes the following information:

-   The repository path. Click this path to view the _summary_ report for the repository.
    
-   The following information for each of the repository’s commits:
    
    -   The time since the commit (or the commit date) and the first line of the commit message, as headers for each commit. Click the first line of the commit message to view the [_commit_](https://docs.cpanel.net/cpanel/files/gitweb//#commit) report for that commit.
    -   The commit author and the date and time of the commit. Click the author’s name to view the results of a search for that commit author.
    -   The full commit message.

#### Linked reports

-   [commit](https://docs.cpanel.net/cpanel/files/gitweb//#commit)
-   [commitdiff](https://docs.cpanel.net/cpanel/files/gitweb//#commitdiff)
-   [shortlog](https://docs.cpanel.net/cpanel/files/gitweb//#shortlog)
-   [summary](https://docs.cpanel.net/cpanel/files/gitweb//#summary)
-   [tree](https://docs.cpanel.net/cpanel/files/gitweb//#tree)

### shortlog

Click _shortlog_ to view an abbreviated list of each commit’s log information. This report includes the following information:

-   The repository path. Click this path to view the [_summary_ report](https://docs.cpanel.net/cpanel/files/gitweb//#summary) for the repository.
    
-   The following information for each of the repository’s commits:
    
    -   The time since the most recent commit or the commit date.
    -   The commit author. Click the author’s name to view the results of a search for that commit author.
    -   The first line of the commit message. Click the first line of the commit message to view the [_commit_](https://docs.cpanel.net/cpanel/files/gitweb//#commit) report for that commit.

Note:

Click _snapshot_ to download the repository’s data at the time of the commit.

#### Linked reports

-   [commit](https://docs.cpanel.net/cpanel/files/gitweb//#commit)
-   [commitdiff](https://docs.cpanel.net/cpanel/files/gitweb//#commitdiff)
-   [log](https://docs.cpanel.net/cpanel/files/gitweb//#log)
-   [summary](https://docs.cpanel.net/cpanel/files/gitweb//#summary)
-   [tree](https://docs.cpanel.net/cpanel/files/gitweb//#tree)

### summary

Click _summary_ to view a summary of repository information. This report includes the following information:

-   _description_ — The repository’s name and description, if they exist.
-   _owner_ — The repository’s owner.
-   _last change_ — The date and time of the most recent commit.
-   _shortlog_ — Click _shortlog_ to view the [shortlog](https://docs.cpanel.net/cpanel/files/gitweb//#shortlog) report for the repository. It will contain a list of the following abbreviated log information for each of the repository’s commits:
    
    -   The time since the most recent commit or the commit date.
    -   The commit author. Click the author’s name to view the results of a search for that commit author.
    -   The first line of the commit message. Click the first line of the commit message to view the [_commit_](https://docs.cpanel.net/cpanel/files/gitweb//#commit) report for that commit.
-   _tags_ — Click _tags_ to view the [_tags_](https://docs.cpanel.net/cpanel/files/gitweb//#tags) report for the repository. It will contain a list of the following Git tag information:
    
    -   The time since the commit or the commit date.
    -   The tag name. Click the tag name to view the [_commit_](https://docs.cpanel.net/cpanel/files/gitweb//#commit) report for that commit.
    -   The tag message. Click the message to view the [_tag_](https://docs.cpanel.net/cpanel/files/gitweb//#tags) report for that commit.
    -   The tag object. Click the tag object to view the [_tag_](https://docs.cpanel.net/cpanel/files/gitweb//#tags) report for that commit.
-   _heads_ — Click _heads_ to view the [_heads_](https://docs.cpanel.net/cpanel/files/gitweb//#heads) report for the repository. It will contain a list of the following local tracking branch information:
    
    -   The time since the most recent commit or the commit date.
    -   The branch name. Click the branch name to view the [_shortlog_](https://docs.cpanel.net/cpanel/files/gitweb//#shortlog) report for that branch.

Note:

Click _snapshot_ to download the repository’s data at the time of the most recent commit.

#### Linked reports

-   [commit](https://docs.cpanel.net/cpanel/files/gitweb//#commit)
-   [commitdiff](https://docs.cpanel.net/cpanel/files/gitweb//#commitdiff)
-   [heads](https://docs.cpanel.net/cpanel/files/gitweb//#heads)
-   [log](https://docs.cpanel.net/cpanel/files/gitweb//#log)
-   [shortlog](https://docs.cpanel.net/cpanel/files/gitweb//#shortlog)
-   [tags](https://docs.cpanel.net/cpanel/files/gitweb//#tags)
-   [tree](https://docs.cpanel.net/cpanel/files/gitweb//#tree)

### tags

Click _tags_ (or, in some reports, _tag_) to view information about the repository’s tags. If you accessed it for an individual tag, this report lists the following information:

-   The tag name, as a header. Click the tag name to view the [_commit_](https://docs.cpanel.net/cpanel/files/gitweb//#commit) report for that commit.
-   _object_ — The `SHA-1` identifier for the commit object.
-   _author_ — The commit author’s name, their email address, and the date and time of the commit.
    
    -   Click the author’s name to view the results of a search for that commit author.
    -   Click the author’s email address to view the results of a search for that email address.
-   The tag message.
    

If you accessed the report via a list of tags, it lists the following information:

-   The repository path. Click this path to view the [_summary_](https://docs.cpanel.net/cpanel/files/gitweb//#summary) report for the repository.
-   The following information for each tag:
    
    -   The time since the commit or the commit date.
    -   The tag name. Click the tag name to view the [_commit_](https://docs.cpanel.net/cpanel/files/gitweb//#commit) report for that commit.
    -   The tag message. Click the message to view the [_tag_](https://docs.cpanel.net/cpanel/files/gitweb//#tags) report for that commit.
    -   The tag object. Click the tag object to view the [_tag_](https://docs.cpanel.net/cpanel/files/gitweb//#tags) report for that commit.
    -   The first line of the commit message.

#### Linked reports

-   [commit](https://docs.cpanel.net/cpanel/files/gitweb//#commit)
-   [commitdiff](https://docs.cpanel.net/cpanel/files/gitweb//#commitdiff)
-   [heads](https://docs.cpanel.net/cpanel/files/gitweb//#heads)
-   [log](https://docs.cpanel.net/cpanel/files/gitweb//#log)
-   [shortlog](https://docs.cpanel.net/cpanel/files/gitweb//#shortlog)
-   [summary](https://docs.cpanel.net/cpanel/files/gitweb//#summary)
-   [tree](https://docs.cpanel.net/cpanel/files/gitweb//#tree)

### tree

Click _tree_ to view the working tree for a specific commit. This report lists the following information:

-   The first line of the commit message, as a header. Click the first line of the commit message to view the [_commit_](https://docs.cpanel.net/cpanel/files/gitweb//#commit) report for that commit.
-   The following information for each file and directory within the working tree:
    
    -   The symbolic character representation of the file or directory’s permissions.
    -   The file size, in bytes, or a hyphen (`-`) for directories.
    -   The file or directory name. Click a directory name to view the [_tree_](https://docs.cpanel.net/cpanel/files/gitweb//#tree) report for that directory, or click the filename to view the [_blob_](https://docs.cpanel.net/cpanel/files/gitweb//#blob) report for that file.

Note:

-   Click _snapshot_ to download the data for this version of the working tree.
-   Click _raw_ to view the plaintext version of a file.

#### Linked reports

-   [blob](https://docs.cpanel.net/cpanel/files/gitweb//#blob)
-   [commit](https://docs.cpanel.net/cpanel/files/gitweb//#commit)
-   [commitdiff](https://docs.cpanel.net/cpanel/files/gitweb//#commitdiff)
-   [history](https://docs.cpanel.net/cpanel/files/gitweb//#history)
-   [log](https://docs.cpanel.net/cpanel/files/gitweb//#log)
-   [shortlog](https://docs.cpanel.net/cpanel/files/gitweb//#shortlog)
-   [summary](https://docs.cpanel.net/cpanel/files/gitweb//#summary)

## Search Gitweb data

In addition to Gitweb’s reports, you can search Gitweb for repository information.

To search Gitweb, perform the following steps:

1.  From the menu to the left of the search text box in the top-left corner of the interface, select the desired search type:
    
    -   _commit_ — Search for commit authors and messages.
    -   _grep_ — Search within the files in the current working tree.
    -   _author_ — Search for the commit date, author name, or author email address.
    -   _committer_ — Search for a commit date, committer’s name, or committer’s email address.
    -   _pickaxe_ — Search for all of the commits that included changes to the specified search terms.
2.  Enter the search terms in the _search_ text box.
    
3.  To use Perl-Compatible Regular Expressions (PCREs) in your search text, select the _re_ checkbox.
    
    Note:
    
    Gitweb’s PCRE searches are case-insensitive.
    
4.  Press Enter. The search results will appear.
