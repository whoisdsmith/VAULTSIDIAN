---
tags:: notes
created: 2022-07-16T21:00:29 (UTC -04:00)
tags: []
source: https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html
author: 
---

# Using the occ Command :: ownCloud Documentation

> ## Excerpt
> Using the occ Command

---
# Using the occ Command

ownCloud’s `occ` command (ownCloud console) is ownCloud’s command-line interface. You can perform many common server operations with `occ`, such as installing and upgrading ownCloud, managing users and groups, encryption, passwords, app settings, and more.

Table of Contents

-   [Running occ](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#running-occ)
    -   [Check if occ Is Set to Executable](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#check-if-occ-is-set-to-executable)
    -   [As Your HTTP User](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#as-your-http-user)
    -   [occ Command Structure](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#occ-command-structure)
    -   [With a Docker Container](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#with-a-docker-container)
    -   [With the ownCloud Appliance](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#with-the-owncloud-appliance)
    -   [Example Commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-commands)
-   [Core Commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#core-commands)
    -   [App Commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#app-commands)
    -   [Background Jobs Selector](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#background-jobs-selector)
    -   [Config Commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#config-commands)
    -   [Config Reports](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#config-reports)
    -   [Command Line Installation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-line-installation)
    -   [Command Line Upgrade](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-line-upgrade)
    -   [DAV Commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#dav-commands)
    -   [Database Commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#database-commands)
    -   [Encryption](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#encryption)
    -   [Federation Sync](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#federation-sync)
    -   [File Operations](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#file-operations)
    -   [Files External](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files-external)
    -   [Group Commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#group-commands)
    -   [Integrity Check](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#integrity-check)
    -   [l10n, Create Javascript Translation Files for Apps](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#l10n-create-javascript-translation-files-for-apps)
    -   [Logging Commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#logging-commands)
    -   [Managing Background Jobs](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#managing-background-jobs)
    -   [Maintenance Commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands)
    -   [Migration Steps Command](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#migration-steps-command)
    -   [Mimetype Update Commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#mimetype-update-commands)
    -   [Notifications](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#notifications)
    -   [Poll Incoming Federated Shares For Updates](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#poll-incoming-federated-shares-for-updates)
    -   [Security](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#security)
    -   [Sharing](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#sharing)
    -   [Trashbin](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#trashbin)
    -   [Two-Factor Authentication](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#two-factor-authentication)
    -   [User Commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#user-commands)
    -   [Versions](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#versions)
-   [Apps Commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#apps-commands)
    -   [Activity](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#activity)
    -   [Anti-Virus](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#anti-virus)
    -   [Auditing](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#auditing)
    -   [Brute Force Protection](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#brute-force-protection)
    -   [Calendar](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#calendar)
    -   [Contacts](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#contacts)
    -   [Custom Groups](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#custom-groups)
    -   [Data Exporter](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#data-exporter)
    -   [File Lifecycle Management](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#file-lifecycle-management)
    -   [Full Text Search](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#full-text-search)
    -   [LDAP Integration](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#ldap-integration)
    -   [Market](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#market)
    -   [Metrics](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#metrics)
    -   [Password Policy](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#password-policy)
    -   [Ransomware Protection (Enterprise Edition only)](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#ransomware-protection-enterprise-edition-only)
    -   [Collabora Online / Secure View](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#collabora-online-secure-view)
    -   [OAuth2](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#oauth2)
    -   [S3 Primary Objectstore](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#s3-primary-objectstore)
    -   [SAML/SSO Shibboleth Integration (Enterprise Edition only)](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#samlsso-shibboleth-integration-enterprise-edition-only)
    -   [Two-Factor TOTP](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#two-factor-totp)
    -   [Windows Network Drive (WND)](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#windows-network-drive-wnd)

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#running-occ)Running occ

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#check-if-occ-is-set-to-executable)Check if occ Is Set to Executable

Note that this step is not necessary when using a docker installation.

To check if the `occ` command is set to executable, change to your ownCloud directory first, then enter the command:

```bash
ls -lhF occ
```

This should give an output similar to this:

```plaintext
-rwxr-x--x 1 root www-data 283 May 18 17:44 occ*
```

In case it does not, set the occ command to executable with:

```bash
sudo chmod +x occ
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#as-your-http-user)As Your HTTP User

On a regular ownCloud installation, `occ` is in the `owncloud/` directory, this is on Ubuntu Linux for example `/var/www/owncloud` . `occ` itself is a PHP script.

**You must run it as your HTTP user** to ensure that the correct permissions are maintained on your ownCloud files and directories. The default HTTP user is different on the various Linux distributions.

-   The HTTP user and group in Debian/Ubuntu is `www-data`.
    
-   The HTTP user and group in Fedora/CentOS is `apache`.
    
-   The HTTP user and group in Arch Linux is `http`.
    
-   The HTTP user in openSUSE is `wwwrun`, and the HTTP group is `www`.
    

<table><tbody><tr><td class="icon"><i class="fa icon-tip" title="Tip"></i></td><td class="content"><div class="paragraph"><p>Use the following command to find your HTTP user:</p></div><div class="listingblock"><div class="content"><pre class="highlightjs highlight"><code class="language-bash hljs" data-lang="bash">ps -ef | egrep <span class="hljs-string">'(apache|apache2)'</span> | <span class="hljs-built_in">grep</span> -v `<span class="hljs-built_in">whoami</span>` | <span class="hljs-built_in">grep</span> -v root | <span class="hljs-built_in">head</span> -n1 | awk <span class="hljs-string">'{print $1}'</span></code><div class="source-toolbox"><span class="source-lang">bash</span><button class="copy-button" title="Copy to clipboard"><img src="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../../../../assets/img/octicons-16.svg#view-clippy" alt="copy icon" class="copy-icon"><span class="copy-toast">Copied!</span></button></div></pre></div></div></td></tr></tbody></table>

If your HTTP server is configured to use a different PHP version than the default (/usr/bin/php), `occ` should be run with the same version.  
For example, in CentOS with SCL-PHP74 installed, the command looks like this:

```bash
sudo -u apache /opt/rh/php74/root/usr/bin/php /var/www/html/owncloud/occ
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#occ-command-structure)occ Command Structure

The `occ` command has _options_, _commands_, and _arguments_.

1.  Options are optional.
    
2.  Commands are required.
    
3.  Arguments can be required _or_ optional.
    

The generic syntax is:

```bash
occ [options] command [arguments]
```

Example command running occ in Ubuntu

```bash
sudo -u www-data /var/www/owncloud/occ
```

If your web server is configured to use a different PHP version than the default (/usr/bin/php), the `occ` command should be run with the same version.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#with-a-docker-container)With a Docker Container

If your ownCloud instance is set up in a docker container, you need a user in the group `docker` to perform `occ` commands. An example command looks like this:

```docker
docker exec --user www-data <owncloud-container-name> occ <your-command>
```

For more information on docker, refer to section [Installing with Docker](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../installation/docker/index.html).

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#with-the-owncloud-appliance)With the ownCloud Appliance

The ownCloud Appliance offers two possibilities to perform `occ` commands:

1.  Log in to the ownCloud instance as root user with the command `univention-app shell owncloud`. Then use `occ` commands without a preceding `sudo -u www-data`.
    
2.  Alternatively, you can use `occ` on the host system with the command `univention-app shell owncloud occ` followed by the desired options, commands and arguments.
    

If you want to find out more about the Appliance, click [here](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../appliance/index.html).

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-commands)Example Commands

Running `occ` with no options lists all commands and options, like this example on Ubuntu:

```bash
sudo -u www-data occ
ownCloud version 10.8.0

Usage:
 command [options] [arguments]

==== Options
 -h, --help            Display this help message
 -q, --quiet           Do not output any message
 -V, --version         Display this application version
     --ansi            Force ANSI output
     --no-ansi         Disable ANSI output
 -n, --no-interaction  Do not ask any interactive question
     --no-warnings     Skip global warnings, show command output only
 -v|vv|vvv, --verbose  Increase the verbosity of messages: 1 for normal output,
                       2 for more verbose output and 3 for debug

Available commands:
 check                 Check dependencies of the server environment
 help                  Displays help for a command
 list                  Lists commands
 status                Show some status information
 upgrade               Run upgrade routines after installation of
                       a new release. The release has to be installed before
```

This is the same as `sudo -u www-data occ list`. Run it with the `-h` option for syntax help:

```bash
sudo -u www-data occ -h
```

Display your ownCloud version:

```bash
sudo -u www-data occ -V
  ownCloud version 10.8.0
```

Query your ownCloud server status:

```bash
sudo -u www-data occ status
  - installed: true
  - version: 10.8.0.4
  - versionstring: 10.8.0
  - edition: Community
```

The `status` command from above has an option to define the output format.

The default is plain text, but it can also be `json`:

```bash
sudo -u www-data occ status --output=json
{"installed":true,"version":"10.8.0.4","versionstring":"10.8.0","edition":""}
```

or `json_pretty`:

```bash
sudo -u www-data occ status --output=json_pretty
{
   "installed": true,
   "version": "10.8.0.4",
   "versionstring": "10.8.0",
   "edition": "Community"
}
```

This output option is available on all list and list-like commands, which include `status`, `check`, `app:list`, `config:list`, `encryption:status` and `encryption:list-modules`.

Get detailed information on individual commands with the `help` command, like in this example for the `maintenance:mode` command:

```bash
sudo -u www-data occ help maintenance:mode --help
Usage:
 maintenance:mode [options]

Options
     --on              Enable maintenance mode
     --off             Disable maintenance mode
     --output[=OUTPUT] Output format (plain, json or json_pretty, default is plain) [default: "plain"]
 -h, --help            Display this help message
 -q, --quiet           Do not output any message
 -V, --version         Display this application version
     --ansi            Force ANSI output
     --no-ansi         Disable ANSI output
 -n, --no-interaction  Do not ask any interactive question
     --no-warnings     Skip global warnings, show command output only
 -v|vv|vvv, --verbose  Increase the verbosity of messages: 1 for normal output,
                       2 for more verbose output and 3 for debug
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#core-commands)Core Commands

This command reference covers the ownCloud core commands, which are always available.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#app-commands)App Commands

The `app` commands list, enable, and disable apps.

```plaintext
app
 app:check-code   check code to be compliant
 app:disable      disable an app
 app:enable       enable an app
 app:getpath      Get an absolute path to the app directory
 app:list         List all available apps
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#list-available-apps)List Available Apps

List all of your installed apps or optionally provide a search pattern to restrict the list of apps to those whose name matches the given regular expression. The output shows whether they are enabled or disabled.

```bash
sudo -u www-data occ app:list [--] [<search-pattern>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>search-pattern</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Show only those apps whose names match the given search pattern (regular expression).</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--enabled</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Only display enabled apps. When used, the output will contain the app’s version number as well</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--disabled</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Only display disabled apps. If the app was previously enabled, the app version is also displayed. When used, the output will contain the app’s version number as well, <em>if</em> it was previously enabled</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--shipped=&lt;SHIPPED&gt;</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">If <code>SHIPPED</code> is set to <code>true</code>, only shipped apps will be listed. If <code>SHIPPED</code> is set to <code>false</code>, only non-shipped apps will be listed</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-m</code><br><code>--minimal</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Minimal view - only display apps with version When used, the output will contain the app’s version number as well.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">--output[=OUTPUT]</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<code>plain</code>, <code>json</code> or <code>json_pretty</code>). [default: "plain"]</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#enable-an-app)Enable an App

Enable an app, for example the Market app.

```bash
sudo -u www-data occ app:enable market
market enabled
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#disable-an-app)Disable an App

```bash
sudo -u www-data occ app:disable market
market disabled
```

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">Be aware that the following apps cannot be disabled: <em>DAV</em>, <em>FederatedFileSharing</em>, <em>Files</em> and <em>Files_External</em>.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#check-app-code)Check App Code

`app:check-code` has multiple checks:

-   It checks if an app uses ownCloud’s public API (`OCP`) or private API (`OC_`),
    
-   It also checks for deprecated methods and the validity of the `info.xml` file.
    

By default all checks are enabled. The Activity app is an example of a correctly-formatted app.

```bash
sudo -u www-data occ app:check-code notifications
App is compliant - awesome job!
```

If your app has issues, you’ll see output like this.

```bash
sudo -u www-data occ app:check-code foo_app
Analysing /var/www/owncloud/apps/files/foo_app.php
4 errors
   line   45: OCP\Response - Static method of deprecated class must not be called
   line   46: OCP\Response - Static method of deprecated class must not be called
   line   47: OCP\Response - Static method of deprecated class must not be called
   line   49: OC_Util - Static method of private class must not be called
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#get-the-app-installation-path)Get the App Installation Path

You can get the full file path to an app.

```bash
sudo -u www-data occ app:getpath notifications
/var/www/owncloud/apps/notifications
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#background-jobs-selector)Background Jobs Selector

Use the `background` command to select which scheduler you want to use for controlling [background jobs](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.htmlbackground_jobs_configuration.html). This is the same as using the **Cron** section on your ownCloud Admin page.

```plaintext
background
 background:ajax       Use ajax to run background jobs
 background:cron       Use cron to run background jobs
 background:webcron    Use webcron to run background jobs
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples)Examples

```bash
# Set the background scheduler to Ajax
sudo -u www-data occ background:ajax

# Set the background scheduler to Cron
sudo -u www-data occ background:cron

# Set the background scheduler to Webcron
sudo -u www-data occ background:webcron
```

<table><tbody><tr><td class="icon"><i class="fa icon-tip" title="Tip"></i></td><td class="content">See <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.htmlbackground_jobs_configuration.html" class="page">background jobs configuration</a> to learn more.</td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#config-commands)Config Commands

The `config` commands are used to configure the ownCloud server.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content"><div class="ulist"><ul><li><p>In general, key names are not checked for validity, they are used as written.</p></li><li><p>Whenever you use the <strong>app</strong> parameter, a config is read or written from or to the database.</p></li><li><p>Whenever you use the <strong>system</strong> parameter, a config is read or written from or to the config.php file.</p></li></ul></div></td></tr></tbody></table>

```
config
 config:app:delete      Delete an app config value
 config:app:get         Get an app config value
 config:app:set         Set an app config value
 config:import          Import a list of configuration settings
 config:list            List all configuration settings
 config:system:delete   Delete a system config value
 config:system:get      Get a system config value
 config:system:set      Set a system config value
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#configapp-references)config:app References

The following apps, core functions or documents use/refer to `config:app` settings:

Standard

-   [Configuring Federation Sharing](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../files/federated_cloud_sharing_configuration.html)
    
-   [Custom Groups](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../user/user_management.html#enabling-custom-groups)
    
-   [File Sharing](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../files/file_sharing_configuration.html)
    
-   [The HSM (Hardware Security Module) Daemon (hsmdaemon)](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.htmlsecurity/hsmdaemon/index.html)
    
-   [Legal Settings Configuration](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.htmllegal_settings_configuration.html)
    
-   [LDAP Integration](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../user/user_auth_ldap.html)
    
-   [Manual File Locking](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../files/manual_file_locking.html)
    
-   [Manually Move a Data Directory](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../maintenance/manually-moving-data-folders.html)
    
-   [Virus Scanner Support](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.htmlvirus-scanner-support.html)
    
-   [OpenID Connect (OIDC)](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../user/oidc/oidc.html)
    
-   [UI Configuration](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.htmlui-configuration.html)
    

Enterprise

-   [Shibboleth Integration](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../enterprise/user_management/user_auth_shibboleth.html)
    
-   [Auditing](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../enterprise/logging/admin_audit.html)
    
-   [File Lifecycle Management](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../enterprise/file_management/files_lifecycle.html)
    

occ Commands

-   [occ Anti-Virus](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#anti-virus)
    
-   [occ Auditing](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#auditing)
    
-   [occ Brute Force Protection](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#brute-force-protection)
    
-   [occ Custom Groups](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#custom-groups)
    
-   [occ Collabora Online / Secure View](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#collabora-online-secure-view)
    
-   [occ Encryption](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#encryption)
    
-   [occ File Lifecycle Management](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#file-lifecycle-management)
    
-   [occ Full Text Search](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#full-text-search)
    
-   [occ LDAP Integration](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#ldap-integration)
    

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#configsystem-references)config:system References

The following apps, core functions or documents use/refer to `config:system` settings:

Standard

-   [Quick Install on Ubuntu 20.04](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../installation/quick_guides/ubuntu_20_04.html)
    
-   [Quick Install on Ubuntu 22.04](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../installation/quick_guides/ubuntu_22_04.html)
    

occ Commands

-   [occ Metrics](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#metrics)
    

Enterprise

-   [Metrics](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../enterprise/reporting/metrics.html)
    

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#config-app-commands)Config App Commands

These commands manage the configurations of apps. Keys and values are stored in the database.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#configappdelete)config:app:delete

```bash
sudo -u www-data occ config:app:delete [options] [--] <app> <name>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-2)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>app</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the app.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>name</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the config to delete.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-2)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--error-if-not-exists</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Checks whether the config exists before deleting it.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<code>plain</code>, <code>json</code> or <code>json_pretty</code>, default is <code>plain</code>).</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples-2)Examples:

```bash
sudo -u www-data occ config:app:delete myappname provisioning_api
Config value provisioning_api of app myappname deleted
```

The delete command will by default not complain if the configuration was not set before. If you want to be notified in that case, set the `--error-if-not-exists` flag.

```bash
sudo -u www-data occ config:app:delete doesnotexist --error-if-not-exists
Config provisioning_api of app appname could not be deleted because it did not exist
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#configappget)config:app:get

```bash
sudo -u www-data occ config:app:get [options] [--] <app> <name>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-3)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>app</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the app.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>name</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the config to get.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-3)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 32.0388%;"> <col style="width: 67.9612%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--default-value[=DEFAULT-VALUE]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">If no default value is set and the config does not exist, the command will exit with 1.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<code>plain</code>, <code>json</code> or <code>json_pretty</code>, default is <code>plain</code>).</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples-3)Examples

```bash
sudo -u www-data occ config:app:get activity installed_version
2.2.1
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#configappset)config:app:set

```bash
sudo -u www-data occ config:app:set [options] [--] <app> <name>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-4)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>app</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the app. Must not be an empty string.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>name</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the config to set. Must not be an empty string.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-4)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--value=[VALUE]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The new value of the config.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--update-only</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Only updates the value. If it is not set before, it is not being added.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<code>plain</code>, <code>json</code> or <code>json_pretty</code>, default is <code>plain</code>).</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples-4)Examples

```bash
sudo -u www-data occ config:app:set \
   files_sharing \
   incoming_server2server_share_enabled \
   --value=true \
   --type=boolean
Config value incoming_server2server_share_enabled for app files_sharing set to yes
```

The `config:app:set` command creates the value, if it does not already exist. To update an existing value, set `--update-only`:

```bash
sudo -u www-data occ config:app:set \
   doesnotexist \
   --value=true \
   --type=boolean \
   --update-only
Value not updated, as it has not been set before.
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#general-config-commands)General Config Commands

These commands manage listing and importing configurations.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#configimport)config:import

The exported content can also be imported again to allow the fast setup of similar instances. The import command will only add or update values. Values that exist in the current configuration, but not in the one that is being imported are left untouched.

```bash
sudo -u www-data occ config:import filename.json
```

It is also possible to import remote files, by piping the input:

```bash
sudo -u www-data occ config:import < local-backup.json
```

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">While it is possible to update/set/delete the versions and installation statuses of apps and ownCloud itself, it is <strong>not</strong> recommended to do this directly. Use the <code>occ app:enable</code>, <code>occ app:disable</code> and <code>occ update</code> commands instead.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#configlist)config:list

The `config:list` command lists all configuration values for your ownCloud setup as well as for any apps.

```bash
sudo -u www-data occ config:list [options] [--] [<app>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-5)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>app</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the app. You can use "<em>system</em>" to get the config.php values, or "<em>all</em>" (the default) for all apps and system.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-5)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--private</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Use this option when you want to include sensitive configs, like passwords and salts.</p></td></tr></tbody></table>

By default, passwords and other sensitive data are omitted from the report so that the output can be posted publicly (e.g., as part of a bug report). You can see a sample output in the example below.

```json
{
    "system": {
        "passwordsalt": "***REMOVED SENSITIVE VALUE***",
        "secret": "***REMOVED SENSITIVE VALUE***",
        "trusted_domains": [
            "localhost",
        ],
        "datadirectory": "\/var\/www\/localhost\/data",
        "overwrite.cli.url": "http:\/\/localhost",
        "dbtype": "mysql",
        "version": "10.3.0.4",
        "dbname": "owncloud",
        "dbhost": "localhost",
        "dbtableprefix": "oc_",
        "dbuser": "***REMOVED SENSITIVE VALUE***",
        "dbpassword": "***REMOVED SENSITIVE VALUE***",
        "logtimezone": "UTC",
        "shareapi_allow_public_notification": "yes",
        "apps_paths": [
            {
                "path": "\/var\/www\/localhost\/apps",
                "url": "\/apps",
                "writable": false
            },
            {
                "path": "\/var\/www\/localhost\/apps-external",
                "url": "\/apps-external",
                "writable": true
            }
        ],
        "installed": true,
        "instanceid": "ocfp00rezy80",
        "loglevel": 2,
        "maintenance": false
    },
    "apps": {
        "backgroundjob": {
            "lastjob": "13"
        },
        "comments": {
            "enabled": "yes",
            "installed_version": "0.3.0",
            "types": "logging,dav"
        },
        "core": {
            "backgroundjobs_mode": "cron",
            "enable_external_storage": "yes",
            "first_install_version": "10.3.0.2",
            "installedat": "1569845065.1792",
            "lastcron": "1571930489",
            "lastupdateResult": "[]",
            "lastupdatedat": "1572536814",
            "oc.integritycheck.checker": "{\"systemtags\":{\"EXCEPTION\":{\"class\":\"OC\\\\IntegrityCheck\\\\Exceptions\\\\MissingSignatureException\",\"message\":\"Signature data not found.\"}},\"comments\":{\"EXCEPTION\":{\"class\":\"OC\\\\IntegrityCheck\\\\Exceptions\\\\MissingSignatureException\",\"message\":\"Signature data not found.\"}}}",
            "public_files": "files_sharing\/public.php",
            "public_webdav": "dav\/appinfo\/v1\/publicwebdav.php",
            "shareapi_allow_mail_notification": "yes",
            "umgmt_set_password": "false",
            "umgmt_show_backend": "true",
            "umgmt_show_email": "true",
            "umgmt_show_is_enabled": "true",
            "umgmt_show_last_login": "true",
            "umgmt_show_password": "false",
            "umgmt_show_quota": "true",
            "umgmt_show_storage_location": "false",
            "vendor": "owncloud"
        },
        "dav": {
            "enabled": "yes",
            "installed_version": "0.5.0",
            "types": "filesystem"
        },
        "federatedfilesharing": {
            "enabled": "yes",
            "installed_version": "0.5.0",
            "types": "filesystem"
        },
        "federation": {
            "enabled": "yes",
            "installed_version": "0.1.0",
            "types": "authentication"
        },
        "files": {
            "cronjob_scan_files": "500",
            "enabled": "yes",
            "installed_version": "1.5.2",
            "types": "filesystem"
        },
        "files_external": {
            "allow_user_mounting": "yes",
            "enabled": "yes",
            "installed_version": "0.7.1",
            "types": "filesystem",
            "user_mounting_backends": "googledrive,owncloud,sftp,smb,dav,\\OC\\Files\\Storage\\SFTP_Key,\\OC\\Files\\Storage\\SMB_OC"
        },
        "files_sharing": {
            "enabled": "yes",
            "installed_version": "0.12.0",
            "types": "filesystem"
        },
        "files_trashbin": {
            "enabled": "yes",
            "installed_version": "0.9.1",
            "types": "filesystem"
        },
        "files_versions": {
            "enabled": "yes",
            "installed_version": "1.3.0",
            "types": "filesystem"
        },
        "provisioning_api": {
            "enabled": "yes",
            "installed_version": "0.5.0",
            "types": "prevent_group_restriction"
        },
        "systemtags": {
            "enabled": "yes",
            "installed_version": "0.3.0",
            "types": "logging"
        },
        "updatenotification": {
            "enabled": "yes",
            "installed_version": "0.2.1",
            "types": ""
        }
    }
}
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#displaying-sensitive-information)Displaying Sensitive Information

To generate a full report which includes sensitive values, such as passwords and salts, use the `--private` option, as in the following example.

```bash
sudo -u www-data occ config:list --private
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#filtering-information-reported)Filtering Information Reported

The output can be filtered to just the core information, core and apps, or one specific app. In the example below, you can see how to filter for each of these categories.

```bash
# List only system configuration details
sudo -u www-data occ config:list -- system

# List system and app configuration details
# This is the default, so doesn't need to be explicitly specified
sudo -u www-data occ config:list -- all

# List configuration details of the dav app
sudo -u www-data occ config:list -- dav
```

Below is an example of listing the config details for a single app.

```json
{
    "apps": {
        "files_versions": {
            "enabled": "yes",
            "installed_version": "1.3.0",
            "types": "filesystem"
        }
    }
}
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#config-system-commands)Config System Commands

These commands manage system configurations.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#configsystemdelete)config:system:delete

```bash
sudo -u www-data occ config:system:delete [options] [--] <name> (<name>)...
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-6)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>name</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the config to delete, specify multiple for array parameter.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-6)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--error-if-not-exists</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Checks whether the config exists before deleting it.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<code>plain</code>, <code>json</code> or <code>json_pretty</code>, default is <code>plain</code>).</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples-5)Examples:

```bash
sudo -u www-data occ config:system:delete maintenance:mode
System config value maintenance:mode deleted
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#configsystemget)config:system:get

```bash
sudo -u www-data occ config:system:get [options] [--] <name> (<name>)...
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-7)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>name</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the config to get. Specify multiple for array parameter.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-7)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 32.0388%;"> <col style="width: 67.9612%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--default-value[=DEFAULT-VALUE]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">If no default value is set and the config does not exist, the command will exit with 1.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<code>plain</code>, <code>json</code> or <code>json_pretty</code>, default is <code>plain</code>).</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples-6)Examples:

```bash
sudo -u www-data occ config:system:get version
10.7.0.4
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#configsystemset)config:system:set

```bash
sudo -u www-data occ config:system:set [options] [--] <name> (<name>)...
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-8)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>name</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the config parameter, specify multiple for array parameter. Must not be an empty string.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-8)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--type=[TYPE]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Value type to use (<code>string</code>, <code>integer</code>, <code>double</code>, <code>boolean</code>, <code>json</code>, default is <code>string</code>).<br>Note: you must use json to write multi array values.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--value=[VALUE]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The new value of the config.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--update-only</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Only updates the value. If it is not set before, it is not being added.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<code>plain</code>, <code>json</code> or <code>json_pretty</code>, default is <code>plain</code>).</p></td></tr></tbody></table>

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">In order to write a boolean, float, JSON, or integer value to the configuration file, you need to specify the type of your command. This applies only to the <code>config:system:set</code> command. See table above for available types.</td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples-7)Examples

Disable the maintenance mode:

```bash
sudo -u www-data occ config:system:set maintenance \
   --value=false \
   --type=boolean

ownCloud is in maintenance mode - no app have been loaded
System config value maintenance set to boolean false
```

Create the `app_paths` config setting (using a JSON payload because of multi array values):

```bash
sudo -u www-data occ config:system:set apps_paths \
      --type=json \
      --value='[
        {
            "path":"/var/www/owncloud/apps",
            "url":"/apps",
            "writable": false
        },
        {
            "path":"/var/www/owncloud/apps-external",
            "url":"/apps-external",
            "writable": true
        }
    ]'
```

Adding Redis to the configuration:

```bash
sudo -u www-data occ config:system:set \
   redis \
   --value '{"host": "127.0.0.1", "port": "6379"}' \
   --type json

System config value redis set to json {"host": "127.0.0.1", "port": "6379"}
```

Some configurations (e.g., the trusted domain setting) are an array of data. The array starts counting with 0. In order to set (and also get) the value of one key, you can specify multiple `config` names separated by spaces:

```bash
sudo -u www-data occ config:system:get trusted_domains
localhost
owncloud.local
sample.tld
```

To replace `sample.tld` with `example.com` trusted\_domains ⇒ 2 needs to be set:

```bash
sudo -u www-data occ config:system:set trusted_domains 2 --value=example.com
System config value trusted_domains => 2 set to string example.com

sudo -u www-data occ config:system:get trusted_domains
localhost
owncloud.local
example.com
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#config-reports)Config Reports

If you’re working with ownCloud support and need to send them a configuration summary, you can generate it using the `configreport:generate` command. This command generates the same JSON-based report as the Admin Config Report, which you can access under `admin → Settings → Admin → General → Generate Config Report → Download ownCloud config report`.

From the command-line in the root directory of your ownCloud installation, run it as your webserver user as follows, (assuming your webserver user is `www-data`):

```bash
sudo -u www-data occ configreport:generate
```

This will generate the report and send it to `STDOUT`. You can optionally pipe the output to a file and then attach it to an email to ownCloud support, by running the following command:

```bash
sudo -u www-data occ configreport:generate > generated-config-report.txt
```

Alternatively, you could generate the report and email it all in one command, by running:

```bash
sudo -u www-data occ configreport:generate | mail \
    -s "configuration report" \
    -r <the email address to send from> \
    support@owncloud.com
```

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">These commands are not available in <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands">single-user (maintenance) mode</a>.</td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-line-installation)Command Line Installation

ownCloud can be installed entirely from the command line. After downloading the tarball and copying ownCloud into the appropriate directories, or after installing ownCloud packages (See [Linux Package Manager Installation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../installation/linux_packetmanager_install.html) and [Manual Installation on Linux](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../installation/manual_installation/manual_installation.html)) you can use `occ` commands in place of running the graphical Installation Wizard.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">These instructions assume that you have a fully working and configured webserver. If not, please refer to the documentation on configuring <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../installation/manual_installation/manual_installation.html#configure-the-web-server" class="page">Configure the Web Server</a> for detailed instructions.</td></tr></tbody></table>

Apply the [correct permissions](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../installation/manual_installation/manual_installation.html#script-guided-installation) to your ownCloud directories. Then choose your `occ` options. This lists your available options:

```bash
sudo -u www-data occ occ
ownCloud is not installed - only a limited number of commands are available
ownCloud version 10.0.8

Usage:
 [options] command [arguments]

== Options
 --help (-h)           Display this help message
 --quiet (-q)          Do not output any message
 --verbose (-v|vv|vvv) Increase the verbosity of messages: 1 for normal output,
                       2 for more verbose output and 3 for debug
 --version (-V)        Display this application version
 --ansi                Force ANSI output
 --no-ansi             Disable ANSI output
 --no-interaction (-n) Do not ask any interactive question

Available commands:
 check                 Check dependencies of the server environment
 help                  Displays help for a command
 list                  Lists commands
 status                Show some status information
 app
  app:check-code       Check code to be compliant
 l10n
  l10n:createjs        Create javascript translation files for a given app
 maintenance
  maintenance:install  Install ownCloud
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-description)Command Description

Display your `maintenance:install` options.

```bash
sudo -u www-data occ help maintenance:install
ownCloud is not installed - only a limited number of commands are available
Usage:
```

```plaintext
maintenance:install [--database=["..."]] [--database-connection-string=["..."]] \
                    [--database-name=["..."]] [--database-host=["..."]] \
                    [--database-user=["..."]] [--database-pass=["..."]] \
                    [--database-table-prefix=["..."]] [--admin-user=["..."]] \
                    [--admin-pass=["..."]] [--data-dir=["..."]]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-9)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 23.913%;"> <col style="width: 76.087%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--database</code></p></td><td class="tableblock halign-left valign-top"><div class="content"><div class="paragraph"><p>Supported database type (default: <code>sqlite</code>). The supported values are:</p></div><div class="ulist"><ul><li><p><code>mysql</code>: MySQL/MariaDB</p></li><li><p><code>oci</code>: Oracle (<em>ownCloud Enterprise edition only</em>)</p></li><li><p><code>pgsql</code>: PostgreSQL</p></li><li><p><code>sqlite</code>: SQLite3 (<em>ownCloud Community edition only</em>)</p></li></ul></div></div></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--database-connection-string</code></p></td><td class="tableblock halign-left valign-top"><div class="content"><div class="paragraph"><p>An Oracle-specific connection string.</p></div><div class="admonitionblock note"><table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">As soon as this parameter is provided, other parameters like database-host and database-name are not used and do not need to be provided. For example:</td></tr></tbody></table></div><div class="paragraph"><p><strong>Example</strong></p></div><div class="listingblock"><div class="content"><pre class="highlightjs highlight"><code class="language-plaintext hljs" data-lang="plaintext">sales=
 (DESCRIPTION=
  (ADDRESS= (PROTOCOL=tcp)(HOST=sales-server)(PORT=1521))
  (CONNECT_DATA=
     (SERVICE_NAME=sales.us.acme.com)))</code><div class="source-toolbox"><span class="source-lang">plaintext</span><button class="copy-button" title="Copy to clipboard"><img src="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../../../../assets/img/octicons-16.svg#view-clippy" alt="copy icon" class="copy-icon"><span class="copy-toast">Copied!</span></button></div></pre></div></div></div></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--database-name</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the database.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--database-host</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Hostname of the database (default: <code>localhost</code>).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--database-user</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User name to connect to the database.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--database-pass</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Password of the database user.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--database-table-prefix</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Prefix for all tables (default: <code>oc_</code> ).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--admin-user</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Password of the admin account.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--data-dir</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Path to data directory (default: <code>/var/www/owncloud/data</code>).</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example)Example

This example completes the installation:

```bash
cd /var/www/owncloud/
sudo -u www-data occ maintenance:install \
   --database "mysql" \
   --database-name "owncloud"  \
   --database-user "root" \
   --database-pass "password" \
   --admin-user "admin" \
   --admin-pass "password"
ownCloud is not installed - only a limited number of commands are available
ownCloud was successfully installed
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-line-upgrade)Command Line Upgrade

These commands are available only after you have downloaded upgraded packages or tar archives, and before you complete the upgrade. List all options, like this example on CentOS Linux:

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-description-2)Command Description

```bash
sudo -u www-data occ upgrade --help
Usage:
upgrade [options]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-10)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--major</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Automatically update apps to new major versions during minor updates of ownCloud Server.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--no-app-disable</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Skip disabling of third party apps.</p></td></tr></tbody></table>

When you are performing an update or upgrade on your ownCloud server (see the Maintenance section of this manual), it is better to use `occ` to perform the database upgrade step, rather than the Web GUI, in order to avoid timeouts. PHP scripts invoked from the Web interface are limited to 3600 seconds. In larger environments this may not be enough, leaving the system in an inconsistent state. After performing all the preliminary steps (see [the maintenance upgrade documentation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../maintenance/upgrading/upgrade.html)) use this command to upgrade your databases, like this example on CentOS Linux:

```bash
sudo -u www-data occ upgrade
ownCloud or one of the apps require upgrade - only a limited number of
commands are available
Turned on maintenance mode
Checked database schema update
Checked database schema update for apps
Updated database
Updating <activity> ...
Updated <activity> to 2.1.0
Update successful
Turned off maintenance mode
```

Note how it details the steps. Enabling verbosity displays timestamps:

```bash
sudo -u www-data occ upgrade -v
ownCloud or one of the apps require upgrade - only a limited number of commands are available
2017-06-23T09:06:15+0000 Turned on maintenance mode
2017-06-23T09:06:15+0000 Checked database schema update
2017-06-23T09:06:15+0000 Checked database schema update for apps
2017-06-23T09:06:15+0000 Updated database
2017-06-23T09:06:15+0000 Updated <files_sharing> to 0.6.6
2017-06-23T09:06:15+0000 Update successful
2017-06-23T09:06:15+0000 Turned off maintenance mode
```

If there is an error it throws an exception, and the error is detailed in your ownCloud logfile, so you can use the log output to figure out what went wrong, or to use in a bug report.

```
Turned on maintenance mode
Checked database schema update
Checked database schema update for apps
Updated database
Updating <files_sharing> ...
Exception
ServerNotAvailableException: LDAP server is not available
Update failed
Turned off maintenance mode
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#dav-commands)DAV Commands

A set of commands to create and sync address books and calendars:

```plaintext
dav
 dav:cleanup-chunks            Cleanup outdated chunks
 dav:create-addressbook        Create a dav address book
 dav:create-calendar           Create a dav calendar
 dav:sync-birthday-calendar    Synchronizes the birthday calendar
 dav:sync-system-addressbook   Synchronizes users to the system address book
```

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">These commands are not available in <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands">single-user (maintenance) mode</a>.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#cleanup-chunks)Cleanup Chunks

`dav:cleanup-chunks` cleans up outdated chunks (uploaded files) more than a certain number of days old. By default, the command cleans up chunks more than 2 days old. However, by supplying the number of days to the command, the range can be increased.

```bash
sudo -u www-data occ dav:cleanup-chunks [options] [--] [<minimum-age-in-days>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-9)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 26.3157%;"> <col style="width: 73.6843%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>minimum-age-in-days</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Minimum age of uploads to cleanup (in days - minimum 2 days - maximum 100) [default: 2]</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-11)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 26.3157%;"> <col style="width: 73.6843%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-l</code><br><code>--local</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Only delete chunks that exist on the local filesystem. This applies to setups with multiple servers connected to the same database and chunk folder is not shared among them.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-2)Example

In the example below, chunks older than 10 days will be removed.

```bash
sudo -u www-data occ dav:cleanup-chunks 10

# example output
Cleaning chunks older than 10 days(2017-11-08T13:13:45+00:00)
Cleaning chunks for admin
   0 [>---------------------------]
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#create-addressbook)Create Addressbook

Create a dav address book.

```bash
sudo -u www-data occ dav:create-addressbook <user> <name>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-10)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 26.3157%;"> <col style="width: 73.6843%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>user</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User for whom the address book will be created</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>name</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the addressbook</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-3)Example

This example creates the address book `mollybook` for the user molly:

```bash
sudo -u www-data occ dav:create-addressbook molly mollybook
```

Molly will immediately see her address book.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#create-calendar)Create Calendar

Create a dav calendar.

```bash
sudo -u www-data occ dav:create-calendar <user> <name>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-11)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 26.3157%;"> <col style="width: 73.6843%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>user</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User for whom the calendar will be created</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>name</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the calendar</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-4)Example

This example creates a new calendar `mollycal` for user molly:

```bash
sudo -u www-data occ dav:create-calendar molly mollycal
```

Molly will immediately see her calendar.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#sync-birthday-calendar)Sync Birthday Calendar

Synchronizes the birthday calendar. It adds all birthdays to your calendar from address books shared with you.

```bash
sudo -u www-data occ dav:sync-birthday-calendar [<user>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-12)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 26.3157%;"> <col style="width: 73.6843%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>user</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User for whom the birthday calendar will be synchronized</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-5)Example

This example syncs to your calendar from user `bernie`:

```bash
sudo -u www-data occ dav:sync-birthday-calendar bernie
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#sync-system-addressbook)Sync System Addressbook

Synchronizes all users to the system addressbook.

```bash
sudo -u www-data occ dav:sync-system-addressbook
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#database-commands)Database Commands

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#database-conversion-commands)Database Conversion Commands

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#convert-the-database-type)Convert the Database Type

The SQLite database is good for testing, and for ownCloud servers with small single-user workloads that do not use sync clients, but production servers with multiple users should use MariaDB, MySQL, or PostgreSQL. You can use `occ` to convert from SQLite to one of these other databases.

```plaintext
db
 db:convert-type     Convert the ownCloud database to the newly configured one
```

You need:

-   Your desired database and its PHP connector installed.
    
-   The login and password of a database admin user.
    
-   The database port number, if it is a non-standard port.
    

This is example converts SQLite to MySQL/MariaDB:

```bash
sudo -u www-data occ db:convert-type mysql oc_dbuser 127.0.0.1 oc_database
```

<table><tbody><tr><td class="icon"><i class="fa icon-tip" title="Tip"></i></td><td class="content">For a more detailed explanation see <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../database/db_conversion.html" class="page">converting database types</a>.</td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#convert-the-mysql-charset)Convert the MySQL Charset

Convert charset of MySQL/MariaDB to use utf8mb4. If you are using an older ownCloud installation, the database may not be setup to use the 4-byte unicode charset. This command changes the database charset to use `utf8mb4`. Check your database charset before you use this command.

```bash
sudo -u www-data occ db:convert-mysql-charset
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#restore-the-table-format)Restore the Table Format

This command sets the default row format of MySQL/MariaDB tables. This is only necessary once before you are going to e.g. install MariaDB 10.6 or higher because the COMPRESSED row format is now read-only by default. As a prerequisite, ownCloud 10.9 needs to be installed first. See the [Database Upgrade](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../maintenance/upgrading/database_upgrade.html) guide for details.

```bash
sudo -u www-data occ db:restore-default-row-format
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#encryption)Encryption

`occ` includes a complete set of commands for managing encryption. When using a HSM (Hardware Security Module, can also be emulated by software), additional occ encryption-related commands can be used.

```plaintext
encryption
 config:app:set encryption encryptHomeStorage Encrypt the users home storage

 encryption:change-key-storage-root  Change key storage root
 encryption:decrypt-all              Disable server-side encryption and decrypt all files
 encryption:disable                  Disable encryption
 encryption:enable                   Enable encryption
 encryption:encrypt-all              Encrypt all files for all users
 encryption:fix-encrypted-version    Fix the encrypted version if the encrypted file(s) are
                                     not downloadable.
 encryption:list-modules             List all available encryption modules
 encryption:migrate                  Initial migration to encryption 2.0
 encryption:recreate-master-key      Replace existing master key with new one. Encrypt the
                                     file system with newly created master key
 encryption:select-encryption-type   Select the encryption type. The encryption types available
                                     are: masterkey and user-keys. There is also no way to
                                     disable it again.
 encryption:set-default-module       Set the encryption default module
 encryption:show-key-storage-root    Show current key storage root
 encryption:status                   Lists the current status of encryption
```

When using a HSM (Hardware Security Module, additional occ encryption-related commands can be used, see the HSM occ documentation below. The occ commands can also be used when HSM is initiated via software emulation like SoftHSM2.

```plaintext
encryption
 encryption:hsmdaemon                Export or Import the Masterkey
 encryption:hsmdaemon:decrypt        Decrypt a String
 config:app:set encryption           Various encryption configuration commands for HSM
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#status)Status

`occ encryption:status` shows whether you have active encryption and your default encryption module. To enable encryption you must first enable the Encryption app and then run `occ encryption:enable`:

```bash
sudo -u www-data occ app:enable encryption
sudo -u www-data occ encryption:enable
sudo -u www-data occ encryption:status
 - enabled: true
 - defaultModule: OC_DEFAULT_MODULE
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#encrypt-the-users-home-storage)Encrypt the Users Home Storage

Server-side encryption for local storage like the users home and remote storages like Google Drive can operate independently of each other. By doing so, you can encrypt a remote storage without also having to encrypt the users home storage on your ownCloud server. Possible values are `0` and `1`

```bash
config:app:set encryption encryptHomeStorage --value '1'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#change-key-storage-root)Change Key Storage Root

`encryption:change-key-storage-root` is for moving your encryption keys to a different folder within your data directory. It takes one argument, which defines your new root folder. The folder must exist and the path is relative to your data directory.

```bash
sudo -u www-data occ encryption:change-key-storage-root ../data/security/oc-keys
```

You can see the current location of your keys folder:

```bash
sudo -u www-data occ encryption:show-key-storage-root
Current key storage root:  default storage location (data/)
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#list-modules)List Modules

`encryption:list-modules` displays your available encryption modules. You will see a list of modules only if you have enabled the Encryption app. Use `encryption:set-default-module [module name]` to set your desired module.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#encrypt-all)Encrypt All

`encryption:encrypt-all` encrypts all data files for all users. You must first put your ownCloud server into [single-user mode](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands) to prevent any user activity until encryption is completed.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-13)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-y</code><br><code>--yes</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Answer yes to all questions.<br>This argument automatically answers, potential, questions with "yes", which is particularly important for automated deployments with Ansible or similar tools.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#decrypt-all)Decrypt All

`encryption:decrypt-all` decrypts all user data files, or optionally a single user:

```bash
sudo -u www-data occ encryption:decrypt freda
```

Users must have enabled recovery keys on their Personal pages. You must first put your ownCloud server into single-user mode, using [the maintenance commands](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands), to prevent any user activity until decryption is completed.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-14)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-m=[METHOD]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Accepts the methods:<br><code>recovery</code> or <code>password</code><br>If the <em>recovery</em> method is chosen, then the recovery password will be used to decrypt files.<br>If the <em>password</em> method is chosen, then individual user passwords will be used to decrypt files.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-c=[COMMAND]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Accepts the commands:<br><code>yes</code> or <code>no</code><br>This lets the command know whether to ask for permission to continue or not.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#method-descriptions)Method Descriptions

###### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#recovery-method)Recovery method

This method reads the value from the environment variable `OC_RECOVERY_PASSWORD`. This variable bounds the value of recovery password set in the encryption page. If this variable is not set the recovery process will be halted. This has to be used for decrypting all users. While opting recovery method user should not forget to set `OC_RECOVERY_PASSWORD` in the shell.

###### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#password-method)Password method

This method reads the value from the environment variable `OC_PASSWORD`. This variable bounds the value of user password. The password which user uses to login to oC account. When password method is opted the user needs to set this variable in the shell.

###### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#continue-option-description)Continue Option Description

The continue option can be used to bypass the permissions asked like `yes` or `no` while decrypting the file system. If the user is sure about what he/she is doing with the command and would like to proceed, then `-c yes` when provided to the command would not ask permissions. If `-c no` is passed to the command, then permissions would be asked to the user. It becomes interactive.

Use `encryption:disable` to disable your encryption module. You must first put your ownCloud server into [single-user mode](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands) to prevent any user activity.

`encryption:migrate` migrates encryption keys after a major ownCloud version upgrade. You may optionally specify individual users in a space-delimited list. See [encryption configuration](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../files/encryption/encryption_configuration.html) to learn more.

`encryption:recreate-master-key` decrypts the ownCloud file system, replaces the existing master key with a new one, and encrypts the entire ownCloud file system with the new master key. Given the size of your ownCloud filesystem, this may take some time to complete. However, if your filesystem is quite small, then it will complete quite quickly. The `-y` switch can be supplied to automate acceptance of user input.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#fix-encrypted-version)Fix Encrypted Version

```bash
sudo -u www-data occ encryption:fix-encrypted-version [options] [--] <user>
```

`encryption:fix-encrypted-version` fixes the encrypted version of files if the encrypted file(s) are not downloadable for a given user. You only need this command if you get an "Invalid Signature" message in the browser or the clients.

Background: the `oc_filecache` database table contains the integer columns "version" and "encryptedVersion" which start with 1 and are incremented on every file modification. When using encryption, those values are used together with the ciphertext to generate a cryptographic signature for the file. The version value is required to verify the signature. In some very rare cases like timeouts or bugs etc., the value might not get updated accordingly or get lost. The brute-force approach is to use the `fix:encrypted:version` command until the file can be decrypted. Starting with ownCloud 10.8, the behavior of the command got improved so that the encryptedVersion value is reset to its original value if no correct version was found. Before that fix, the last tried value was stored in the database thus modifying the state of the system and making further rescue attempts non-deterministic.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-15)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>user</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The id of the user whose files need fixing.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-12)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-p</code><br><code>--path=PATH</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Limit files to fix with path, e.g., --path="/Music/Artist".<br>If path indicates a directory, all the files inside directory will be fixed.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-i</code><br><code>--increment-range=INCREMENT-RANGE</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Find the correct version of the file to verify the signature.<br>Searches in increments from -n to +n. [default: "5"]</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#hsm-related-commands)HSM Related Commands

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#export-or-import-the-masterkey)Export or Import the Masterkey

```bash
sudo -u www-data occ encryption:hsmdaemon [options]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-13)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--export-masterkey</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Export the private master key in base64</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--import-masterkey=<br>IMPORT-MASTERKEY</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Import a base64 encoded private masterkey.</p></td></tr></tbody></table>

`--export-masterkey` prints the base64\_encode of the file `data/files_encryption/OC_DEFAULT_MODULE/master_*.privateKey`.

The private key file in the directory may be named like `master_08ea43b7.privateKey`.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#test-to-decrypt-a-string)Test to Decrypt a String

Allows to test the `hsmdaemon` setup by providing an encrypted string to ownCloud and test if it can be decrypted.

```bash
sudo -u www-data occ encryption:hsmdaemon:decrypt [options] [--] <decrypt>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-16)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>decrypt</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The string to decrypt</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-14)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--username[=USERNAME]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The name of the user who is able to decrypt the provided string</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--keyId[=KEYID]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The keyId which was used to encrypt the provided string</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-the-hsm-url)Set the HSM URL

Set the url on which the `hsmdaemon` REST-API is reachable.

```bash
sudo -u www-data occ config:app:set encryption hsm.url --value 'http://127.0.0.1:8513'
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-the-json-web-token-secret)Set the JSON Web Token Secret

To access the `hsmdaemon` API, ownCloud must authenticate with a JWT (JSON Web Token). The given secret is shared between the `hsdmdaemon` (see the hsmdaemon.toml configuration file) and ownCloud to sign the JWT. See the [HSM documentation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.htmlsecurity/hsmdaemon/index.html) for an example how to generate a secret.

```bash
sudo -u www-data occ config:app:set encryption hsm.jwt.secret --value '7a7d1826-b514-4d9f-afc7-a7485084e8de'
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-the-jwt-clockskew)Set the JWT Clockskew

The JWT described above has an expiry timestamp. In case the time clocks on ownCloud and hsmdaemon system drift or skew apart, additional time is added to the expiry time to counteract this situation. Set or change the clockskew only if ownCloud advises to do so. Defaults to 120, value is in seconds.

```bash
sudo -u www-data occ config:app:set encryption hsm.jwt.clockskew --value '120'
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#federation-sync)Federation Sync

Synchronize the address books of all federated ownCloud servers.

Servers connected with federation shares can share user address books, and auto-complete usernames in share dialogs. Use this command to synchronize federated servers:

```bash
sudo -u www-data occ federation:sync-addressbooks
```

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">This command is only available when the "Federation" app (<code>federation</code>) is enabled.</td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#file-operations)File Operations

`occ` has the following commands for managing files in ownCloud.

```plaintext
files
 files:check-cache          Check if the target file exists in the primary storage
 files:checksums:verify     Get all checksums in filecache and compares them by
                            recalculating the checksum of the file.
 files:cleanup              Deletes orphaned file cache entries.
 files:scan                 Rescans the filesystem.
 files:transfer-ownership   All files and folders are moved to another user
                            - outgoing shares are moved as well (incoming shares are
                            not moved as the sharing user holds the ownership of the respective files).
 files:troubleshoot-transfer-ownership
                            Scan for problems that might have occurred while running ownership transfer
```

<table><tbody><tr><td class="icon"><i class="fa icon-important" title="Important"></i></td><td class="content">These commands are not available in <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands">single-user (maintenance) mode</a>.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#the-filescheck-cache-command)The files:check-cache command

The main purpose of this command is to clear the cache for objectstores (`objectstore` and `files_primary_S3` apps) as primary storage, but it is not limited to this type of storage. It can be used for any other type as long it is the primary storage.

Files in the primary storage could be deleted outside of ownCloud, leaving information in ownCloud’s file cache. This command intends to check if the target file can be read from the primary backend storage and, if not, allows you to remove the information cached.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content"><div class="paragraph"><p>Removing files directly from the primary storage is not supported and should not happen. As such, the cases where you need to run this command should be extremely rare. This is why this command is only provided to check for one file instead of scanning the whole of ownCloud’s filesystem.</p></div></td></tr></tbody></table>

```bash
sudo -u www-data occ files:check-cache --help
 Usage:
   files:check-cache [options] [--] <uid> <target-file>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-17)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The user (user id) who owns the file</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>target-file</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The file we want to check</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-15)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--remove</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Remove the file from the cache if it’s missing in the backend</p></td></tr></tbody></table>

Examples of checking files for user maria:

```bash
sudo -u www-data occ files:check-cache maria welcome.txt

welcome.txt has been accessed properly
```

```bash
sudo -u www-data occ files:check-cache maria maria@smbhome/myfile.txt

Ignoring maria@smbhome/myfile.txt because it is shared or not inside the primary storage
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#the-fileschecksumsverify-command)The files:checksums:verify command

ownCloud supports file integrity checking, by computing and matching checksums. Doing so ensures that transferred files arrive at their target in the exact state as they left their origin.

In some rare cases, wrong checksums are written to the database which leads to synchronization issues, such as with the Desktop Client. To mitigate such problems a new command is available: `occ files:checksums:verify`.

Executing the command recalculates checksums, either for all files of a user or within a specified filesystem path on the designated storage. It then compares them with the values in the database. The command also offers an option to repair incorrect checksum values (`-r, --repair`).

<table><tbody><tr><td class="icon"><i class="fa icon-caution" title="Caution"></i></td><td class="content">Executing this command might take some time depending on the file count.</td></tr></tbody></table>

Below is sample output that you can expect to see when using the command.

```bash
sudo -u www-data occ files:checksums:verify

This operation might take very long.
Mismatch for files/welcome.txt:
 Filecache:   SHA1:eeb2c08011374d8ad4e483a4938e1aa1007c089d MD5:368e3a6cb99f88c3543123931d786e21 ADLER32:c5ad3a63
 Actual:  SHA1:da39a3ee5e6b4b0d3255bfef95601890afd80709 MD5:d41d8cd98f00b204e9800998ecf8427e ADLER32:00000001
Mismatch for thumbnails/9/2048-2048-max.png:
 Filecache:   SHA1:2634fed078d1978f24f71892bf4ee0e4bd0c3c99 MD5:dd249372f7a68c551f7e6b2615d49463 ADLER32:821230d4
 Actual:  SHA1:da39a3ee5e6b4b0d3255bfef95601890afd80709 MD5:d41d8cd98f00b204e9800998ecf8427e ADLER32:00000001
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-16)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-r, --repair</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Repair filecache-entry with mismatched checksums.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-u, --user=USER</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Specific user to check.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-p, --path=PATH</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Path to check relative to user folder. [default: ""]. For example, if the user’s id was "john" and the <code>--path</code> value was "tree/apple", the command would check the ownCloud directory <code>/john/files/tree/apple</code>.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#the-filescleanup-command)The files:cleanup command

`files:cleanup` tidies up the server’s file cache by deleting all file entries that have no matching entries in the storage table.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#the-filesscan-command)The files:scan command

The `files:scan` command

-   Scans for new files.
    
-   Scans not fully scanned files.
    
-   Repairs file cache holes.
    
-   Updates the file cache.
    

File scans can be performed per-user, for a space-delimited list of users, for groups of users, and for all users.

```bash
sudo -u www-data occ files:scan --help
 Usage:
   files:scan [options] [--] [<user_id>]...
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-18)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>user_id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Will rescan all files of the given user(s).</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-17)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<code>plain</code>, <code>json</code> or <code>json_pretty</code>, default is <code>plain</code>).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-p --path=[PATH]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Limit rescan to this path, e.g. --path="/alice/files/Music", the user_id is determined by the path and the user_id parameter and --all are ignored.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--group=[GROUP]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Scan user(s) under the group(s). This option can be used as --group=foo --group=bar to scan groups foo and bar (multiple values allowed)</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-g --groups=[GROUP]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Scan user(s) under the group(s). This option can be used as --groups=foo,bar to scan groups foo and bar (multiple values allowed separated by commas)</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-q --quiet</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Do not output any message.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--all</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Will rescan all files of all known users.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--repair</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Will repair detached filecache entries (slow).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--unscanned</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Only scan files which are marked as not fully scanned.</p></td></tr></tbody></table>

<table><tbody><tr><td class="icon"><i class="fa icon-tip" title="Tip"></i></td><td class="content">If not using <code>--quiet</code>, statistics will be shown at the end of the scan.</td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#the-path-option)The `--path` Option

When using the `--path` option, the path must be in one of the following formats:

```
"user_id/files/path"
"user_id/files/mount_name"
"user_id/files/mount_name/path"
```

For example:

```
--path="/alice/files/Music"
```

In the example above, the user\_id `alice` is determined implicitly from the path component given. To get a list of scannable mounts for a given user, use the following command:

```bash
sudo -u www-data occ files_external:list user_id
```

<table><tbody><tr><td class="icon"><i class="fa icon-tip" title="Tip"></i></td><td class="content">Mounts are only scannable at the point of origin. Scanning of shares including federated shares is not necessary on the receiver side and therefore not possible.</td></tr></tbody></table>

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">Mounts based on session credentials can not be scanned as the users credentials are not available to the occ command set.</td></tr></tbody></table>

The `--path`, `--all`, `--group`, `--groups` and `[user_id]` parameters are exclusive - only one must be specified.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#the-repair-option)The `--repair` Option

As noted above, repairs can be performed for individual users, groups of users, and for all users in an ownCloud installation. What’s more, repair scans can be run even if no files are known to need repairing and if one or more files are known to be in need of repair. Two examples of when files need repairing are:

-   If folders have the same entry twice in the web UI (known as a '_ghost folder_'), this can also lead to strange error messages in the desktop client.
    
-   If entering a folder doesn’t seem to lead into that folder.
    

<table><tbody><tr><td class="icon"><i class="fa icon-caution" title="Caution"></i></td><td class="content">We strongly suggest that you backup the database before running this command.</td></tr></tbody></table>

The `--repair` option can be run within two different scenarios:

-   Requiring a downtime when used on all affected storages at once.
    
-   Without downtime, filtering by a specified User Id.
    

The following commands show how to enable single user mode, run a repair file scan in bulk on all storages, and then disable single user mode. This way is much faster than running the command for every user separately, but it requires single user mode.

```bash
sudo -u www-data occ maintenance:singleuser --on
sudo -u www-data occ files:scan --all --repair
sudo -u www-data occ maintenance:singleuser --off
```

The following command filters by the storage of the specified user.

```bash
sudo -u www-data occ files:scan USERID --repair
```

<table><tbody><tr><td class="icon"><i class="fa icon-tip" title="Tip"></i></td><td class="content">If many users are affected, it could be convenient to create a shell script, which iterates over a list of User ID’s.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#the-filestransfer-ownership-command)The files:transfer-ownership command

You may transfer all files and **outgoing** shares from one user to another.

Incoming shares are not transferred.

If the target users don’t exist, they will be created.

This command is useful before removing users.

```bash
sudo -u www-data occ files:transfer-ownership --help
 Usage:
   files:transfer-ownership [options] [--] <source-user> <destination-user>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-19)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>source-user</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">owner of files which shall be moved</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>destination-user</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">user who will be the new owner of the files</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-18)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--path=[PATH]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">selectively provide the path to transfer.<br>For example --path="folder_name"</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-s,<br>--accept-skipped-shares</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">always confirm to continue in case of skipped shares.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--destination-use-user-folder</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">transfer directly to top-level user folder,<br>operation only possible if destination user<br>never logged in and command aborts otherwise.</p></td></tr></tbody></table>

For example, to move all files from `<source-user>` to `<destination-user>` transfer folder, use the following command:

```bash
sudo -u www-data occ files:transfer-ownership \
    <source-user> \
    <destination-user>
```

You can also move a limited set of files from `<source-user>` to `<destination-user>` transfer folder by making use of the `--path` switch, as in the example below. Ownership of `folder/to/move` and all files and folders which it contains will be transferred to `<destination-user>` transfer folder.

```bash
sudo -u www-data occ files:transfer-ownership \
    --path="folder/to/move" \
    <source-user> \
    <destination-user>
```

If the entire user folder of `<source-user>` needs to be migrated to `<destination-user>` user folder, use the `--destination-use-user-folder` switch, as in the example below. The destination user needs to be created but never log in, we recommend using owncloud maintenance mode for this operation.

```bash
sudo -u www-data occ files:transfer-ownership \
    --destination-use-user-folder \
    <source-user> \
    <destination-user>
```

Please keep the following in mind when using this command:

1.  The directory provided to the `--path` switch **must** exist inside `data/<source-user>/files`.
    
2.  The directory and its contents won’t be moved as-is between the users. It will be moved into the destination user’s `files` directory, into a directory name which follows the format: `transferred from <source-user> on <timestamp>`. Using the example above, it will be stored under: `data/<destination-user>/files/transferred from <source-user> on 20170426_124510/`
    
3.  Currently file versions can’t be transferred. Only the latest version of moved files will appear in the destination user’s account.
    

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#the-filestroubleshoot-transfer-ownership-command)The files:troubleshoot-transfer-ownership command

This command is used to scan for problems, that might have occurred during a run of ownership transfer using the above command `files:transfer-ownership`. It can also be used to automatically attempt to fix problems. For example, transferred shares that may now have an invalid share owner.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">By default, the command performs a dry run and displays the problems found to the console output.</td></tr></tbody></table>

```bash
sudo -u www-data occ files:troubleshoot-transfer-ownership --help
 Usage:
   files:troubleshoot-transfer-ownership [options] [--] [<type>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-20)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 25%;"> <col style="width: 75%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>type</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">"all", "invalid-owner", "invalid-initiator",<br>[default: ""]</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-19)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-f, --fix</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">perform auto-fix for found problems</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-u, --uid=UID</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">scope for particular user</p></td></tr></tbody></table>

Run the command with one of the type arguments:

```bash
sudo -u www-data occ files:troubleshoot-transfer-ownership \
    <all|invalid-owner|invalid-initiator>
```

The command can attempt to fix the issues with the `--fix` flag,  
or execute for a single user using `--uid <uid>`

```bash
sudo -u www-data occ files:troubleshoot-transfer-ownership all \
    --fix \
    --uid=UID
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files-external)Files External

These commands replace the `data/mount.json` configuration file used in ownCloud releases before 9.0. Commands for managing external storage.

```plaintext
files_external
 files_external:applicable  Manage applicable users and groups for a mount
 files_external:backends    Show available authentication and storage backends
 files_external:config      Manage backend configuration for a mount
 files_external:create      Create a new mount configuration
 files_external:delete      Delete an external mount
 files_external:export      Export mount configurations
 files_external:import      Import mount configurations
 files_external:list        List configured mounts
 files_external:option      Manage mount options for a mount
 files_external:verify      Verify mount configuration
```

These commands replicate the functionality in the ownCloud Web GUI, plus two new features: `files_external:export` and `files_external:import`.

Use `files_external:export` to export all admin mounts to stdout, and `files_external:export [user_id]` to export the mounts of the specified ownCloud user.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">These commands are only available when the "External storage support" app (<code>files_external</code>) is enabled. It is not available in <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands">single-user (maintenance) mode</a>.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files_externallist)files\_external:list

List configured mounts.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage)Usage

```plaintext
files_external:list [--show-password] [--full] [-a|--all] [-s|--short] [--] [<user_id>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-21)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>user_id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User ID to list the personal mounts for, if no user is provided admin mounts will be listed.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-20)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--show-password</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Show passwords and secrets</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--mount-options</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Show all mount options independent if they are set to their default value or not</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--full</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Don’t truncate long values in table output</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-a, --all</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Show both system-wide mounts and all personal mounts.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-s, --short</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Show only a reduced mount info.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-i, --importable-format</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Provide output values in a format compatible with files_external:import</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<code>plain</code>, <code>json</code> or <code>json_pretty</code>, default is <code>plain</code>).</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-6)Example

```bash
sudo -u www-data occ files_external:list user_1 --short
+----------+------------------+----------+
| Mount ID | Mount Point      | Type     |
+----------+------------------+----------+
| 1        | /mount_1         | Personal |
| 2        | /mount_2         | Personal |
+----------+------------------+----------+
```

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">The <code>--importable-format</code> option helps to make the technical mount settings visible. To see all settings you still need to use the other options such as <code>--show-password</code>, <code>--full</code> and <code>--all</code>. When you want to export the mount settings for later import, use the <code>files_external:export</code> command. <code>files_external:export</code> ensures that all the necessary settings are included in the output.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files_externalapplicable)files\_external:applicable

Manage applicable users and groups for a mount.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-2)Usage

```plaintext
files_external:applicable
    [--add-user     ADD-USER]
    [--remove-user  REMOVE-USER]
    [--add-group    ADD-GROUP]
    [--remove-group REMOVE-GROUP]
    [--remove-all]
    [--output       [OUTPUT]]
    [--]
    <mount_id>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-22)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>mount_id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Can be obtained using <code>occ files_external:list</code>.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-21)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--add-user</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">user to add as applicable (multiple values allowed).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--remove-user</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">user to remove as applicable (multiple values allowed).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--add-group</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">group to add as applicable (multiple values allowed).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--remove-group</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">group to remove as applicable (multiple values allowed).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--remove-all</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Set the mount to be globally applicable.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (plain, json or json_pretty, default is plain).</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files_externalbackends)files\_external:backends

Show available authentication and storage backends.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-3)Usage

```plaintext
files_external:backends [options]
    [--]
    [<type>]
    [<backend>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-23)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>type</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Only show backends of a certain type. Possible values are <code>authentication</code> or <code>storage</code>.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>backend</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Only show information of a specific backend.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-22)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (plain, json or json_pretty, default is plain.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files_externalconfig)files\_external:config

Manage backend configuration for a mount.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-4)Usage

```plaintext
files_external:config [options]
    [--]
    <mount_id>
    <key>
    [<value>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-24)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>mount_id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The ID of the mount to edit.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>key</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Key of the config option to set/get.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>value</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Value to set the config option to, when no value is provided the existing value will be printed.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-23)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<em>plain</em>, <em>json</em> or <em>json_pretty</em>. The default is plain).</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files_externalcreate)files\_external:create

Create a new mount configuration.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-5)Usage

\[source,plaintext

```
files_external:create [options]
    [--]
    <mount_point>
    <storage_backend>
    <authentication_backend>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-25)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>mount_point</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Mount point for the new mount.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>storage_backend</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Storage backend identifier for the new mount, see <code>occ files_external:backends</code> for possible values.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>authentication_backend</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Authentication backend identifier for the new mount, see <code>occ files_external:backends</code> for possible values.</p></td></tr></tbody></table>

###### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-24)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--user=[USER]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User to add the mount configurations for, if not set the mount will be added as system mount.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-c, --config=[CONFIG]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Mount configuration option in <code>key=value</code> format (multiple values allowed).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--dry</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Don’t save the imported mounts, only list the new mounts.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<code>plain</code>, <code>json</code> or <code>json`pretty</code>). The default is <code>plain</code>.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#storage-backend-details)Storage Backend Details

 
| Storage Backend | Identifier |
| --- | --- |
| 
Windows Network Drive

 | 

`windows_network_drive`

 |
| 

WebDav

 | 

`dav`

 |
| 

Local

 | 

`local`

 |
| 

ownCloud

 | 

`owncloud`

 |
| 

SFTP

 | 

`sftp`

 |
| 

Amazon S3

 | 

`amazons3`

 |
| 

Dropbox

 | 

`dropbox`

 |
| 

Google Drive

 | 

`googledrive`

 |
| 

SMB / CIFS

 | 

`smb`

 |

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#authentication-details)Authentication Details

 
| Authentication method | Identifier, name, configuration |
| --- | --- |
| 
Log-in credentials, save in session

 | 

`password::sessioncredentials`

 |
| 

Log-in credentials, save in database

 | 

`password::logincredentials`

 |
| 

User entered, store in database

 | 

`password::userprovided` (\*)

 |
| 

Global Credentials

 | 

`password::global`

 |
| 

None

 | 

`null::null`

 |
| 

Builtin

 | 

`builtin::builtin`

 |
| 

Username and password

 | 

`password::password`

 |
| 

OAuth1

 | 

`oauth1::oauth1` (\*)

 |
| 

OAuth2

 | 

`oauth2::oauth2` (\*)

 |
| 

RSA public key

 | 

`publickey::rsa` (\*)

 |
| 

OpenStack

 | 

`openstack::openstack` (\*)

 |
| 

Rackspace

 | 

`openstack::rackspace` (\*)

 |
| 

Access key (Amazon S3)

 | 

`amazons3::accesskey` (\*)

 |

(\*) - Authentication methods require additional configuration.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">Each Storage Backend needs its corresponding authentication methods.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files_externaldelete)files\_external:delete

Delete an external mount.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-6)Usage

```plaintext
files_external:delete [options] [--] <mount_id>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-26)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>mount_id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The ID of the mount to edit.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-25)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-y, --yes</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Skip confirmation.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (plain, json or json_pretty, default is plain).</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files_externalexport)files\_external:export

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-7)Usage

```plaintext
files_external:export [options] [--] [<user_id>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-27)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>user_id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User ID to export the personal mounts for, if no user is provided admin mounts will be exported.</p></td></tr></tbody></table>

###### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-26)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-a, --all</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Show both system-wide mounts and all personal mounts.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files_externalimport)files\_external:import

Import mount configurations.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-8)Usage

\[source,plaintext

```
files_external:import [options] [--] <path>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-28)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>path</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Path to a json file containing the mounts to import, use <code>-</code> to read from stdin.</p></td></tr></tbody></table>

###### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-27)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--user=[USER]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User to add the mount configurations for, if not set the mount will be added as system mount.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--dry</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Don’t save the imported mounts, only list the new mounts.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<em>plain</em>, <em>json</em> or <em>json_pretty</em>, default is <em>plain</em>).</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files_externaloption)files\_external:option

Manage mount options for a mount.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-9)Usage

```plaintext
files_external:option <mount_id> <key> [<value>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-29)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>mount_id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The ID of the mount to edit.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>key</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Key of the mount option to set/get.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>value</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Value to set the mount option to, when no value is provided the existing value will be printed.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files_externalverify)files\_external:verify

Verify mount configuration.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-10)Usage

```plaintext
files_external:verify [options] [--] <mount_id>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-30)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>mount_id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The ID of the mount to check.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-28)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-c, --config=[CONFIG]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Additional config option to set before checking in <code>key=value</code> pairs, required for certain auth backends such as login credentials (multiple values allowed).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (<em>plain</em>, <em>json</em> or <em>json_pretty</em>, default is plain).</p></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#group-commands)Group Commands

The `group` commands provide a range of functionality for managing ownCloud groups. This includes creating and removing groups and managing group membership. Group names are case-sensitive, so "Finance" and "finance" are two different groups.

The full list of commands is:

```plaintext
group
 group:add                           Adds a group
 group:add-member                    Add members to a group
 group:delete                        Deletes the specified group
 group:list                          List groups
 group:list-members                  List group members
 group:remove-member                 Remove member(s) from a group
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#creating-groups)Creating Groups

You can create a new group with the `group:add` command. The syntax is:

```
group:add groupname
```

This example adds a new group, called "Finance":

```bash
sudo -u www-data occ group:add Finance
  Created group "Finance"
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#listing-groups)Listing Groups

You can list the names of existing groups with the `group:list` command. The syntax is:

```
group:list [options] [<search-pattern>]
```

Groups containing the `search-pattern` string are listed. Matching is not case-sensitive. If you do not provide a search-pattern then all groups are listed.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-29)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 28.5714%;"> <col style="width: 71.4286%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Output format (plain, json or json_pretty, default is plain) [default: "plain"].</p></td></tr></tbody></table>

This example lists groups containing the string "finance".

```bash
sudo -u www-data occ group:list finance
 - All-Finance-Staff
 - Finance
 - Finance-Managers
```

This example lists groups containing the string "finance" formatted with `json_pretty`.

```bash
sudo -u www-data occ group:list --output=json_pretty finance
 [
   "All-Finance-Staff",
   "Finance",
   "Finance-Managers"
 ]
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#listing-group-members)Listing Group Members

You can list the user IDs of group members with the `group:list-members` command. The syntax is:

```
group:list-members [options] <group>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-30)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 28.5714%;"> <col style="width: 71.4286%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Output format (plain, json or json_pretty, default is plain) [default: "plain"].</p></td></tr></tbody></table>

This example lists members of the "Finance" group.

```bash
sudo -u www-data occ group:list-members Finance
 - aaron: Aaron Smith
 - julie: Julie Jones
```

This example lists members of the Finance group formatted with `json_pretty`.

```bash
sudo -u www-data occ group:list-members --output=json_pretty Finance
 {
   "aaron": "Aaron Smith",
   "julie": "Julie Jones"
 }
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#adding-members-to-groups)Adding Members to Groups

You can add members to an existing group with the `group:add-member` command. Members must be existing users. The syntax is:

```
group:add-member [-m|--member [MEMBER]] <group>
```

This example adds members "aaron" and "julie" to group "Finance":

```bash
sudo -u www-data occ group:add-member --member aaron --member julie Finance
  User "aaron" added to group "Finance"
  User "julie" added to group "Finance"
```

You may attempt to add members that are already in the group, without error. This allows you to add members in a scripted way without needing to know if the user is already a member of the group. For example:

```bash
sudo -u www-data occ group:add-member --member aaron --member julie --member fred Finance
  User "aaron" is already a member of group "Finance"
  User "julie" is already a member of group "Finance"
  User fred" added to group "Finance"
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#removing-members-from-groups)Removing Members from Groups

You can remove members from a group with the `group:remove-member` command. The syntax is:

```
group:remove-member [-m|--member [MEMBER]] <group>
```

This example removes members "aaron" and "julie" from group "Finance".

```bash
sudo -u www-data occ group:remove-member --member aaron --member julie Finance
  Member "aaron" removed from group "Finance"
  Member "julie" removed from group "Finance"
```

You may attempt to remove members that have already been removed from the group, without error. This allows you to remove members in a scripted way without needing to know if the user is still a member of the group. For example:

```bash
sudo -u www-data occ group:remove-member --member aaron --member fred Finance
  Member "aaron" could not be found in group "Finance"
  Member "fred" removed from group "Finance"
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#deleting-a-group)Deleting a Group

To delete a group, you use the `group:delete` command, as in the example below:

```bash
sudo -u www-data occ group:delete Finance
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#integrity-check)Integrity Check

Apps which have an official tag **must** be code signed. Unsigned official apps won’t be installable anymore. Code signing is optional for all third-party applications.

```plaintext
integrity
 integrity:check-app                 Check app integrity using a signature.
 integrity:check-core                Check core integrity using a signature.
 integrity:sign-app                  Signs an app using a private key.
 integrity:sign-core                 Sign core using a private key
```

After creating your signing key, sign your app like this example:

```bash
sudo -u www-data occ integrity:sign-app \
   --privateKey=/Users/karlmay/contacts.key \
   --certificate=/Users/karlmay/CA/contacts.crt \
   --path=/Users/karlmay/Programming/contacts
```

Verify your app:

```bash
sudo -u www-data occ integrity:check-app --path=/pathto/app appname
```

When it returns nothing, your app is signed correctly. When it returns a message then there is an error.

`integrity:sign-core` is for ownCloud core developers only.

<table><tbody><tr><td class="icon"><i class="fa icon-tip" title="Tip"></i></td><td class="content">See <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../general_topics/code_signing.html" class="page">code signing</a> to learn more.</td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#l10n-create-javascript-translation-files-for-apps)l10n, Create Javascript Translation Files for Apps

This command creates JavaScript and JSON translation files for ownCloud applications.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">The command does not update existing translations if the source translation file has been updated. It only creates translation files when none are present for a given language.</td></tr></tbody></table>

```plaintext
l10n
  l10n:createjs                Create Javascript translation files for a given app
```

The command takes two parameters; these are:

-   `app`: the name of the application.
    
-   `lang`: the output language of the translation files; more than one can be supplied.
    

To create the two translation files, the command reads translation data from a source PHP translation file.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#a-working-example)A Working Example

In this example, we’ll create Austrian German translations for the Comments app.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">This example assumes that the ownCloud directory is <code>/var/www/owncloud</code> and that it uses ownCloud’s standard apps directory, <code>app</code>.</td></tr></tbody></table>

First, create a source translation file in `/var/www/owncloud/apps/comments/l10n`, called `de_AT.php`. In it, add the required translation strings, as in the following example. Refer to the developer documentation on [creating translation files](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../../developer_manual/app/advanced/l10n.html#creating-your-own-translatable-files), if you’re not familiar with creating them.

```php
<?php
// The source string is the key, the translated string is the value.
$TRANSLATIONS = [
  "Share" => "Freigeben"
];
$PLURAL_FORMS = "nplurals=2; plural=(n != 1);";
```

After that, run the following command to create the translation.

```bash
sudo -u www-data occ l10n:createjs comments de_AT
```

This will generate two translation files, `de_AT.js` and `de_AT.json`, in `/var/www/owncloud/apps/comments/l10n`.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#create-translations-in-multiple-languages)Create Translations in Multiple Languages

To create translations in multiple languages simultaneously, supply multiple languages to the command, as in the following example:

```bash
sudo -u www-data occ l10n:createjs comments de_AT de_DE hu_HU es fr
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#logging-commands)Logging Commands

These commands view and configure your ownCloud logging preferences.

```plaintext
log
 log:manage     Manage logging configuration
 log:owncloud   Manipulate ownCloud logging backend
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-description-3)Command Description

Run `log:owncloud` to see your current logging status:

```bash
sudo -u www-data occ log:owncloud
Log backend ownCloud: enabled
Log file: /opt/owncloud/data/owncloud.log
Rotate at: disabled
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-31)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 28.5714%;"> <col style="width: 71.4286%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--enable</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Enable this logging backend.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--file=[FILE]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Set the log file path.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--rotate-size=[ROTATE-SIZE]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Set the file size for log rotation, 0 = disabled.</p></td></tr></tbody></table>

Use the `--enable` option to turn on logging. Use `--file` to set a different log file path. Set your rotation by log file size in bytes with `--rotate-size`; 0 disables rotation. Run `log:manage` to set your logging backend, log level, and timezone: The defaults are `owncloud`, `Warning`, and `UTC`.

Options for `log:manage`:

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 28.5714%;"> <col style="width: 71.4286%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--backend=[BACKEND]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Set the logging backend [owncloud, syslog, errorlog].</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--level=[LEVEL]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Set the log level [debug, info, warning, error, fatal].</p></td></tr></tbody></table>

Log level can be adjusted by entering the number or the name:

```bash
sudo -u www-data occ log:manage --level 4
sudo -u www-data occ log:manage --level error
```

<table><tbody><tr><td class="icon"><i class="fa icon-tip" title="Tip"></i></td><td class="content">Setting the log level to debug ( 0 ) can be used for finding the cause of an error, but should not be the standard as it increases the log file size.</td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#managing-background-jobs)Managing Background Jobs

Use the `background:queue` command to manage background jobs.

```plaintext
background:queue
 background:queue:delete     Delete a job from the queue
 background:queue:execute    Run a single background job from the queue
 background:queue:status     List queue status
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#deleting-a-background-job)Deleting a Background Job

The command `background:queue:delete` deletes a queued background job. It requires the job id of the job to be deleted.

```plaintext
background:queue:delete <Job ID>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-31)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>Job ID</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">ID of the job to be deleted</p></td></tr></tbody></table>

<table><tbody><tr><td class="icon"><i class="fa icon-warning" title="Warning"></i></td><td class="content">Deleting a job cannot be undone. Be sure that you want to delete the job before doing so.</td></tr></tbody></table>

This example deletes queued background job #12.

```bash
sudo -u www-data occ background:queue:delete 12

Job has been deleted.
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#executing-a-background-job)Executing a Background Job

The command `background:queue:execute` executes a queued background job. It requires the job id of the job to be executed.

```plaintext
background:queue:execute [options] [--] <Job ID>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-32)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>Job ID</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">ID of the job to be deleted</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-32)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-f</code><br><code>--force</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Force run the job even if within timing interval</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--accept-warning</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">No warning about the usage of this command will be displayed</p></td></tr></tbody></table>

This example executes queued background job #12.

```bash
sudo -u www-data occ background:queue:execute 12

This command is for maintenance and support purposes.
This will run the specified background job now. Regular scheduled runs of the job will
continue to happen at their scheduled times.
If you still want to use this command please confirm the usage by entering: yes
yes
Found job: OCA\UpdateNotification\Notification\BackgroundJob with ID 12
Running job...
Finished in 0 seconds
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#list-queued-backgroundjobs)List Queued Backgroundjobs

The command `background:queue:status` will list queued background jobs, including details when it last ran.

```plaintext
background:queue:status
```

This example lists the queue status:

```bash
sudo -u www-data occ background:queue:status

+----+---------------------------------------------------+---------------------------+---------------+
| Id | Job                                               | Last run                  | Job Arguments |
+----+---------------------------------------------------+---------------------------+---------------+
| 1  | OCA\Files\BackgroundJob\ScanFiles                 | 2018-06-13T15:15:04+00:00 |               |
| 2  | OCA\Files\BackgroundJob\DeleteOrphanedItems       | 2018-06-13T15:15:04+00:00 |               |
| 3  | OCA\Files\BackgroundJob\CleanupFileLocks          | 2018-06-13T15:15:04+00:00 |               |
| 4  | OCA\DAV\CardDAV\SyncJob                           | 2018-06-12T19:15:02+00:00 |               |
| 5  | OCA\Federation\SyncJob                            | 2018-06-12T19:15:02+00:00 |               |
| 6  | OCA\Files_Sharing\DeleteOrphanedSharesJob         | 2018-06-13T15:15:04+00:00 |               |
| 7  | OCA\Files_Sharing\ExpireSharesJob                 | 2018-06-12T19:15:02+00:00 |               |
| 8  | OCA\Files_Trashbin\BackgroundJob\ExpireTrash      | 2018-06-13T15:15:04+00:00 |               |
| 9  | OCA\Files_Versions\BackgroundJob\ExpireVersions   | 2018-06-13T15:15:04+00:00 |               |
| 10 | OCA\UpdateNotification\Notification\BackgroundJob | 2018-06-12T19:15:03+00:00 |               |
| 11 | OC\Authentication\Token\DefaultTokenCleanupJob    | 2018-06-13T15:15:04+00:00 |               |
+----+---------------------------------------------------+---------------------------+---------------+
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands)Maintenance Commands

Use these commands when you upgrade ownCloud, manage encryption, perform backups and other tasks that require locking users out until you are finished.

```plaintext
maintenance
 maintenance:data-fingerprint        Update the systems data-fingerprint after a backup is restored
 maintenance:install                 Install ownCloud
 maintenance:mimetype:update-db      Update database mimetypes and update filecache
 maintenance:mimetype:update-js      Update mimetypelist.js
 maintenance:mode                    Set maintenance mode
 maintenance:repair                  Repair this installation
 maintenance:singleuser              Set single user mode
 maintenance:update:htaccess         Updates the .htaccess file
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#update-the-systems-data-fingerprint)Update the Systems Data-Fingerprint

When a backup has been restored, the ETag information, which is necessary when accessing ownCloud with clients, has been changed. Run the following command to tell desktop and mobile clients that a server backup has been restored.

```bash
sudo -u www-data occ maintenance:data-fingerprint
```

This command changes the ETag for all files in the communication with sync clients, informing them that one or more files were modified. After the command completes, users will be prompted to resolve any conflicts between newer and older file versions.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#install-owncloud)Install ownCloud

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">This command is only available if the following key in your <code>config.php</code> is not present or set to <code>false</code>. This is the case when the installation has not been made or not finalized. This key automatically turns to <code>true</code> after a successful installation. This results in the command no longer being available.</td></tr></tbody></table>

```php
'installed' => false,
```

```bash
sudo -u www-data occ maintenance:install [options]
```

The `maintenance:install` command supports the following options:

 
| Option | Description |
| --- | --- |
| 
`--database`\=DATABASE

 | 

Supported database type. \[default: `sqlite`\]  
Possible values: `sqlite` ,`mysql`, `pgsql`, `oci`  
Note that `oci` (Oracle) is only available with the Enterprise license.

 |
| 

`--database-connection-string`\=DATABASE-CONNECTION-STRING

 | 

Oracle specific connection string. As soon as this parameter is provided, other parameters like database-host and database-name are not used and do not need to be provided.

 |
| 

`--database-name`\=DATABASE-NAME

 | 

Name of the database.

 |
| 

`--database-host`\=DATABASE-HOST

 | 

Hostname of the database. \[default: "localhost"\]

 |
| 

`--database-user`\=DATABASE-USER

 | 

User name to connect to the database.

 |
| 

`--database-pass`\=DATABASE-PASS

 | 

Password of the database user.

 |
| 

`--database-table-prefix`\=DATABASE-TABLE-PREFIX

 | 

Prefix for all tables (default: oc\_).

 |
| 

`--admin-user`\=ADMIN-USER

 | 

User name of the admin account. \[default: "admin"\]

 |
| 

`--admin-pass`\=ADMIN-PASS

 | 

Password of the admin account.

 |
| 

`--data-dir`\=DATA-DIR

 | 

Path to the data directory. \[default: "/var/www/owncloud/data"\]

 |

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#update-database-mimetypes)Update Database Mimetypes

Update database mimetypes and file cache.

Usage:

```bash
sudo -u www-data occ maintenance:mimetype:update-db [options]
```

The `maintenance:mimetype:update-db` command supports the following options:

 
| Option | Description |
| --- | --- |
| 
`--repair-filecache`

 | 

Repair the file cache for all mimetypes, not just the new ones.

 |

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#update-the-mimetypelist-js-file)Update the mimetypelist.js File

This command updates the `mimetypelist.js` file.

Usage:

```bash
sudo -u www-data occ maintenance:update-js
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#enable-or-disable-maintenance-mode)Enable or Disable Maintenance Mode

`maintenance:mode` command locks the sessions of all logged-in users, including administrators, and displays a status screen warning that the server is in maintenance mode. Users who are not already logged in cannot log in until maintenance mode is turned off. Once you take the server out of maintenance mode, logged-in users must refresh their Web browsers to continue working.

Usage:

```bash
sudo -u www-data occ maintenance:mode [options]
```

The `maintenance:repair` command supports the following options:

 
| Option | Description |
| --- | --- |
| 
`--on`

 | 

Enable maintenance mode.

 |
| 

`--off`

 | 

Disable maintenance mode.

 |

Turn on maintenance mode:

```bash
sudo -u www-data occ maintenance:mode --on
```

Turn it off when you’re finished with the maintenance tasks:

```bash
sudo -u www-data occ maintenance:mode --off
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#installation-repair-commands)Installation Repair Commands

The `maintenance:repair` command helps administrators repair an installation. The command runs automatically during upgrades to clean up the database. So, while you can run it manually, there usually isn’t a need to.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">Your ownCloud installation needs to be in maintenance mode to use the <code>maintenance:repair</code> command.</td></tr></tbody></table>

Usage:

```bash
sudo -u www-data occ maintenance:repair [options]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#repair-command-options)Repair Command Options

The `maintenance:repair` command supports the following options:

 
| Option | Description |
| --- | --- |
| 
`--list`

 | 

Lists all possible repair steps.

 |
| 

`-s` `--single=SINGLE`

 | 

Run just one repair step given its class name.

 |
| 

`--include-expensive`

 | 

Use this option when you want to include resource and load expensive tasks.

 |

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#running-all-repair-steps)Running All Repair Steps

Here is an example of running the command:

```bash
sudo -u www-data occ maintenance:repair
```

To list all off the possible repair steps, use the `--list` option. It should output the following list to the console:

```plaintext
Found 16 repair steps

OC\Repair\RepairMimeTypes -> Repair mime types
OC\Repair\RepairMismatchFileCachePath -> Detect file cache entries with path that does not match parent-child relationships
OC\Repair\FillETags -> Generate ETags for file where no ETag is present.
OC\Repair\CleanTags -> Clean tags and favorites
OC\Repair\DropOldTables -> Drop old database tables
OC\Repair\DropOldJobs -> Drop old background jobs
OC\Repair\RemoveGetETagEntries -> Remove getetag entries in properties table
OC\Repair\RepairInvalidShares -> Repair invalid shares
OC\Repair\RepairSubShares -> Repair sub shares
OC\Repair\SharePropagation -> Remove old share propagation app entries
OC\Repair\MoveAvatarOutsideHome -> Move user avatars outside the homes to the new location
OC\Repair\RemoveRootShares -> Remove shares of a users root folder
OC\Repair\RepairUnmergedShares -> Repair unmerged shares
OC\Repair\DisableExtraThemes -> Disable extra themes
OC\Repair\OldGroupMembershipShares -> Remove shares of old group memberships
OCA\DAV\Repair\RemoveInvalidShares -> Remove invalid calendar and addressbook shares
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#running-a-single-repair-step)Running a Single Repair Step

To run a single repair step, use either the `-s` or `--single` options, as in the following example.

Usage:

```bash
sudo -u www-data occ maintenance:repair \
     --single="OCA\DAV\Repair\RemoveInvalidShares"
```

<table><tbody><tr><td class="icon"><i class="fa icon-tip" title="Tip"></i></td><td class="content">The step’s name must be quoted, otherwise you will see the following warning message appear, and the command will fail: "<em>Repair step not found. Use --list to show available steps.</em>"</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#single-user-mode)Single User Mode

Putting your ownCloud server into single-user mode allows admins to log in and work, but not ordinary users. This is useful for performing maintenance and troubleshooting on a running server.

Usage:

```bash
sudo -u www-data occ maintenance:singleuser --on
```

Turn it off when you’re finished:

```bash
sudo -u www-data occ maintenance:singleuser --off
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#update-the-htaccess-file)Update the .htaccess File

This command updates the `.htaccess` file.

Usage:

```bash
sudo -u www-data occ maintenance:update:htaccess
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#migration-steps-command)Migration Steps Command

You can run migration steps with the `migrations` command.

```bash
sudo -u www-data occ migrations:execute <app> <version>
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-33)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>app</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the app this migration command shall work on.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>version</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The version to execute.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-7)Example

This example executes the migration step for the core app:

```bash
sudo -u www-data occ migrations:execute core 20181220085457
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#mimetype-update-commands)Mimetype Update Commands

`maintenance:mimetype:update-db` updates the ownCloud database and file cache with changed mimetypes found in `config/mimetypemapping.json`. Run this command after modifying `config/mimetypemapping.json`. If you change a mimetype, run `maintenance:mimetype:update-db --repair-filecache` to apply the change to existing files.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#notifications)Notifications

If you want to send notifications to users or groups use the following command.

```sourceCode
notifications
  notifications:generate   Generates a notification.
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-description-4)Command Description

```bash
sudo -u www-data occ notifications:generate [-u|--user USER] [-g|--group GROUP] [-l|--link <linktext>] [--] <subject> [<message>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-34)Arguments:

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>subject</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The notification subject - maximum 255 characters.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>message</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">A more extended message - maximum 4000 characters.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>linktext</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">A link to an HTML page.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-33)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-u [USER]</code><br><code>--user=[USER]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User id to whom the notification shall be sent.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-g [GROUP]</code><br><code>--group=[GROUP]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Group id to whom the notification shall be sent.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-l [LINK]</code><br><code>--link=[LINK]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">A link associated with the notification.</p></td></tr></tbody></table>

At least one user or group must be set. A link can be useful for notifications shown in client apps. Example:

```bash
sudo -u www-data occ notifications:generate -g Office "Emergency Alert" "Rebooting in 5min"
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#poll-incoming-federated-shares-for-updates)Poll Incoming Federated Shares For Updates

This command must be used if received federated shares are being referenced by desktop clients but not regularly accessed via the webUI. This is because, for performance reasons, federated shares do not update automatically. Instead, federated share directories are only updated when users browse them using the [webUI](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../../../../webui/next/classic_ui/files/webgui/overview.html).

ownCloud and system administrators can use the `incoming-shares:poll` command to poll federated shares for updates.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">The command polls all received federated shares, so does not require a path.</td></tr></tbody></table>

```bash
sudo -u www-data occ incoming-shares:poll
```

<table><tbody><tr><td class="icon"><i class="fa icon-important" title="Important"></i></td><td class="content"><div class="paragraph"><p>When using federation, it is recommended to execute <code>occ incoming-shares:poll</code> regularly <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.htmlbackground_jobs_configuration.html#cron-jobs" class="page">using Cron jobs</a>. The time interval between executions is a trade-off between the availability of changes in federated shares and resource consumption; which naturally depends a lot on the number of federated shares and the frequency of changes within those shares.</p></div><div class="paragraph"><p>Executing the command once every 12 hours <em>should</em> be safe enough for most instances. However, the interval can be reduced to once every 2 hours, for instances with a small number of federated shares.</p></div><div class="paragraph"><p>Depending on the desired resource consumption, this value should be lowered or increased based on individual expectations. To find a value that fits a specific setup, it is recommended to execute the command once, measure the execution time and set the interval, so that the background job can finish before the next execution is triggered.</p></div></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#security)Security

Use these commands when you manage security related tasks. Routes displays all routes of ownCloud. You can use this information to grant strict access via firewalls, proxies or load balancers etc.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-description-5)Command Description

```plaintext
security:routes [options]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-34)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Output format (plain, json or json-pretty, default is plain).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--with-details</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Adds more details to the output.</p></td></tr></tbody></table>

Example 1:

```bash
sudo -u www-data occ security:routes
```

```plaintext
+-----------------------------------------------------------+-----------------+
| Path                                                      | Methods         |
+-----------------------------------------------------------+-----------------+
| /apps/federation/auto-add-servers                         | POST            |
| /apps/federation/trusted-servers                          | POST            |
| /apps/federation/trusted-servers/<id>                     | DELETE          |
| /apps/files/                                              | GET             |
| /apps/files/ajax/download.php                             |                 |
...
```

Example 2:

```bash
sudo -u www-data occ security:routes --output=json-pretty
```

```plaintext
[
  {
      "path": "\/apps\/federation\/auto-add-servers",
      "methods": [
          "POST"
      ]
  },
```

Example 3:

```bash
sudo -u www-data occ security:routes --with-details
```

```plaintext
+---------------------------------------------+---------+-------------------------------------------------------+--------------------------------+
| Path                                        | Methods | Controller                                            | Annotations                    |
+---------------------------------------------+---------+-------------------------------------------------------+--------------------------------+
| /apps/files/api/v1/sorting                  | POST    | OCA\Files\Controller\ApiController::updateFileSorting | NoAdminRequired                |
| /apps/files/api/v1/thumbnail/{x}/{y}/{file} | GET     | OCA\Files\Controller\ApiController::getThumbnail      | NoAdminRequired,NoCSRFRequired |
...
```

The following commands manage server-wide SSL certificates. These are useful when you create federation shares with other ownCloud servers that use self-signed certificates.

```plaintext
security:certificates         List trusted certificates
security:certificates:import  Import trusted certificate
security:certificates:remove  Remove trusted certificate
```

This example lists your installed certificates:

```bash
sudo -u www-data occ security:certificates
```

Import a new certificate:

```bash
sudo -u www-data occ security:certificates:import /path/to/certificate
```

Remove a certificate:

```bash
sudo -u www-data occ security:certificates:remove [certificate name]
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#sharing)Sharing

This is an occ command to cleanup orphaned remote storages. To explain why this is necessary, a little background is required. While shares are able to be deleted as a normal matter of course, remote storages with `shared::` are not included in this process.

This might not, normally, be a problem. However, if a user has re-shared a remote share which has been deleted it will. This is because when the original share is deleted, the remote re-share reference is not. Internally, the `fileid` will remain in the file cache and storage for that file will not be deleted.

As a result, any user(s) who the share was re-shared with will now get an error when trying to access that file or folder. That’s why the command is available. So, to cleanup all orphaned remote storages, run it as follows:

```bash
sudo -u www-data occ sharing:cleanup-remote-storages
```

You can also set it up to run as [a background job](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#background-jobs-selector).

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">These commands are not available in <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands">single-user (maintenance) mode</a>.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#system)System

```console
 system
  system:cron             Execute background jobs as cron
```

```bash
sudo -u www-data occ -h system:cron
-Usage:
  system:cron [options]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-35)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">-p, --progress</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Shows a progress bar - for use in manual execution. Do not use when executing from crontab</p></td></tr></tbody></table>

To execute [background jobs](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.htmlbackground_jobs_configuration.html) using [cron](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.htmlbackground_jobs_configuration.html#cron), you can use the `system:cron` command, as in the following example:

```bash
sudo -u www-data occ system:cron
```

If the `--progress` or `-p` argument is specified, then progress output will be displayed in the console, as in the example below.

```console
Executing: 12 - OCA\UpdateNotification\Notification\BackgroundJob
  13 [------------->--------------]
```

If neither of these arguments is provided, no output will be displayed by the command.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">Displaying progress information is useful when you want visual confirmation that background jobs have been executed. However, in a non-interactive environment, such as crontab, it should not be used.</td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#updating-an-existing-system-cron-configuration)Updating an Existing System Cron Configuration

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content"><div class="paragraph"><p>If you have already automated background jobs via Cron, you must update the relevant <code>crontab</code> entry using the example below as a guide.</p></div><div class="paragraph"><p>Instead of the following configuration</p></div><div class="listingblock"><div class="content"><pre class="highlightjs highlight"><code class="language-console hljs language-shell" data-lang="console">/usr/bin/php -f /path/to/your/owncloud/cron.php</code><div class="source-toolbox"><span class="source-lang">console</span><button class="copy-button" title="Copy to clipboard"><img src="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../../../../assets/img/octicons-16.svg#view-clippy" alt="copy icon" class="copy-icon"><span class="copy-toast">Copied!</span></button></div></pre></div></div><div class="paragraph"><p>Use the following one instead</p></div><div class="listingblock"><div class="content"><pre class="highlightjs highlight"><code class="language-bash hljs" data-lang="bash"><span class="hljs-built_in">sudo</span> -u www-data <span class="hljs-built_in">occ</span> system:cron</code><div class="source-toolbox"><span class="source-lang">bash</span><button class="copy-button" title="Copy to clipboard"><img src="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../../../../assets/img/octicons-16.svg#view-clippy" alt="copy icon" class="copy-icon"><span class="copy-toast">Copied!</span></button></div></pre></div></div></td></tr></tbody></table>

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content"><div class="paragraph"><p>This command does not work if:</p></div><div class="ulist"><ul><li><p><a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands">Maintenance or Admin-only (single user) modes</a> are enabled</p></li><li><p>Background jobs are disabled</p></li></ul></div></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#trashbin)Trashbin

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">These commands are only available when the 'Deleted files' app (<code>files_trashbin</code>) is enabled. These commands are not available in <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands">single-user (maintenance) mode</a>.</td></tr></tbody></table>

```plaintext
trashbin
 trashbin:cleanup   Remove deleted files
 trashbin:expire    Expires the users trash bin
```

The `trashbin:cleanup` command removes the deleted files of the specified users in a space-delimited list, or all users if none are specified. This example removes all the deleted files of all users:

```bash
sudo -u www-data occ trashbin:cleanup
Remove all deleted files
Remove deleted files for users on backend Database
 freda
 molly
 stash
 rosa
 edward
```

This example removes the deleted files of users `molly` and `freda`:

```bash
sudo -u www-data occ trashbin:cleanup molly freda
Remove deleted files of   molly
Remove deleted files of   freda
```

`trashbin:expire` deletes only expired files according to the `trashbin_retention_obligation` setting in `config.php` (see [the "Deleted Files" section documentation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.htmlconfig_sample_php_parameters.html)). The default is to delete expired files for all users, or you may list users in a space-delimited list.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#two-factor-authentication)Two-Factor Authentication

The following commands only enable or disable the two-factor authentication for a particular user. See the [Two-Factor TOTP](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#two-factor-totp) section for managing the two-factor app provided by ownCloud.

If a two-factor provider app is enabled, it is enabled for all users by default but a user has to opt-in, though the provider can decide whether or not the user has to pass the challenge. In case a user is losing access to the second factor like a lost or defect phone with two-factor SMS/app verification, the user would now be locked out. To give the user access to his account, an admin can temporarily disable the two-factor check for that user via the occ command. After the issue has been fixed, the admin can reenable two-factor authentication for that user.

The following commands are available for the two-factor authentication:

```plaintext
 twofactorauth
  twofactorauth:disable  Disable two-factor authentication for a user.
  twofactorauth:enable   Enable two-factor authentication for a user.
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#disable)Disable

Disable two-factor authentication for a user:

```bash
sudo -u www-data occ twofactorauth:disable [options] [--] <uid>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-35)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The user (user id) to be disabled for two-factor authentication.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#enable)Enable

Enable two-factor authentication for a user:

```bash
sudo -u www-data occ twofactorauth:enable [options] [--] <uid>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-36)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The user (user id) to be (re)enabled for twofactor authentication.</p></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#user-commands)User Commands

The `user` commands provide a range of functionality for managing ownCloud users. This includes: creating and removing users, resetting user passwords, displaying a report which shows how many users you have, and when a user was last logged in. The full list, of commands is:

```plaintext
user
 user:add                            Adds a user
 user:delete                         Deletes the specified user
 user:disable                        Disables the specified user
 user:enable                         Enables the specified user
 user:home                           List home directories and users in a particular home
 user:inactive                       Reports users who are known to owncloud,
                                     but have not logged in for a certain number of days
 user:lastseen                       Shows when the user was logged in last time
 user:list                           List users
 user:list-groups                    List groups for a user
 user:modify                         Modify user details
 user:move-home                      Move a user's home folder to a new location
 user:report                         Shows how many users have access
 user:resetpassword                  Resets the password of the named user
 user:setting                        Read and modify user application settings
 user:sync                           Sync local users with an external backend service
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#creating-users)Creating Users

You can create a new user with the `user:add` command.

```bash
sudo -u www-data occ user:add \
    [--password-from-env] \
    [--display-name [DISPLAY-NAME]] \
    [--email [EMAIL]] \
    [-g|--group [GROUP]] \
    [--] \
    <uid>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-37)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User ID used to login (must only contain a-z, A-Z, 0-9, -, _ and @).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--password-from-env</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Read the password from the <code>OC_PASS</code> environment variable. A password is <strong>not required</strong>, <em>if</em> an email address is provided. If a password is not provided, a temporary one will be generated. It cannot be set to <code>0</code>.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--display-name=[DISPLAY-NAME]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">This corresponds to the <strong>Full Name</strong> on the Users page in your ownCloud Web UI.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--email=[EMAIL]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Email address for the user (optional). The user will be emailed a link to set their password, <em>if</em> email is configured correctly.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-g [GROUP]</code><br><code>--group=[GROUP]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The groups the user should be added to. The group will be created if it does not exist. Multiple values are allowed.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-examples)Command Examples

This example adds new user, Layla Smith, and adds her to the `users` and `db-admins` groups. If either group does not exist, it is created.

Create a user with a password, email address, and display name, and add them to two groups

```bash
sudo -u www-data occ user:add \
  --display-name="Layla Smith" \
  --group="users" \
  --group="db-admins" \
  --email=layla.smith@example.com layla
  Enter password:
  Confirm password:
  The user "layla" was created successfully
  Display name set to "Layla Smith"
  Email address set to "layla.smith@example.com"
  User "layla" added to group "users"
  User "layla" added to group "db-admins"
```

Create a user with a temporary password (the user will receive a link to set their password).

```bash
sudo -u www-data occ user:add \
  --display-name "Layla Smith" \
  --email "***********" \
  --group "users" \
  --group "db-admins" layla

The user "layla" was created successfully
Display name set to "Layla Smith"
Email address set to "************"
User layla added to group users
User layla added to group db-admins
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#deleting-a-user)Deleting A User

To delete a user, you use the `user:delete` command.

```bash
sudo -u www-data occ user:delete [options] [--] <uid>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-38)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The username.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-36)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-f</code><br><code>--force</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Try to force the deletion of the user data even if the user is missing.</p></td></tr></tbody></table>

```bash
sudo -u www-data occ user:delete fred
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#disable-users)Disable Users

Admins can disable users via the occ command too:

```bash
sudo -u www-data occ user:disable <uid>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-39)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The user name.</p></td></tr></tbody></table>

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">Once users are disabled, their connected browsers will be disconnected. Use the following command to enable the user again:</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#enable-users)Enable Users

```bash
sudo -u www-data occ user:enable <uid>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-40)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The user name.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#list-user-home-directories)List User Home Directories

List all available root directories for user homes that are currently in use. For details see [Moving the User Home](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../user/user_management.html#moving-the-user-home) documentation.

This command is complementary when using `user:move-home`.

```bash
sudo -u www-data occ user:home:list-dirs [options]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-37)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Output format (plain, json or json_pretty, default is plain) [default: "plain"].</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples-8)Examples

```bash
sudo -u www-data occ user:home:list-dirs
  - /var/www/owncloud/data
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#list-all-users-for-a-given-home-directory)List all Users For a Given Home Directory

List all users that have their home in a given path. For details see [Moving the User Home](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../user/user_management.html#moving-the-user-home) documentation.

This command is complementary when using `user:move-home`.

```bash
sudo -u www-data occ user:home:list-users [options] [--] [<path>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-41)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>path</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Path where the user home must be located</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-38)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--all</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">List all users for every home path.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Output format (plain, json or json_pretty, default is plain) [default: "plain"].</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples-9)Examples

Note for the example below, some user accounts originated from LDAP.

```bash
sudo -u www-data occ user:home:list-users /var/www/owncloud/data
  - admin
  - aca4c3ec-691d-103b-8380-55a4da3d3a76
  - 9918b614-6a2e-103b-89a7-f5edf5d332f5
  - c298ae18-6a2e-103b-89a8-f5edf5d332f5
  - dbcca7b4-7306-103b-813a-19652cf0a9d2
```

Run the following command to list all users from all available home directories. The example shows, that user `lisa` has been moved to a different home directory with `user:move-home`.

```bash
sudo -u www-data occ user:home:list-users --all
  - /mnt/newhome_1
    - lisa
  - /var/www/owncloud/data
    - admin
    - user01
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#finding-inactive-users)Finding Inactive Users

To view a list of users who’ve not logged in for a given number of days, use the `user:inactive` command.

```bash
sudo -u www-data occ user:inactive [options] [--] <days>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-42)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>&lt;days&gt;</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The number of days (integer) that the user has not logged in since.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-39)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Output format (plain, json or json_pretty, default is plain) [default: "plain"].</p></td></tr></tbody></table>

The example below searches for users inactive for five days or more:

```bash
sudo -u www-data occ user:inactive 5
```

By default, this will generate output in the following format:

```plaintext
- 0:
  - uid: admin
  - displayName: admin
  - inactiveSinceDays: 5
```

You can see a counting number starting with `0`, the user’s user ID, display name and the number of days they’ve been inactive. If you’re passing or piping this information to another application for further processing, you can also use the `--output` switch to change its format. Using the output option `json` will render the output formatted as follows.

```json
[{"uid":"admin","displayName":"admin","inactiveSinceDays":5}]
```

Using the output option `json_pretty` will render the output formatted as follows.

```json
[
    {
        "uid": "admin",
        "displayName": "admin",
        "inactiveSinceDays": 5
    }
]
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#finding-the-users-last-login)Finding the User’s Last Login

To view a user’s most recent login, use the `user:lastseen` command:

```bash
sudo -u www-data occ user:lastseen <uid>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-43)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The user name.</p></td></tr></tbody></table>

Example

```bash
sudo -u www-data occ user:lastseen layla
  layla's last login: 09.01.2015 18:46
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#listing-users)Listing Users

You can list existing users with the `user:list` command.

```bash
sudo -u www-data occ user:list [options] [<search-pattern>]
```

User IDs containing the `search-pattern` string are listed. Matching is not case-sensitive. If you do not provide a search-pattern then all users are listed.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-40)Options

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Output format (plain, json or json-pretty, default is plain).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-a [ATTRIBUTES]</code><br><code>--attributes=[ATTRIBUTES]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Adds more details to the output.<br>Allowed attributes, multiple values possible:<br><code>uid</code>, <code>displayName</code>, <code>email</code>, <code>quota</code>, <code>enabled</code>, <code>lastLogin</code>, <code>home</code>,<br><code>backend</code>, <code>cloudId</code>, <code>searchTerms</code> [default: [<code>displayName</code>]]</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-s</code><br><code>--show-all-attributes</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">All attributes to include from <code>uid</code>, <code>displayName</code>, <code>email</code>, <code>quota</code>,<br><code>enabled</code>, <code>lastLogin</code>, <code>home</code>, <code>backend</code>, <code>cloudId</code>, <code>searchTerms</code></p></td></tr></tbody></table>

This example lists user IDs containing the string `ron`

```bash
sudo -u www-data occ user:list ron
 - aaron: Aaron Smith
```

The output can be formatted in JSON with the output option `json` or `json_pretty`.

```bash
sudo -u www-data occ user:list --output=json_pretty
 {
   "aaron": "Aaron Smith",
   "herbert": "Herbert Smith",
   "julie": "Julie Jones"
 }
```

This example lists all users including the attribute `enabled`.

```bash
sudo -u www-data occ user:list -a enabled
 - admin: true
 - foo: true
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#listing-group-membership-of-a-user)Listing Group Membership of a User

You can list the group membership of a user with the `user:list-groups` command.

```bash
sudo -u www-data occ user:list-groups [options] [--] <uid>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-44)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User ID.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-41)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Output format (plain, json or json-pretty, default is plain).</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples-10)Examples

This example lists group membership of user `julie`:

```bash
sudo -u www-data occ user:list-groups julie
 - Executive
 - Finance
```

The output can be formatted in JSON with the output option `json` or `json_pretty`:

```bash
sudo -u www-data occ user:list-groups --output=json_pretty julie
 [
   "Executive",
   "Finance"
 ]
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#modify-user-details)Modify User Details

This command modifies either the users username or email address.

```bash
sudo -u www-data occ user:modify [options] [--] <uid> <key> <value>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-45)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User ID used to login.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>key</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Key to be changed. Valid keys are: <code>displayname</code> and <code>email</code>.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>value</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The new value of the key.</p></td></tr></tbody></table>

All three arguments are mandatory and can not be empty. Example to set the email address:

```bash
sudo -u www-data occ user:modify carla email foobar@foo.com
```

The email address of `carla` is updated to `foobar@foo.com`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#move-a-users-home-folder)Move a Users Home Folder

This command moves a user’s home folder to a new location. For details see [Moving the User Home](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../user/user_management.html#moving-the-user-home) documentation. Note that moving a users home is only possible for POSIX file systems. Also see the `user:home` commands for additional support.

```bash
sudo -u www-data occ user:move-home <user_id> <new_location>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-46)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>user_id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">ID of the user whose home folder is to be moved.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>new_location</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Absolute path to the parent folder of the new location of the home folder.</p></td></tr></tbody></table>

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content"><div class="paragraph"><p>You must not use temp directories like <code>/tmp</code> and <code>/var/tmp</code> as target directory.</p></div><div class="ulist"><ul><li><p>Any data located in one of the two directories will not survive a reboot</p></li><li><p>For systemd services, they are private sub-directories of the host’s real /tmp/ and /var/tmp/, and thus not system-wide locations anymore, but service-specific ones. For more details see <a href="https://systemd.io/TEMPORARY_DIRECTORIES/">Using /tmp/ and /var/tmp/ Safely</a></p></li></ul></div></td></tr></tbody></table>

Example:

```bash
sudo -u www-data occ user:move-home lisa /mnt/newhome_1
```

This command moves the home directory of user `lisa` to the new location `/mnt/newhome_1`

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#generating-a-user-count-report)Generating a User Count Report

Generate a simple report that counts all users including users on external user authentication servers such as LDAP, and guest users which are created by the guests app.

```bash
sudo -u www-data occ user:report
```

There are no arguments and no options beside the default once to parametrize the output.

```bash
sudo -u www-data occ user:report
+--------------------------+-----+
| User Report              |     |
+--------------------------+-----+
| OCA\User_LDAP\User_Proxy | 23  |
| OC\User\Database         | 100 |
|                          |     |
| guest users              | 20  |
|                          |     |
| total users              | 143 |
|                          |     |
| user directories         | 4   |
+--------------------------+-----+
```

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">A user directory is created, when a local user has logged on the first time after creation. Therefore the difference between <code>OC\User\Database</code> and <code>user directories</code> equals all users which have been created locally, but have not logged on at least once.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#setting-a-users-password)Setting a User’s Password

Resets the password of the named user.

```bash
sudo -u www-data occ user:resetpassword [options] [--] <user>
```

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">Password changes automatically log out <strong>all</strong> connected browsers/devices.</td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-47)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 26.3157%;"> <col style="width: 73.6843%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The user’s name.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-42)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 26.3157%;"> <col style="width: 73.6843%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--password-from-env</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Read the password from the OC_PASS environment variable.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--send-email</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The email ID set while creating the user, will be used to send. link for password reset. This option will also display the link sent to user.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output-link</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The link to reset the password will be displayed.</p></td></tr></tbody></table>

`password-from-env` allows you to set the user’s password from an environment variable. This prevents the password from being exposed to all users via the process list and will only be visible in the history of the user (root) running the command. This also permits creating scripts for adding multiple new users.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">To use <code>password-from-env</code> you must run as "real" root, rather than <code>sudo</code>, because <code>sudo</code> strips environment variables.</td></tr></tbody></table>

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">To use <code>send-email</code>, the ownCloud instance must have email access fully configured.</td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples-11)Examples

Add a new user, called Fred Jones:

```plaintext
export OC_PASS=newpassword
su -s /bin/sh www-data -c 'occ user:add --password-from-env
  --display-name="Fred Jones" --group="users" fred'
The user "fred" was created successfully
Display name set to "Fred Jones"
User "fred" added to group "users"
```

You can reset any user’s password, including administrators (see [Reset Admin Password](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../user/reset_admin_password.html)):

```bash
sudo -u www-data occ user:resetpassword layla
  Enter a new password:
  Confirm the new password:
Successfully reset password for layla
```

You may also use `password-from-env` to reset passwords:

```plaintext
export OC_PASS=newpassword
su -s /bin/sh www-data -c 'occ user:resetpassword \
  --password-from-env \
  layla'
Successfully reset password for layla
```

This example emails a password reset link to the user. Additionally, when the command completes, it outputs the password reset link to the console:

```bash
sudo -u www-data occ user:resetpassword \
  --send-email \
  --output-link \
  layla
The password reset link is: http://localhost:8080/index.php/lostpassword/reset/form/rQAlCjNeQf3aphA6Hraq2/layla
```

If the specified user does not have a valid email address set, then the following error will be output to the console, and the email will not be sent:

```plaintext
Email address is not set for the user layla
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#user-application-settings)User Application Settings

To manage application settings for a user, use the `user:setting` command. This command provides the ability to:

-   Retrieve all settings for an application
    
-   Retrieve a single setting
    
-   Set a setting value
    
-   Delete a setting
    

```bash
sudo -u www-data occ user:setting [options] [--] <uid> [[<app> [<key>]]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-48)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User ID used to login.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>app</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Restrict listing the settings for a given app. [default: ""].</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>key</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Setting key to set, get or delete [default: ""].</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-43)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output=[OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Output format (plain, json or json-pretty, default is plain).</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--ignore-missing-user</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Use this option to ignore errors when the user does not exist.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--default-value=[DEFAULT-VALUE]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">If no default value is set and the config does not exist, the command<br>will exit with 1. Only applicable on get.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--value=[VALUE]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The new value of the setting.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--update-only</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Only updates the value, if it is not set before, it is not being added.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--delete</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Specify this option to delete the config.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--error-if-not-exists</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Checks whether the setting exists before deleting it.</p></td></tr></tbody></table>

The descriptions for the `app` and `key` arguments may not be completely transparent. Here’s a description of both.

 
| Argument | Description |
| --- | --- |
| 
`app`

 | 

When a value is supplied, `user:setting` limits the settings displayed to those for that specific application - assuming that the application is installed and that there are settings available for it. Some example applications are `core`, `files_trashbin`, and `user_ldap`. A complete list cannot be supplied as it is impossible to know the entire list of applications a user could potentially install.

 |
| 

`key`

 | 

This value specifies the setting key to be manipulated (set, retrieved, or deleted) by the `user:setting` command.

 |

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#retrieving-user-settings)Retrieving User Settings

To retrieve settings for a user, you need to call the `user:setting` command and supply at least the user’s user name. You can drill down restricting results to a particular app and a key in the app.

```bash
sudo -u www-data occ user:setting <uid> [<app>] [<key>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-49)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User ID used to log in.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>app</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Restrict listing the settings for a given app. [default: ""].</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>key</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Setting key to set, get or delete [default: ""].</p></td></tr></tbody></table>

**Examples:**

1.  Retrieve all settings set for a given user:
    
    ```bash
    sudo -u www-data occ user:setting layla
      - core:
        - lang: en
      - login:
        - lastLogin: 1465910968
      - settings:
        - email: layla@example.tld
    ```
    
    Here we see that the user has settings for the application `core`, when they last logged in, and what their email address is.
    
2.  Retrieve all settings set restricted to application `core` for a given user:
    
    ```bash
    sudo -u www-data occ user:setting layla core
     - core:
        - lang: en
    ```
    
    In the output, you can see that one setting is in effect, `lang`, which is set to `en`.
    
3.  Retrieve all settings set restricted to application `core`, key `lang` for a given user
    
    ```bash
    sudo -u www-data occ user:setting layla core lang
    ```
    
    This will display the value for that setting, such as `en`.
    

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#setting-and-deleting-a-setting)Setting and Deleting a Setting

```bash
sudo -u www-data occ user:setting [options] [--] <uid> [<app>] [<key>]
```

<table><tbody><tr><td class="icon"><i class="fa icon-important" title="Important"></i></td><td class="content">In case you want to change the email address, use <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#modify-user-details">the <code>user:modify</code> command</a>.</td></tr></tbody></table>

Here’s an example of how you would set the language of the user `layla`.

```bash
sudo -u www-data occ user:setting layla core lang --value=en
```

Deleting a setting is quite similar to setting a setting. In this case, you supply the username, application (or setting category) and key as above. Then, in addition, you supply the `--delete` flag.

```bash
sudo -u www-data occ user:setting layla core lang --delete
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#syncing-user-accounts)Syncing User Accounts

This command syncs users stored in external backend services, such as _LDAP_, _Shibboleth_, and _Samba_, with ownCloud’s, internal user database. However, it’s not essential to run it regularly, unless you have a large number of users whose account properties have changed in a backend outside of ownCloud. When run, it will pick up changes from alternative user backends, such as LDAP, where properties like `cn` or `display name` have changed, and sync them with ownCloud’s user database. If accounts are found that no longer exist in the external backend, you are given the choice of either removing or disabling the accounts.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">It’s also <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.htmlbackground_jobs_configuration.html#available-background-jobs" class="page">one of the commands</a> that you should run on a regular basis to ensure that your ownCloud installation is running optimally.</td></tr></tbody></table>

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">This command replaces the old <code>show-remnants</code> functionality, and brings the LDAP feature more in line with the rest of ownCloud’s functionality.</td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-11)Usage

```plaintext
user:sync [options] [--] [<backend-class>]
```

Synchronize users from a given backend to the accounts table.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-50)Arguments:

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 38.4615%;"> <col style="width: 61.5385%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>backend-class</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The quoted PHP class name for the backend, e.g.,<br>- LDAP: <code>"OCA\User_LDAP\User_Proxy"</code><br>- Samba: <code>"OCA\User\SMB"</code><br>- Shibboleth: <code>"OCA\User_Shibboleth\UserBackend"</code><br></p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-44)Options

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 38.4615%;"> <col style="width: 61.5385%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-l</code><br><code>--list</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">List all enabled backend classes.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-u [UID]</code><br><code>--uid=[UID]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Sync only the user with the given user id.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-s</code><br><code>--seenOnly</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Sync only seen users.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-c</code><br><code>--showCount</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Calculate user count before syncing.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-m [MISSING-ACCOUNT-ACTION]</code><br><code>--missing-account-action[=MISSING-ACCOUNT-ACTION]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Action to take if the account isn’t connected to a backend any longer.<br>Options are <code>disable</code> and <code>remove</code>.<br>Note that removing the account will also remove the stored data and files for that account</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-r</code><br><code>--re-enable</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">When syncing multiple accounts re-enable accounts that are disabled in ownCloud but available in the synced backend.</p></td></tr></tbody></table>

Below are examples of how to use the command with an _LDAP_, _Samba_, and _Shibboleth_ backend.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#ldap)LDAP

```bash
sudo -u www-data occ user:sync "OCA\User_LDAP\User_Proxy"
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#samba)Samba

```bash
sudo -u www-data occ user:sync "OCA\User\SMB" -vvv
```

Below are examples of how to use the command with the **LDAP** backend along with example console output.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-1)Example 1

```bash
sudo -u www-data occ user:sync "OCA\User_LDAP\User_Proxy" -m disable -r
  Analysing all users ...
      6 [============================]

  No removed users have been detected.

  No existing accounts to re-enable.

  Insert new and update existing users ...
      4 [============================]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-2-2)Example 2

```bash
sudo -u www-data occ user:sync "OCA\User_LDAP\User_Proxy" -m disable -r
  Analysing all users ...
      6 [============================]

  Following users are no longer known with the connected backend.
  Disabling accounts:
  9F625F70-08DD-4838-AD52-7DE1F72DBE30, Bobbie, bobbie@example.org disabled
  53CDB5AC-B02E-4A49-8FEF-001A13725777, David, dave@example.org disabled
  34C3F461-90FE-417C-ADC5-CE97FE5B8E72, Carol, carol@example.org disabled

  No existing accounts to re-enable.

  Insert new and update existing users ...
      1 [============================]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-3-2)Example 3

```bash
sudo -u www-data occ user:sync "OCA\User_LDAP\User_Proxy" -m disable -r
  Analysing all users ...
      6 [============================]

  Following users are no longer known with the connected backend.
  Disabling accounts:
  53CDB5AC-B02E-4A49-8FEF-001A13725777, David, dave@example.org skipped, already disabled
  34C3F461-90FE-417C-ADC5-CE97FE5B8E72, Carol, carol@example.org skipped, already disabled
  B5275C13-6466-43FD-A129-A12A6D3D9A0D, Alicia3, alicia3@example.org disabled

  Re-enabling accounts:
  9F625F70-08DD-4838-AD52-7DE1F72DBE30, Bobbie, bobbie@example.org enabled

  Insert new and update existing users ...
      1 [============================]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-4-2)Example 4

```bash
sudo -u www-data occ user:sync "OCA\User_LDAP\User_Proxy" -m disable -r
  Analysing all users ...
      6 [============================]

  No removed users have been detected.

  Re-enabling accounts:
  53CDB5AC-B02E-4A49-8FEF-001A13725777, David, dave@example.org enabled
  34C3F461-90FE-417C-ADC5-CE97FE5B8E72, Carol, carol@example.org enabled
  B5275C13-6466-43FD-A129-A12A6D3D9A0D, Alicia3, alicia3@example.org enabled

  Insert new and update existing users ...
      4 [============================]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-5-2)Example 5

```bash
sudo -u www-data occ user:sync "OCA\User_LDAP\User_Proxy" -m remove
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-6-2)Example 6

```bash
sudo -u www-data occ user:sync "OCA\User_LDAP\User_Proxy"
If unknown users are found, what do you want to do with their accounts? (removing the account will also remove its data)
[0] disable
[1] remove
[2] ask later
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#syncing-via-cron-job)Syncing via cron job

Here is an example for syncing with LDAP four times a day on Ubuntu:

```bash
crontab -e -u www-data
```

```plaintext
* */6 * * * /usr/bin/php /var/www/owncloud/occ user:sync -vvv \
    --missing-account-action="disable" \
    -n "OCA\User_LDAP\User_Proxy"
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#versions)Versions

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">These commands are only available when the "Versions" app (<code>files_versions</code>) is enabled. These commands are not available in <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#maintenance-commands">single-user (maintenance) mode</a>.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#versionscleanup)versions:cleanup

`versions:cleanup` can delete all versioned files, as well as the `files_versions` folder, for either specific users, or for all users.

```bash
sudo -u www-data occ versions:cleanup [<user_id>]...
```

Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 23.913%;"> <col style="width: 76.087%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>user_id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Delete versions of the given user(s), if no user is given all versions will be deleted.</p></td></tr></tbody></table>

The example below deletes all versioned files for all users:

```bash
sudo -u www-data occ versions:cleanup
Delete all versions
Delete versions for users on backend Database
  freda
  molly
  stash
  rosa
  edward
```

You can delete versions for specific users in a space-delimited list:

```bash
sudo -u www-data occ versions:cleanup freda molly
Delete versions of   freda
Delete versions of   molly
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#versionsexpire)versions:expire

`versions:expire` deletes only expired files according to the `versions_retention_obligation` setting in `config.php` (see the File versions section in config\_sample\_php\_parameters). The default is to delete expired files for all users, or you may list users in a space-delimited list.

```bash
sudo -u www-data occ versions:expire [<user_id>]...
```

Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 23.913%;"> <col style="width: 76.087%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>user_id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Expire file versions of the given user(s), if no user is given file versions for all users will be expired.</p></td></tr></tbody></table>

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#apps-commands)Apps Commands

This command reference covers the ownCloud maintained apps commands, which are only available if the respective app is installed and enabled.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#activity)Activity

The `activity` command is used for sending automated activity email notifications in ownCloud server.

```plaintext
 activity
  activity:send-emails  Send all pending activity emails now
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#send-emails-now)Send Emails Now

The `activity:send-emails` command sends all pending activity emails immediately, regardless of the time they are scheduled.

```bash
sudo -u www-data occ activity:send-emails
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#manage-rename-and-move-action-notifications)Manage Rename and Move Action Notifications

Starting with Activity app version 2.7.0, rename and move action notifications can be sent. This feature is disabled by default and must be enabled manually.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#enable-rename-and-move-action-notifications)Enable Rename and Move Action Notifications

```bash
sudo -u www-data occ config:app:set activity enable_move_and_rename_activities --value "yes"
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#disable-rename-and-move-action-notifications)Disable Rename and Move Action Notifications

```bash
sudo -u www-data occ config:app:set activity enable_move_and_rename_activities --value "no"
```

or

```bash
sudo -u www-data occ config:app:delete activity enable_move_and_rename_activities
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#anti-virus)Anti-Virus

Marketplace URL: [Anti-Virus](https://marketplace.owncloud.com/apps/files_antivirus)

Use these commands to configure the Anti-Virus app. Parametrisation must be done with the `occ config` command set.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#list-the-current-settings)List the Current Settings

```bash
sudo -u www-data occ config:list files_antivirus
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-the-setting)Set the Setting

To set a new value, use the command below and replace `<Key>` and value `<Value>` accordingly.

```bash
sudo -u www-data occ config:app:set files_antivirus <Key> --value=<Value> --update-only
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#antivirus-mode-string)Antivirus Mode \[string\]

Antivirus Configuration.

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>av_mode</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">'executable'</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Possible Values</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">'executable'<br>'daemon'<br>'socket'</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#antivirus-socket-string)Antivirus Socket \[string\]

Antivirus Socket.

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>av_socket</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">'/var/run/clamav/clamd.ctl'</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#antivirus-host-string)Antivirus Host \[string\]

Hostname or IP address of Antivirus Host.

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>av_host</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#antivirus-port-integer)Antivirus Port \[integer\]

Port number of Antivirus Host, 1-65535.

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>av_port</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Possible Values</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">1-65535</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#antivirus-command-line-options-string)Antivirus Command Line Options \[string\]

Extra command line options (comma-separated).

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>av_cmd_options</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#antivirus-path-to-executable-string)Antivirus Path to Executable \[string\]

Path to clamscan executable.

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>av_path</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">'/usr/bin/clamscan'</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#antivirus-maximum-filesize-integer)Antivirus Maximum Filesize \[integer\]

File size limit, -1 means no limit.

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>av_max_file_size</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">'-1'</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Possible Values</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">'-1'<br>integer number</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#antivirus-maximum-stream-length-integer)Antivirus Maximum Stream Length \[integer\]

Max Stream Length.

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>av_stream_max_length</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">'26214400'</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#antivirus-action-string)Antivirus Action \[string\]

When infected files were found during a background scan.

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>av_infected_action</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">'only_log'</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Possible Values</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">'only_log'<br>'delete'</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#antivirus-scan-process-string)Antivirus Scan Process \[string\]

Define scan process.

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>av_scan_background</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">'true'</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Possible Values</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">'true'<br>'false'</p></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#auditing)Auditing

Marketplace URL: [Auditing](https://marketplace.owncloud.com/apps/admin_audit)

Tracks various activities and actions of your users and admins. For details, please see the [Auditing](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../enterprise/logging/admin_audit.html) documentation.

Ignore all CLI triggered events.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-or-change-ignore-cli-events)Set or Change Ignore CLI Events

To ignore all CLI triggered events, you can set the following option, defaults to track cli events:

```bash
sudo -u www-data occ config:app:set \
     "admin_audit ignore_cli_events" \
     --value "yes"
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#get-value-of-ignore-cli-events)Get Value of Ignore CLI Events

This command reads the value of `admin_audit ignore_cli_events`:

```bash
sudo -u www-data occ config:app:get "admin_audit ignore_cli_events"
```

```plaintext
yes
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#delete-ignore-cli-events)Delete Ignore CLI Events

This command completely removes the key and the value:

```bash
sudo -u www-data occ config:app:delete "admin_audit ignore_cli_events"
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#brute-force-protection)Brute Force Protection

Marketplace URL: [Brute-Force Protection](https://marketplace.owncloud.com/apps/brute_force_protection)

Use these commands to configure the Brute Force Protection app. Parametrisation must be done with the `occ config` command set. The combination of `uid` and `IP address` is used to trigger the ban.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#list-the-current-settings-2)List the Current Settings

```bash
sudo -u www-data occ config:list brute_force_protection
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-the-setting-2)Set the Setting

To set a new value, use the command below and replace `<Key>` and value `<Value>` accordingly.

```bash
sudo -u www-data occ config:app:set brute_force_protection <Key> --value=<Value> --update-only
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#fail-tolerance-attempts)Fail Tolerance \[attempts\]

Number of wrong attempts to trigger the ban.

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>brute_force_protection_fail_tolerance</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">3</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#time-threshold-seconds)Time Threshold \[seconds\]

Time in which the number of wrong attempts must occur to trigger the ban.

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>brute_force_protection_time_threshold</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">60</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#ban-period-seconds)Ban Period \[seconds\]

Time how long the ban will be active if triggered.

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Key</p></td><td class="tableblock halign-left valign-top"><p class="tableblock"><code>brute_force_protection_ban_period</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock">Default</p></td><td class="tableblock halign-left valign-top"><p class="tableblock">300</p></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#calendar)Calendar

Marketplace URL: [Calendar](https://marketplace.owncloud.com/apps/calendar)

For commands for managing the calendar, please see the DAV Command section in the occ core command set.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#contacts)Contacts

Marketplace URL: [Contacts](https://marketplace.owncloud.com/apps/contacts)

For commands for managing contacts, please see the DAV Command section in the occ core command set.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#custom-groups)Custom Groups

Marketplace URL: [Custom Groups](https://marketplace.owncloud.com/apps/customgroups)

Use these commands to configure the Custom Groups app.

Parameterization should be done with the `occ config` command set, though some but not all settings result in an entry in config.php which also can be set manually.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#get-a-current-setting)Get a Current Setting

You can get the value of a current setting. For details how to do so see the [Config Command Set](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#config-commands).

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#disallow-admin-access)Disallow Admin Access

By default, administrators can administrate custom groups of an instance. When changed, only group admins can administrate custom groups. You can change this behaviour with the following command:

```bash
sudo -u www-data occ config:system:set \
  customgroups.disallow-admin-access-all \
  --type boolean --value true
```

This occ command will create a key-value pair in your config.php which must be writable for the webserver user. You can also do this manually by adding the following key in config.php:

```ini
  'customgroups.disallow-admin-access-all' => true,
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#disallow-members-of-defined-groups)Disallow Members of Defined Groups

You can hide custom groups from a user’s personal settings page based on a user’s group membership. This makes it easier to collect users you want to exclude into defined groups which will be further used for this setting:

```bash
sudo -u www-data occ config:system:set \
  customgroups.disallowed-groups \
  --type json \
  --value '["no_guest_app_users", "project5"]'
```

This occ command will create a key-value pair in your config.php which must be writable for the webserver user to be set. You can also set this manually by adding the following key in config.php:

```php
  'customgroups.disallowed-groups' =>
  array (
    0 => 'no_guest_app_users',
    1 => 'project5',
  ),
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#restrict-group-creation)Restrict Group Creation

This setting defines if ordinary users are allowed to create custom groups. By default, all users can create custom groups, but this can be restricted to admins (if allowed as above) and group-admins. Values to be set can be 'true' and 'false', defaults to 'false'.

```bash
sudo -u www-data occ config:app:set \
  customgroups \
  only_subadmin_can_create \
  --value 'true'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#restrict-add-or-remove-group-members)Restrict Add or Remove Group Members

This setting defines if an existing ordinary group member is allowed to add other users to the target group or remove them. By default, all users can add members to groups, but this can be restricted to admins (if allowed as above) and group-admins. Values to be set can be 'yes' and 'no', defaults to 'no'.

```bash
sudo -u www-data occ config:app:set \
  core \
  shareapi_only_share_with_group_members \
  --value 'yes'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#allow-duplicate-group-display-names)Allow Duplicate Group Display Names

This setting allows the creation of multiple groups with the same display name. By default, group display names must be unique, but it can be be allowed to have multiple identical group display names. Values to be set can be 'true' and 'false', defaults to 'false'.

```bash
sudo -u www-data occ config:app:set \
  customgroups \
  allow_duplicate_names \
  --value 'false'
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#data-exporter)Data Exporter

This app is only available as a [git clone](https://github.com/owncloud/data_exporter.git). See the [Data Exporter](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../maintenance/export_import_instance_data.html) description for more information how to install this app. Import and export users from one ownCloud instance in to another. The export contains all user-settings, files and shares.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#export-user-data)Export User Data

```
instance:export:user <userId> <exportDirectory>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-51)Arguments

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>userId</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User to export.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>exportDirectory</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Path to the directory to export data to.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#import-user-data)Import User Data

```
instance:import:user [options] [--] <importDirectory>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-52)Arguments

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>userId</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User to export.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>importDirectory</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Path to the directory to import data from.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-45)Options

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-a [UID]</code><br><code>--as=[UID]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Import the user under a different user id.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#migrate-shares)Migrate Shares

```
instance:export:migrate:share <userId> <remoteServer>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-53)Arguments

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>userId</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The exported userId whose shares we want to migrate.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>remoteServer</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The remote ownCloud server where the exported user is now, for example "https://myown.server:8080/owncloud".</p></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#file-lifecycle-management)File Lifecycle Management

Marketplace URL: [File Lifecycle Management](https://marketplace.owncloud.com/apps/files_lifecycle)

The File Lifecycle Management extension allows service providers to manage the lifecycle of files within ownCloud. For details please see the [File Lifecycle Management](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../enterprise/file_management/files_lifecycle.html) documentation.

The `lifecycle` commands configure the File Lifecycle Management app.

App Configuration

```plaintext
lifecycle
 lifecycle:archive          Archive files which have reached a certain age
 lifecycle:expire           Expire files from Archive which have reached a certain age
 lifecycle:restore          Restore files from Archive to the original location
 lifecycle:restore-all      Restore all archived files in the system back to their
                            original locations
 lifecycle:set-upload-time  Set upload time for files which do not have one
```

`config:app` commands configure the Policies for the File Lifecycle Management app.

Policy Configuration

```plaintext
 config:app:get|set
 files_lifecycle archive_period   Number of days since upload (or restore)
                                  after which files will be archived
 files_lifecycle expire_period    Number of days since archiving after which files will
                                  be permanently deleted
 files_lifecycle excluded_groups  Define groups of users that are exempt from the
                                  lifecycle policies
 files_lifecycle policy           Restoration policies for users
 files_lifecycle disable_ui       Enable/Disable the user interface components
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#app-configuration)App Configuration

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#archive-aged-files)Archive Aged Files

Archive files which have reached a certain age.

```bash
sudo -u www-data occ lifecycle:archive [options]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-46)Options

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-d,<br>--dryrun[=DRYRUN]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Don’t apply changes to the system [default: false]</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#expire-files-from-archive)Expire Files From Archive

Expire files from archive which have reached a certain age.

```bash
sudo -u www-data occ lifecycle:expire [options]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-47)Options

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-d,<br>--dryrun[=DRYRUN]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Don’t apply changes to the system [default: false]</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#restore-files-from-archive)Restore Files From Archive

Restore files from archive to the original location. Note that the location for archived files always follows the pattern `$userid/archive/files/…`

```bash
sudo -u www-data occ lifecycle:restore <path>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-54)Arguments

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>path</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Enter path to a folder or to a single file</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-8)Example

Restore all files in folder `project1` for user alice with path `/work/projects/project1`

```bash
sudo -u www-data occ lifecycle:restore /alice/archive/files/work/projects/project1
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#restore-all-files-from-archive)Restore All Files From Archive

Restore all archived files for all users in the system back to their original locations. This command has no additional arguments or options.

```bash
sudo -u www-data occ lifecycle:restore-all
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-default-upload-time)Set Default Upload Time

Set upload time for files which do not have one.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">Files without upload time are silently skipped by <code>occ lifecycle:archive</code> This can happen with files that were uploaded before the files_lifecycle app was configured or when it was temporarily disabled and therefore do not have an upload time set.</td></tr></tbody></table>

```bash
sudo -u www-data occ lifecycle:set-upload-time [options] [--] <date>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-55)Arguments

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>date</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Date in format y-m-d. Example: 2018-07-23</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-48)Options

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-d,<br>--dryrun[=DRYRUN]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Don’t apply changes to the system [default: false]</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#policy-configuration)Policy Configuration

All policy configurations are set and queried with the `config:app` command set. The examples below set a value. To query a value use `config:app:get` and the corresponding key without any options or attributes.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-the-archive-period)Set the Archive Period

The number of days since upload (or restore) after which files will be archived.

The following example command sets the time passed since upload (or restore) for archiving files to 90 days.

```bash
sudo -u www-data occ config:app:set files_lifecycle archive_period --value='90'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-the-expire-period)Set the Expire Period

The number of days since archiving after which files will be permanently deleted.

The following example command sets the time passed to delete files to 180 days.

```bash
sudo -u www-data occ config:app:set files_lifecycle expire_period --value='180'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-groups-to-be-excluded)Set Groups to be Excluded

Define groups of users that are exempt from the lifecycle policies (comma-separated group ids).

The following example command specifies groups whose members will not be part of the lifecycle management.

```bash
sudo -u www-data occ config:app:set files_lifecycle excluded_groups --value='group1,group2'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#restoration-policy-for-users)Restoration Policy for Users

Set a policy who can restore files. Use the value `soft` for self-service and `hard` for admin/groupadmin-service.

The following example command sets the restoration policy for users to `soft` (default).

```bash
sudo -u www-data occ config:app:set files_lifecycle policy --value='soft'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#disable-user-interface)Disable User Interface

Disable the whole user interface for the File Lifecycle Management app.

The following example command disables the user interface for the File Lifecycle Management app.

```bash
sudo -u www-data occ config:app:set files_lifecycle disable_ui --value='yes'
```

You can reenable it by deleting the key:

```bash
sudo -u www-data occ config:app:delete files_lifecycle disable_ui
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#full-text-search)Full Text Search

Use these commands when you manage full text search related tasks.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-description-6)Command Description

```plaintext
search
  search:index:create    Create initial Search Index for one or all users.
                         This command could not update the search index correctly
                         after the initial indexing.
  search:index:rebuild   Rebuild the search index for a given User.
                         If you want to rebuild the whole index, run
                         `search:index:reset` and then `search:index:create --all`
  search:index:reset     Reset the index
  search:index:update    Update the search index by running all pending background jobs.
```

In addition to the settings provided by the Full Text Search app, you can set/read additional options via the `occ config:app` commands. These are [Set App Modes](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-app-modes), [Index Metadata Only](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#index-metadata-only) and [Limit Metadata Search for Groups](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#limit-metadata-search-for-groups).

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#create-the-full-text-search-index)Create the Full Text Search Index

The command `search:index:create` creates the initial full text search index for one or all users.

```bash
sudo -u www-data occ search:index:create <user_id> (<user_id>)...
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-56)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 16.6666%;"> <col style="width: 83.3334%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>&lt;user_id&gt;</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The ID of the user (or space-separated list of user IDs) to create a full text search index for. A full text search index is created for all users, if this value is omitted.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-49)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 16.6666%;"> <col style="width: 83.3334%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--all</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Will create index for all files of all known users.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-1-2)Example 1

This example creates a full text search index for the user with user id `testuser`.

```bash
sudo -u www-data occ search:index:create testuser

Indexing user testuser
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-2-3)Example 2

This example creates a full text search index for the users with user ids `admin` and `testuser`.

```bash
sudo -u www-data occ search:index:create admin testuser

Indexing user admin
Indexing user testuser
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#rebuild-the-full-text-search-index)Rebuild the Full Text Search Index

Rebuild the search index for a given user.  
If you want to rebuild the whole index, run `search:index:reset` and then `search:index:create --all`.

```bash
sudo -u www-data occ search:index:rebuild <user_id> (<user_id>)...
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-57)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 16.6666%;"> <col style="width: 83.3334%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>&lt;user_id&gt;</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Provide a user ID. This argument is required.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-50)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 16.6666%;"> <col style="width: 83.3334%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-q</code> <code>--quiet</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Do not output any message.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-f</code> <code>--force</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Use this option to reset the index without further questions.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-1-3)Example 1

