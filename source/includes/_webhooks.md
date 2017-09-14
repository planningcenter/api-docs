# Webhooks

Webhooks allow a third-party application to receive events when something changes in Planning Center

## AvailableEvents

An event supported by webhooks



### List Available Events

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/webhooks/v2/available_events"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/webhooks/v2/available_events`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)







## Deliveries



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
event | Event | _false_ | 

### List Deliveries

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/webhooks/v2/subscriptions/1/events/1/deliveries"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/webhooks/v2/subscriptions/1/events/1/deliveries`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)
order | created_at | prefix with a hyphen (-created_at) to reverse the order

### Get a single Delivery

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/webhooks/v2/subscriptions/1/events/1/deliveries/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Delivery",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "request_body": "string",
      "request_headers": "string",
      "response_body": "string",
      "response_headers": "string",
      "status": 1,
      "timing": 1.42,
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "event": {
        "data": {
          "type": "Event",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/webhooks/v2/subscriptions/1/events/1/deliveries/1`

#### URL Parameters

_none_







## Events



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
subscription | Subscription | _false_ | 

### List Events

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/webhooks/v2/subscriptions/1/events"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/webhooks/v2/subscriptions/1/events`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[uuid] | _string_ | query on a specific uuid
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)
order | created_at | prefix with a hyphen (-created_at) to reverse the order

### Get a single Event

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/webhooks/v2/subscriptions/1/events/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Event",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "payload": "string",
      "updated_at": "2000-01-01T12:00:00Z",
      "uuid": "string"
    },
    "relationships": {
      "subscription": {
        "data": {
          "type": "Subscription",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/webhooks/v2/subscriptions/1/events/1`

#### URL Parameters

_none_

### Associations for an Event

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
deliveries | https://api.planningcenteronline.com/webhooks/v2/subscriptions/1/events/1/deliveries | Delivery

### Actions for an Event

You can perform the following actions on an Event by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
redeliver | https://api.planningcenteronline.com/webhooks/v2/subscriptions/1/events/1/redeliver | 









## Organizations



### Get a single Organization

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/webhooks/v2"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Organization",
    "id": "primary_key",
    "attributes": {
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/webhooks/v2`

#### URL Parameters

_none_

### Associations for an Organization

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
available_events | https://api.planningcenteronline.com/webhooks/v2/available_events | AvailableEvent
subscriptions | https://api.planningcenteronline.com/webhooks/v2/subscriptions | Subscription

### Actions for an Organization

You can perform the following actions on an Organization by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
 |  | 









## Subscriptions

### Attribute Info

<span class='attribute-info-name'>authenticity_secret</span>

Every delivery will include a header `X-PCO-Webhooks-Authenticity`.

This header will be the `HMAC-SHA256` value of this the `authenticity_secret` used as the key,
and the message as the webhook body.

`hmac_sha256(authenticity_secret, webhook_body)`


### List Subscriptions

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/webhooks/v2/subscriptions"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/webhooks/v2/subscriptions`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[application_id] | _string_ | query on a specific application_id
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Subscription

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/webhooks/v2/subscriptions/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Subscription",
    "id": "primary_key",
    "attributes": {
      "active": true,
      "application_id": "string",
      "authenticity_secret": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "updated_at": "2000-01-01T12:00:00Z",
      "url": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/webhooks/v2/subscriptions/1`

#### URL Parameters

_none_

### Associations for a Subscription

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
events | https://api.planningcenteronline.com/webhooks/v2/subscriptions/1/events | Event

### Actions for a Subscription

You can perform the following actions on a Subscription by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
rotate_secret | https://api.planningcenteronline.com/webhooks/v2/subscriptions/1/rotate_secret | 



### Create a new Subscription

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Subscription","attributes":{...}}}' "https://api.planningcenteronline.com/webhooks/v2/subscriptions"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/webhooks/v2/subscriptions`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
url | string
active | boolean

### Update an existing Subscription

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Subscription","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/webhooks/v2/subscriptions/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/webhooks/v2/subscriptions/1`

#### Resource Attributes

Attribute | Type
--------- | ----
active | boolean

### Delete a Subscription

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/webhooks/v2/subscriptions/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/webhooks/v2/subscriptions/1`