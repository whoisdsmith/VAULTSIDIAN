# Working Copy - Users Guide

![](/img/action-shot-72-1200.jpg)

[Working Copy](/) is a full featured Git client for iOS and since Git is a powerful version-control system it can take some time to master. The same is true for Working Copy, and even though you will not need to work with the command-line, some understanding of Git is needed. If you are not confident with Git's core concepts you should read the first few chapters of [Pro Git](http://git-scm.com/book/en/v2) by Scott Chacon or the excellent [tutorials](https://www.atlassian.com/git/tutorials/) Atlassian has made available.

### 1.1 Cloning repositories

![Video showing cloning on phone: User presses + in the upper right corner and picks clone. Picks protocol, types username, hostname and path on the Other tab. Picks repository from list on GitHub tab. Presses Clone to start transfer. When cloning completes the repository contents are shown.](/img/clone-77.png)

The first step is to get hold of a local copy of the Git repositories you want to access. Duplicating a repository from a remote server is known as cloning, and you do this by pressing + on the list of repositories.

You provide a URL pointing to a repository on the Git remote you wish to clone from. Working Copy can transfer data from the remote using http, https, git or ssh protocols. However, you should be careful using http transfer since data will be sent without encryption, which means your login credentials and your source code can be intercepted. If you are not on a trusted network you should avoid using http transfer.

There is special support for BitBucket, GitHub and some other [hosting providers](/manual/hosting-provider) to list your available repositories such that cloning amounts to picking a repository and tapping clone. Even when Working Copy has no specific support for a hosting provider, you can copy-paste your URL into the top field and Working Copy will clone just as well. 

You can also import repositories from a Mac or PC by dragging directories into iTunes Document lists. If the directory does not contain a .git subdirectory at top-level, Working Copy assumes you want a new repository with all these files added. Zip-files can also be dragged into iTunes.

![](/img/css-content-45-transparent.png)

### 1.2 Accessing files

Data in Working Copy is organized as repositories, containing directories, which themselves contain either sub-directories or files. Tapping a file shows the file content, the changes to the file and the status of the file.

File content is shown with syntax highlighting for sourcecode and a preview of html and document files. To edit you will need to switch away from Preview mode with the button at the top showing your current mode. Tap the action-button in the upper-right corner to send the file to other applications such as Mail through a share sheet.

The editing inside Working Copy is bare-bones and neutral in that neither programming languages, markdown nor regular text files get special treatment. If you are performing heavy editing consider using a specialized text-editor app for programming, markdown or other purposes. You can read [more](/manual/extending-ios) about using Working Copy in combination with other applications.

