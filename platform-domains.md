---
title: Platform Domains
description: Understand the platform domains associated with site environments on Pantheon.
tags: [infrastructure]
categories: []
---
Every site on Pantheon is given multiple environments (Dev, Test, and Live), each with their own unique platform domains which are bound to isolated resources, and are uniquely addressable on the internet via Pantheon's own DNS. [Multidev](/docs/multidev/) environments get the same treatment. Platform domains are configured as subdomains, and are generated by prefixing the environment to the site name:

- dev-site-name.pantheonsite.io
- test-site-name.pantheonsite.io
- live-site-name.pantheonsite.io
- multidev-env-site-name.pantheonsite.io

## Legacy Platform Domains

DNS configurations for paid sites that use the `gotpantheon.com` or `pantheon.io` legacy platform domain will continue to work, as requests will be permanently redirected to `pantheonsite.io`.  However, we recommend switching the CNAME value from `gotpantheon.com` or `pantheon.io` to `pantheonsite.io` within the domain's DNS provider to prevent unnecessary redirects and take advantage of uptime and reliability improvements.

<div class="alert alert-info" role="alert">
<h4 class="info">Note</h4>
<p>Sandbox sites that are converged will lose their legacy <code> pantheon.io </code> domain. We suggest you update your DNS configuration to <code> pantheonsite.io </code> immediately.</p>
</div>

## Platform Domains as CDN Origin

Customers frequently use CDNs on top of Pantheon, and are free to use platform domains for this purpose. They can rely on Pantheon's HTTPS edge to ensure secure communication between their CDN provider and their "origin" instance on Pantheon. For an example of this use case, see [Adding HTTPS For Free With Cloudflare](/docs/guides/cloudflare-enable-https/).

If you use the platform in this way, you cannot use legacy platform domains and must update your configuration to use a `pantheonsite.io` domain.

## Vanity Domains
Pantheon Partners, Strategic Partners, Enterprise accounts, Resellers, and OEM Partners have the ability to replace `pantheonsite.io` for each environment on every site they run with a custom vanity domain.

For details, see [Vanity Domains](/docs/vanity-domains/).