---
tags:: notes
---

# Prometheus-nextcloud-exporter

Monitoring of a Nextcloud instance using the servinfo plugin

## Purpose

This repository has been made to monitor a Nextcloud instance using Prometheus through the serverinfo plugin.

## Install

Having a working Golang environment:

```bash
go install github.com/trazfr/prometheus-nextcloud-exporter@latest
```

## Use

This program is configured through a JSON configuration file.

To run, just `prometheus-nextcloud-exporter config.json`

## Examples of Configuration File

This configuration shows:

- A timeout of 20 seconds for each requests (default=`5`)
- Listens to the port `9092` (default value=`:9091`)
- A Nextcloud instance
  - using HTTPS (you may also use `http`)
  - with credentials: user is `myuser` and the password is `mypassword`
  - the server is `cloud.example.com`
  - it is using the default path for the serverinfo plugin: `/ocs/v2.php/apps/serverinfo/api/v1/info`

```json
{
    "timeout": 20,
    "nextcloud_url": "https://myuser:mypassword@cloud.example.com",
    "listen": ":9092"
}
```

Another configuration example where the Nextcloud is installed in the path `/mynextcloud`:

```json
{
    "nextcloud_url": "https://anotheruser:anotherpassword@server.example.com/mynextcloud"
}
```

Your server may have an exotic configuration and the serverinfo endpoints may be behind another path.  
For instance if you have a reverse proxy which rewrites `/serverinfo` into `/ocs/v2.php/apps/serverinfo/api/v1/info`:

```json
{
    "nextcloud_url": "https://anotheruser:anotherpassword@exotic.example.com/serverinfo",
    "append_default_serverinfo_path": false
}
```
