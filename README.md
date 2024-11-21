Attribution Reporting Demo
==========================

Like [trust-safety-demo](https://github.com/GoogleChromeLabs/trust-safety-demo/tree/main/attribution-reporting), but built up from first principles.

Docker Compose simulates an environment with an advertiser site, publisher site, and adtech report collection server.

This is a learning example and shouldn't be used for anything serious. I'll make mistakes along the way.

Setup
-----

Chrome Privacy Sandbox APIs may only trust HTTPS resources. This example requires all resources are served over HTTPS. This can be achieved by configuring a browser to trust CA, or (more simply), using a domain name and [lego](https://go-acme.github.io/lego/) or a similar tool to create a certificate:

1. Register a domain name, e.g. attribution-reporting-demo.com
1. Obtain a .crt/.key pair for a wildcard subdomain cert (e.g. `*.attribution-reporting-demo.com`) using Lego or a similar tool and the registrar/DNS provider.
1. Symlink the .crt/.key to `cert.crt` and `cert.key` in the root of this repo
1. Add `attribution-reporting-demo.com` subdomains to /etc/hosts pointing to localhost

Run
---

1. `docker compose up --build`
1. Navigate to `attribution-reporting-demo.com` to access the demo

Paths so far:

- /adtech - simulate an ad tech report collection server & other ad tech functions such as prompting the browser to register an attribution source.
