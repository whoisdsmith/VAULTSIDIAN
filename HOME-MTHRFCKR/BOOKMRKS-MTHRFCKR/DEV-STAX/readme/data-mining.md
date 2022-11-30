# Data Mining

* [Count](data-mining.md#count)
* [Metabase](data-mining.md#metabase)

## Count

[Product page](https://count.co/)

* _Free tier_: Single user, single database connection
* _Pros_: Connects to your database (BigQuery, PostgreSQL, others coming soon). Analysis is performed in a notebook interface, either by writing SQL or using drag-and-drop. Notebooks are rich documents containing analysis, media, and interactive elements.
* _Limitations_: Cannot share notebooks publically in free tier, and can only connect to one database.

## Metabase

[Product page](http://www.metabase.com/)

* _Free tier_: Completely free to use (on premises)
* _Pros_: Allows you to run queries without knowing SQL, build dashboards, set up nightly email reports and ask questions from Slack. Works with your application database or a dedicated data warehouse, and supports MySQL, PostgreSQL, AWS Redshift, Google BigQuery and many others.
* _Limitations_: Require external hosting but may fit in AWS free tier.

## Database Hosting

* [AWS DynamoDB](data-mining.md#aws-dynamodb)
* [Cloudant CouchDB](data-mining.md#cloudant-couchdb)
* [DataStax Astra Cassandra](data-mining.md#datastax-astra-cassandra)
* [Dydra](data-mining.md#dydra)
* [ElephantSQL](data-mining.md#elephantsql)
* [Fauna](data-mining.md#fauna)
* [Firebase database](data-mining.md#firebase-database)
* [Google Cloud Datastore](data-mining.md#google-cloud-datastore)
* [InfluxDB Cloud](data-mining.md#influxdb-cloud)
* [MongoDB Atlas](data-mining.md#mongodb-atlas)
* [OpenShift MongoDB](data-mining.md#openshift-mongodb)
* [Oracle Cloud Free Tier](data-mining.md#oracle-cloud-free-tier)
* [Railway](data-mining.md#railway)
* [Redis Cloud](data-mining.md#redis-cloud)
* [Supabase Postgres](data-mining.md#supabase-postgres)

## AWS DynamoDB

[Pricing page](https://aws.amazon.com/dynamodb/pricing/)

* _Free tier_: 25 GB of Storage, 25 Units of Write Capacity, 25 Units of Read Capacity
* _Pros_: A NoSQL database with both document and key-value store models, replicated with high availability. The free tier is enough to handle up to 200M requests per month.
* _Limitations_: One unit of read/write capacity handles one request per second (or two requests per second in the case of eventually consistent reads). Has both strongly consistent and eventually consistent reads.

## Cloudant CouchDB

[Pricing page](https://www.ibm.com/cloud/cloudant/pricing)

* _Free tier_: 1$/GB per month, $0.015$/100 "heavy" requests, $0.015/500 "light" requests, first $50 per month free
* _Pros_: Full CouchDB hosting. Can host also static sites and javascript applications
* _Limitations_: Account on shared multitenant instance
* _Exceeding the free tier_: Credit card needed after first 30 days to charge exceeding usage

## DataStax Astra Cassandra

[Product page](https://www.datastax.com/products/datastax-astra)

* _Free tier_: 25$ per month for free, serverless databases. Up to 30 million reads, 4.5 million writes, 40GB in total.
* _Pros_: Unlimited number of databases, Grafana-based health monitor, multiple providers (GCP, Azure, AWS)
* _Limitations_: Does not support VPC peering, multi-region databases, materialized views, or logged batches

## Dydra

[Product page](https://dydra.com)

* _Free tier_: Simple graph storage with unlimited repositories (public and private)
* _Pros_: Repositories support [SPARQL Query](http://www.w3.org/TR/sparql11-protocol/#query-operation), [SPARQL Update](http://www.w3.org/TR/sparql11-protocol/#update-operation) and [SPARQL Graph protocol](http://www.w3.org/TR/sparql11-http-rdf-update/) and [query federation](http://docs.dydra.com/federation). There is also a simple Web interface for querying datasets, a Web API and a Command-line interface
* _Limitations_: Invite Only.

## ElephantSQL

[Product page](https://www.elephantsql.com/)

* _Free tier_: 20MB storage, 5 simultaneous connections
* _Pros_: SQL web browser for simple database inspection, secure connection over SSL, full automatic backups
* _Limitations_: No SLA no in-memory cache, shared server

## Fauna

[Product page](https://fauna.com/)

* _Free tier_: 100k read ops, 100k write ops, 500k compute ops, 100MB storage
* _Pros_: Serverless with global replication and ACID transactions. Native GraphQL support, ABAC security model and support for relational, document, graph, and time-series patterns.
* _Limitations_: No team management or preview sandbox on free tier.
* _Exceeding the free tier_: Hard limits enforced on free tier. Subscription plans offer metered overages.

## Firebase Database

[Pricing page](https://firebase.google.com/pricing/)

* _Free tier_: 1GB storage, 10GB/month transfer, 100 simultaneous connections
* _Pros_: really fast can be used for real time pub/sub, libraries for multiple platforms, designed to be used directly from frontend (with security rules), integrates with Firebase Authentication
* _Limitations_: no backups, limited queries, complicated security rules (read the manual!)

## Google Cloud Datastore

[Product page](https://cloud.google.com/datastore/)

* _Free tier_: 1GB storage/day, 50K reads/day, 20K writes/day, 20K deletes/day
* _Pros_: dashboard, clients available in multiple languages, fully managed (sharding and replication), ACID transactions
* _Limitations_: complex requests needs specific indexes (read the manual)

## InfluxDB Cloud

[Product page](https://www.influxdata.com/products/influxdb-cloud/)

* _Free tier_: Writes: 5MB every 5 minutes, Tasks & Queries: 300MB every 5 minutes, Storage: 30 days of retention, Cardinality: Up to 10,000 series, Alerting: 2 alert checks and 2 notification rules, You can create up to: 5 dashboards, 5 tasks, 2 databases to store your time series data
* _Pros_: purpose-built time series database, pre-built UI and dashboarding tools, background processing and monitoring agent

## MongoDB Atlas

[Pricing page](https://www.mongodb.com/cloud/atlas/pricing)

* _Free tier_: Start with a free 3-node replica set and 512 MB of storage / Shared RAM.
* _Pros_: Fast, secure, and highly available MongoDB service for any scale.

## OpenShift MongoDB

[Product Page](https://developers.openshift.com/databases/mongodb.html)

* _Free tier_: 1Gb storage
* _Pros_: Easy to deploy
* _Limitations_: Only support mongodb 2.4

## Oracle Cloud

[Product Page](https://www.oracle.com/cloud/free/#always-free)

* _Free tier_: 2 Autonomous Database instances with 1 OCPU and 20GB storage each
* _Pros_: Flexible workload tuning
* _Limitations_: Maximum of 20 simultaneous database sessions

## Railway

[Pricing page](https://railway.app/pricing)

* _Free tier_: 1GB memory per container, shared CPU, 1GB disk usage (10GB hard limit), 100GB outbound traffic (unlimited inbound). [Read more](https://railway.app/legal/fair-use)
* _Pros_: Allows hosting multiple databases (PostgreSQL, MySQL, Redis, MongoDB) and you can have your app and database on the same platform and run both of them for free. [Also see](../DEV-STAX.md#railway) for app hosting.
* _Limitations_: 3 projects, 2 plugins per project, 2 environments per project, 3 live deploys per environment.

## Redis Cloud

[Pricing page](https://redislabs.com/pricing)

* _Free tier_: 30MB, 30 connections
* _Pros_: managed, possibility to choose cloud provider (AWS, Azure, GCE, IBM Softlayer) and availability zones

## Supabase Postgres

[Pricing Page](https://supabase.io/pricing)

* _Free tier_: 500Mb storage, 100 simultaneous connections
* _Pros_: Open source, built in realtime capabilities and auth, 40+ extensions and pgbouncer preinstalled
* _Limitations_: Paused after 1 week of inactivity
* _Exceeding the free tier_: There are no overage charges. Team will reach out asking user to upgrade to a higher plan if limits are exceeded.
