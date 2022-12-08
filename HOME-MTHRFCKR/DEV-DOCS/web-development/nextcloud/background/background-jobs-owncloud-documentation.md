---
tags:: occ
created: 2022-07-16T20:59:00 (UTC -04:00)
tags: []
source: https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html
author: 
---

# Background Jobs :: ownCloud Documentation

> ## Excerpt
> Background Jobs

---
# Background Jobs

Table of Contents

-   [Introduction](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#introduction)
    -   [Docker Note](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#docker-note)
-   [Cron Jobs](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#cron-jobs)
    -   [Cron](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#cron)
    -   [Webcron](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#webcron)
    -   [AJAX](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#ajax)
    -   [Parallel Task Execution](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#parallel-task-execution)
    -   [Available Background Jobs](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#available-background-jobs)
-   [Troubleshooting](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#troubleshooting)
    -   [Remove Non-Existent Background Jobs](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#remove-non-existent-background-jobs)
    -   [Forbidden error for Scanner.php](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#forbidden-error-for-scanner-php)

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#introduction)Introduction

A system like ownCloud sometimes requires tasks to be done on a regular basis without requiring user interaction or hindering ownCloud’s performance. For that reason, as a system administrator you can configure background jobs (for example, database clean-ups) to be executed without any user interaction.

These jobs are typically referred to as [Cron Jobs](https://en.wikipedia.org/wiki/Cron). Cron jobs are commands or shell-based scripts that are scheduled to periodically run at fixed times, dates, or intervals. To run Cron jobs with ownCloud, we recommend that you use the occ `system:cron` command.

Use the [occ background command set](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.htmlocc_command.html#background-jobs-selector) to select which scheduler you want to use for controlling.

As an example:

```bash
sudo -u www-data occ background:cron
```

Is the same as using the **Cron** section on your ownCloud Admin page.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#docker-note)Docker Note

If you are using the official docker images you don’t need to take care about the configuration for background jobs, the docker image is already configured to use cron internally. If required, this can also be adjusted by the [environment variables](https://github.com/owncloud-docker/base#environment-variables) `OWNCLOUD_CROND_ENABLED` and `OWNCLOUD_CROND_SCHEDULE`.

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#cron-jobs)Cron Jobs

You can schedule Cron jobs in three ways: [Cron](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#cron), [Webcron](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#webcron), or [AJAX](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#ajax). These can all be configured in the admin settings menu. However, the recommended method is to use Cron. The following sections describe the differences between each method.

There are a number of things to keep in mind when choosing an automation option:

1.  While the default method is AJAX, though the preferred way is to use Cron.  
    The reason for this distinction is that AJAX is easier to get up and running. As a result, it makes sense (often times) to accept it in the interests of expediency. However, doing so is known to cause issues, such as backlogs and potentially not running every job on a heavily-loaded system. What’s more, an increasing amount of ownCloud automation has been migrated from AJAX to Cron in recent versions. For this reason, we encourage you to not use it for too long — especially if your site is rapidly growing.
    
2.  While Webcron is better than AJAX, it has limitations too.  
    For example, running Webcron will only remove a single item from the job queue, not all of them. Cron, however, will clear the entire queue.
    

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">It’s for this reason that we encourage you to use Cron — if at all possible.</td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#cron)Cron

Using the operating system Cron feature is the preferred method for executing regular tasks. This method enables the execution of scheduled jobs without the inherent limitations which the web server might have.

For example, to run a Cron job on a \*nix system every 15 minutes (recommended), under the default web server user (often, `www-data` or `wwwrun`) you must set up the following Cron job to call the occ `background:cron` command:

```bash
sudo crontab -u www-data -e
*/15  *  *  *  * /usr/bin/php -f /path/to/your/owncloud/occ system:cron
```

You can verify if the cron job has been added and scheduled by executing:

```bash
sudo crontab -u www-data -l
*/15  *  *  *  * /usr/bin/php -f /path/to/your/owncloud/occ system:cron
```

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">You have to make sure that PHP is found by Cron; hence why we’ve deliberately added the full path.</td></tr></tbody></table>

Please refer to [the crontab man page](https://linux.die.net/man/1/crontab) for the exact command syntax if you don’t want to have it run every 15 minutes.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">There are other methods to invoke programs by the system regularly, e.g., <a href="https://wiki.archlinux.org/index.php/Systemd/Timers">systemd timers</a></td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#webcron)Webcron

By registering your ownCloud `cron.php` script address as an external webcron service (for example, [easyCron](http://www.easycron.com/)), you ensure that background jobs are executed regularly. To use this type of service, your external webcron service must be able to access your ownCloud server using the Internet. For example:

```plaintext
URL to call: http[s]://<domain-of-your-server>/owncloud/cron.php
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#ajax)AJAX

The AJAX scheduling method is the default option.  
However, it is also the _least_ reliable. Each time a user visits the ownCloud page, a single background job is executed. The advantage of this mechanism, however, is that it does not require access to the system nor registration with a third party service. The disadvantage of this mechanism, when compared to the [Webcron](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#webcron) service, is that it requires regular visits to the page for it to be triggered.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">Especially when using the Activity App or external storages, where new files are added, updated, or deleted one of the other methods should be used.</td></tr></tbody></table>

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#parallel-task-execution)Parallel Task Execution

Regardless of the approach which you take, since ownCloud 9.1, Cron jobs can be run in parallel. This is done by running `background:cron` multiple times. Depending on the process which you are automating, this may not be necessary. However, for longer-running tasks, such as those which are LDAP related, it may be very beneficial.

There is no way to do so via the ownCloud UI. But, the most direct way to do so, is by opening three console tabs and in each one run

```bash
sudo -u www-data occ system:cron
```

Each of these processes would acquire their own list of jobs to process without overlapping any other.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#available-background-jobs)Available Background Jobs

A number of existing background jobs are available to be run just for specific tasks.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content"><div class="paragraph"><p>These jobs are generally only needed on large instances and can be run as background jobs. If the number of users in your installation ranges between 1,000 and 3,000, or if you’re using LDAP and it becomes a bottleneck, then admins can delete several entries in the <code>oc_jobs</code> table and replace them with the corresponding <code>occ</code> command, which you can see here:</p></div><div class="ulist"><ul><li><p><code>OCA\\DAV\CardDAV\\SyncJob</code> → <code>occ dav:sync-system-addressbook</code></p></li><li><p><code>OCA\\Federation\\SyncJob</code> → <code>occ federation:sync-addressbooks</code></p></li><li><p><code>OCA\\Files_Trashbin\\BackgroundJob\\ExpireTrash</code> → <code>occ trashbin:expire</code></p></li><li><p><code>OCA\\Files_Versions\\BackgroundJob\\ExpireVersions</code> → <code>occ versions:expire</code></p></li></ul></div><div class="paragraph"><p>If used, these should be scheduled to run on a daily basis.</p></div></td></tr></tbody></table>

While not exhaustive, these include:

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#cleanupchunks)CleanupChunks

The `CleanupChunks` command, `occ dav:cleanup-chunks`, will clean up outdated chunks (uploaded files) more than a certain number of days old and needs to be added to your crontab.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">There is no matching background job to delete from the <code>oc_jobs</code> table.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#expiretrash)ExpireTrash

The ExpireTrash job, contained in `OCA\Files_Trashbin\BackgroundJob\ExpireTrash`, will remove any file in the ownCloud trash bin which is older than the specified maximum file retention time. It can be run, as follows, using the [OCC trashbin](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.htmlocc_command.html#trashbin) command:

```bash
sudo -u www-data occ trashbin:expire
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#expireversions)ExpireVersions

The ExpireVersions job, contained in `OCA\Files_Versions\BackgroundJob\ExpireVersions`, will expire versions of files which are older than the specified maximum version retention time. It can be run, as follows, using the [OCC versions](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.htmlocc_command.html#versions) command:

```bash
sudo -u www-data occ versions:expire
```

<table><tbody><tr><td class="icon"><i class="fa icon-caution" title="Caution"></i></td><td class="content">Please take care when adding <code>ExpireTrash</code> and <code>ExpireVersions</code> as <a href="https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#cron">Cron</a> jobs. Make sure that they’re not started in parallel on multiple machines. Running in parallel on a single machine is fine. But, currently, there isn’t sufficient locking in place to prevent them from conflicting with each other if running in parallel across multiple machines.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#syncjob-carddav)SyncJob (CardDAV)

The `CardDAV SyncJob`, contained in `OCA\DAV\CardDAV\SyncJob`, syncs the local system address book, updating any existing contacts, and deleting any expired contacts. It can be run, as follows, using the [OCC dav](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.htmlocc_command.html#dav-commands) command:

```bash
sudo -u www-data occ dav:sync-system-addressbook
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#syncjob-federation)SyncJob (Federation)

OCAFederationSyncJob

It can be run, as follows, using the [OCC federation sync](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.htmlocc_command.html#federation-sync) command:

```bash
sudo -u www-data occ federation:sync-addressbooks
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#troubleshooting)Troubleshooting

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#remove-non-existent-background-jobs)Remove Non-Existent Background Jobs

See the [Remove Non-Existent Background Jobs](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html../../troubleshooting/remove_non_existent_bg_jobs.html) section in the general troubleshooting documentation for more details.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/background_jobs_configuration.html#forbidden-error-for-scanner-php)Forbidden error for Scanner.php

If you find a **Forbidden** error message in your log files, with a reference to the `Scanner.php` file, then you should:

-   Check if you have any shares with the status `pending`.
    
-   Configure `conditional logging` for cron to see more output.
