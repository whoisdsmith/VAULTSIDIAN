---
tags:: apps
---
# Nextcloud netdata Plugin

This is a [netdata](https://github.com/netdata/netdata/) plugin that polls
a number of metrics from a Nexctloud server.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see http://www.gnu.org/licenses/.

## Installation

With your default netdata installation copy the `nextcloud.chart.py` script to
`/usr/libexec/netdata/python.d/` and the `nextcloud.conf` config file to
`/etc/netdata/python.d/`. The location of these directories may vary depending
on your distribution. Read your given release of netdata for more information.

Optional: Copy health configuration `health.d/nextcloud.conf` to `/etc/netdata/health.d/` to enable warnings if there are pending app updates.

Log in as aministrator in Nextcloud and create a new app password for netdata.
Note: The [metadata](https://apps.nextcloud.com/apps/metadata) plugin must be installed and activated in Nextcloud.

Edit the config file `/etc/netdata/python.d/nextcloud.conf` to set the Nextcloud API URL,
user name and app password.

Please note: beginning with v0.2 the configuration only needs the hostname and not
the full URL to the monitoring API!

Restart netdata to activate the plugin after you have made these changes.

To disable the Nextcloud plugin, edit `/etc/netdata/python.d.conf` and add
`nextcloud: no`.

## Debugging

If problems occur, the plugin execution can be debugged as follows:

1. `sudo su -s /bin/bash netdata`
2. `/usr/libexec/netdata/plugins.d/python.d.plugin nextcloud debug trace`

## Version History

- v0.3 - Add apps metric, including a health check for pending updates
- v0.2 - More metrics, using JSON instead of XML, changed configuration (thanks to Luca Olivetti)
- v0.1 - Initial release