To copy files tap and hold to show a context menu, pick _Copy_, then navigate to the destination directory and press _+_ in the upper right corner to insert _File from clipboard_. Move files and directories by [dragging](https://support.apple.com/guide/ipad/drag-and-drop-ipadaa83b207/ios) them around directory listings. 

### 1.3 Committing changes

![](/img/commit-sheet-32-transparent.png)

When you have file modifications the Changes tab lights up. You can see what has been added in green and what has been deleted in red. If you are satisfied with the changes you can commit them to the repository with a button on the Status tab. A faster way, however, is to swipe left on the file in the directory listing. Swiping left can generally be performed on lists of files, directories and repositories allowing convenient access to frequent actions.

You can commit a single file, multiple files or the entire repository at once, and it is considered good practice to make a commit represent one conceptual change to your repository. Following this practice also makes it easier to come up with concise yet descriptive commit messages. 

Word suggestions are shown above the keyboard when writing your commit message. Suggestions are based on the filenames and changes you are about to commit, as well as previous commit messages in the same repository. This is combined with frequently used sentences in commit messages in public repositories. No information from your commits or repository is collected to make this happen. 

The list of files include everything that can be committed. You tap files to stage or unstage for commit and the rightmost button shows the difference for this particular file between working directory and last commit. When looking at differences you can stage/unstage individual hunks by long-tapping and swiping making it possible to commit some changes in a file but leave others uncommitted. 

When you have made one or more commits your on-device repository is seen as being ahead of the remote repository and you _push_ these commits to the remote. Because _Commit_ and _Push_ are distinct actions you can _Commit_ while offline and _Push_ once you get back online.

To _Push_ after _Commit_ tap and hold a repository and _Push_ from the context menu. You need to [unlock](/manual/purchase) the ability to _Push_ with an in-app purchase.

### 1.4 Staying up-to-date

![](/img/status-79-transparent.png)

Commits can be pushed to the remote from many sources. Other people contribute their work, or you could be doing something on a regular computer or another iOS device which results in commits that end up on the remote. 

You get commits back into Working Copy through a two-step process where you _Fetch_ and _Merge_. _Fetch_ reads commits from the server and requires a network connection. The commits will not be integrated with the local data on your device until you _Merge_, which will combine the new commits from the server with your local data. 

You can pull the list of repositories down to _Fetch_ for all your repositories. If any of your repositories received new commits you will be able to _Merge_ all these repositories with a single tap.

Sometimes data cannot be automatically combined because your local changes conflict with the changes from the commits fetched. These conflicts can be resolved by manually editing files and picking the wanted parts from the conflict markers and tapping the Resolve button. A faster solution is to use the [Resolve](/manual/resolve-tool) tool that lets you resolve conflicts for many files at once.

Performing a _Fetch_ followed by a _Merge_ is called _Pull_. On the remote detail screen you can _Fetch_, then _Merge_ and finally _Push_ with the _Sync_ button.

You can configure repositories to _Rebase_ instead of _Merge_ commits from the Configuration page inside Repository status. This is a pro configuration available to users that purchased or upgraded their [pro unlock](/manual/purchase) on October 17, 2018 or later.

### 1.5 Repository actions

![](./img/iPad-navbar-buttons.png)

![](/img/status-sheet.png)

To make it easier to perform important actions a floating fingerprint button is available in the lower right corner on iPhone. This button opens a repository status sheet with easy access to _Commit_, _Revert_, _Fetch_, _Pull_ & _Push_ and lists modified files. 

On iPads with sufficient screen space these repository actions are available at the top of the screen without the need to open any sheet. It gets easier to remember what each button does when you realise the icons are used on the status sheet and in context menus as well. 

On iPad the fingerprint button can be dragged into a new window to show the repository status sheet and since this displays modified files and updates as files change, it can be very useful while using external editors such as Textastic. 

You can tap and hold this floating button to change the location on screen. 

### 1.6 Deleting repositories

Once you are done with a repository you can delete it from the repository context menu or status screen. This has no influence on remote repositories. 

## 2\. Remotes

![](/img/remote-details-81-transparent.png)

Git remotes are server-side duplicates of your repositories with full history. These can be services such as GitHub, BitBucket etc. or they can be be privately hosted servers.

When you clone a repository, the URL of the remote repository is your starting point. Working Copy supports ssh, https and http remotes and the URL consists of protocol scheme, the hostname, username and the path to the repository on the host. The following are typical examples of remote URLs:
    
    
    https://user@git.company.se/home/user/site.git
    ssh://andrew@company.se/home/andrew/git/site.git/
    andrew@company.se/home/andrew/git/site.git/
    
    
    
            
    
    The last two URLs are equivalent since ssh is the default protocol. 
    
    
    
            
    
    Authentication will always try with a username included on the form _username@_
                otherwise remembering the last username for that host.
                The username _git_ has special meaning for many hosts such that the actual user
            account is derived from the SSH key used to authenticate.
    
    
            
    
    If you enter the Repository page you can add or delete remotes. After cloning there is only a single “origin”
                remote and, in many scenarios, there is no need for additional remotes.
    
    
    
        
    
    
        
    
    
            
    
    ### 2.1 Clone catalog
    
    
            
    
    ![](/img/clone-catalog-transparent.png)
    
    
    
            
    
    When cloning repositories from BitBucket and GitHub you can enter your credentials to get a list of repositories to clone.
                Working Copy tries to show the most relevant repositories at the top, these being the ones where you have administrative
                or push privileges. Your GitHub Gists and BitBucket Snippets are also available from this list.
            
    
    
            
    
    If the list is long, enter keywords in the search field in order to only see repositories containing these.
                If you do not see the repository you wish to clone, you can still copy-paste the clone URL into the top-field manually.
    
    
    
            
    
    Organizations on GitHub can be configured to
                [restrict](https://help.github.com/articles/about-third-party-application-restrictions/)
                third-party applications such that repositories are not listed and you might need to
                [ask
                    your administrator](https://help.github.com/articles/requesting-organization-approval-for-your-authorized-applications/) to approve Working Copy.
            
    
    
    
            
    
    You configure additional [hosting providers](/manual/hosting-provider) from Working Copy settings
               or you can clone using a URL from the clipboard.
    
    
    
        
    
    
    
        
    
    
            
    
    ### 2.2 SSH keys
    
    
            
    
    ![](/img/ssh-config-30-transparent.png)
    
    
    
            
    
    SSH transfers support password authentication but also public/private key authentication for
                improved security. The public part of a SSH key corresponds to a padlock that you use to
                lock-down resources. The private part of the SSH key corresponds to the physical key that
                opens the padlock. Your private key must be kept secret and the public key can be
                distributed to servers where you want to store remote repositories.
    
    
    
            
    
    If you tap “Connect with BitBucket” or “Connect with GitHub” your public key will automatically
                be registered with BitBucket or GitHub. For other Git hosting providers such as
                [OpenShift](https://www.openshift.com) or
                [AWS CodeCommit](https://aws.amazon.com/codecommit/) you need to
                enter your public key in  the settings page for that service. The details will depend upon
                the service in question, but your first step is to Export the public key.
                When using a Linux server, you need to append the public key to the
                _$HOME/.ssh/authorized_keys_ file.
    
    
            
    
    Working Copy generates 4096 bit RSA keys and imports RSA, ECDSA or Ed25519 private keys in
                PEM or OpenSSH format.
    
    
        
    
    
        
    
        
    
    
            
    
    ### 2.3 SSH Troubleshooting
    
    
            
    
    If you are having problems authenticating with an SSH server check that the public key installed on the server
                matches the private key in Working Copy. If you have some other SSH client on your device or computer, you should make sure
                you can connect from these without problems. If this works, you must also make sure you use the same SSH key in Working Copy,
                possibly importing the private key from the other application.
    
    
            
    
    When exporting the public key you end up with something on the form:
    
    
            
    
    
    ssh-rsa AAAAB3NzaC1…g+y4Pfz9 WorkingCopy@iPadPro-31092017
    
    
            
    
    Everything after the second space is just a comment, that makes it easier to
                determine where and how the key was created. It can sometimes help to remove this comment,
                before registering the key with your Git server.
    
    
        
    
    
        
    
    
            
    
    ### 2.4 Heroku Remotes
    
    
            
    
    It is possible to deploy to
                [Heroku](http://heroku.com/) using Git.
                You need to setup a second remote for your repository that points
                to your Heroku application. Since the
                [Heroku Toolbelt](https://toolbelt.heroku.com/)
                is not available on iOS, you must manually configure the remote. 
    
    
                
    
    The easiest way to do this is to
                    [setup your remote](https://devcenter.heroku.com/articles/git#creating-a-heroku-remote)
                    on a regular computer and determine the remote
                details on the command line by entering:
    
    
                
    
    
    git remote -v
    
    
                
    
    You then create a new remote from this URL in Working Copy. Note that username and password
                    for remote is not your Heroku account credentials. You will find this information
                    in your home directory in the hidden file _.netrc_
    
    
                
    
    
    cat ~/.netrc
    
    
              
    
    When you push to your Heroku remote the deployment status is [logged and shown](/manual/logfiles) inside
                 Working Copy.
    
    
    
            
    
    ### 2.5 AWS CodeCommit
    
    
            
    
    To use Working Copy with [AWS CodeCommit](https://aws.amazon.com/codecommit/)
                you need to create an IAM user with the _IAMUserSSHKeys_ Policy. You also need to add some Policy allowing
                repository access and _AWSCodeCommitPowerUser_ is a good choice, unless you only need to
                clone and fetch code in which case _AWSCodeCommitReadOnly_ is preferable.
            
    
    
            
    
    You must also export your SSH Key from Working Copy and _Upload SSH Public Key_. This is done
             in the _Security Credentials_ tab of your
                [IAM User](https://console.aws.amazon.com/iam/#users).
                When your SSH Key has been uploaded it
            will be listed with a _SSH Key Id_ that will be needed for the next step.
    
    
            
    
    
             Your repositories are listed in the [CodeCommit Dashboard](https://console.aws.amazon.com/codecommit/).
                When looking at individual repositories
                you can request the Clone URL in the SSH format, which can be used inside Working Copy, but you need to
                use the _SSH Key Id_ as your username. Your URL should end up looking something like:
            
    
    
            
    
    
    ssh://APKAJMDDPOLPSL7OAYOA@git-codecommit.us-east-1.amazonaws.com/v1/repos/test
    
    
    
            
    
    ### 2.6 Glitch
    
    
            
    
    [Glitch](https://glitch.com/) is a online service and community for creating web apps.
                You can edit from a web browser but they also provide access through a Git remote.
             
    
    
             
    
    If you use
                _Process in Working Copy_ from the share sheet in Safari
                the equivalent Git repository is opened in Working Copy cloning it as needed. If you are editing
                on glitch.com when using _Process in Working Copy_ the remote url includes a username
                token that grants you push permissions on the remote.
             
    
    
             
    
    When pushing changes back to glitch you need to push to another branch than master and
                use their console to merge in and reload changes. You can read about this
                [here](https://support.glitch.com/t/possible-to-code-locally-and-push-to-glitch-with-git/2704/3).
            
    
    
            
    
    Git remotes at _api.glitch.com_ behave slightly differently than other Git remotes and you need
               to include the username and a empty password to the remote url for pushing to work.
    
    
    
            
    
    ### 2.7 Hosting Providers
    
    
            
    
    To make it easier to [list](/manual/clone-catalog) your repositories, to create new remote repositories
                and to configure your [SSH keys](/manual/ssh-keys) you can configure hosting providers.
    
    
    
            
    
    ![](/img/hosting-provider-transparent.png)
    
    
    
            
    
    Working Copy supports private instances of
                BitBucket [Server](https://www.atlassian.com/software/bitbucket/server)
                (previously known as Stash),
                GitHub [Enterprise](https://enterprise.github.com/),
                [GitLab](https://about.gitlab.com/features/),
                Team Foundation Server ([TFS](https://www.visualstudio.com/en-us/news/releasenotes/tfs2017-relnotes))
                and [Gogs](https://gogs.io).
    
    
            
    
    
                You enter the hostname of your server and the instance type is identified automatically trying a
                combination of schemes and ports. If your hosting provider isn't recognised or auto-detection is
                taking too long it can help to enter a full URL including scheme and port.
    
            
    
    
            
    
    You can configure cloud instances of the above hosting providers as well as
                [Azure DevOps](https://azure.microsoft.com/en-us/services/devops/) and
                [Beanstalk](http://beanstalkapp.com).
                Even a regular Linux server, BSD server or
                [Synology NAS](https://www.youtube.com/watch?v=WMcAcUknHMw)
                can act as a hosting provider, using SSH commands for
                listing repositories.
            
    
    
            
    
    If you have several user accounts for a hosting provider you can bake the user
                into the server field as _https://username@github.com_ to get a hosting provider
                for each user.
    
    
            
    
    When you add hosting providers it is often a good idea to disable the built-in providers you are
                not using to avoid clutter in other parts of Working Copy. This is especially important when
                you configure providers with a baked-in username as the default providers for the same service
                will switch between user accounts. 
    
    
    
            
    
    ### 2.8 Access Tokens
    
    
            
    
    If you hosting provider does not allow authenticating with a regular password
               access tokens can often be used instead.
    
    
            
    
    For GitHub Enterprise you visit the website and go to _Settings > Developer Settings > Personal access tokens_
               and tap _Generate new token_. This token should be granted _repo_, _read:org_,
                _admin:public_key_, _gist_ and _admin:gpg_key_
                to support all Working Copy features but _repo_ is the most important one.
    
    
                
    
    GitHub Enterprise Server instances are configured as new hosting providers 
                where GitHub Enterprise Cloud is part of the built-in GitHub hosting provider such that 
                you need to disable _OAuth Authentication_ to allow access tokens authentication.
    
    
            
    
    On GitLab you go to _User Settings > Access Tokens_ to create new tokens
                where the _api_ scope is required.
            
    
    
            
    
    You normally use the access token instead of a password and it will be remembered
               until you sign out of the service. The exception is _Gitea_ where the access token replaces 
               the username and the password is kept blank.
    
    
        
    
    
    
        
        
    
        
    
# 3. Viewing and editing
    
    
        
    
    
            
    
    ![](/img/dir-structure-21-transparent.png)
    
    
            
    
    
             ![](/img/content-action-sheet-34.png)
            
    
    
            
    
    A repository is presented as a hierarchy of directories and files where you tap a directory to enter and
                view the contents.
    
    
            
    
    You can swipe right on entries or press and hold to access commonly used actions such as _Commit_,
              _Revert_ and invoke the share sheet which allows exporting single files, directories or the entire
                repository.
    
    
    
            
    
    Open recently accessed documents
                from the bookmark button in the upper right corner above repository or
                file listings.
    
    
    
            
    
     If you tap a file and pick the Content tab you can view the file in different modes.
                This is controlled by the button in the top bar indicating the current mode. The top choices
                are the recommended mode for this file and depends on both filename and file content.
                When you pick a mode for a given file, Working Copy remembers this choice for other files
                with the same file extension.
            
    
    
          
    
    
      
        
    
    
            
    
### 3.1 Text Editing
    
    
            
    
    ![](/img/content-preview.png)
    
    
    
            
    
    Text files can be viewed as plain text or with syntax highlighting for one of the
                supported languages.
                
               Font size is adjusted in the popup switching between modes and is remembered
               individually for different modes.
    
    
            
    
    You can pick between a number of included fonts or import new OpenType or TrueType fonts
                as a pro feature.
    
    
             
    
    Looking at source code you can tap anywhere to start editing. _Done_ in the upper right corner
              stops editing. You undo latest changes with the undo-button above the keyboard on iPad or by shaking
                 your iPhone. If you want to undo all your changes, switch to the Status tab where you can revert the
                 file to how it was at last commit.
    
    
            
    
    
                 Any text selection can be transformed with action extensions, which will let you do things such as URL encode text
                 from within the editor.
                [Shortcuts](https://itunes.apple.com/app/workflow-powerful-automation/id915249334?mt=8&at=1000lHq)
                is the prime example of such a application.
    
    
            
    
    
                 When your selection matches a valid [CSS color](https://en.wikipedia.org/wiki/Web_colors)
                you can adjust this. Placing the caret where a color is expected the popup menu also
                 lets you use the color picker to make a new color.
    
    
            
    
    Use [.editorconfig](https://editorconfig.org/) files to control encoding, newline style
               and indentation in a manner supported by a wide range of editors and IDEs.
    
    
    
        
    
### 3.2 Preview
    
    
    
            
    
    You enable _Preview_ mode with the button in the upper right corner which is available
                for HTML, Javascript, Markdown, org-mode, AsciiDoc and Jupyter notebook files.
            
    
    
    
            
    
    When previewing HTML files, relative links to images, javascript and stylesheets resolve to files inside
                repository and will work without Internet connection. External assets require a Internet connection to load.
                If offline preview is important to you, consider including javascript frameworks inside repository.
            
    
    
            You can make edits from other apps while previewing using the iOS [document picker](/manual/extending-ios)
            or [WebDAV](/manual/webdav-server) access.
            When there are changes to the file being previewed or any local assets it depends on, the preview will automatically
            reload. To make it easy to evaluate changes, the scroll and zoom settings are restored during reload.
        
    
    
            Enable the Javascript Console to check for errors, warnings or log statements.
            Errors that occur in javascript files inside repository can be tapped taking you to the line in
            the source file. You can evaluate javascript
            in the context of the HTML page and when external keyboard is attached, the ↑↓ keys let you step through
            evaluation history.
        
    
    
            
    
    
                You can preview from other devices or computers, by enabling _External URL_. Long tap the URL
                to put it on the clipboard or use Handoff to connect. This preview will keep working as you switch back to
                editing mode.
            
    
    
            Putting your iPad in split screen mode you can have Safari side-by-side with Working Copy to preview and edit
            simultaneously. 
            
    
    
            
    
    External preview is a pro feature available to users that [purchased](/manual/purchase) the unlock or upgraded their
                pro unlock on January 8, 2018 or later.
    
    
    
        
    
    
    
            
    
    ### 3.3 Search and navigation
    
    
            
    
    You can search repository files by name, text content or symbol declarations, which is often
               the fastest way to navigate a large repository.
    
    
            
    
    
                When you search from the top of directory listings, results are included from this location
                in the file hierarchy including files inside sub-directories. Search from the _Content_ tab of a file
                includes results from the entire repository or the current file depending on the scope selection.
           
    
    
        
    
    ![](/img/manual-search.png)
    
    
        
    
    Search queries will be matched against filenames, symbols, line numbers and text content. For filenames
                and symbols a fuzzy matching will be performed which means that the characters in query must occur in the given
                order but characters can be skipped. The query _read.md_
                will fuzzy match both __read_me_.md__ and __read_me_.m_ark_d_own_ but the first one
                will be ranked higher as it's closer to a non-fuzzy match.
            
    
    
                When you type several search words they all have to match either a filename, symbol, line number or text.
                The query _read.md 10_ will be understood as
                
    
    
                 
      * line 10 of the files where name fuzzy matches "read.md"
    
                 
      * occurrences of the text "10" in files where name fuzzy matches "read.md"
    
                 
      * files containing the text "read.md" and "10"
    
                
               To make it easier to restrict queries, the words matching the filename must lead your query and search results
               matching filenames or symbols will appear at the top of search results with lower ranking the more fuzzyness was
               required to reach a match.
            
            
    
    
               All files in your repository need to be read and parsed to satisfy searching for text content and symbols.
             When you search for the first time in a large repository, indexing can take several minutes and the progress is shown
               in the right part of the search field. Filename searches will be available almost immediately
                while text content and symbol results will update as the repository is indexed.
                Only files that have changed since the last search will be indexed
                when you search a repository that has been indexed previously, requiring much less work.
            
    
    
            
    
    Editor search uses your current selection or the word at your cursor as the start of your search.
               This is convenient to lookup a symbol declaration or the usages of
               a function or class. Invoking search when looking at the _Content_ tab of a non-text file the query will be your
                current filename, showing usages of that particular file.
            
    
    
            
            
    
     The prefilled query is selected such that it can be deleted with a single tap and when the query is
                empty you are shown recent edit points for repository scope and symbol declarations for the file scope,
                which is useful for quick back and forth navigation. 
                [Regular expression](https://en.wikipedia.org/wiki/Regular_expression) search is supported 
                for the file scope by wrapping your pattern in slashes such as _/[0-9]+/_ to find all integers.
            
    
    
           
    
    Typing on a external keyboard it can be efficient to not more your hands from the keyboard to the screen.
              The arrow keys let you cycle through search history, but this makes it impossible to navigate search results
              with these keys. The trick is to refine your query until the result you want is the top one,
               and ⌘⏎ lets you pick the top result.
              
    
    
    
        
    
    
        
    
### 3.4 File changes
    
    
        
    
    ![](/img/split-diff-36-transparent.png)
    
    
        
    
    ![](/img/image-diff-83.png)
    
    
        
    
    A badge on the Changes tab shows the number of lines added or deleted from a file.
            The Changes tab itself shows the differences
            between the last version committed and the current version.  The two-panel split-view in the screenshot requires the screen to be wide and for phones to be
            turned to landscape mode.
    
    
    
        
    
    Image changes can be viewed in a split-mode where zooming one image will make the other one follow -
            making it easy to focus on the details.
            If you are unsure as to where the changes are in an image, use the Color mode that
            highlights changed areas in green where identical areas are without color. Cut mode is useful for images with
            global changes and allows you to drag and rotate a partitioning line in such a way that everything on one side is the old image.
            The previous image will have a red border, and the new one a green border.
    
    
    
        
    
    The Status tab says whether the file is modified and allows you to commit or revert changes.
        
    
    
        
    
    
    
    
        
    
## 4. Committing or reverting
    
    
        
    
    
            
    
    ![](/img/commit-sheet-32-transparent.png)
    
    
    
            
    
    You can commit changes to your files for the entire repository, for all files in a sub-directory or for a specific file.
                If you do not wish to commit some of your files you can Revert to how they where at the last commit.
                The files taken into account are determined by where in the directory structure you initiate the commit.
                As a short-hand you can swipe left on a repository, directory or file to commit.
    
    
            
    
    ![](/img/status-modified-19-transparent.png)
    
    
    
            
    
    During commit you are shown a list of changed files and can view differences for individual files by pressing the button
                that shows the number of lines added or deleted. Files with a checkmark will be included in the commit and you toggle the
                checkmark by tapping the file.
                Working Copy will push the commit to the remote right away if you enable the _+Push_ button.
    
    
    
            
    
    As a general rule you should make commits with a single purpose and only include the changed files that helped achieve this purpose.
                You should write a message in the top line describing this purpose;
                if it is hard to write something short but concrete you might
                need to break your commit into smaller parts.
    
    
        
    
    
    
        
    
    
            
    
    ![](/img/commit-list-28-transparent.png)
    
    
    
            
    
### 4.1 Commit history
    
    
            
    
    The value of well-drafted commit messages becomes apparent when looking at a log of previous commits.
                You may do this for either the entire repository, a directory with all its files or for single files.
                If your commit messages are meaningful, even if you return to a project after months or years you have a much
                better chance of making sense of the source-code.
                Tap a commit to see specific changes this commit made to the files in question.
    
    
    
            
    
    The images shown in commit-logs are determined from the email-address of the person making the commit with the
                help of [gravatar.com](http://gravatar.com/).
                At the commit-list for the entire repository you can Checkout old versions of your
                files by swiping left on a commit. Your repository will be in a “detached head” state where you cannot commit any changes,
                but if you make modifications and wish to keep these, you should create a new branch.
            
    
    
            
    
    Checking out the topmost commit will reattach the head in such a way that your repository is back to normal.
    
    
            
    
    When not yet pushed to a remote, you can _Undo_ your latest commit by swiping left in the commit-list.
                All changes for that commit are kept in your working directory as modified files. If you commit again
                the last commit message is remembered, making it very easy to commit again to fix typos in the
            commit message or only commit some of the files, splitting a large commit into smaller ones. When the
            last commit has been undone, you can _Undo_ another, letting you squash several
            commits into one.
    
    
        
    
    
    
        
        
    
    
            
    
### 4.2 Branches
    
    
    
            
    
    ![](/img/branch-merge.png)
    
    
    
            
    
    A great advantage of Git compared to other version-control software is the ease at 
            which you can branch your
                repository to work independently on different things.
                Once you are confident with the work undertaken in a branch, it can be merged
                back into one of your main branches.
    
    
    
            
    
    
            The current branch (main in the screenshot) is shown in directory listings 
            between the Status cell and the 
            actual file listing. Switch to other branches with the button to the right of the branch name
            tapping the bottom of the branch picker popup for a list of all branches.
            
    
    
            
    
    Tapping a branch from the full list brings up a detail view
                where you can checkout the branch (make it current), rename or delete it. 
    
    
            
    
    Swipe left on branches to _Checkout_, _Rename_ or _Delete_ 
            without having to go to the detail screen. When a local branch is ahead of its 
            remote, you can _Push_ as well.
            
    
    
    
            
    
     You create new branches from the current one with the upper-rightmost button.
                To put commits on a branch you can either _Merge_ or _Rebase_. Atlassian has a
                great [tutorial](https://www.atlassian.com/git/tutorials/merging-vs-rebasing/)
                describing the differences. In both situations you change your current branch to include commits from some
                other branch.
             
    
    
            
    
    
                Merge will create a merge-commit as needed, while rebase will rewrite commits from your
                current branch on top of the commits from the other branch. Working Copy will not rebase if this
                requires rewriting commits that have already been pushed to a server. You can override this behaviour
                by configuring the branch for _History Rewriting_, but this in turn requires you to _Force Push_.
                This also lets you [Undo](/manual/commit-undo) commits already pushed to a remote.
             
    
    
    
            
    
### 4.3 Branch Editing
    
    
            
    
    
                You _Reset_ the head of the current branch from the commit you want to
                become HEAD. This is a soft reset that leaves the working directory as before the reset which can be
                fixed with _Revert_ as needed. If you navigate the commit list through a non-current local branch 
                you are able to _Reset_ the head of this branch. In all cases you will be told what is about 
                to happen as you confirm the _Reset_.
            
    
    
            
            
    
    ![](/img/branch-editing.png)
    
    
    
            
    
    Each commit represents changes made to files and it can be useful to apply these changes
               differently to improve the commit history. Applying a singlecommit is called cherry picking 
               and applying the changes from a series of commits is called rebasing.
    
    
               
            
    
    Command line Git is able to 
            [rebase interactively](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History) 
               to change the order in which commits are applied, discard commits, edit commit messages and more.
               You can get equivalent results in Working Copy from the commit list of individual branches.
            
    
    
            
    
    Long tapping commits you can _Delete Commit_ to rewrite the branch without the work
               contributed by this single commit or _Edit Message_ to change a commit
               message while still applying the same changes from the commit.
    
    
            
    
    Drag one or several consecutive commits to change the order in which changes are 
               applied. When commits are rewritten in different order it might cause conflicts that
               you will be asked to resolve.
    
    
               
            
    
    Rewriting history can cause problems for others working on 
               the same branch and when commits are already pushed to the remote
               you will be asked to enable _history rewriting_.            
             
    
    
             
              
    
    
               _Undo_ history rewriting by shaking your iPhone, 
               using three-finger left swipe or pressing _⌘+Z_ on external keyboards.
             
    
    
    
            
    
    Branch Editing is a [Pro feature](/manual/purchase).
    
    
    
            
    
### 4.4 Pull Requests
    
    
            
    
    ![](/img/pull-request.png)
    
    
            
    
    
                Where _Merge_ and _Rebase_ incorporates changes from other branches into your current
                branch, a Pull Request or _PR_ works in the opposite direction asking others to incorporate
                changes from your current branch into some base branch. Working Copy supports creating these for
                [BitBucket](https://www.atlassian.com/git/tutorials/making-a-pull-request),
                [GitHub](https://help.github.com/en/articles/about-pull-requests) and
                [GitLab](https://docs.gitlab.com/ee/user/project/merge_requests/).
            
    
    
            
    
    You tap _PR_ from the full list of branches and pick the remote branch that should be the base of
                the Pull Request. It is the base branch that receives new commits from your current branch.
    
    
            
    
    In order to open Pull
               Requests between different repositories you need to have a remote configured corresponding to the
               repository with the base branch. When cloning from GitHub and GitLab the app tries to
               configure a _upstream_ remote when the cloned repository is a fork.
                Do a single _Fetch_ after enabling the upstream remote to include
               this repository in your branch list.
    
    
    
                
               
    
    Creating a Pull Request is the first step in a workflow that might involve code review, discussions or
                automated verification and ends up with the pull request being accepted or closed days or weeks later. 
    
    
    
                
    
    Manage the communication aspects of Pull Requests in your browser or with apps such as
                    [GitHub for Mobile](https://apps.apple.com/app/github/id1477376905?ls=1)
                    and handle the code in Working Copy.
                
    
    
    
                
    
    
                    Continue work on existing pull requests by invoking the share sheet on a link and picking _Process in Working Copy_.
                    Working Copy makes sure the repository is cloned, relevant remotes are configured and the branch is checked out.
                
    
    
                
    
    Long tap the repository to jump back to the Pull Request page on the hosting provider website.
    
    
            
                
    
            
    
    Pull Request creation is a [Pro feature](/manual/purchase).
    
    
    
            
            
    
### 4.5 Commit Graph
    
    
    
            
    
    ![](/img/commit-graph.png)
    
    
    
            
    
    To explore repository changes across branches use the Commit Graph available from the Repository screen.
    
    
            
    
    Commits are presented in chronological order with lines showing which commits are based on each other,
                with tags and branch heads displayed as well as the commit message summary, date and information about the
                author of the commit.
            
    
    
            
    
    Pinch to zoom will let you explore additional details, such as the full commit message, the full name of the author
                rather than initials, a commit identifier and the files modified by this commit. If you connect an external
            screen or projector to your device, you will get a full-screen Commit Graph without any interface elements
            obscuring the view. This makes for a convenient tool when your team needs to discuss the project.
    
    
            
    
    Tap and hold or double-tap elements of a commit for additional actions, where
                the commit message itself takes you to a detail view.
    
    
            
    
    You can copy the author email to the clipboard or start composing a email to the author.
    
    
            
    
    It is also possible to view the commit date in your calendar to see what else happened around this time and
                when [Fantastical](https://flexibits.com/fantastical-iphone) is installed,
                it will be used instead of the built-in Calendar app.
    
    
    
            
            
    
### 4.6 Resolving conflicts
    
    
            
    
    ![](/img/resolve-tool.png)
    
    
    
            
    
    Working Copy has a built-in Resolve tool that can be used to fix conflicts for the entire repository,
            a subdirectory or single files, depending on where in the directory hierarchy the tool is invoked.
            Swipe left on cells for repository, directories or files to get started.
    
    
    
            
    
    Text files are shown as chunks of text, where everything both files agree on start out in the center,
               and everything from _our_ version is to the left and
                _their_ version to the right.
               You swipe these chunks towards the center to include them and away to exclude them. This way your final
                file will be lined up at the center. Chunks at the border are pending your decision.
            
    
    
            
    
    If you want to use all chunks from one version of a file and discard the other version of the file entirely,
                you can tap one of the branch names
              at the header of the file. These are _HEAD_ and
                _other_ in the screenshot.
    
    
    
            
    
    There is no way to combine conflicted images and other binary files.
                You need to pick one or the other by tapping the one you want.
                The selected version is marked by a thick border.
    
    
    
            
    
    When all chunks have been either accepted or rejected and no binary files are awaiting your choice,
                tap _Resolve_ to verify your choice and mark files as resolved. Next commit
            will conclude the merge. If there are chunks or files pending your decision, the _Resolve_
            button will scroll to indicate this.
    
    
    
            
    
    You can also resolve conflicts by manually editing files. The Content tab for a conflicted file
            has a _Resolve_ button for marking the file as resolved, when you have picked the content
            you want and removed conflict markers.
    
    
    
            
    
 ### 4.7 Signed Commits
    
    
            
    
    Git supports
                [signing commits](https://git-scm.com/book/en/v2/Git-Tools-Signing-Your-Work#_signing_commits)
               to make it possible for others to verify that commits have been made by you. When signing you need
                a [GPG](https://gnupg.org) private key that must be kept secret and when
                verifying commits the corresponding public key is needed.
    
    
            
    
    
                You attach a private key to your Identity which can be imported or generated inside the app.
                If the key is generated inside Working Copy you can attach
                it to your GitHub account with a single tap or you can export the public or private parts of
                the key to do manual configuration.
            
    
    
                Your private key needs a passphrase. You can configure
                Working Copy to _Ask_ every time the passphrase is needed, to store the passphrase in the keychain
                requiring you to authenticate with _Touch ID_ before it is read or to just
                _Remember_ the passphrase in the keychain. 
    
    
    
            
    
    ![](/img/commit-signing.png)
    
    
    
            
    
    Signing commits makes it possible to verify that the commit is made by someone with access to
               the private key. This information is only useful when other people can trust the private key is yours
               and they need a PGP public key for this. GitHub makes this easy by letting you
                [associate](https://help.github.com/articles/adding-a-new-gpg-key-to-your-github-account/)
                a public key with your [user account](https://github.com/settings/keys),
                but commit verification is possible in other environments
                by [importing public keys](https://www.gnupg.org/gph/en/manual/x56.html#AEN83) into the GPG keyring.
            
    
    
    
            
    
  ### 4.8 Tagging
    
    
            
    
    Git has the ability to create a [tag](https://git-scm.com/book/en/v2/Git-Basics-Tagging) in a
                repository to reference a specific point in history. This is typically used to mark a release or
                other milestone on a project.
    
    
    
            
    
    Create tags by navigating to a specific commit and tapping _Tag_ along the top.
                To create a lightweight tag you enter a name and leave the message empty. Enter a message
                for a full annotated tag that includes author information, date and the message entered.
                Creating annotated tags is generally considered best practice. 
    
    
            
            
    
    
                Your tags will be send to the remote on next _Push_.
            
    
    
    
        
    
    ![](/img/stash-transparent.png)
    
    
            
    
### 4.9 Stashing changes
    
    
            
    
    Sometimes your repository has modified files that aren't
               ready for commit but prevent you from doing other work.
               Stashing makes your repository clean 
               until you bring the changes back by unstashing.
            
    
    
            
    
    You _Stash_ and _Unstash_ from the context menu 
               of repositories. 
    
    
                 
    
    Stashing is a pro feature available to users that purchased 
                     the unlock or upgraded their 
                     pro unlock on December 9, 2019 or later.
    
    
    
        
    
    
    
        
    
        
    
  ## 5. Extending iOS
    
    
        
    
    
            
    
    ![](/img/extending-ios.png)
    
    
    
            
    
    All repositories in Working Copy can be accessed by other applications using the document picker or
                file browser components.
                The other application is allowed to read and make changes to this file and these changes stay inside Working Copy.
                You can perform editing in this application and switch to
                Working Copy to review and commit changes.
                
    
    
            
    
    Initially you need to
                [enable](https://support.apple.com/en-au/HT206481#thirdparty)
                Working Copy as a Location in the Files app and on iPad you can
                use [Split View](https://help.apple.com/ipad/9/#/iPad63ea0cbb)
                to avoid switching between Working Copy and the editing application.
    
    
    
            
    
    [Textastic](https://itunes.apple.com/dk/app/textastic-code-editor-6/id1049254261?mt=8&at=1000lHq) is a
                very good general purpose/programmers editor that works well with Working Copy. Use _Open…_
                to open files and _Add External Folder…_ to open entire directories in-place. You can read more
                about this in the Textastic [documentation](https://www.textasticapp.com/v9/manual/integration_other_apps/git_client_working_copy.html).
    
    
            
    
    [iA Writer](https://ia.net/writer) is a markdown editor
                with great design and typography that can edit Working Copy files and directories in-place.
                Files are added at the _From Other Apps_ screen. Add entire
                directories by tapping _Edit_ and then _Add Location…_ from the
                [Library](https://ia.net/writer/support/ios/the-library) screen.
    
    
                
    
    [Ulysses](https://ulysses.app) is a focused and feature rich writing 
                    app where the library of files can be [kept inside](/ulysses.html) Working Copy for easy version control of 
                    your writing.
    
    
            
    
    [1Writer](https://itunes.apple.com/us/app/1writer/id680469088?ls=1&mt=8&at=1000lHq)
            is another good Markdown editor and you open files in Working Copy by tapping ![+](/img/1writer-plus.png)
            in the lower right corner. If you need to work with images
                [Pixelmator](https://itunes.apple.com/us/app/pixelmator/id924695435?mt=8&at=1000lHq)
                is a good choice.
    
    
    
            
            
    
### 5.1 Drag and Drop
    
    
            
    
    
                Drag and Drop makes it much easier to get files into or out of your repositories.
            
    
    
            
    

    
    
            
    
    Drag files from your emails, the Files app or any other supporting app to add to your repositories.
                When files already exist you can import as a new file or overwrite the existing one and when the existing file in your
                repository is already committed overwriting is automatic, saving you a little time, as it is very easy to Revert to
                get back old files.
    
    
            
    
    Directories can be dragged into repositories or to the repository list to import a new repository and zip
                archives can be decompressed as they are dragged.
    
    
           
    
    When dragging files out of Working Copy the result will depend on the target app. Dragging files into
               emails will attach them and dragging into the Files app will export to this location. Editing apps such as
			   
               [Textastic](https://itunes.apple.com/dk/app/textastic-code-editor-6/id1049254261?mt=8&at=1000lHq)
               that support this can receive a reference to files or directories letting them edit in-place such that changes are made
               inside the repository.
    
    
    
            
            
    
  ### 5.2 Saving to Working Copy
    
    
            
    
    ![](/img/edit-in-app-transparent-x.png)
    
    
            
    
    Saving files into Working Copy can be accomplished by way of a Share sheet,
                the mechanism also used to share files with Mail or Messages.
                Picking _Working Copy_ on a Share sheet will present a list of repositories,
                where you drill down to the
                directory where the file should be saved.
                To overwrite existing files you tap a file before confirming. Otherwise you will be prompted to
                enter a new file name.
    
    
    
            
    
    After saving a file you can optionally _Commit_ this change immediately and _Push_ to
                the remote right away.
    
    
    
            
    
    When saving zip-archives into Working Copy you can either import the archive as a new
            repository, extract to a existing repository overwriting existing files as needed,
            or you can save the zip-file as is.
    
    
    
            
    
   ### 5.3 Edit in App
    
    
    
            
    
    In some situations you browse files in Working Copy and need to pick out a file you want to edit in
            another application. The action-button in the upper-right corner used to present a share-sheet also
            lets you send files to other applications.
    
    
    
            
    
    _Open In …_ or _Copy to …_ is the most basic choice and lets you pick any app
                supporting that type of file. Editing will often be on a copy of the file and it must be transferred back
                to Working Copy with _Save in Working Copy_, but if the app you pick
                says _Open in_ as opposed to _Copy to_
                the application is able to edit the file in-place with no need to write back changes.
                In some situations the iOS share sheet does not know whether editing will be on a copy of the
                file or in-place until you have picked the action once. This has been known to happen with
                [Textastic](https://itunes.apple.com/dk/app/textastic-code-editor-6/id1049254261?mt=8&at=1000lHq)
                that might start out with the action _Copy to Textastic_ even though editing happens in-place.
            
    
    
            
    
    To edit with [Editorial](https://itunes.apple.com/app/editorial/id673907758?mt=8&at=1000lHq)
                you transfer a copy of the file into Editorial with a filename such that Working Copy can recognise the file later on.
                This requires a workflow inside Editorial to facilitate file transfer. It
                is installed the first time you use _Edit in Editorial_ or if you delete
                or rename the workflow. This workflow serves a dual purpose in that it receives files
                when activated from Working Copy, and returns files to Working Copy when activated from Editorial. 
    
    
        
    
    
            You will only see actions for apps you have already installed and you can change the order
            by picking _More_ to the far right.
        
    
    
        
    
    
    
        
        
    
    
            
    
    ### 5.4 External repositories
    
    
            
    
    Some apps do not support opening files or directories in-place. If they use
                _iCloud Drive_ or _On My Device_ to store documents, you can link 
                from the other app into Working Copy to manage documents using Git.
    
    
    
            
    
     When adding repositories you tap _Link external directory_ and pick a folder 
                in the Files app. This will appear as any other repository inside Working Copy and 
                as you edit, commit, push and pull the changes are made to the original linked 
                directory.
    
    
    
            
                                   
            
    
    Alternatively you can drag directories from the Files app into the repository
               list in Working Copy to create links. This is the only way to link to
               document packages likes Swift Playgrounds and Codea projects that are not treated as 
              folders by iOS.
            
    
    
             
    
    Working Copy needs folder-level access which can only work with Files app locations that support 
    		    picking folders such as _iCloud Drive_, _On My Device_ or 
    		    [Secure ShellFish](https://secureshellfish.app/).
    		    Unfortunately the major cloud storage solutions only support granting file-level 
    		    access.
    
    
    
    		
    
    A _.git_ folder is created if the directory you pick isn't a repository and kept 
    		   inside Working Copy to not confuse other apps. You can change the location of the _.git_ 
    		   directory from the repository configuration screen.
    
    
    		   
    		
    
    You can convert regular repositories inside Working Copy into external repos.
    		   Long tap the repository and pick _Share_ and tap _Link Repository to Folder_ or 
    		   _Link Repository to Document_ where the latter works for directory-like documents 
    		   such as Swift Playgrounds and Codea projects. 
    
    
    
            
    
    
            Linked external repositories is a pro feature available to users 
            that purchased or upgraded their pro unlock after September 2020.
            
    
    
                    
            
    
    This can be used with apps such as
                  [Codea](https://codea.io/),
                  [iA Writer](https://ia.net/writer),
                  [Obsidian](https://obsidian.md/),
                  [Scriptable](https://scriptable.app/),
                  [Swift Playgrounds](https://www.apple.com/swift/playgrounds/)
                  and other apps that store documents in _iCloud Drive_ or _On my Device_ 
                  but depending on the app in question they can be confused if the document files are 
                  changed while they are running.
    
    
            
        
    
    
    
        
        
    
    
            
    
    ### 5.5 Files synchronisation
    
    
    		This is a legacy feature and has been replaced by external repositories
    		that solves similar use-cases with more efficiency and flexibility.
    
            
    
            
    
    Configure Working Copy to open directories used by these other apps in-place.
               As you work in the other apps, your changes are synced back to Working Copy to be committed.
                When you pull down commits from a remote any changed files are written back to the directory
                in iCloud Drive or "On my Device" for the other apps to use.
            
    
    
    
            
    
    You configure a brand new repository for syncing by tapping
             _+_ from the repository list, _Setup synced directory_ and pick a directory.
                All files from this directory will be imported into a new repository ready to be committed.
                You can add a remote from the Repository status screen.
            
    
    
    
            
    
    For existing repositories use the _Setup Folder Sync_ action from the sharesheet of the
                repository itself or a sub-directory. Initial synchronisation will combine all files from both sides
                but later on the modification dates are used to determine what needs to be copied and what needs
                to be deleted. It is currently only possible to have a single directory synced with each
                repository in Working Copy but there are plans to loosen this restriction.
            
    
    
            
    
    When picking a directory for sync, iOS doesn't allow picking _document packages_,
               which are documents that are directories rather than files. Use _Setup Package Sync_ 
               to bypass this limitation.
    
    
    
            
    
    Sync status is shown with a icon above directory listings that you tap for a list of recent sync operations.
               You can restore files overwritten or deleted by tapping _Restore_ from this list.
                Backup files are kept for at least seven days.
    
    
    
            
    
    You can deactivate syncing from the list of sync operations.
    
    
    
            
    
    In some situations both sides of a file have been modified since the last sync and
                Working Copy will pick the side most recently changed. To draw your attention to
                this possible data-loss these sync entries have a warning icon and the sync icon shows a orange counter with
                the number of warnings since you last viewed the history. A red counter indicates the number
                of errors since you last displayed the sync history.
    
    
    
        
    
    
    
        
    
    
            
    
    ### 5.6 WebDAV access
    
    
            
    
    ![](/img/webdav-settings.png)
    
    
    
            
    
    In situations where you need to transfer entire directory hierarchies,
                a good way to get files into and out of Working Copy is the built-in
                [WebDAV](https://en.wikipedia.org/wiki/WebDAV) server.
            
    
    
            
    
    
                WebDav cababilities are built into the macOS
                [Finder](https://support.apple.com/kb/ph18514) and most versions
                of Windows also let you access WebDAV by mapping to a network drive. You will also be able to
                use third party WebDAV clients for [macOS](https://panic.com/transmit/),
                [Windows](https://cyberduck.io),
                Linux, [Android](https://play.google.com/store/apps/details?id=com.estrongs.android.pop&hl=en) & [iOS](https://panic.com/transmit-ios/).
            
    
    
            
    
    As a security precaution you need to start the server before each use and it automatically shuts down
                after 15 minutes of inactivity. You should be cautious of using the WebDAV server on untrusted
                networks as the transfers are unencrypted. In these cases you should restrict yourself
                to connections from applications on the same device, as the traffic cannot be intercepted when
                it never leaves your device. Local connections are also possible in situations without an Internet
                connection. You need to specify _localhost_ as the hostname in these situations.
    
    
            
    
    Applications on iOS are restricted as to how long they are allowed to run in the background. If you start
               the WebDAV server and switch to some other application, you will be given a grace period before
                Working Copy and its WebDAV server is terminated. A notification will inform you of this and you
                can _Restart_ right from the notification to extend this grace period.
            
    
    
           
    
    
            Enable _Server Persistence_ to keep track of your location while WebDAV is enabled
            and keep Working Copy running in the background.
    
    
        
    
    
        
    
    
            
    
    ### 5.7 Shortcuts and automation
    
    
            
    
    Working Copy supports automation through the Shortcuts app where files and other data can
                flow between actions. You locate these actions inside _Apps > Working Copy_.
    
    
    
            
    
    ![](/img/shortcuts.png)
    
    
    
            
    
    Use _Get Repository Files_ to get one or several files from a repository that
               can be passed to other actions. The _Path_ parameters can contain wildcards such as
               _docs/*.md_ and if it points to a directory all files inside are returned.
               You can configure the action to only include files with a particular status such as _modified_
                and combining this with _Path=/_ can be useful to get all files with this status.
            
    
    
            
    
    Files returned from _Get Repository Files_ can be changed in-place by the shortcut
               but only some actions work like that and often you need _Write Repository File_
                to put content back into repositories.
               This writes a single file at a time but you can use the built-in
                _Repeat with Each_ action to write several files. _Path_ controls the
                destination and can be a directory to write inside this directory,
                but the action refuses to overwrite existing files unless you enable this as one
                of the options shown when you tap _Show More_.
    
    
            
    
    Once you have changes use _Commit Repository_ to commit
              with some _Message_. No commit dialog is shown and the action looks at what
                has been staged for commit either through the _Write Repository File_ that stages
                written files by default, through the _Stage for Commit_ action or from using
                the Commit dialog elsewhere and cancelling that dialog. You can configure the commit to
                include all _modified_ files and not just the _staged_ ones.
              
    
    
            
    
    _Pull Repository_ fetches and merges any new commits from the remote and
               _Push Repository_ pushes back commits. It can often be useful to include
               these actions as the first and last in a shortcut to make sure work doesn't
                just stay on your device. Both actions can be configured to use a
               specific _Remote_ if you have several.
    
    
            
    
    Switch between branches with _Checkout Branch_ as long
                as there are no modified files and implement custom Git flows with _Create Branch_,
                _Merge Branch_ & _Delete Branch_.
    
    
            
    
    List the most recent commits using _Repository History_
               from any branch, current branch or a specific branch of your choice. Each commit
                contains the message, author, date, sha1 identifier and [link](https://github.com/golang/go/commit/bdf0fe54480034cd21e36cfed6e44f10f4cb5c92) to
                GitHub.com and other hosting provider websites when Working Copy can determine this.
    
    
            
    
    All previous actions work from the Shortcuts app without having to launch Working Copy, but it can be useful
               to be able to launch the app to show specific information. The _Open in Working Copy_ action
               can be used to show files, directories or the repository itself and to clone repositories as needed. 
    
    
    
        
    
    
        
    
    
            
    
    ### 5.8 Callback URLs
    
    
    
            
    
    Use [Siri Shortcuts](https://help.apple.com/iphone/12/#/iph7d118960c) and
              [x-callback-url](/url-schemes.html#x-callback-url)
               to speed up common operations and to automate your Git operations on iOS 12.
    
    
    
            
    
    The easiest way to automate something on iOS 12 is to do it manually first, as
                the latest actions performed will be shown as _Callback examples_ inside settings where parameters
                can be edited by tapping parameters.
                You can create Siri Shortcuts to trigger actions through voice commands or _Copy_
                and drag commands to apps supporting x-callback-url.
    
    
    
            
    
    ![](/img/callback-editing.png)
    
    
    
            
    
    Most Siri Actions can run in the background without Working Copy being shown, but the clipboard is the only
                way to get data into or out of Siri Shortcuts. Use x-callback-url for greater control
                over data and control flow  with apps such as
                [Shortcuts](https://itunes.apple.com/us/app/id915249334?mt=8),
                [Scriptable](https://itunes.apple.com/us/app/scriptable/id1405459188?ls=1&mt=8) or
                [Drafts](https://itunes.apple.com/dk/app/drafts-4-quickly-capture-notes/id905337691?mt=8&at=1000lHq).
                Note that supplied parameter values must be url-encoded.
            
    
    
            
    
    You will find additional information in the x-callback-url [documentation](/url-schemes.html#x-callback-url) and
                the ability to [chain](/url-schemes.html#chain) several commands into a single
                callback is especially useful.
            
    
    
            
    
    
                As a security measure x-callback-url needs to be enabled from the settings screen and is protected by a random key.
            
    
    
    
    
            
    
    ### 5.9 DraftCode
    
    
            
    
    
                [DraftCode](http://solesignal.com/draftcode/) is comprehensive
                editor and runtime for PHP, that lets you run entire websites on your iPad or iPhone.
                Everything happens on your device and works when offline.
    
    
             
    
    You can transfer a directory to DraftCode by picking _Copy_
                 from the share sheet of a repository or directory and then using the Files app navigate to
             _Locations > On My Device > DraftCode > filestore_
              where you tap-and-hold and pick _Paste_.
    
    
        
    
    
    
        
    
    
        
        
    
    ## 6. Beyond iOS
    
    
    
        
    
    
        
    
    Not every tool is available on iOS, and Working Copy lets you
           use remote computers to work on the files in your repositories.
           Git remotes can be
            [configured](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)
            to perform operations at _Push_ or you can use secure-shell to upload files to remote server
            and invoke commands.
        
    
    
        
    
    
    
        
    
    
            
    
    ### 6.1 Log files
    
    
            
    
    
                Working Copy will record log files as you clone, fetch from and push to repositories.
                This can be helpful when troubleshooting connection problems and if you are pushing to
                special remotes such as [Heroku](https://devcenter.heroku.com/articles/git)
                the log can contain information such as whether deployment was successful.
    
    
    
            
    
    ![](/img/log-file.png)
    
    
    
            
    
    When something interesting is logged during a remote transfer, a log thumbnail
                will appear in the lower right corner. You can drag this out of the
                screen to fully hide it or tap to open up the log.
    
    
    
            
    
    Access the list of previous logs using a button at the top of the repository list.
                To keep this list tidy, only recent log files will be kept, but you can mark
                a log file as favourite by tapping the star to avoid automatic cleanup.
    
    
    
            
    
    Log files can be linked to a repository inside Working Copy, such that filenames
                are turned into references. Regular URL's and email addresses are detected
                as well and tapping these will show a preview and let you act on them and
                while preview is shown, you will be able to
                [Handoff](https://support.apple.com/en-us/HT204681) the link
                to nearby Macs or iOS devices for browsing.
    
    
    
            
    
    Often the log files exist outside Working Copy in emails, on build-server
                status pages or as raw text in actual log files.
                To import logs into the app, use the _Process in Working Copy_
                action extension from the share sheet. It knows how to deal with build status pages from
                [App Center](https://appcenter.ms/),
                [BitRise](https://www.bitrise.io/),
                [Circle CI](https://circleci.com/) and
                [Jenkins](https://jenkins.io) but it can be used on raw text as well.
                Zip archives will be unzipped and imported as a single log-file
                with special markers to indicate filenames.
            
    
    
            
    
    The best way to capture logs from App Center builds is to tap _Download Logs_
               and use _Process in Working Copy_ on the zip archive.
            
    
    
    
            
    
    Your log files are entirely private and unless you explicitly export them
                they stay on your device.
    
    
    
            
        
    
    
    
        
    
    
            
    
    ### 6.2 SSH Upload
    
    
            
    
    
                It can be convenient to upload the files in your repository to a test server,
                and to keep server files in sync as you make changes on iOS. To do this you
                enable the _SSH Upload_ feature from the share sheet for a repository or directory.
    
    
    
            
    
    As implied by the name, files are transferred using secure shell, where you either
               authenticate using password or SSH keys. You pick a server, a _Remote_
               directory and a _Local_ directory where the entire repository is used if you
               do not specify a Local directory. You access a list of previously used servers
                with a button to the right of the _Server_ field which also contains computers
                [advertising](https://developer.apple.com/library/content/documentation/Cocoa/Conceptual/NetServices/Introduction.html)
                SSH services.
            
    
    
            
    
    ![](/img/ssh-upload.png)
    
    
    
            
    
    Tap _Upload_ to start, where the app will compare files and directories
               in the _Remote_ directory to those in the _Local_ directory uploading any files
               missing on the remote server or where the local file is different than the remote file.
             
    
    
             
    
    Once initial upload has completed, the local directory is watched for changes
                and these are transferred automatically until _Upload_ is stopped. This is especially
                 useful when working on Jekyll sites, Node.js services and other technologies that
                 can reload when files change.
             
    
    
             
    
    You can switch to other
                apps for editing files, but Working Copy is only allowed to keep running in the
                 background for a limited time. A notification will inform you when _Upload_
                 is stopped for this reason.
             
    
    
            
    
    Once _SSH Upload_ is configured for a repository, a new button is available
               in the upper right corner of the directory listing. This makes it easy to access
                configuration and the icon will show status, turning green when _Upload_
                is enabled and indicating when files are actively being transferred and if there are
                errors. If you clear all fields in the configuration, you can tap _Hide_
                to disable _SSH Upload_ entirely until you enable it
                again with the share sheet.
               
    
    
         
    
    
    
        
    
    
            
    
    ### 6.3 SSH Command
    
    
            
    
    Sometimes you need to apply a tool on your server to the files in your
                repository on iOS. You can run
                [make](https://www.gnu.org/software/make/)
                on a Makefile, have _pdflatex_ create a PDF file from
                LaTeX, use
                [xcodebuild](https://developer.apple.com/library/content/technotes/tn2339/_index.html)
                to build apps or almost anything else you can invoke on the command line.
            
    
    
            
    
     _SSH Command_ lets you configure commands for different file types that can be
               invoked on your server using secure shell. Output from the command is shown as a
                [log](/manual/logfiles) file,
                where mentions of files that exist in your repository are converted into links.
                Files on the server created or modified by running the command are
                downloaded back into your repository.
            
    
    
            
    
    You do this from the context menu of files and directories or 
                with _⌘ $_ or _⌘ ⇧ S_ as keyboard shortcuts. 
                Configuration is similar to
               [SSH Upload](/manual/ssh-upload) but you also 
               configure a _Command_ to run on the server.
               When you tap _Start_ a initial upload is performed, but while waiting for
                local changes the specified command is run on the remote server. When this command has
                completed upload syncing stops and any files created or modified will be
                downloaded into your _Local_ directory.
            
    
    
            
    
    Machine generated files are often not version controlled,
               and the easiest way to enforce this, is to add these to your _.gitignore_ file.
                Sliding left on files in the directory listing and picking _Ignore_ is the fastest
                way to achieve this. Note that files in _.gitignore_ are still downloaded and uploaded.
                It is only for version-control purposes they are ignored.
    
    
            
    
    ![](/img/ssh-command.png)
    
    
            
    
    Since Working Copy has no way of knowing which files are relevant, everything in your
               _Local_ directory is synced to the _Remote_ directory. If you run
               the same command many times using the same remote directory, there will often only
                be a few files that have changed and need to be uploaded. When configuring
                the command it can be helpful to create a subdirectory just for running this command,
                which can be done by tapping _+_ in the remote directory picker. 
    
    
    
            
    
    The app will remember previous commands and these are available from the
                button to the right of the _Command_
                field combining commands for the exact filename, the same file extension or
                the most recent commands for any file. The top choice for a given file is available as a
               action when sliding left on files in directory listings. 
    
    
    
            
    
    You need a Linux or BSD server accessible through secure shell to use this feature,
               but it doesn't have to be a expensive server. A small virtual private server (vps)
               will get you far and can be purchased for less than $5 per month. You can use your Mac
                as a server by enabling
                [Remote Login](https://support.apple.com/kb/PH25252?locale=en_GB).
            
    
    
            
    
    Even though you can run all sorts of commands, this feature is not a
                substitute for a standalone SSH client. When your operation has multiple steps or you
                are not 100% sure what option a command takes, a standalone interactive SSH client
                should be used. A good compromise for complicated commands is to use a interactive client
                to create shell scripts that you invoke with _SSH Command_.
                
                [Secure ShellFish](https://apps.apple.com/us/app/secure-shellfish/id1336634154?ls=1)
                is full SSH client by the developer of Working Copy and the editor
                [Textastic](https://itunes.apple.com/dk/app/textastic-code-editor-6/id1049254261?mt=8)
                contains an interactive SSH client.
            
    
    
            
    
    To exclude the files uploaded and downloaded put a _.sshignore_ file
                in the outermost directory of your repository. The format is similar to _.gitignore_
                in that each line is a glob pattern of files to exclude,
                where _*_ matches a number of filename characters and
                _**_ matches a number of characters including /. Matches are done against the entire path when /
                is part of the pattern and otherwise only the filename should match. Details of the pattern
                format is the same as for [.editorconfig](https://editorconfig.org/#file-format-details).
            
    
    
            
    
    
                Lines starting with _#_ are comments and
                you start lines with _^_ to make reverse rules overriding
                earlier but not later lines.
            
    
    
            
    
    
    # Ignore .bin files everywhere, but only .js files inside tmp & don't ignore Index.js
    *.bin
    /tmp/*.js
    ^Index.js
    
    
    
            
    
    If the server claims your regular commands do not exist
                the _$PATH_ variable is probably not what you expect. Try running
                _echo $PATH_ using SSH Command as a troubleshooting step.
                Working Copy identifies itself as a interactive login shell,
                but in reality it isn't interactive and if the server detects this your _.bashrc_ script
                might not run. Doing path configurations in _.profile_ or _.bash_profile_
                can fix this.
               
    
    
        
    
    
    
        
        
    
    ## 7. Help and Support
    
    
        
    
    
            
    
    A lot of work has gone into making Working Copy as trouble-free to use as possible,
                but despite that, problems will sometimes occur. Please send your
                questions by email to [anders@workingcopy.app](mailto:anders@workingcopy.app) and I will do my very best to assist.
    
    
    
            
    
    ### 7.1 File Backup
    
    
            
    
    Files stored in Git are often very safe, since repositories are stored in multiple
               locations some on local computers and some on remote servers. Files that have not yet
               been committed and pushed to a server are somewhat vulnerable to data loss.
    
    
            
    
     These files
                takes part in regular
                iOS backup to either iCloud or a local computer through iTunes. You access the files using
                [iTunes File Sharing](https://support.apple.com/en-us/HT201301)
                and since this uses a external computer, you can recover your files in situations
                where Working Copy itself has problems running. Your files will be in a directory
                called _changes_.
            
    
    
            
    
    When you restore a iPad or iPhone from backup you can reclone some or all your old repositories
                by going to "Previous repositories" in settings. When cloning completes any changed and not yet pushed
                files are moved into the repository for you to either commit or discard.
                Previous repositories without a remote cannot be cloned but are listed to let you export the backed up files.
            
    
    
    
        
    
    
    
        
    
    
            
    
    ### 7.2 How to purchase
    
    
            
    
    ![](/img/unlock-transparent.png)
    
    
            
    
    Working Copy is a free download but you need to pay to unlock pro features:
          
    
    
            
      1. [Push](/manual/push-feature) to remote
    
            
      2. Override system color scheme
    
            
      3. SSH [Upload](/manual/ssh-upload)
    
            
      4. SSH [Command](/manual/ssh-command)
            
            
      5. Font [customization](/manual/font-customisation)
    
            
      6. External Preview
    
            
      7. Repository Folders
    
            
      8. [Pull Request](/manual/pull-requests) creation
    
            
      9. [Rebase](/manual/rebase-pull) from remotes
    
            
      10. [Stash](/manual/stashing) changes
    
            
      11. Unlimited repositories
    
            
      12. Editing [Branch](/manual/branch-editing) history
    
            
      13. [Linked external](/manual/external-repos) repositories
    
          
                This unlock is a one-time purchase remembered by
                Apple such that you can restore the unlock on other devices using the same Apple ID.
            
            
    
    The features you unlock are permanently available and any other pro features
                added the next 12 months after purchase are also permanently available.
                After one year new pro features introduced will be locked until you purchase
                a upgrade. Even if you do not purchase a new unlock after 12 months, the app will
                still be updated with improvements and bug-fixes.
            
    
    
            
    
    Students have access to all features for free through 
                the [GitHub Education Pack](/education/).
    
    
        
    
    
    
    
    
    


___

#article 
