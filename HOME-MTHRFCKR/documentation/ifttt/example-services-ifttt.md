There are two types of example services:

1.  The [Hello World examples](https://ifttt.com/docs/example_services#hello-world-examples) are very simple versions of an IFTTT service in a couple different programming languages, designed to explain how a service can work.
2.  The [service templates](https://ifttt.com/docs/example_services#service-templates) are frameworks based on services in popular categories on IFTTT. These can be cloned into your organization to give you a head start, though they don't have any example code behind them.

## Hello World examples

Let's get started by creating a "Hello World" service that runs on your local machine and communicates with IFTTT. These represent the simplest implementation of a service.

First, if you don't see a Hello World service in your account, simply click [here](https://platform.ifttt.com/services/create_default) to create one. Then spin up one of these options:

-   [Getting started with Ruby on Rails](https://ifttt.com/docs/example_services#getting-started-with-ruby-on-rails)
    -   [Using Docker](https://ifttt.com/docs/example_services#hello-world-ruby-on-rails-using-docker)
    -   [Using your local Ruby and Rails](https://ifttt.com/docs/example_services#hello-world-ruby-on-rails-using-your-local-ruby-and-rails)
-   [Getting started with Node.js using Glitch](https://ifttt.com/docs/example_services#getting-started-with-node-js)
-   [Getting started with Python and FastAPI](https://ifttt.com/docs/example_services#getting-started-with-python-and-fastapi)

In this tutorial, we’ll answer your questions and help get your service up and running on the IFTTT Platform quickly by creating a simple service. We'll verify that the service is working by using the IFTTT endpoint tests. If you'd prefer, feel free to skim over this section or dive right into the [Service API Reference](https://ifttt.com/docs/api_reference)!

_Note: Deleting the Hello World service is not recommended unless you have another service under your organization. Click [here](https://platform.ifttt.com/services/create_default) to recreate the Hello World service if you're having issues accessing the IFTTT Platform._

### Getting started with Ruby on Rails

#### Hello World: Ruby on Rails using Docker

##### Run `hello_world.rb` via Docker

First, [install Docker](https://docs.docker.com/install/#supported-platforms).

Then, run the following in your command line to deploy the Hello World Ruby on Rails application within a Docker container (replace XXXXXX with [your service key](https://platform.ifttt.com/mkt/api):

`docker run -e IFTTT_SERVICE_KEY='XXXXXX' -p 3000:3000 ifttt/hello-world-ruby`

Surf to http://localhost:3000/ to see it running. You should see a "Hello, World!" message.

Now you're ready to [expose your local server via ngrok](https://ifttt.com/docs/example_services#expose-your-local-server-via-ngrok).

#### Hello World: Ruby on Rails using your local Ruby and Rails

##### Check your Ruby version

In order to run the Rails app you'll need version 2.2.2 or greater of the [Ruby](https://www.ruby-lang.org/en/) programming language installed. You can see which version of Ruby you have installed by running:

```
ruby -v
```

If you run into any issues with your local version of Ruby, we recommend [using Docker](https://ifttt.com/docs/example_services#hello-world-ruby-on-rails-using-docker) instead.

Then, copy the following to a file named `hello_world.rb` in your home directory:

##### Add your service key to your Rails app

Your service key is a secret key that is shared between your app and IFTTT. You'll need to copy and paste this key into your Rails app so IFTTT can correctly identify your service.

To get your key, visit [the API page for your service](https://ift.tt/your-service-key) and copy the service key. Then, open your local Rails app and set `IFTTT_SERVICE_KEY` to that value ([line #1 in the gist above](https://ifttt.com/docs/example_services#file-ifttt_hello_world-rb-L1)).

##### Run the Rails app

You'll need to open your Terminal and install the bundler Ruby gem:

```
gem install bundler
```

And then you'll be able to run the application:

```
ruby hello_world.rb
```

Now, you can view the Rails app running at [http://0.0.0.0:3000/](http://0.0.0.0:3000/) in your browser. You should see a "Hello, World!" message. You'll need to keep your Terminal window open so the application keeps running.

Now you're ready to [expose your local server via ngrok](https://ifttt.com/docs/example_services#expose-your-local-server-via-ngrok).

#### Expose your local server via ngrok

Now that the application is running on your local machine, you'll need a way to forward IFTTT's request to your local development environment. We recommend [ngrok](https://ngrok.com/) for this because it's easy to install and free for our simple use case.

Open a new Terminal window and follow the [ngrok installation instructions](https://ngrok.com/download). Once you have ngrok installed, you can expose the app running on your local machine to the internet. Just tell ngrok what port your web server is listening on. In this case, it should be port 3000:

```
ngrok http 3000
```

You'll see some output which will include "Forwarding" URLs for http and https. These are the URLs where your application is accessible on the internet.

We'll be using the secure https URL, which will look something like this: https://abc123.ngrok.io (where the "abc123" will be some other random identifier.)

Visit the forwarding URL in your browser and you should see that "Hello, World!" message again.

You can now skip to the [Give IFTTT your API URL](https://ifttt.com/docs/example_services#give-ifttt-your-api-url) section below.

### Getting started with Node.js

#### Hello World: Node.js using Glitch

Visit the [Hello World app](https://glitch.com/~ifttt-hello-world-service) on Glitch and click the “Remix To Edit” button. That will clone it and you’ll get your own version that you can later tweak and build upon.

After remixing the project you’ll notice a few files in your new Hello World project. You’ll see `server.js`, `package.json`, and `.env`. Until you decide to expand your service, these are the barebones that are needed.

Now, before we run all the tests for your service, let’s add the service key into your API.

#### Add your service key to your app

Your service key is a secret key that is shared between your app and IFTTT. You’ll need to use this key in your Node API so IFTTT can correctly identify your service.

First, to get your key visit the API page for your service [here](https://platform.ifttt.com/mkt/api) and copy the service key.

Now inside of the .env file that you saw earlier, you’ll see a key called `IFTTT_KEY`. Paste your service key in there. It should be formatted like the following:

```
IFTTT_KEY="rG4_x0f26jSfY…"
```

#### Give IFTTT your API URL

1.  If you used ngrok and already have a forwarding URL, you may skip to step 2. Otherwise, copy the URL by clicking the “Show” drop-down and then the "In A New Window" button.
    
2.  Visit your new service’s API page [here](https://platform.ifttt.com/mkt/api), and input that URL into the IFTTT API URL field.
    

#### Run the endpoint tests

Visit the endpoint tests [here](https://platform.ifttt.com/mkt/%2Fapi%2Fendpoint_tests), and click the Begin Test button. You should see that all the endpoint tests pass. Now go take a look at your Terminal or Glitch console to see the requests/responses from the endpoint test. Learn more about the endpoint tests [here](https://ifttt.com/docs/testing).

#### Build your own service

Try experimenting by adding new actions and triggers until you get the hang of things. Afterwards you can re-run the endpoint tests to see what happens. Then, check out the [service API documentation](https://ifttt.com/docs/api_reference) to start building your own service (or take a look at the [service templates](https://ifttt.com/docs/example_services#service-templates) below)!

### Getting started with Python and FastAPI

#### Hello World: setting up the environment

Make sure you are running Python3.6+ in your development environment. Run the following command to [install FastAPI](https://fastapi.tiangolo.com/) and its dependencies:

```
pip install fastapi
```

Create a new hello\_world.py file and copy the following to it.

##### Add your service key to your FastAPI app

Your service key is a secret key that is shared between your app and IFTTT. You'll need to copy and paste this key into your FastAPI app so IFTTT can correctly identify your service.

To get your key, visit [the API page for your service](https://ift.tt/your-service-key) and copy the service key. Then, open your local Python app and set `IFTTT_SERVICE_KEY` to that value ([line #17 in the gist above](https://ifttt.com/docs/example_services#file-ifttt_hello_world-py-L17)).

#### Run the app locally

To start the app run this command from your working directory:

```
uvicorn hello_world:app
```

Now you're ready to [expose your local server via ngrok](https://ifttt.com/docs/example_services#expose-your-local-server-via-ngrok) on port 8000.

#### Add the API URL to your service

Visit your new service’s API page [here](https://platform.ifttt.com/mkt/api), and input the ngrok URL into the IFTTT API URL field.

#### Test the service

Visit the endpoint tests [here](https://platform.ifttt.com/mkt/%2Fapi%2Fendpoint_tests), and click the Begin Test button. You should see that all the endpoint tests pass. Now go take a look at your Terminal to see the requests/responses from the endpoint test. Learn more about the endpoint tests [here](https://ifttt.com/docs/testing).

___

## Service Templates

These are templates based on services in popular categories on IFTTT. These can be cloned into your organization to give you a head start, though they don't have any example code associated with them.

A few notes:

-   You are free to add, remove, or update any of the triggers or actions in your cloned service. These are just a starting point.
-   These services are not functional in their current state. You'll need to connect your API, add user authentication, etc. in order for the services to interact with real data.
-   Is there an example service you were hoping was available here? [Let us know](mailto:platform-support+example-service-request@ifttt.com?subject=I%20would%20like%20to%20request%20the%20following%20service%20template%3A)!

### Bank

A service that interacts with bank account deposits, withdrawals, purchases, current balance, and more.

[Preview this service](https://ifttt.com/features/redeem?code=266977-fb862dd0aec7e06122bf869f2c79a580) | [Request to clone this service](mailto:platform-support+example-service-clone-request@ifttt.com?subject=Request%20to%20clone%20Example%20Bank%20service%20into%20my%20organization%20%28ID%3A%20418513%2C%20username%3A%20whoisdsmith%29)

___

### Bookmarking app

A service based on an app where users can manage their bookmarks.

[Preview this service](https://ifttt.com/features/redeem?code=280822-2de93570fa79fe7cb69329ca7f8c097a) | [Request to clone this service](mailto:platform-support+example-service-clone-request@ifttt.com?subject=Request%20to%20clone%20Example%20Bookmarking%20app%20service%20into%20my%20organization%20%28ID%3A%20418513%2C%20username%3A%20whoisdsmith%29)

___

### News site

A service based on news publications where users can be alerted about breaking news or specific topics.

[Preview this service](https://ifttt.com/features/redeem?code=304047-19c7516da7b7df6f7e708c0d9f37eea0) | [Request to clone this service](mailto:platform-support+example-service-clone-request@ifttt.com?subject=Request%20to%20clone%20Example%20News%20site%20service%20into%20my%20organization%20%28ID%3A%20418513%2C%20username%3A%20whoisdsmith%29)

___

### Power management

A service based on electricity usage where users can be alerted about energy prices and their own consumption.

[Preview this service](https://ifttt.com/features/redeem?code=353513-671108b38e3c549dfa42ab34f544c419) | [Request to clone this service](mailto:platform-support+example-service-clone-request@ifttt.com?subject=Request%20to%20clone%20Example%20Power%20management%20service%20into%20my%20organization%20%28ID%3A%20418513%2C%20username%3A%20whoisdsmith%29)

___

### To do list app

A service based on an app where users can manage tasks.

[Preview this service](https://ifttt.com/features/redeem?code=284234-a414ca0570639d9717fcaee527223ef1) | [Request to clone this service](mailto:platform-support+example-service-clone-request@ifttt.com?subject=Request%20to%20clone%20Example%20To%20do%20list%20app%20service%20into%20my%20organization%20%28ID%3A%20418513%2C%20username%3A%20whoisdsmith%29)

___

#### _More coming soon_

Do you have a suggestion for another example service that would be helpful? [Let us know](mailto:platform-support+example-service-request@ifttt.com?subject=I%20would%20like%20to%20request%20the%20following%20service%20template%3A)!

___

#### Next steps:

-   Explore the [Service API](https://ifttt.com/docs/api_reference).
-   Learn about [testing your service](https://ifttt.com/docs/testing).
-   Create your first connection with our [Connect Quick Start Guide](https://ifttt.com/docs/getting_started_connect).

---

#ifttt 