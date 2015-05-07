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

Welcome to the Planning Center Online API! You can use our API to access data in some of our apps
(with other apps coming online soon) through a single unified API.

# Authentication

There are several ways to authenticate with the API.

## Session Authentication

If you need to access the API via a browser, you can use session (cookie) based authentication:

1. Visit [accounts.planningcenteronline.com](https://accounts.planningcenteronline.com) and sign in.
2. Visit [api.planningcenteronline.com/people/v1/people](https://api.planningcenteronline.com/people/v1/people)
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

This API is built to conform to the [JSON API](http://jsonapi.org/) standard.

Some benefits:

* Excellent documentation is already available [here](http://jsonapi.org/format/) and we do our best to stay true to it.
* Our API returns resources that contain links to related resources, making it easier to "browse" this API and learn about associated endpoints.
* You can include related resources by adding `?include=something` to the URL. This makes grabbing what you need much simpler.

Gotchas:

* Resources are wrapped in an object that looks like this: `{ "data": { ... } }`.
  This means you will need to dive one layer down into any API result to get the resource you're looking for.
* Creating or updating resources also requires that same `data` key. Put the resource's attributes _inside_ the "data" object.
