# Chef

- Chef is a particularly popular IaC tool among CI/CD practitioners. The fact that Chef uses Ruby-based DSL is certainly a huge plus too. It supports "cookbook" versioning from the beginning and allows you to maintain a consistent configuration—even when the infrastructure needs to keep up with the rapid growth of the app it hosts.

- Chef provides recipes and cookbooks at the heart of its configuration—these are self-styled appellations for templates and collections of templates that you can use out of the box. One cookbook should relate to a single task, but it can deliver a number of different server configurations based on the resources involved (e.g., a web application with a database will have two recipes, one for each part, stored together). Thanks to its support for cloud provisioning APIs, Chef also works really well with other IaC tools including Terraform as well as multiple other cloud environments.