This example rebuilds the full text search index for the user with user ID `testuser`.

Rebuild the index for a single user

```bash
sudo -u www-data occ search:index:rebuild testuser

Indexing user testuser

This will delete all full text search index data for testuser! Do you want to proceed?
  [0] no
  [1] yes
 > 1
Rebuilding full text search Index for testuser
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-2-4)Example 2

This example rebuilds the full text search index for the users with user IDs `admin` and `testuser`.

Rebuild the index for multiple users

```bash
sudo -u www-data occ search:index:rebuild admin testuser

This will delete all search index data for admin, testuser! Do you want to proceed?
  [0] no
  [1] yes
 > 1
Rebuilding Search Index for admin
Rebuilding Search Index for testuser
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#rebuild-the-entire-index)Rebuild the Entire Index

The entire index can be rebuilt by running the following two commands:

```
sudo -u www-data occ search:index:reset
sudo -u www-data occ search:index:create --all
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#reset-the-full-text-search-index)Reset the Full Text Search Index

The command `search:index:reset` resets (recreates and clears) the full text search index for all users.

```bash
sudo -u www-data occ search:index:reset
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-58)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 16.6666%;"> <col style="width: 83.3334%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-f</code> <code>--force</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Use this option to reset the index without further questions.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-9)Example

```bash
sudo -u www-data occ search:index:reset
This will delete the whole search index! Do you want to proceed?
  [0] no
  [1] yes
 > 1
Search index has been reset.
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#update-the-full-text-search-index)Update the Full Text Search Index

Updates to the search index due to changed content or changed metadata are happening via background jobs that are added to a queue. These background jobs are normally run by the ownCloud cronjob. The command `search:index:update` updates the full text search index by running all pending background jobs.

```bash
sudo -u www-data occ search:index:update
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-59)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 16.6666%;"> <col style="width: 83.3334%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-q</code> <code>--quiet</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Suppress all output from the command.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#example-10)Example

