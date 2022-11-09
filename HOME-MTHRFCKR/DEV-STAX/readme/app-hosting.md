# App Hosting

* [AppHarbor](app-hosting.md#appharbor)
* [AWS EC2](app-hosting.md#aws-ec2)
* [Azure App Service](app-hosting.md#azure-app-service)
* [Fly](app-hosting.md#fly)
* [GearHost](app-hosting.md#gearhost)
* [Glitch](app-hosting.md#glitch)
* [Google App Engine](app-hosting.md#google-app-engine)
* [Google Compute Engine](app-hosting.md#google-compute-engine)
* [IBM Cloud](app-hosting.md#ibm-cloud)
* [Koyeb](app-hosting.md#koyeb)
* [Netlify](app-hosting.md#netlify)
* [OpenShift](app-hosting.md#openshift)
* [Oracle](app-hosting.md#oracle)
* [Qoddi](app-hosting.md#qoddi)
* [Railway](app-hosting.md#railway)
* [Vercel](app-hosting.md#vercel)

## AppHarbor

[Pricing page](https://appharbor.com/pricing)

* _Free tier_: 1 worker unit, apphb.com hostname
* _Pros_: Auto scaling, Deploy with git, One of few PaaS for .NET apps
* _Limitations_: No custom domain on free tier

## AWS EC2

[Product page](https://aws.amazon.com/free/)

* _Free tier_: 750 hours/month of t2.micro instances
* _Limitations_: Expires 12 months after sign-up

## Azure App Service

[Pricing page](https://azure.microsoft.com/en-us/pricing/details/app-service/)

* _Free tier_: 10 applications, 1 shared core, 1GB RAM and 1GB storage per application
* _Pros_: Supports .NET, easy publishing directly from Git/GitHub/Bitbucket
* _Limitations_: Cumulative limit for CPU (60 minutes allowed every 24 hours), No uptime SLA, No custom domain, No SSL

## Fly

[Pricing page](https://fly.io/docs/about/pricing/)

* _Free tier_: 2340 shared CPU hours per month, 160GB outbound bandwidth per month (unlimited inbound), Unlimited IPv6 and 1 IPv4 Anycast IPs per active app, 10 active certificates per app
* _Limitations_: No uptime SLA, No web app (access through CLI only)

## GearHost

[Pricing page](https://www.gearhost.com/pricing)

* _Free tier_: 1 shared node and 1 worker at max, 100MB storage, 1GB bandwidth/month, Custom domains
* _Pros_: Supports .NET (4.6), PHP (5.3-5.5) and Node.js apps, MSSQL and MySQL databases, Easy publishing over FTP, WebDeploy or directly from Git/GitHub/Bitbucket
* _Limitations_: Cumulative limits for CPU (60 minutes allowed every 24 hours) and RAM (256MB allocated every hour), 1GB bandwidth allowd every 24 hours, [250 concurrent connections](https://www.gearhost.com/documentation/difference-free-standard-reserved-plans), No SSL support, only 32bits processes
* _Exceeding the free tier_: If CPU usage, RAM usage or bandwidth consumed reaches the limit within its timefame, the application goes offline until the counter resets

## Glitch

[Pricing page](https://glitch.com/pricing)

* _Free tier_: Instantly deployed Node.js app with collaboration tool, 1000 project hours, 4000 requests/hour, 512MB ram, 200MB disk excluding node\_modules, Custom domain
* _Pros_: Based on Node.js, Online editor with real time collaboration, Live redeploy, Great for prototyping and collaboration
* _Limitations_: Free tier instances will sleep after 5 mins of inactivity but will turn on when someone accesses the website

## Google App Engine

[Product page](https://cloud.google.com/appengine)

* _Free tier_: 28 instance hours/day, 1GB outbound bandwidth/day, 1GB inbound bandwidth/day, 5GB Cloud storage, Shared memcache, 1000 search operations per day, 10MB search indexing, 100 emails per day
* _Pros_: Managed, Autoscaling, Works well with other Google Cloud features (load balancing, datastores, etc.), Multiple languages supported
* _Limitations_: Free tier only applies to a standard environment which supports Python, Java, PHP and Go

## Google Compute Engine

[Product page](https://cloud.google.com/compute/)

* _Free tier_: 1 f1-micro instance per month (US regions only), 30GB-months HDD, 5GB-months snapshot, 1GB network egress from North America to all region destinations per month (excluding China and Australia)
* _Pros_: Works well with other Google Cloud features (load balancing, datastores, etc.)
* _Limitations_: Limited to US region only for now

## IBM Cloud

[Pricing page](https://cloud.ibm.com/pricing/)

* _Free tier_: 512MB/month
* _Pros_: Can deploy multiple smaller instance for free for a total of 512MB (4x128MB, 2x256MB…), Supports multiple languages (Java, JS, Go, PHP, Python Ruby), Supports containers

## Koyeb

[Pricing page](https://www.koyeb.com/pricing)

* _Free tier_: 2 nano services, 1vCPU per service, 256MB of RAM per service, 2.5GB SSD per service, 100GB outbound bandwidth (unlimited inbound)
* _Pros_: Native autoscaling, Intuitive web interface and CLI, Deploy with Git, Edge CDN, Cron background tasks, Good observability, Supports containers
* _Limitations_: Custom domains not supported yet, Websockets not supported yet, No uptime SLA on free tier.

## Netlify

[Pricing page](https://www.netlify.com/pricing/)

* _Free tier_: 100GB bandwidth per month, 1 concurrent build, 300 build minutes/month, 125000 serverless function invocations per month, 100 form submissions per month, 1000 active Identity users per month, 2500 large media transformations per month
* _Pros_: Deploy with Git, Edge CDN
* _Limitations_: No site analytics on free tier

## OpenShift

[Pricing page](https://www.openshift.com/pricing/index.html)

* _Free tier_: 1 project, 2GB memory, 2GB storage, no custom domain
* _Pros_: Gears can be used to deploy apps in a lot of languages and/or databases, Many deployment templates are provided
* _Limitations_: Deployment requires installation of OpenShift app, Idle apps take longer to load (>30s)

## Oracle

[Pricing page](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier.htm)

* _Free tier_: 2 Compute(AMD) Micro instances (1/8th OCPU, 1GB memory each), Ampere A1 Compute(Arm) instances (4 OCPUs and 24GB of memory that you can allocate flexibly), 20TB outbound bandwidth (unlimited inbound) [Read more](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier\_topic-Always\_Free\_Resources.htm)
* _Pros_: Free forever virtual machines
* _Limitations_: OS selection restricted to Oracle Enterprise Linux, CentOS and Ubuntu

## Qoddi

[Pricing page](https://qoddi.com/#pricing)

* _Free tier_: 512MB RAM, 1 vCPU
* _Pros_: Always online, Unlimited build minutes
* _Limitations_: No uptime SLA on free tier

## Railway

[Pricing page](https://railway.app/pricing)

* _Free tier_: 1GB memory per container, Shared CPU, 1GB disk usage (10GB hard limit), 100GB outbound bandwidth (unlimited inbound). [Read more](https://railway.app/legal/fair-use)
* _Pros_: You can have your app and database on the same platform and run both of them for free, [see](../DEV-STAX.md#railway) for database hosting
* _Limitations_: Only 99% uptime SLA, 3 projects, 2 plugins per project, 2 environments per project, 3 live deploys per environment

## Vercel

[Pricing page](https://vercel.com/pricing)

* _Free tier_: 100GB bandwidth per month, 100GB-Hours serverless function execution, 1000 image optimizations, Unlimited serverless function invocations, 100000 edge function invocations, 6000 build minutes/month, 1 concurrent build, 50 domains per project, 3 projects per git repository, 100 deployments per day, 12 serverless functions written in Node.js, Go, Python and Ruby
* _Pros_: Deploy with git, Edge CDN, Preview deployments, Next.js API endpoints are converted to serverless functions automatically. [Also see](../DEV-STAX.md#vercel) for static hosting
* _Limitations_: No uptime SLA on free tier, Free tier does not allow commercial usage, observability is limited, Free tier has limited analytics
