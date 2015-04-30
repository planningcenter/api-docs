---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - people
  - errors

search: true
---

# Introduction

Welcome to the Planning Center Online API! You can use our API to access data in some of our apps (with other apps coming online soon) through a single unified API.

# Authentication

TODO

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