This example updates the full text search index for all users.

```bash
sudo -u www-data occ search:index:update
Start Updating the Elastic search index:
No pending jobs found.
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-app-modes)Set App Modes

To do an initial full indexing without the Full Text Search app interfering, it can be put in passive mode. See the [App Modes](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#configuration/general_topics/search.html#app-modes) section in the Full Text Search description for details.

```bash
sudo -u www-data occ config:app:set \
    search_elastic mode --value passive
```

Switching back to active mode can be done by running the following command:

```bash
sudo -u www-data occ config:app:set \
    search_elastic mode --value active
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#restrict-search-results)Restrict Search Results

Search results can be restricted in different ways, see the [Restrict Search Results](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../general_topics/search.html#restrict-search-results) section in the Full Text Search description for details.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#index-metadata-only)Index Metadata Only

```bash
sudo -u www-data occ config:app:set \
    search_elastic nocontent --value true
```

Switching back to provide all content search results can be done by running the following command:

```bash
sudo -u www-data occ config:app:set \
    search_elastic nocontent --value false
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#limit-metadata-search-for-groups)Limit Metadata Search for Groups

```bash
sudo -u www-data occ config:app:set \
    search_elastic group.nocontent \
    --value group1,group2,"group with blank"
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#ldap-integration)LDAP Integration

Marketplace URL: [LDAP Integration](https://marketplace.owncloud.com/apps/user_ldap)

```plaintext
ldap
 ldap:check-user               Checks whether a user exists on LDAP
 ldap:create-empty-config      Creates an empty LDAP configuration
 ldap:delete-config            Deletes an existing LDAP configuration
 ldap:invalidate-cache         Invalidates the LDAP cache
 ldap:search                   Executes a user or group search
 ldap:set-config               Modifies an LDAP configuration
 ldap:show-config              Shows the LDAP configuration
 ldap:test-config              Tests an LDAP configuration
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#search-for-a-user)Search for a User

Search for an LDAP user, using this syntax:

```bash
sudo -u www-data occ ldap:search [options] [--] <search>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-60)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>search</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The search string (can be empty)</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-51)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--group</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Searches groups instead of users</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--offset=OFFSET</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The offset of the result set. Needs to be a multiple of limit. [default: 0]</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--limit=LIMIT</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Limit the results. 0 means no limit. [default: 15]</p></td></tr></tbody></table>

