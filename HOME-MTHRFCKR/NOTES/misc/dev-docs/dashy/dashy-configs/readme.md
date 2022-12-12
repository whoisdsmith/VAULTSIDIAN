<h1 align="center">Example Configuration Files for Dashy</h1>
<p align="center"><i><a href="https://github.com/Lissy93/dashy">Dashy</a> is a self-hosted dashboard, to help you keep your lab organized</i></p>
<p align="center"><a href="https://github.com/Lissy93/dashy"><img width="100" src="https://i.ibb.co/yhbt6CY/dashy.png" /></a></p>

---

### Dashy Quick Start

With [Docker](https://www.docker.com/): `docker run -p 8080:80 lissy93/dashy`. See the **[Getting Started Docs](https://github.com/Lissy93/dashy/blob/master/docs/deployment.md)** for full setup instructions.

---

### Example Config Files

This post contains several example files to help you get started
- [Getting Started](#file-example-1-getting-started-conf-yml)
- [Bookmarks](#file-example-2-bookmarks-conf-yml)
- [Home Lab](#file-example-3-demo-home-lab-conf-yml)
- [Demonstrating Features](#file-example-4-testing-features-conf-yml)
- [CFT Toolbox](#file-example-5-cft-toolbox-conf-yml)
- [Dashy Live](#file-example-7-dashy-live-conf-yml)
- [Crypto Currency Widgets](#file-example-8-dashy-crypto-widgets-conf-yml)
- [System Resource Monitoring](#file-example-9-system-monitoring-conf-yml)
- [Start Page](#file-example-10-start-page-conf-yml)

---

### About the Config File

- This `conf.yml` file contains all data and settings for your dashboard. It is located at `/public/conf.yml`, and written in [YAML](https://yaml.org/)
- If you're using Docker, you can use a `--volume` to pass the config file from your host system to Dashy, for example: `-v /root/my-local-conf.yml:/app/public/conf.yml`
- After making changes to the configuration, the application need to be rebuilt. This should happen automatically once running, but a rebuild can also be manually triggered with `yarn build` (or `docker exec -it [container-id] yarn build` in Docker)
- Changes to your config can also be made directly through the UI under the Config menu. And either written to disk, or applied locally
- To check that your conf.yml is valid and matched Dashy's schema. Run `yarn validate-config` (or for Docker: `docker exec -it [container-id] yarn build`)

> For full details and available fields, see the **[Configuring Documentation](https://github.com/Lissy93/dashy/blob/master/docs/configuring.md)**

---

### Helpful Tools
- [Config Schema Example](https://json-schema.app/view/%23?url=https%3A%2F%2Fraw.githubusercontent.com%2FLissy93%2Fdashy%2Fmaster%2Fsrc%2Futils%2FConfigSchema.json)
- [JSON Validator w Schema](https://www.jsonschemavalidator.net/s/JFUj7X9J)
- [JSON to YAML](https://jsonformatter.org/json-to-yaml)
- [YAML to JSON](https://jsonformatter.org/yaml-to-json)
- [Config Guide](https://dashy.to/docs/configuring)