# PCO Giving (BETA)

PCO Giving tracks all donations for your church, allowing people to give a one-time gift or set up recurring donations.

## Batches

### Attribute Info

<span class='attribute-info-name'>status</span>

One of `in_progress` or `committed`.

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
      "created_at": "2017-07-06T11:59:38Z",
      "status": "in_progress",
      "total_cents": 150000,
      "total_currency": "USD",
      "updated_at": "2017-07-06T11:59:38Z"
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
owner | https://api.planningcenteronline.com/giving/v2/batches/1/owner | Person







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
      "created_at": "2017-07-06T11:59:38Z",
      "total_cents": 350000,
      "total_currency": "USD",
      "updated_at": "2017-07-06T11:59:38Z"
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
include | fund | include associated fund
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
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/giving/v2/donations/1/designations/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | fund | include associated fund

### Associations for a Designation

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
fund | https://api.planningcenteronline.com/giving/v2/donations/1/designations/1/fund | Fund







## Donations

### Attribute Info

<span class='attribute-info-name'>payment_status</span>

One of `pending`, `succeeded`, or `failed`.

<span class='attribute-info-name'>payment_method</span>

One of `ach`, `cash`, `check`, or `card`.

<span class='attribute-info-name'>payment_method_sub</span>

For cards only. One of `credit`, `debit`, `prepaid`, or `unknown`. Will be `null` for other payment method types.

### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
person | Person | _false_ | 

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
      "created_at": "2017-07-06T11:59:38Z",
      "fee_cents": -88,
      "fee_currency": "USD",
      "payment_brand": "Visa",
      "payment_last4": "4242",
      "payment_method": "card",
      "payment_method_sub": "debit",
      "payment_status": "succeeded",
      "updated_at": "2017-07-06T11:59:38Z"
    },
    "relationships": {
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







## Funds

### Attribute Info

<span class='attribute-info-name'>color</span>

Hex color code.

<span class='attribute-info-name'>visibility</span>

One of `everywhere`, `admin_only`, or `nowhere`.

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
      "created_at": "2017-07-06T11:59:38Z",
      "description": "These funds are used to support our missionary efforts here in the US.",
      "ledger_code": "dm-22314",
      "name": "Domestic Missions",
      "updated_at": "2017-07-06T11:59:38Z",
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
people | https://api.planningcenteronline.com/giving/v2/people | Person
recurring_donations | https://api.planningcenteronline.com/giving/v2/recurring_donations | RecurringDonation







## PaymentMethods

### Attribute Info

<span class='attribute-info-name'>verified</span>

For bank accounts only. Will be `null` for cards.

<span class='attribute-info-name'>method_type</span>

Either `card` or `bank_account`.

<span class='attribute-info-name'>method_subtype</span>

For cards, either `credit` or `debit`. For bank accounts, either `checking or savings`.

<span class='attribute-info-name'>expiration</span>

For cards only. String representation of the expiration date in the `MM/YYYY` form (without leading zeros). Will be `null` for bank accounts.

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
      "created_at": "2017-07-06T11:59:38Z",
      "expiration": "8/2018",
      "last4": "4242",
      "method_subtype": "credit",
      "method_type": "card",
      "updated_at": "2017-07-06T11:59:38Z",
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







## People

### Attribute Info

<span class='attribute-info-name'>permissions</span>

Either `administrator` or `null`.

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

One of `active`, `on hold indefinitely` or `on hold until {date}`.

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
      "created_at": "2017-07-06T11:59:38Z",
      "last_donation_received_at": "2017-07-05T00:00:00Z",
      "next_occurrence": "2017-08-05T00:00:00Z",
      "schedule": {
        "day_in_month": {
          "day": 5
        }
      },
      "status": "active",
      "updated_at": "2017-07-06T11:59:38Z"
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