Note that the search string can be empty to list all users, or groups when the `--group` option is set. In this case, the search string must be declared with `''`. It is by default a prefix search. Start the string with `*` to change to infix (substring) search.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#search-configuration-and-rules)Search Configuration and Rules

Search attributes are configurable in the LDAP wizard (**Settings**  **Admin**  **User Authentication**  **LDAP**) or via an occ command `ldap:set-config` as described below:

General rule

1.  If User/Group _Search Attributes_ are **NOT** defined (empty), the entry defined in the User/Group _Display Name Field_ is used as the search attribute, for details see below.
    
2.  Important when having multiple search attributes, results are unique as long hits correspond to a unique user or group entry.
    

Rules for users

1.  If **User Search Attributes** are defined (not empty) in:
    
    **Settings**  **Admin**  **User Authentication**  **LDAP**  **Advanced**  **User Search Attributes**
    
    `ldapAttributesForUserSearch`
    
    1.  Example
        
        If your search attributes would be `givenName` and `sn` you can find users by first name + last name very quickly. You will find "Terri Hanson" by searching for `te ha`. Trailing whitespace is ignored.
        
    
2.  Else use the **User Display Name Field** which usually defaults to the default displayname attribute "displayname"
    
    **Settings**  **Admin**  **User Authentication**  **LDAP**  **Advanced**  **User Display Name Field**
    
    `ldapUserDisplayName`
    

