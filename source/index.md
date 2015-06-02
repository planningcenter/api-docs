---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://api.planningcenteronline.com/oauth/applications'>Sign Up for an Authentication Key</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - people
  - errors

search: true

# _
---

# Introduction

The Planning Center Online API can be used to interact with all of your organization's data inside Planning Center. In this first iteration of the API the data inside PCO People is available; we are now working towards adding endpoints for some of our other apps (including an all new API for Services).

# Authentication

There are several ways to authenticate with the API.

## Session Authentication

If you need to access the API via a browser, you can use session (cookie) based authentication:

1. Visit [accounts.planningcenteronline.com](https://accounts.planningcenteronline.com) and sign in.
2. Visit [api.planningcenteronline.com/people/v2/people](https://api.planningcenteronline.com/people/v2/people)
   (for example) or other API endpoints.

Browsing the API with your web browser is best experienced with an extension like JSONView, which formats
JSON output in the browser for easier reading.

## Personal Access Token

Create a Personal Access Token and use HTTP Basic Auth if you just need access to your own account:

1. Visit [api.planningcenteronline.com/oauth/applications](https://api.planningcenteronline.com/oauth/applications).
2. Create a new "HTTP Basic Application"
3. Pass your token and secret in every request using [HTTP Basic Auth](https://en.wikipedia.org/wiki/Basic_access_authentication).

## OAuth 2.0

If you are distributing your app to multiple churches, you should use [OAuth](https://en.wikipedia.org/wiki/OAuth).

1. Visit [api.planningcenteronline.com/oauth/applications](https://api.planningcenteronline.com/oauth/applications)
   and create an OAuth application token.
2. Make sure your app conforms to the [OAuth 2.0](http://oauth.net/2/) specification.

# JSON API

This API is built to conform to the [JSON API](http://jsonapi.org/) 1.0 specification.

Some benefits:

* Excellent documentation is already available [here](http://jsonapi.org/format/) and we do our best to stay true to it.
* Our API returns resources that contain links to related resources, making it easier to "browse" this API and learn about associated endpoints.
* You can include related resources by adding `?include=something` to the URL. This makes grabbing what you need much simpler.

Gotchas:

* Resources are wrapped in an object that looks like this: `{ "data": { "type": "Thing", "id": "1", "attributes": { ... } } }`.
* Creating or updating resources also requires that same structure. Be sure to pass the "type" key and put the resource's attributes _inside_ the "attributes" object.

# Dates & Times

All dates and times conform to the [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) standard and look like this:

| value         | format               | example              |
| ------------- | -------------------- | -------------------- |
| date          | YYYY-MM-DD           | 2015-05-05           |
| date and time | YYYY-MM-DDTHH:MM:SSZ | 2015-05-05T22:40:07Z |

<aside class='info'>Times are always returned in UTC.</aside>
