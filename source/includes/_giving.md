# PCO Giving

PCO Giving tracks all donations for your church, allowing people to give a one-time gift or set up recurring donations.

## Batches

### Attribute Info

<span class='attribute-info-name'>committed_at</span>

The datetime that a batch was committed. If it's `null`, the batch is still in progress



### List Batches

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/batches"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/batches`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | owner | include associated owner
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Batch

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/batches/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Batch",
    "id": "1",
    "attributes": {
      "committed_at": null,
      "created_at": "2018-02-28T17:56:35Z",
      "total_cents": 150000,
      "total_currency": "USD",
      "updated_at": "2018-02-28T17:56:35Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/batches/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | owner | include associated owner

### Associations for a Batch

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
batch_group | https://api.planningcenteronline.com/giving/v2/batches/1/batch_group | BatchGroup
donations | https://api.planningcenteronline.com/giving/v2/batches/1/donations | Donation
owner | https://api.planningcenteronline.com/giving/v2/batches/1/owner | Person

### Actions for a Batch

You can perform the following actions on a Batch by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
commit | https://api.planningcenteronline.com/giving/v2/batches/1/commit | Used to commit an in progress batch.

#### commit

This action takes an uncommitted batch and commits it.
It will respond with `unprocessable_entity` if the batch cannot be committed.

It does not expect a body.


### Create a new Batch

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Batch","attributes":{...}}}' "https://api.planningcenteronline.com/giving/v2/batches"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/giving/v2/batches`

#### Resource Attributes

Attribute | Type
--------- | ----
description | string

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Batch","attributes":{...}}}' "https://api.planningcenteronline.com/giving/v2/batch_groups/1/batches"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/giving/v2/batch_groups/1/batches`

#### Resource Attributes

Attribute | Type
--------- | ----
description | string

### Update an existing Batch

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Batch","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/giving/v2/batches/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/giving/v2/batches/1`

#### Resource Attributes

Attribute | Type
--------- | ----
description | string

### Delete a Batch

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/giving/v2/batches/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/giving/v2/batches/1`

## BatchGroups





### List Batch Groups

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/batch_groups"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/batch_groups`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | owner | include associated owner
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Batch Group

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/batch_groups/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "BatchGroup",
    "id": "1",
    "attributes": {
      "committed": true,
      "created_at": "2018-02-28T17:56:35Z",
      "total_cents": 350000,
      "total_currency": "USD",
      "updated_at": "2018-02-28T17:56:35Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/batch_groups/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | owner | include associated owner

### Associations for a Batch Group

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
batches | https://api.planningcenteronline.com/giving/v2/batch_groups/1/batches | Batch
owner | https://api.planningcenteronline.com/giving/v2/batch_groups/1/owner | Person







## Designations



### Relationships

Name | Type | To Many | Description
---- | ---- | ------- | -----------
fund | Fund | _false_ |

### List Designations

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/donations/1/designations"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/donations/1/designations`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Designation

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/donations/1/designations/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Designation",
    "id": "2345",
    "attributes": {
      "amount_cents": 1000,
      "amount_currency": "USD"
    },
    "relationships": {
      "fund": {
        "data": {
          "type": "Fund",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/donations/1/designations/1`

#### URL Parameters

_none_

### Associations for a Designation

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
fund | https://api.planningcenteronline.com/giving/v2/donations/1/designations/1/fund | Fund







## DesignationRefunds



### Relationships

Name | Type | To Many | Description
---- | ---- | ------- | -----------
designation | Designation | _false_ |

### List Designation Refunds

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/donations/1/refund/designation_refunds"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/donations/1/refund/designation_refunds`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | designation | include associated designation
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Designation Refund

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/donations/1/refund/designation_refunds/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "DesignationRefund",
    "id": "2345",
    "attributes": {
      "amount_cents": -1000,
      "amount_currency": "USD"
    },
    "relationships": {
      "designation": {
        "data": {
          "type": "Designation",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/donations/1/refund/designation_refunds/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | designation | include associated designation

### Associations for a Designation Refund

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
designation | https://api.planningcenteronline.com/giving/v2/donations/1/refund/designation_refunds/1/designation | Designation







## Donations

### Attribute Info

<span class='attribute-info-name'>payment_brand</span>

For cards, this is the card brand (eg Visa, Mastercard, etc). For checks, this is the bank name

<span class='attribute-info-name'>payment_status</span>

Read only. One of `pending`, `succeeded`, `failed`, or `unknown`.For Stripe donations, this is the payment status. For batch donations, `pending` and `succeeded` values are dependent on whether the batch has been committed.

Possible values: `pending`, `succeeded`, or `failed`

<span class='attribute-info-name'>payment_method_sub</span>

For cards only. Will be `null` for other payment method types.

Possible values: `credit`, `debit`, `prepaid`, or `unknown`

<span class='attribute-info-name'>refundable</span>

Read only. A boolean indicating whether this donation can be refunded via the API. Note that for some donations, this may be false, even though the donation _can_ be refunded in the UI.

<span class='attribute-info-name'>payment_method</span>

Possible values: `ach`, `cash`, `check`, or `card`

### Relationships

Name | Type | To Many | Description
---- | ---- | ------- | -----------
person | Person | _false_ |
payment_source | PaymentSource | _false_ | `PaymentSource` is required, but cannot be `planning_center`, as that is reserved for Donations created in the Planning Center Giving Web UI.

### List Donations

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/donations"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/donations`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[payment_method] | _string_ | query on a specific payment_method
include | designations | include associated designations
include | labels | include associated labels
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=designations,labels</code></aside>

### Get a single Donation

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/donations/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Donation",
    "id": "1",
    "attributes": {
      "amount_cents": 2000,
      "amount_currency": "USD",
      "created_at": "2018-02-28T17:56:35Z",
      "fee_cents": -88,
      "fee_currency": "USD",
      "payment_brand": "Visa",
      "payment_check_dated_at": null,
      "payment_check_number": null,
      "payment_last4": "4242",
      "payment_method": "card",
      "payment_method_sub": "debit",
      "payment_status": "succeeded",
      "received_at": "2018-02-28T00:00:00Z",
      "refunded": false,
      "updated_at": "2018-02-28T17:56:35Z"
    },
    "relationships": {
      "payment_source": {
        "data": {
          "type": "PaymentSource",
          "id": "123"
        }
      },
      "person": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/donations/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | designations | include associated designations
include | labels | include associated labels

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=designations,labels</code></aside>

### Associations for a Donation

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
designations | https://api.planningcenteronline.com/giving/v2/donations/1/designations | Designation
labels | https://api.planningcenteronline.com/giving/v2/donations/1/labels | Label
refund | https://api.planningcenteronline.com/giving/v2/donations/1/refund | Refund

### Actions for a Donation

You can perform the following actions on a Donation by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
issue_refund | https://api.planningcenteronline.com/giving/v2/donations/1/issue_refund | Used to refund a batch donation

#### issue_refund

This action refunds a batch donation.
It will respond with `unprocessable_entity` if the donation cannot be refunded, or if the donation is not part of a batch.

`refunded_at` is optional, but recommended for data accuracy.

```json
{
  "data": {
    "attributes": {
      "refunded_at": "1959-02-03"
    }
  }
}
```


### Create a new Donation

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Donation","attributes":{...}}}' "https://api.planningcenteronline.com/giving/v2/batches/1/donations"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/giving/v2/batches/1/donations`

#### Resource Attributes

Attribute | Type
--------- | ----
payment_method_sub | string
payment_last4 | string
payment_brand | string
payment_check_number | integer
payment_check_dated_at | date
fee_cents | integer
received_at | date_time
payment_method | string

#### Included Resources

```shell
# to create a record with Designations...
curl -v -u token:secret -X POST -d '{"data":{"type":"Donation",...},"included":[{"type":"Designation","attributes":{...}}]}' "https://api.planningcenteronline.com/giving/v2/donations"
```

You may include Designations to create inline with the Donation.

Attribute | Type
--------- | ----
amount_cents | integer

##### Relationships

Name | Type | To Many | Description
---- | ---- | ------- | -----------
fund | Fund | _false_ |

```shell
# A full example of creating a Donation...
curl -u token:secret -X POST -d '
  {
    "data": {
      "type": "Donation",
      "attributes": {
        "payment_method": "cash",
        "received_at": "2017-10-10"
      },
      "relationships": {
        "person": {
          "data": { "type": "Person", "id": "123" }
        },
        "payment_source": {
          "data": { "type": "PaymentSource", "id": "123" }
        }
      }
    },
    "included": [
      {
        "type": "Designation",
        "attributes": { "amount_cents": 2000 },
        "relationships": {
          "fund": {
            "data": { "type": "Fund", "id": "123" }
          }
        }
      }
    ]
  }' https://api.planningcenteronline.com/giving/v2/batches/1/donations
```

#### Notes

When creating a Donation, you _must_ include at least one Designation,
and each Designation _must_ have `amount_cents` and a Fund relationship

### Update an existing Donation

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Donation","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/giving/v2/donations/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/giving/v2/donations/1`

#### Resource Attributes

Attribute | Type
--------- | ----
payment_method_sub | string
payment_last4 | string
payment_brand | string
payment_check_number | integer
payment_check_dated_at | date
fee_cents | integer
received_at | date_time
payment_method | string

#### Included Resources

```shell
# to update a record with Designations...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Donation","id":"1",...},"included":[{"type":"Designation","id":"1","attributes":{...}}]}' "https://api.planningcenteronline.com/giving/v2/donations/1"
```

You may include Designations to update inline with the Donation.

Attribute | Type
--------- | ----
amount_cents | integer

##### Relationships

Name | Type | To Many | Description
---- | ---- | ------- | -----------
fund | Fund | _false_ |

#### Notes

When updating a Donation, if you specify an `id` attribute for each Designation,
those Designations can be updated.

However, if you have Designations in the `included` array _without_ `id`s,
all Designations will be removed and replaced with the Designations in your `PATCH`
request.

### Delete a Donation

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/giving/v2/donations/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/giving/v2/donations/1`

## Funds

### Attribute Info

<span class='attribute-info-name'>color</span>

Hex color code.

<span class='attribute-info-name'>deletable</span>

Read only. Boolean that tells if you if the fund can be deleted or not. Read more [in our product documentation](https://pcogiving.zendesk.com/hc/en-us/articles/205197070-Managing-Funds#deleting-funds)

<span class='attribute-info-name'>visibility</span>

Possible values: `everywhere`, `admin_only`, `nowhere`, or `hidden`



### List Funds

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/funds"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/funds`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Fund

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/funds/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Fund",
    "id": "1",
    "attributes": {
      "color": "#9ccc79",
      "created_at": "2018-02-28T17:56:35Z",
      "deletable": false,
      "description": "These funds are used to support our missionary efforts here in the US.",
      "ledger_code": "dm-22314",
      "name": "Domestic Missions",
      "updated_at": "2018-02-28T17:56:35Z",
      "visibility": "everywhere"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/funds/1`

#### URL Parameters

_none_

### Create a new Fund

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Fund","attributes":{...}}}' "https://api.planningcenteronline.com/giving/v2/funds"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/giving/v2/funds`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
ledger_code | string
description | string
visibility | string
color_identifier | integer

When creating a Fund, a `color_identifier` must be assigned.
A `color_identifier` is an integer that corresponds to an available fund color.
These colors are predefined and not configurable.
There are 12 colors available.

Identifier | Hex Code
--- | ---
1 | #a1a1a1
2 | #b2cf74
3 | #9ccc79
4 | #9bd3b7
5 | #81bbbc
6 | #78afce
7 | #d99fca
8 | #c0a0d2
9 | #f19ca2
10 | #f59b79
11 | #fab676
12 | #cfab77


### Update an existing Fund

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Fund","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/giving/v2/funds/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/giving/v2/funds/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
ledger_code | string
description | string
visibility | string
color_identifier | integer

### Delete a Fund

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/giving/v2/funds/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/giving/v2/funds/1`

## Labels





### List Labels

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/labels"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/labels`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)







## Organizations





### Get a single Organization

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Organization",
    "id": "33445",
    "attributes": {
      "name": "First Ballard Church"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2`

#### URL Parameters

_none_

### Associations for an Organization

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
batch_groups | https://api.planningcenteronline.com/giving/v2/batch_groups | BatchGroup
batches | https://api.planningcenteronline.com/giving/v2/batches | Batch
donations | https://api.planningcenteronline.com/giving/v2/donations | Donation
funds | https://api.planningcenteronline.com/giving/v2/funds | Fund
labels | https://api.planningcenteronline.com/giving/v2/labels | Label
payment_sources | https://api.planningcenteronline.com/giving/v2/payment_sources | PaymentSource
people | https://api.planningcenteronline.com/giving/v2/people | Person
recurring_donations | https://api.planningcenteronline.com/giving/v2/recurring_donations | RecurringDonation







## PaymentMethods

### Attribute Info

<span class='attribute-info-name'>verified</span>

For bank accounts only. Will be `null` for cards.

<span class='attribute-info-name'>method_subtype</span>

For cards, either `credit` or `debit`. For bank accounts, either `checking` or `savings`.

<span class='attribute-info-name'>expiration</span>

For cards only. String representation of the expiration date in the `MM/YYYY` form (without leading zeros). Will be `null` for bank accounts.

<span class='attribute-info-name'>method_type</span>

Possible values: `card` or `bank_account`



### List Payment Methods

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/people/1/payment_methods"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/people/1/payment_methods`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Payment Method

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/people/1/payment_methods/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "PaymentMethod",
    "id": "1",
    "attributes": {
      "brand": "Visa",
      "created_at": "2018-02-28T17:56:35Z",
      "expiration": "8/2018",
      "last4": "4242",
      "method_subtype": "credit",
      "method_type": "card",
      "updated_at": "2018-02-28T17:56:35Z",
      "verified": null
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/people/1/payment_methods/1`

#### URL Parameters

_none_

### Associations for a Payment Method

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
recurring_donations | https://api.planningcenteronline.com/giving/v2/people/1/payment_methods/1/recurring_donations | RecurringDonation







## PaymentSources





### List Payment Sources

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/payment_sources"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/payment_sources`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Payment Source

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/payment_sources/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "PaymentSource",
    "id": "1",
    "attributes": {
      "created_at": "2018-02-28T17:56:35Z",
      "name": "PayPal",
      "updated_at": "2018-02-28T17:56:35Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/payment_sources/1`

#### URL Parameters

_none_

### Associations for a Payment Source

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
donations | https://api.planningcenteronline.com/giving/v2/payment_sources/1/donations | Donation

### Create a new Payment Source

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"PaymentSource","attributes":{...}}}' "https://api.planningcenteronline.com/giving/v2/payment_sources"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/giving/v2/payment_sources`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string

### Update an existing Payment Source

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"PaymentSource","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/giving/v2/payment_sources/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/giving/v2/payment_sources/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string

### Delete a Payment Source

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/giving/v2/payment_sources/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/giving/v2/payment_sources/1`

## People

### Attribute Info

<span class='attribute-info-name'>permissions</span>

Possible values: `administrator`



### List People

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/people"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/people`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[first_name] | _string_ | query on a specific first_name
where[last_name] | _string_ | query on a specific last_name
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Person

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/people/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Person",
    "id": "1",
    "attributes": {
      "addresses": [
        {
          "street": "123 Fake Street",
          "city": "Springfield",
          "state": "CA",
          "zip": "40069",
          "location": "Home"
        }
      ],
      "email_addresses": [
        {
          "address": "pico@pco.bz",
          "location": "Home"
        }
      ],
      "first_name": "PiCO",
      "last_name": "Das Robot",
      "permissions": "administrator",
      "phone_numbers": [
        {
          "number": "(859) 555-4444",
          "carrier": null,
          "location": "Home"
        }
      ]
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/people/1`

#### URL Parameters

_none_

### Associations for a Person

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
 |  | 
batch_groups | https://api.planningcenteronline.com/giving/v2/people/1/batch_groups | BatchGroup
batches | https://api.planningcenteronline.com/giving/v2/people/1/batches | Batch
donations | https://api.planningcenteronline.com/giving/v2/people/1/donations | Donation
payment_methods | https://api.planningcenteronline.com/giving/v2/people/1/payment_methods | PaymentMethod
recurring_donations | https://api.planningcenteronline.com/giving/v2/people/1/recurring_donations | RecurringDonation







## RecurringDonations

### Attribute Info

<span class='attribute-info-name'>status</span>

One of `active`, `indefinite_hold` or `temporary_hold`.

<span class='attribute-info-name'>release_hold_at</span>

The date when a `temporary_hold` will be released.

<span class='attribute-info-name'>schedule</span>

JSON representation of the billing schedule. See the [`repeatable`](https://github.com/molawson/repeatable#time-expressions) Ruby gem for more details on the structure and meaning.



### List Recurring Donations

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/recurring_donations"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/recurring_donations`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | designations | include associated designations
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Recurring Donation

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/recurring_donations/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "RecurringDonation",
    "id": "1",
    "attributes": {
      "amount_cents": 15000,
      "amount_currency": "USD",
      "created_at": "2018-02-28T17:56:35Z",
      "last_donation_received_at": "2018-02-27T00:00:00Z",
      "next_occurrence": "2018-03-27T00:00:00Z",
      "schedule": {
        "day_in_month": {
          "day": 27
        }
      },
      "status": "active",
      "updated_at": "2018-02-28T17:56:35Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/recurring_donations/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | designations | include associated designations

### Associations for a Recurring Donation

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
designations | https://api.planningcenteronline.com/giving/v2/recurring_donations/1/designations | RecurringDonationDesignation
payment_method | https://api.planningcenteronline.com/giving/v2/recurring_donations/1/payment_method | PaymentMethod







## RecurringDonationDesignations





### List Recurring Donation Designations

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/recurring_donations/1/designations"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/recurring_donations/1/designations`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | fund | include associated fund
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Recurring Donation Designation

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/recurring_donations/1/designations/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "RecurringDonationDesignation",
    "id": "1",
    "attributes": {
      "amount_cents": 500,
      "amount_currency": "USD"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/recurring_donations/1/designations/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | fund | include associated fund

### Associations for a Recurring Donation Designation

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
fund | https://api.planningcenteronline.com/giving/v2/recurring_donations/1/designations/1/fund | Fund







## Refund





### Get a single Refund

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/giving/v2/donations/1/refund"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Refund",
    "id": "1",
    "attributes": {
      "amount_cents": -2000,
      "amount_currency": "USD",
      "created_at": "2018-02-28T17:56:35Z",
      "fee_cents": -88,
      "fee_currency": "USD",
      "payment_method": "card",
      "refunded_at": "2018-02-28T00:00:00Z",
      "updated_at": "2018-02-28T17:56:35Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/donations/1/refund`

#### URL Parameters

_none_

### Associations for a Refund

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
designation_refunds | https://api.planningcenteronline.com/giving/v2/donations/1/refund/designation_refunds | DesignationRefund