Rules for groups

1.  If **Group Search Attributes** are defined (not empty) in:
    
    **Settings**  **Admin**  **User Authentication**  **LDAP**  **Advanced**  **Group Search Attributes**
    
    `ldapAttributesForGroupSearch`
    
2.  Else use the **Group Display Name Field** which usually defaults to the default displayname attribute "cn"
    
    **Settings**  **Admin**  **User Authentication**  **LDAP**  **Advanced**  **Group Display Name Field**
    
    `ldapGroupDisplayName`
    

Offset and Limit

The best way understanding `offset` and `limit` is the following table when using `occ ldap:search '' [options]`

 
| Options | Result Set |
| --- | --- |
| 
`--offset 0`  
`--limit 5`

 | 

"A", "B", "C", "D" and "E"

 |
| 

`--offset 5`  
`--limit 5`

 | 

"F", "G", "H", "I" and "J"

 |
| 

`--offset 1`  
`--limit 3`

 | 

"B", "C" and "D"

 |

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples-12)Examples

Searches match at the beginning of the attribute value only. This example searches for `givenNames` that start with 'rob':

```bash
sudo -u www-data occ ldap:search "rob"
```

This will find "robbie", "roberta", and "robin". Broaden the search to find, for example, `jeroboam` with the asterisk wildcard:

