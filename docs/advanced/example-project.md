---
title: Example Project
---

## Introduction

What follows is a more in-depth look at the [example project](https://github.com/MasterKale/SimpleWebAuthn/tree/master/example) available in the repo. A single-file Express server and a few HTML files have been combined with the packages in this project to demonstrate what it takes to get up and running with WebAuthn. This is intended to be a practical reference for implementing the SimpleWebAuthn libraries to add WebAuthn-based Two-Factor Authentication (2FA) support to your website.

Before going any further, though, it's worth noting that the WebAuthn browser API by itself isn't very useful. Developers that want to leverage this API and these libraries are required to have a server with a few things already up and running:

- A **stateful** server capable of temporarily persisting values
- A database that can store information linked to individual users

:::tip

Don't fret if you don't already have a setup like this! The example project mocks out enough of this functionality to offer you a simple WebAuthn sandbox to play around with before you dive in further.

:::

## Getting started

The example server is a Node server, so you'll need the following available on your machine:

- Node v10.0.0+ ([install](https://nodejs.org/))
  - Install the current LTS release if you're new to all of this
  - The `npm` (Node Package Manager) executable comes with an installation of Node

### Downloading the code

First and foremost, get the SimpleWebAuthn code downloaded to your machine. You can [click here to download](https://github.com/MasterKale/SimpleWebAuthn/archive/master.zip) a ZIP file containing a current snapshot of the codebase, or clone it with `git`:

```bash
$> git clone https://github.com/MasterKale/SimpleWebAuthn.git
```

After unzipping or cloning the codebase, `cd` to it in a terminal before continuing:

```bash
$> cd SimpleWebAuthn
./SimpleWebAuthn/ $>
```

### Installing dependencies

First, navigate to the example project directory:

```bash
./SimpleWebAuthn/ $> cd example
./example/ $>
```

Next, install dependencies with `npm`:

```bash
./example/ $> npm install
```

### Setting up HTTPS support

Websites that want to use WebAuthn _must_ be served over HTTPS, **including during development!** Fortunately it's simple to generate SSL certificates to host the site locally over HTTPS:

1. [Install mkcert](https://github.com/FiloSottile/mkcert#installation) as per its instructions
2. Run `mkcert -install` to initialize mkcert
3. Run the following command from within the **example/** directory to generate SSL certificates for `localhost`:

```bash
./example/ $> mkcert -key-file localhost.key -cert-file localhost.crt localhost
```

This command should generate the following two files:

- **example/localhost.key**
- **example/localhost.crt**

The SSL certificate has been successfully generated if you see these two files. If these files don't exist, make sure you're in the **example/** directory before retrying the last step.

### Starting the server

Once the two files above are in-place, you can start the server:

```bash
./example/ $> npm start
```

The example server should now be available at [https://localhost](https://localhost)!

## Server Architecture

TBD

## Browser Architecture

TBD
