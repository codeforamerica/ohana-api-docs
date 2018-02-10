---
title: Ohana API Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby

toc_footers:
  - <a href='http://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - version
  - schema
  - requests
  - parameters
  - authentication
  - cors
  - root
  - organizations
  - get_organization
  - create_organization
  - patch_organization
  - delete_organization
  - get_organization_locations
  - locations
  - get_location
  - create_location
  - patch_location
  - delete_location
  - create_address
  - patch_address
  - delete_address
  - create_mail_address
  - patch_mail_address
  - delete_mail_address
  - get_location_contacts
  - create_contact
  - update_contact
  - delete_contact
  - create_phone
  - update_phone
  - delete_phone
  - get_location_services
  - create_service
  - patch_service
  - delete_service
  - search
  - nearby
  - categories
  - get_category_children
  - update_service_categories
  - pagination
  - errors

search: true
---

# Introduction
Welcome to the Ohana API documentation. The [Ohana API Rails app](https://github.com/codeforamerica/ohana-api) allows any community to deploy their own instance of the API, and to maintain their own resource directory of human service providers.

We provide code examples for the Shell and Ruby in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Apps Powered by Ohana API

[Ohana Web Search](https://github.com/codeforamerica/ohana-web-search) is an open source Rails application that allows you to search for and display information provided by the API in a user-friendly website.

# Live Deployments of Ohana API
Currently, there is only one live deployment: in San Mateo County, California. We expect more cities and counties to deploy, and as they do, we will add them to this list. If you have deployed an instance of Ohana API, feel free to add it to this list via a pull request, since this documentation is open source.

**San Mateo County, California**

- API: <http://api.smc-connect.org>
- Admin Interface: <http://admin.smc-connect.org>
- Web Search: [SMC-Connect](http://smc-connect.org)
- Developer Portal: <http://developer.smc-connect.org>