```bash
sudo -u www-data occ ldap:search "*rob"
```

The following examples use `offset` and `limit` options:

```bash
sudo -u www-data occ ldap:search "re"
Rebecca OShea (Rebecca.OShea)
Rebecca Vintin (Rebecca.Vintin)
Rebekka Da-Cahuna (Rebekka.Da-Cahuna)
Rekha Cox (Rekha.Cox)
Rekha Craft (Rekha.Craft)
```

```bash
sudo -u www-data occ ldap:search "re" --offset 0 --limit 3
Rebecca OShea (Rebecca.OShea)
Rebecca Vintin (Rebecca.Vintin)
Rebekka Da-Cahuna (Rebekka.Da-Cahuna)
```

```bash
sudo -u www-data occ ldap:search "re" --offset 3 --limit 3
Rekha Cox (Rekha.Cox)
Rekha Craft (Rekha.Craft)
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#check-if-an-ldap-user-exists)Check if an LDAP User Exists

This only works if the ownCloud server is connected to an LDAP server.

```plaintext
ldap:check-user [options] [--] <ocName>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-61)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>ocName</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The user name as used in ownCloud (see e.g. the user’s Federated Cloud ID).</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-52)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--force</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Ignores disabled LDAP configuration</p></td></tr></tbody></table>

Example:

```bash
sudo -u www-data occ ldap:check-user robert
```

`ldap:check-user` will not run a check when it finds a disabled LDAP connection. This prevents users that exist on disabled LDAP connections from being marked as deleted. If you know for sure that the user you are searching for is not in one of the disabled connections and exists on an active connection, use the `--force` option to force a check of all active LDAP connections.

```bash
sudo -u www-data occ ldap:check-user --force robert
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#create-an-empty-ldap-configuration)Create an Empty LDAP Configuration

Create an empty LDAP configuration.

```plaintext
ldap:create-empty-config [<configID>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-62)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>configID</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Create a configuration with the specified id</p></td></tr></tbody></table>

Configurations that you create without assigning a <configID> are automatically assigned IDs.

```bash
sudo -u www-data occ ldap:create-empty-config
   Created new configuration with configID 's01'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#list-and-view-your-configurations)List and View Your Configurations

You can list and view your configurations:

```bash
sudo -u www-data occ ldap:show-config [options] [--] [<configID>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-63)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>configID</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Will show the configuration of the specified id</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-53)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--show-password</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Show LDAP bind password</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output[=OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (plain, json or json_pretty). [default: "plain"]</p></td></tr></tbody></table>

###### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#examples-13)Examples

If you omit the `configID`, all configuration ID’s with their settings are listed:

```bash
sudo -u www-data occ ldap:show-config
```

View the configuration for a single `configID`:

```bash
sudo -u www-data occ ldap:show-config s01
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#delete-an-existing-ldap-configuration)Delete an Existing LDAP Configuration

Deletes an existing LDAP configuration.

```plaintext
 ldap:delete-config <configID>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-64)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>configID</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The configuration ID</p></td></tr></tbody></table>

```bash
sudo -u www-data occ ldap:delete  s01
Deleted configuration with configID 's01'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#invalidate-ldap-cache)Invalidate LDAP Cache

This command invalidates the LDAP cache for all users:

```bash
sudo -u www-data occ ldap:invalidate-cache
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#manipulate-ldap-configurations)Manipulate LDAP Configurations

This command manipulates LDAP configurations.

```bash
sudo -u www-data occ ldap:set-config <configID> <configKey> <configValue>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-65)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>configID</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The configuration ID</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>configKey</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The configuration key</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>configValue</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The new configuration value</p></td></tr></tbody></table>

If a `configKey` allows multiple entries like the key `ldapAttributesForUserSearch`, use semicolons without a whitespace to separate them.

This example sets search attributes:

```bash
sudo -u www-data occ ldap:set-config s01 ldapAttributesForUserSearch "cn;givenname;sn;displayname;mail"
```

Available keys, along with default values for configValue, are listed in the table below.

 
| Configuration | Setting |
| --- | --- |
| 
hasMemberOfFilterSupport

 |  |
| 

hasPagedResultSupport

 |  |
| 

homeFolderNamingRule

 |  |
| 

lastJpegPhotoLookup

 | 

0

 |
| 

ldapAgentName

 | 

cn=admin,dc=owncloudqa,dc=com

 |
| 

ldapAgentPassword

 | 

_\*_

 |
| 

ldapAttributesForGroupSearch

 |  |
| 

ldapAttributesForUserSearch

 |  |
| 

ldapBackupHost

 |  |
| 

ldapBackupPort

 |  |
| 

ldapBase

 | 

dc=owncloudqa,dc=com

 |
| 

ldapBaseGroups

 | 

dc=owncloudqa,dc=com

 |
| 

ldapBaseUsers

 | 

dc=owncloudqa,dc=com

 |
| 

ldapCacheTTL

 | 

600

 |
| 

ldapConfigurationActive

 | 

1

 |
| 

ldapDynamicGroupMemberURL

 |  |
| 

ldapEmailAttribute

 |  |
| 

ldapExperiencedAdmin

 | 

0

 |
| 

ldapExpertUUIDGroupAttr

 |  |
| 

ldapExpertUUIDUserAttr

 |  |
| 

ldapExpertUsernameAttr

 |  |
| 

ldapGroupDisplayName

 | 

cn

 |
| 

ldapGroupFilter

 |  |
| 

ldapGroupFilterMode

 | 

0

 |
| 

ldapGroupFilterObjectclass

 |  |
| 

ldapGroupMemberAssocAttr

 | 

uniqueMember

 |
| 

ldapHost

 | 

ldap://host

 |
| 

ldapIgnoreNamingRules

 |  |
| 

ldapLoginFilter

 | 

(&objectclass=inetOrgPerson(uid=%uid))

 |
| 

ldapLoginFilterAttributes

 |  |
| 

ldapLoginFilterEmail

 | 

0

 |
| 

ldapLoginFilterMode

 | 

0

 |
| 

ldapLoginFilterUsername

 | 

1

 |
| 

ldapNestedGroups

 | 

0

 |
| 

ldapOverrideMainServer

 |  |
| 

ldapPagingSize

 | 

500

 |
| 

ldapPort

 | 

389

 |
| 

ldapQuotaAttribute

 |  |
| 

ldapQuotaDefault

 |  |
| 

ldapTLS

 | 

0

 |
| 

ldapUserDisplayName

 | 

displayName

 |
| 

ldapUserDisplayName2

 |  |
| 

ldapUserFilter

 | 

objectclass=inetOrgPerson

 |
| 

ldapUserFilterGroups

 |  |
| 

ldapUserFilterMode

 | 

0

 |
| 

ldapUserFilterObjectclass

 | 

inetOrgPerson

 |
| 

ldapUuidGroupAttribute

 | 

auto

 |
| 

ldapUuidUserAttribute

 | 

auto

 |
| 

turnOffCertCheck

 | 

0

 |
| 

useMemberOfToDetectMembership

 | 

1

 |

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#test-your-configuration)Test Your Configuration

Tests whether your configuration is correct and can bind to the server.

```bash
sudo -u www-data occ ldap:test-config <configID>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-66)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>configID</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The configuration ID</p></td></tr></tbody></table>

Example:

```bash
sudo -u www-data occ ldap:test-config s01
The configuration is valid and the connection could be established!
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-and-unset-ldap-app-configurations)Set and Unset LDAP App Configurations

```bash
sudo -u www-data occ config:app:set user_ldap updateAttributesInterval --value=7200
```

In the example above, the interval is being set to 7200 seconds. Assuming the above example was used, the command would output the following:

```plaintext
Config value updateAttributesInterval for app user_ldap set to 7200
```

If you want to reset (or unset) the setting, then you can use the following command:

```bash
sudo -u www-data occ config:app:delete user_ldap updateAttributesInterval
```

**Reuse Existing LDAP Accounts if Available**

If you want to allow new LDAP logins to attempt to reuse existing `oc_accounts` entries that match the resolved username attribute, and have backend set to `User_Proxy`, then set the `reuse_accounts` config setting to `yes`.

Below is an example of how to do so.

```bash
sudo -u www-data occ config:app:set user_ldap reuse_accounts --value="yes"
```

This functionality is valuable for several reasons; these are:

-   It handles the situation of when admins mistakenly delete one or more user mappings, and subsequent logins then create new accounts.
    
-   It allows auto-provisioned users with Shibboleth to be moved over to an LDAP server, but be able to continue using ownCloud.
    

<table><tbody><tr><td class="icon"><i class="fa icon-important" title="Important"></i></td><td class="content"><div class="paragraph"><p>This functionality will not work in the following situations:</p></div><div class="olist arabic"><ol class="arabic"><li><p>No user or group account exists with the supplied username.</p></li><li><p>A user or group account exists, but it uses a different backend.</p></li></ol></div></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#market)Market

Marketplace URL: [Market](https://marketplace.owncloud.com/apps/market)

The `market` commands _install_, _uninstall_, _list_, and _upgrade_ applications from the ownCloud Marketplace.

```plaintext
market
  market:install    Install apps from the marketplace. If already installed and
                    an update is available the update will be installed.
  market:uninstall  Uninstall apps from the marketplace.
  market:list       Lists apps as available on the marketplace.
  market:upgrade    Installs new app versions if available on the marketplace
```

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">The user running the update command, which will likely be your webserver user, requires write permission for the <code>/apps</code> respectively <code>apps-external</code> folder.</td></tr></tbody></table>

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">If they don’t have write permission, the command may report that the update was successful, but it may silently fail.</td></tr></tbody></table>

These commands are not available in single-user (maintenance) mode. For more details please see the Maintenance Commands section in the occ core command set.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#install-an-application)Install an Application

Applications can be installed both from [the ownCloud Marketplace](https://marketplace.owncloud.com/) and from a local file archive.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#install-apps-from-the-marketplace)Install Apps From The Marketplace

To install an application from the Marketplace, you need to supply the app’s id, which can be found in the app’s Marketplace URL. For example, the URL for _Two factor backup codes_ is [https://marketplace.owncloud.com/apps/twofactor\_backup\_codes](https://marketplace.owncloud.com/apps/twofactor_backup_codes). So its app id is `twofactor_backup_codes`.

```bash
sudo -u www-data occ market:install <ids> [option]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-67)Arguments

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>ids</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Ids of the apps</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-54)Options

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-l [LOCAL]</code><br><code>--local=[LOCAL]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Optional path to a local app package.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#install-apps-from-a-file-archive)Install Apps From a File Archive

To install an application from a local file archive, you need to supply the path to the archive, and that you pass the `-l` switch. Only `zip`, `gzip`, and `bzip2` archives are supported.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-example)Usage Example

```bash
# Install an app from the marketplace.
sudo -u www-data occ market:install twofactor_backup_codes

# Install an app from a local archive.
sudo -u www-data occ market:install -l /mnt/data/richdocuments-2.0.0.tar.gz
```

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">The target directory has to be <strong>accessible to the webserver user</strong> and you have to <strong>enable</strong> the app afterwards with the <code>occ app:enable</code> command.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#uninstall-an-application)Uninstall an Application

To uninstall an application use the following commands:

```bash
sudo -u www-data occ market:uninstall <ids>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-68)Arguments

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>ids</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Ids of the apps</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#list-apps-from-the-marketplace)List Apps From The Marketplace

This command lists apps available on the marketplace. It returns the ids of the apps.

```bash
sudo -u www-data occ market:list
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#upgrade-an-application)Upgrade an Application

Install new app versions if available on the marketplace by using following commands:

```bash
sudo -u www-data occ market:upgrade <ids> [options]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-69)Arguments

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>ids</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Ids of the apps</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-55)Options

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-l [LOCAL]</code><br><code>--local=[LOCAL]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Optional path to a local app package.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--major</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Allow update to a new major version.</p></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#metrics)Metrics

Marketplace URL: [Metrics](https://marketplace.owncloud.com/apps/metrics)

Monitoring and reporting of ownCloud Server. For details please see the [Metrics](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../enterprise/reporting/metrics.html) documentation.

Set a secret for authenticating requests at the endpoint.

In case you want to generate a random secret, use the following example command:  

```bash
echo $(tr -dc 'a-z0-9' < /dev/urandom | head -c 20)
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-or-change-the-secret)Set or change the Secret

Writes the key `metrics_shared_secret` and the secret to config.php. The name must not be changed and be exactly as written.

Note: You can also set the config key/value manually into your config.php file.

```bash
sudo -u www-data occ config:system:set \
     "metrics_shared_secret" \
     --value "your-metrics-secret"
```

The above command adds the following at the end of `config.php`:

```php
'metrics_shared_secret' => 'your-metrics-secret',
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#get-the-secret)Get the Secret

This command reads the value of the `metrics_shared_secret` key from config.php:

```bash
sudo -u www-data occ config:system:get "metrics_shared_secret"
```

```plaintext
your-metrics-secret
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#delete-the-secret)Delete the Secret

This command completely removes the key and the value from config.php:

```bash
sudo -u www-data occ config:system:delete "metrics_shared_secret"
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#password-policy)Password Policy

Marketplace URL: [Password Policy](https://marketplace.owncloud.com/apps/password_policy)

Command to expire a user or group of users’ passwords.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-description-7)Command Description

```bash
sudo -u www-data occ user:expire-password <uid> [<expiredate>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-70)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 19.6078%;"> <col style="width: 80.3922%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>uid</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">User ID.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>expiredate</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The date and time when a password expires,<br>e.g. <code>2019-01-01 14:00:00 CET</code> or -1 days.</p></td></tr></tbody></table>

<table><tbody><tr><td class="icon"><i class="fa icon-tip" title="Tip"></i></td><td class="content">The expiry date can be provided using any of <a href="https://www.php.net/manual/datetime.formats.php">PHP’s supported date and time formats</a>.</td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-56)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 21.9047%;"> <col style="width: 78.0953%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-a, --all</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Will add password expiry to all known users. uid and group option are discarded if the option is provided by user.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-u [UID]</code><br><code>--uid=[UID]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The uid of the user to expire the password for.<br>To expire the password of multiple users, pass the <code>-u</code> or <code>--uid</code> option multiple times, as in this example: <code>--uid "Alice" --uid "Bob"</code>.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-g [GROUP]</code><br><code>--group=[GROUP]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Add password expiry to user(s) in one or more groups.<br>This option can be used as <code>--group foo --group bar</code> to add expiry passwords for users in multiple groups.</p></td></tr></tbody></table>

If an expiry date is not supplied, the password will expire with immediate effect. This is because the password will be set as being expired 24 hours before the command was run. For example, if the command was run at `2018-07-**12** 13:15:28 UTC`, then the password’s expiry date will be set to `2018-07-**11** 13:15:28 UTC`.

After the command completes, console output, similar to that below, confirms when the user’s password is set to expire.

```
The password for frank is set to expire on 2018-07-12 13:15:28 UTC.
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-examples-2)Command Examples

```bash
# The password for user "frank" will be set as being expired 24 hours before the command was run.
sudo -u www-data occ user:expire-password -u frank

# Expire the user "frank"'s password in 2 days time.
sudo -u www-data occ user:expire-password -u frank '+2 days'

# Expire the user "frank"'s password on the 15th of August 2005, at 15:52:01 in the local timezone.
sudo -u www-data occ user:expire-password --uid frank '2005-08-15T15:52:01+00:00'

# Expire the user "frank"'s password on the 15th of August 2005, at 15:52:01 UTC.
sudo -u www-data occ user:expire-password --uid frank '15-Aug-05 15:52:01 UTC'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#caveats)Caveats

Please be aware of the following implications of enabling or changing the password policy’s "**days until user password expires**" option.

-   Administrators need to run the `occ user:expire-password` command to initiate expiry for new users.
    
-   Passwords will never expire for users who have **not** changed their initial password, because they do not have a password history. To force password expiration use the `occ user:expire-password` command.
    
-   A password expiration date will be set after users change their password for the first time. To force password expiration use the `occ user:expire-password` command.
    
-   Passwords changed for the first time, will expire based on the **active** password policy. If the policy is later changed, it will not update the password’s expiry date to reflect the new setting.
    
-   Password expiration dates of users where the administrator has run the `occ user:expire-password` command **won’t** automatically update to reflect the policy change. In these cases, Administrators need to run the `occ user:expire-password` command again and supply a new expiry date.
    

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#ransomware-protection-enterprise-edition-only)Ransomware Protection (Enterprise Edition only)

Marketplace URL: [Ransomware Protection](https://marketplace.owncloud.com/apps/ransomware_protection)

Use these commands to help users recover from a Ransomware attack. You can find more information about the application in the [Ransomware Protection documentation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../enterprise/security/ransomware-protection/index.html).

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#command-description-8)Command Description

```bash
sudo -u www-data occ ransomguard:scan <timestamp> <user>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-71)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>&lt;timestamp&gt;</code><br><code>&lt;user&gt;</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Report all changes in a user’s account, starting from timestamp.</p></td></tr></tbody></table>

```bash
sudo -u www-data occ ransomguard:restore <timestamp> <user>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-72)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>&lt;timestamp&gt;</code><br><code>&lt;user&gt;</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Revert all operations in a user account after a point in time.</p></td></tr></tbody></table>

```bash
sudo -u www-data occ ransomguard:lock <user>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-73)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>&lt;user&gt;</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Set a user account as read-only for ownCloud and other WebDAV clients when malicious activity is suspected.</p></td></tr></tbody></table>

```bash
sudo -u www-data occ ransomguard:unlock <user>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-74)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>&lt;user&gt;</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Unlock a user account after ransomware issues have been resolved.</p></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#collabora-online-secure-view)Collabora Online / Secure View

Marketplace URL: [Collabora Online](https://marketplace.owncloud.com/apps/richdocuments)

Collabora Online allows you to work with all kinds of collabora office documents inside ownCloud for improved productivity. For details, see the [Collabora Online / Secure View](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../enterprise/collaboration/collabora_secure_view.html) documentation.

`config:app` commands to configure the Collabora Online app.

```plaintext
 config:app:get|set
 richdocuments wopi_url            WOPI Server URL
 richdocuments secure_view_option  Enable Secure View
 richdocuments watermark_text      Watermark pattern displayed in the document
 richdocuments open_in_new_tab     Open documents in a new tab
 richdocuments secure_view_can_print_default    Define if documents can be printed or exported
 richdocuments secure_view_open_action_default  Enforce displaying the watermark by default
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#app-configuration-2)App Configuration

All app configurations are set and queried with the `config:app` command set. The examples below set a value. To query a value use `config:app:get` and the corresponding key without any options or attributes. Note that values have to be set in single quotes.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#define-the-wopi-server-url)Define the WOPI Server URL

WOPI Server URL

This command sets the WOPI Server to `[IP/URL]:port`  
`[IP/URL]:port` can be any IP/URL plus the port on which the WOPI server can be accessed like:

-   `a.b.c.d`
    
-   `[http://a.b.c.d:8098](http://a.b.c.d:8098)`
    
-   `[https://rd.yourdomain.com](https://rd.yourdomain.com)`
    
-   …
    

Adding the port is only necessary when not using standard ports.

```bash
sudo -u www-data occ config:app:set richdocuments wopi_url --value='[IP/URL]:port'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#enable-secure-view)Enable Secure View

Enable Secure View (possible values: true/false, default: false).

The following example command enables secure view globally on the system:

```bash
sudo -u www-data occ config:app:set richdocuments secure_view_option --value='true'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#define-the-watermark-pattern-displayed)Define the Watermark Pattern Displayed

A watermark pattern is displayed in the document when it is viewed. It can be an arbitrary string. The keyword {viewer-email} will be replaced with the current user’s email address in the document watermark. If an email address is not set, then the user’s display name will be used.

The following example command sets the watermark pattern displayed in the document:

```bash
sudo -u www-data occ config:app:set richdocuments watermark_text --value='Restricted to {viewer-email}'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#open-documents-in-a-new-tab)Open Documents in a New Tab

By default, documents will open in a new tab if not otherwise defined. You can change this behaviour with a command (possible values: true/false, default: false).

The following example command makes documents open in the same tab:

```bash
sudo -u www-data occ config:app:set richdocuments open_in_new_tab --value='false'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#define-the-print-and-exporting-option)Define the Print and Exporting Option

Enable documents in secure view mode to be printed and exported (possible values: true/false, default: false).

The following example command enables the option to globally print and export documents although secure view is enabled:

```bash
sudo -u www-data occ config:app:set secure_view_can_print_default --value='true'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#enforce-displaying-the-watermark)Enforce Displaying the Watermark

Open documents in secure view with watermark by default (possible values: true/false, default: false).

The following example command enables the option to globally enforce displaying the watermark when documents are viewed:

```bash
sudo -u www-data occ config:app:set richdocuments secure_view_open_action_default --value='true'
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#delete-a-key-or-change-a-key)Delete a Key or Change a Key

You can delete a key with the following example command:

```bash
sudo -u www-data occ config:app:delete richdocuments secure_view_open_action_default
```

You can change a key with the following example command:

```bash
sudo -u www-data occ config:app:set richdocuments secure_view_option --value='false'
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#oauth2)OAuth2

Marketplace URL: [OAuth2](https://marketplace.owncloud.com/apps/oauth2)

Use these commands to configure OAuth2 clients via the OAuth2 app:

```plaintext
oauth2
  oauth2:add-client     Adds an OAuth2 client
  oauth2:list-clients   Lists OAuth2 clients
  oauth2:remove-client  Removes an OAuth2 client
  oauth2:modify-client  Modify OAuth2 client details
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#add-a-client)Add a Client

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-12)Usage

```plaintext
oauth2:add-client <name> <client-id> <client-secret> <redirect-url> [<allow-sub-domains> [<trusted> [<force-trust>]]]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-75)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>name</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the client - will be displayed in the authorization page to the user</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>client-id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Identifier of the client - used by the client during the implicit and authorization code flow</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>client-secret</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Secret of the client - used by the client during the authorization code flow</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>redirect-url</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Redirect URL - used in the OAuth flows to post back tokens and authorization codes to the client</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>allow-sub-domains</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Defines if the redirect url is allowed to use sub-domains. Enter true or false [default: "false"]</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>trusted</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Defines if the client is trusted. Enter true or false [default: "false"]</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>force-trust</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Trust the client even if the redirect-url is localhost. [default: "false"]</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#list-clients)List Clients

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-13)Usage

```plaintext
oauth2:list-clients [options]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-57)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output[=OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (plain, json or json_pretty). [default: "plain"]</p></td></tr></tbody></table>

Example Output

```plaintext
  - Desktop Client:
    - name: Desktop Client
    - redirect-url: http://localhost:*
    - client-id: xdXOt13JKxym1B1QcEncf2XDkLAexMBFwiT9j6EfhhHFJhs2KM9jbjTmf8JBXE69
    - client-secret: UBntmLjC2yYCeHwsyj73Uwo9TAaecAetRwMw0xYcvNL9yRdLSUi0hUAHfvCHFeFh
    - allow-sub-domains: false
    - trusted: false
  - Android:
    - name: Android
    - redirect-url: oc://android.owncloud.com
    - client-id: e4rAsNUSIUs0lF4nbv9FmCeUkTlV9GdgTLDH1b5uie7syb90SzEVrbN7HIpmWJeD
    - client-secret: dInFYGV33xKzhbRmpqQltYNdfLdJIfJ9L5ISoKhNoT9qZftpdWSP71VrpGR9pmoD
    - allow-sub-domains: false
    - trusted: false
  - iOS:
    - name: iOS
    - redirect-url: oc://ios.owncloud.com
    - client-id: mxd5OQDk6es5LzOzRvidJNfXLUZS2oN3oUFeXPP8LpPrhx3UroJFduGEYIBOxkY1
    - client-secret: KFeFWWEZO9TkisIQzR3fo7hfiMXlOpaqP8CFuTbSHzV1TUuGECglPxpiVKJfOXIx
    - allow-sub-domains: false
    - trusted: false
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#modify-client-details)Modify Client Details

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-14)Usage

```plaintext
oauth2:modify-client <name> <key> <value>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-76)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>name</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of client</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>key</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Key to be changed. Valid keys are:<br><code>name</code>, <code>client-id</code>, <code>client-secret</code>, <code>redirect-url</code>, <code>allow-sub-domains</code>, <code>trusted</code></p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>value</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The new value of the key.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#remove-a-client)Remove a Client

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#usage-15)Usage

```plaintext
oauth2:remove-client <client-id>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-77)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>client-id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Identifier of the client - used by the client during the implicit and authorization code flow</p></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#s3-primary-objectstore)S3 Primary Objectstore

Commands to configure Amazon S3 compatible object storages as the primary ownCloud storage location.

Marketplace URL: [S3 Primary Object Storage](https://marketplace.owncloud.com/apps/files_primary_s3)

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#list-objects-buckets-or-versions-of-an-object)List objects, buckets or versions of an object

```bash
sudo -u www-data occ s3:list
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-78)Arguments

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>bucket</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the bucket; it`s objects will be listed.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>object</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Key of the object; it`s versions will be listed.</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#create-a-bucket-as-necessary-to-be-used)Create a bucket as necessary to be used

```bash
sudo -u www-data occ s3:create-bucket
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-79)Arguments

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>bucket</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Name of the bucket to be created.</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-58)Options

<table class="tableblock frame-all grid-all" style="width: 80%;"><colgroup><col style="width: 30%;"> <col style="width: 70%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>update-configuration</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">If the bucket exists, the configuration will be updated.</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>accept-warning</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">No warning about the usage of this command will be displayed.</p></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#samlsso-shibboleth-integration-enterprise-edition-only)SAML/SSO Shibboleth Integration (Enterprise Edition only)

Marketplace URL: [SAML/SSO Integration](https://marketplace.owncloud.com/apps/user_shibboleth)

`shibboleth:mode` sets your Shibboleth mode to `notactive`, `autoprovision`, or `ssoonly`

```bash
sudo -u www-data occ shibboleth:mode [mode]
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#two-factor-totp)Two-Factor TOTP

Marketplace URL: [2-Factor Authentication](https://marketplace.owncloud.com/apps/twofactor_totp)

The following commands manage the _2-Factor Authentication App_. TOTP stands for _time-based one-time password_. There is also a core component independent of the _2-Factor Authentication App_ with which a particular user can be enabled or disabled for the two-factor authentication. For details see section [Two-Factor Authentication](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#two-factor-authentication).

The following commands are available for the 2-Factor Authentication app:

```plaintext
 twofactor_totp
  twofactor_totp:delete-redundant-secret         Delete the redundant secret of non-existing users
  twofactor_totp:set-secret-verification-status  Set secret verification status of specified users or all users
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#delete-redundant-secrets)Delete Redundant Secrets

Delete the redundant secrets of non-existing users:

```bash
sudo -u www-data occ twofactor_totp:delete-redundant-secret
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-secret-verification-status)Set Secret Verification Status

Set secret verification status of specified users or all users:

```bash
sudo -u www-data occ  twofactor_totp:set-secret-verification-status [options] [--] <set-verified>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-80)Arguments

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>set-verified</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Secret verification status to set. (true or false)</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-59)Options

<table class="tableblock frame-all grid-all stretch"><colgroup><col style="width: 22.2222%;"> <col style="width: 77.7778%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--all</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Will affect all users that use TOTP</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-u, --uid=UID</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The user’s uid is used.<br>This option can be used as --uid="Alice" --uid="Bob" (multiple values allowed)</p></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#windows-network-drive-wnd)Windows Network Drive (WND)

Marketplace URL: [External Storage: Windows Network Drives](https://marketplace.owncloud.com/apps/windows_network_drive)

Integrate Windows and Samba/CIFS shared network drives as external storages. For details please see the [Windows Network Drive (WND)](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../enterprise/external_storage/windows-network-drive_configuration.html) documentation.

The `wnd` commands configure the WND app.

```plaintext
wnd
 wnd:listen                 Listen to smb changes and store notifications for later processing
 wnd:process-queue          Process the notifications stored by the wnd:listen command
 wnd:set-service-account    Sets the service account for the target mount point (deprecated)
```

Please see the [Windows Network Drive Notifications](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html../../enterprise/external_storage/windows-network-drive_configuration.html#wnd-notifications) for how to properly setup `wnd:listen` and `wnd:process-queue`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#configure-the-listener)Configure the Listener

Listen to smb changes and store notifications for later processing in the database

```bash
sudo -u www-data occ wnd:listen [options] [--] <host> <share> <username> [<password>]
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-81)Arguments

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>host</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The hostname or IP address of the server to listen to</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>share</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The share inside the host to listen to for changes</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>username</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The username that will be used to connect to the share</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>password</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The user’s password (will be asked for if it isn’t provided)</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-60)Options

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>-p,<br>--path=PATH</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The path inside the share to watch for changes [default: ""]</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--password-file=PASSWORD-FILE</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The file containing the password for the account to be used to listen</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--password-from-service-account</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Use the password from the matching service account. This works only for collaborative WND mounts</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--password-trim</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Trim blank characters from the password</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--unbuffering-option=UNBUFFERING-OPTION</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">Force the usage of that unbuffering option for the underlying smbclient command. Possible options are either "auto", "pty" or "stdbuf" [default: "auto"]</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output[=OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (plain, json or json_pretty). [default: "plain"]</p></td></tr></tbody></table>

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content"><div class="olist arabic"><ol class="arabic"><li><p>To enter the password of the service account via the console, the <code>password</code> option, the <code>password-file</code> option and the <code>password-from-service-account</code> option must not be set.</p></li><li><p>To use the password for the service account from the mount point settings, use the <code>password-from-service-account</code> option.</p></li><li><p>If you use the <code>password</code> option together with the <code>password-file</code> option, the <code>password-file</code> option takes precedence over the <code>password</code> argument.</p></li></ol></div></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#process-notifications)Process Notifications

Process the notifications stored by the `wnd:listen` command

```bash
sudo -u www-data occ wnd:process-queue [options] [--] <host> <share>
```

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-82)Arguments

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>host</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The server whose notifications will be processed</p></td></tr><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>share</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The share whose notifications will be processed</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-61)Options

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output[=OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (plain, json or json_pretty). [default: "plain"]</p></td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#set-the-service-account)Set the Service Account

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">This command is deprecated starting with ownCloud 10.8. All mount options marked as <em>password</em> are now encrypted by default. Existing old settings are migrated automatically.</td></tr></tbody></table>

Sets the service account for the target mount point. You’ll be asked for the password of the service account.

```bash
sudo -u www-data occ wnd:set-service-account [options] [--] <mount-id>
```

Please see the occ documentation of [files\_external:list](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#files_externallist) to get the required mount-id.

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#arguments-83)Arguments

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>mount-id</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">ID of the mount point. Use "occ files_external:list --short" to find it</p></td></tr></tbody></table>

##### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/occ_command.html#options-62)Options

<table class="tableblock frame-all grid-all" style="width: 90%;"><colgroup><col style="width: 33.3333%;"> <col style="width: 66.6667%;"></colgroup><tbody><tr><td class="tableblock halign-left valign-top"><p class="tableblock"><code>--output[=OUTPUT]</code></p></td><td class="tableblock halign-left valign-top"><p class="tableblock">The output format to use (plain, json or json_pretty). [default: "plain"]</p></td></tr></tbody></table>
