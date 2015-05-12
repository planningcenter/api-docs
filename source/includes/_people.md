# People

Our People app helps you manage contact data, membership info, and everything you need to know about your people with confidence.

## Addresses

An address represents a physical and/or mailing address for a person.

### List Addresses

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/people/1/addresses"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people/1/addresses`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[city] | _string_ | filter on a specific city
where[state] | _string_ | filter on a specific state
where[zip] | _string_ | filter on a specific zip
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Address

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/people/1/addresses/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "city": "string",
    "state": "string",
    "zip": "string"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people/1/addresses/1`

#### URL Parameters

_none_

### Create a new Address

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/people/1/addresses"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/people/1/addresses`

#### Resource Attributes

Attribute | Type
--------- | ----
city | string
state | string
zip | string

### Update an existing Address

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/people/1/addresses/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/people/1/addresses/1`

#### Resource Attributes

Attribute | Type
--------- | ----
city | string
state | string
zip | string

### Delete an Address

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/people/1/addresses/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/people/1/addresses/1`

## Apps

An app is one of the handful of apps that PCO offers that organizations can subscribe to, e.g. Services, Registrations, etc.

### List Apps

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/apps"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/apps`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | filter on a specific name
where[url] | _string_ | filter on a specific url
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single App

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/apps/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "name": "string",
    "url": "string"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/apps/1`

#### URL Parameters

_none_







## Conditions

A condition is an individual criterion used by a List Rule.

### List Conditions

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/lists/1/rules/1/conditions"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/lists/1/rules/1/conditions`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[application] | _string_ | filter on a specific application
where[definition_class] | _string_ | filter on a specific definition_class
where[comparison] | _string_ | filter on a specific comparison
where[settings] | _text_ | filter on a specific settings
where[definition_identifier] | _string_ | filter on a specific definition_identifier
where[description] | _string_ | filter on a specific description
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Condition

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/lists/1/rules/1/conditions/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "application": "string",
    "definition_class": "string",
    "comparison": "string",
    "settings": "stuff",
    "definition_identifier": "string",
    "description": "string",
    "created_at": "2000-01-01T12:00:00Z",
    "updated_at": "2000-01-01T12:00:00Z"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/lists/1/rules/1/conditions/1`

#### URL Parameters

_none_







## ConnectedPeople

A Connected Person is an account from a different organization linked to an account in this organization.

### List Connected People

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/people/1/connected_people"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people/1/connected_people`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Connected Person

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/people/1/connected_people/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ConnectedPerson",
    "id": "1",
    "first_name": "PiCO",
    "middle_name": "Ross",
    "last_name": "Das Robot",
    "gender": "M",
    "organization_id": 1,
    "organization_name": "Ministry Centered Technologies"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people/1/connected_people/1`

#### URL Parameters

_none_







## Emails

An email represents an email address and location.

### List Emails

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/emails"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/emails`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[address] | _string_ | filter on a specific address
where[location] | _string_ | filter on a specific location
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Email

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/emails/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "address": "string",
    "location": "string"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/emails/1`

#### URL Parameters

_none_

### Associations for an Email

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
person | https://api.planningcenteronline.com/people/v1/emails/1/person

### Create a new Email

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/people/1/emails"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/people/1/emails`

#### Resource Attributes

Attribute | Type
--------- | ----
address | string
location | string

### Update an existing Email

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/emails/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/emails/1`

#### Resource Attributes

Attribute | Type
--------- | ----
address | string
location | string

### Delete an Email

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/emails/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/emails/1`

## FieldData

A field datum is an individual piece of data for a custom field.

### List Field Data

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/people/1/field_data"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people/1/field_data`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | filter on a specific value
where[file] | _string_ | filter on a specific file
where[file_size] | _integer_ | filter on a specific file_size
where[file_content_type] | _string_ | filter on a specific file_content_type
include | field_definition | include associated field_definition
include | field_option | include associated field_option
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=field_definition,field_option</code></aside>

### Get a single Field Datum

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/people/1/field_data/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "value": "string",
    "file": "string",
    "file_size": 1,
    "file_content_type": "string"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people/1/field_data/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | field_definition | include associated field_definition
include | field_option | include associated field_option

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=field_definition,field_option</code></aside>

### Associations for a Field Datum

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
field_definition | https://api.planningcenteronline.com/people/v1/people/1/field_data/1/field_definition
field_option | https://api.planningcenteronline.com/people/v1/people/1/field_data/1/field_option

### Create a new Field Datum

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/people/1/field_data"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/people/1/field_data`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string
value | string
file | string

### Update an existing Field Datum

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/people/1/field_data/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/people/1/field_data/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string
value | string
file | string

### Delete a Field Datum

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/people/1/field_data/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/people/1/field_data/1`

## FieldDefinitions

A field definition represents a custom field -- its name, data type, etc.

### List Field Definitions

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/field_definitions"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/field_definitions`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[data_type] | _string_ | filter on a specific data_type
where[name] | _string_ | filter on a specific name
where[sequence] | _integer_ | filter on a specific sequence
where[slug] | _string_ | filter on a specific slug
where[deleted_at] | _datetime_ | filter on a specific deleted_at
include | field_options | include associated field_options
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

To exclude deleted field definitions, query with `where[deleted_at]=` (blank value).

### Get a single Field Definition

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/field_definitions/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "data_type": "string",
    "name": "string",
    "sequence": 1,
    "slug": "string",
    "deleted_at": "2000-01-01T12:00:00Z"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/field_definitions/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | field_options | include associated field_options

### Associations for a Field Definition

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
field_options | https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options

### Create a new Field Definition

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/tabs/1/field_definitions"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/tabs/1/field_definitions`

#### Resource Attributes

Attribute | Type
--------- | ----
data_type | string
name | string
sequence | integer
slug | string
deleted_at | datetime

### Update an existing Field Definition

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/field_definitions/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/field_definitions/1`

#### Resource Attributes

Attribute | Type
--------- | ----
data_type | string
name | string
sequence | integer
slug | string
deleted_at | datetime

### Delete a Field Definition

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/field_definitions/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/field_definitions/1`

Deleting a field definition internally sets its `deleted_at` attribute to the current time.

## FieldOptions

A field option represents an individual option for a custom field of type "select" or "checkboxes".

### List Field Options

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | filter on a specific value
where[sequence] | _integer_ | filter on a specific sequence
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Field Option

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "value": "string",
    "sequence": 1
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options/1`

#### URL Parameters

_none_

### Create a new Field Option

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string
sequence | integer

### Update an existing Field Option

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string
sequence | integer

### Delete a Field Option

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options/1`

## HouseholdMemberships

A household membership is the linking record between a household and a person.

### List Household Memberships

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/households/1/household_memberships"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/households/1/household_memberships`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[person_name] | _string_ | filter on a specific person_name
where[pending] | _boolean_ | filter on a specific pending
include | person | include associated person
include | household | include associated household
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=person,household</code></aside>

### Get a single Household Membership

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/households/1/household_memberships/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "person_name": "string",
    "pending": "stuff"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/households/1/household_memberships/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person
include | household | include associated household

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=person,household</code></aside>

### Associations for a Household Membership

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
household | https://api.planningcenteronline.com/people/v1/households/1/household_memberships/1/household
person | https://api.planningcenteronline.com/people/v1/households/1/household_memberships/1/person

### Create a new Household Membership

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/households/1/household_memberships"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/households/1/household_memberships`

#### Resource Attributes

Attribute | Type
--------- | ----
person_id | integer
pending | boolean

### Update an existing Household Membership

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/households/1/household_memberships/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/households/1/household_memberships/1`

#### Resource Attributes

Attribute | Type
--------- | ----
person_id | integer
pending | boolean

### Delete a Household Membership

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/households/1/household_memberships/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/households/1/household_memberships/1`

## Households

A household links people together and can have a primary contaact.

### List Households

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/households"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/households`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | filter on a specific name
where[member_count] | _integer_ | filter on a specific member_count
where[primary_contact_name] | _string_ | filter on a specific primary_contact_name
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
include | people | include associated people
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Household

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/households/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "name": "string",
    "member_count": 1,
    "primary_contact_name": "string",
    "created_at": "2000-01-01T12:00:00Z",
    "updated_at": "2000-01-01T12:00:00Z",
    "primary_contact_id": 1
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/households/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | people | include associated people

### Associations for a Household

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
household_memberships | https://api.planningcenteronline.com/people/v1/households/1/household_memberships
people | https://api.planningcenteronline.com/people/v1/households/1/people

### Create a new Household

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/households"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/households`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
member_count | integer
primary_contact_id | integer

### Update an existing Household

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/households/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/households/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
member_count | integer
primary_contact_id | integer

### Delete a Household

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/households/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/households/1`

## InactiveReasons

An inactive reason is a small bit of text indicating why a member is no longer active.

### List Inactive Reasons

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/inactive_reasons"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/inactive_reasons`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | filter on a specific value
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Inactive Reason

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/inactive_reasons/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "value": "string"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/inactive_reasons/1`

#### URL Parameters

_none_

### Create a new Inactive Reason

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/inactive_reasons"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/inactive_reasons`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Update an existing Inactive Reason

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/inactive_reasons/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/inactive_reasons/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Delete an Inactive Reason

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/inactive_reasons/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/inactive_reasons/1`

## Lists

A list (aka "filter") is a powerful tool for finding and grouping people together using any criteria imaginable.

### List Lists

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/lists"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/lists`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | filter on a specific name
where[status] | _string_ | filter on a specific status
where[batch_completed_at] | _datetime_ | filter on a specific batch_completed_at
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
include | created_by | include associated created_by
include | updated_by | include associated updated_by
include | owner | include associated owner
include | people | include associated people
include | rules | include associated rules
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=created_by,updated_by</code></aside>

### Get a single List

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/lists/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "name": "string",
    "status": "string",
    "batch_completed_at": "2000-01-01T12:00:00Z",
    "created_at": "2000-01-01T12:00:00Z",
    "updated_at": "2000-01-01T12:00:00Z"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/lists/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | created_by | include associated created_by
include | updated_by | include associated updated_by
include | owner | include associated owner
include | people | include associated people
include | rules | include associated rules

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=created_by,updated_by</code></aside>

### Associations for a List

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
created_by | https://api.planningcenteronline.com/people/v1/lists/1/created_by
owner | https://api.planningcenteronline.com/people/v1/lists/1/owner
people | https://api.planningcenteronline.com/people/v1/lists/1/people
rules | https://api.planningcenteronline.com/people/v1/lists/1/rules
updated_by | https://api.planningcenteronline.com/people/v1/lists/1/updated_by







## MaritalStatuses

A martial status represents a member's current status, e.g. married, single, etc.

### List Marital Statuses

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/marital_statuses"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/marital_statuses`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | filter on a specific value
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Marital Status

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/marital_statuses/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "value": "string"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/marital_statuses/1`

#### URL Parameters

_none_

### Create a new Marital Status

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/marital_statuses"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/marital_statuses`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Update an existing Marital Status

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/marital_statuses/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/marital_statuses/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Delete a Marital Status

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/marital_statuses/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/marital_statuses/1`

## MessageGroups

A message group represents one or more emails or text messages sent from one of the PCO apps. The message group indicates the from person, app, etc.

### List Message Groups

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/message_groups"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/message_groups`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[uuid] | _string_ | filter on a specific uuid
where[message_type] | _string_ | filter on a specific message_type
where[from_address] | _string_ | filter on a specific from_address
where[subject] | _string_ | filter on a specific subject
where[message_count] | _integer_ | filter on a specific message_count
where[system_message] | _boolean_ | filter on a specific system_message
where[created_at] | _datetime_ | filter on a specific created_at
include | messages | include associated messages
include | from | include associated from
include | app | include associated app
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=messages,from</code></aside>

### Get a single Message Group

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/message_groups/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "uuid": "string",
    "message_type": "string",
    "from_address": "string",
    "subject": "string",
    "message_count": 1,
    "system_message": "stuff",
    "created_at": "2000-01-01T12:00:00Z"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/message_groups/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | messages | include associated messages
include | from | include associated from
include | app | include associated app

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=messages,from</code></aside>

### Associations for a Message Group

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
app | https://api.planningcenteronline.com/people/v1/message_groups/1/app
from | https://api.planningcenteronline.com/people/v1/message_groups/1/from
messages | https://api.planningcenteronline.com/people/v1/message_groups/1/messages







## Messages

A message is an individual email or sms text sent to a member. Every message has a parent message group.

### List Messages

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/messages"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/messages`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[kind] | _integer_ | filter on a specific kind
where[to_addresses] | _string_ | filter on a specific to_addresses
where[subject] | _string_ | filter on a specific subject
where[file] | _string_ | filter on a specific file
where[delivery_status] | _string_ | filter on a specific delivery_status
where[reject_reason] | _string_ | filter on a specific reject_reason
where[created_at] | _datetime_ | filter on a specific created_at
where[sent_at] | _datetime_ | filter on a specific sent_at
where[bounced_at] | _datetime_ | filter on a specific bounced_at
where[rejection_notification_sent_at] | _datetime_ | filter on a specific rejection_notification_sent_at
include | message_group | include associated message_group
include | to | include associated to
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=message_group,to</code></aside>

### Get a single Message

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/messages/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "kind": 1,
    "to_addresses": "string",
    "subject": "string",
    "file": "string",
    "delivery_status": "string",
    "reject_reason": "string",
    "created_at": "2000-01-01T12:00:00Z",
    "sent_at": "2000-01-01T12:00:00Z",
    "bounced_at": "2000-01-01T12:00:00Z",
    "rejection_notification_sent_at": "2000-01-01T12:00:00Z"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/messages/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | message_group | include associated message_group
include | to | include associated to

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=message_group,to</code></aside>

### Associations for a Message

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
message_group | https://api.planningcenteronline.com/people/v1/messages/1/message_group
to | https://api.planningcenteronline.com/people/v1/messages/1/to







## NamePrefixes

A name prefix is one of Mr., Mrs., etc.

### List Name Prefixes

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/name_prefixes"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/name_prefixes`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | filter on a specific value
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Name Prefix

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/name_prefixes/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "value": "string"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/name_prefixes/1`

#### URL Parameters

_none_

### Create a new Name Prefix

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/name_prefixes"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/name_prefixes`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Update an existing Name Prefix

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/name_prefixes/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/name_prefixes/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Delete a Name Prefix

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/name_prefixes/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/name_prefixes/1`

## NameSuffixes

A name suffix is one of Sr., Jr., etc.

### List Name Suffixes

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/name_suffixes"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/name_suffixes`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | filter on a specific value
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Name Suffix

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/name_suffixes/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "value": "string"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/name_suffixes/1`

#### URL Parameters

_none_

### Create a new Name Suffix

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/name_suffixes"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/name_suffixes`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Update an existing Name Suffix

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/name_suffixes/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/name_suffixes/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Delete a Name Suffix

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/name_suffixes/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/name_suffixes/1`

## Organizations

The organization represents a single church. Every other resource is scoped to this record.

### Get a single Organization

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "name": "string"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1`

#### URL Parameters

_none_

### Associations for an Organization

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
apps | https://api.planningcenteronline.com/people/v1/apps
emails | https://api.planningcenteronline.com/people/v1/emails
field_definitions | https://api.planningcenteronline.com/people/v1/field_definitions
households | https://api.planningcenteronline.com/people/v1/households
inactive_reasons | https://api.planningcenteronline.com/people/v1/inactive_reasons
lists | https://api.planningcenteronline.com/people/v1/lists
marital_statuses | https://api.planningcenteronline.com/people/v1/marital_statuses
message_groups | https://api.planningcenteronline.com/people/v1/message_groups
messages | https://api.planningcenteronline.com/people/v1/messages
name_prefixes | https://api.planningcenteronline.com/people/v1/name_prefixes
name_suffixes | https://api.planningcenteronline.com/people/v1/name_suffixes
people | https://api.planningcenteronline.com/people/v1/people
reports | https://api.planningcenteronline.com/people/v1/reports
school_options | https://api.planningcenteronline.com/people/v1/school_options
social_profiles | https://api.planningcenteronline.com/people/v1/social_profiles
tabs | https://api.planningcenteronline.com/people/v1/tabs







## People

A person record represents a single member/user of the application. Each person has different permissions that determine how the user can use this app (if at all).

### List People

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/people"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[first_name] | _string_ | filter on a specific first_name
where[middle_name] | _string_ | filter on a specific middle_name
where[last_name] | _string_ | filter on a specific last_name
where[birthdate] | _date_ | filter on a specific birthdate
where[anniversary] | _date_ | filter on a specific anniversary
where[gender] | _string_ | filter on a specific gender
where[grade] | _integer_ | filter on a specific grade
where[child] | _boolean_ | filter on a specific child
where[status] | _string_ | filter on a specific status
where[school_type] | _string_ | filter on a specific school_type
where[graduation_year] | _integer_ | filter on a specific graduation_year
where[site_administrator] | _boolean_ | filter on a specific site_administrator
where[people_permissions] | _string_ | filter on a specific people_permissions
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
include | emails | include associated emails
include | addresses | include associated addresses
include | phone_numbers | include associated phone_numbers
include | households | include associated households
include | school | include associated school
include | inactive_reason | include associated inactive_reason
include | marital_status | include associated marital_status
include | name_prefix | include associated name_prefix
include | name_suffix | include associated name_suffix
include | field_data | include associated field_data
include | apps | include associated apps
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=emails,addresses</code></aside>

### Get a single Person

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/people/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Person",
    "id": "1",
    "first_name": "PiCO",
    "middle_name": "Ross",
    "last_name": "Das Robot",
    "birthdate": "1982-01-01",
    "anniversary": "2012-04-01",
    "gender": "M",
    "grade": null,
    "child": false,
    "status": "active",
    "school_type": "elementary",
    "graduation_year": 2000,
    "site_administrator": true,
    "people_permissions": "Viewer",
    "created_at": "2015-03-18T19:31:54Z",
    "updated_at": "2015-04-21T22:52:53Z",
    "avatar": "https://account-center-production.s3.amazonaws.com/uploads/person/1-1426707114/avatar.4.png"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | emails | include associated emails
include | addresses | include associated addresses
include | phone_numbers | include associated phone_numbers
include | households | include associated households
include | school | include associated school
include | inactive_reason | include associated inactive_reason
include | marital_status | include associated marital_status
include | name_prefix | include associated name_prefix
include | name_suffix | include associated name_suffix
include | field_data | include associated field_data
include | apps | include associated apps

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=emails,addresses</code></aside>

### Associations for a Person

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
addresses | https://api.planningcenteronline.com/people/v1/people/1/addresses
apps | https://api.planningcenteronline.com/people/v1/people/1/apps
connected_people | https://api.planningcenteronline.com/people/v1/people/1/connected_people
emails | https://api.planningcenteronline.com/people/v1/people/1/emails
field_data | https://api.planningcenteronline.com/people/v1/people/1/field_data
household_memberships | https://api.planningcenteronline.com/people/v1/people/1/household_memberships
households | https://api.planningcenteronline.com/people/v1/people/1/households
inactive_reason | https://api.planningcenteronline.com/people/v1/people/1/inactive_reason
marital_status | https://api.planningcenteronline.com/people/v1/people/1/marital_status
name_prefix | https://api.planningcenteronline.com/people/v1/people/1/name_prefix
name_suffix | https://api.planningcenteronline.com/people/v1/people/1/name_suffix
phone_numbers | https://api.planningcenteronline.com/people/v1/people/1/phone_numbers
school | https://api.planningcenteronline.com/people/v1/people/1/school
social_profiles | https://api.planningcenteronline.com/people/v1/people/1/social_profiles

### Create a new Person

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/people"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/people`

#### Resource Attributes

Attribute | Type
--------- | ----
first_name | string
middle_name | string
last_name | string
birthdate | date
anniversary | date
gender | string
grade | integer
child | boolean
status | string
school_type | string
graduation_year | integer
site_administrator | boolean
people_permissions | string
name_prefix_id | integer
name_suffix_id | integer
inactive_reason_id | integer
school_id | integer
marital_status_id | integer

### Update an existing Person

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/people/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/people/1`

#### Resource Attributes

Attribute | Type
--------- | ----
first_name | string
middle_name | string
last_name | string
birthdate | date
anniversary | date
gender | string
grade | integer
child | boolean
status | string
school_type | string
graduation_year | integer
site_administrator | boolean
people_permissions | string
name_prefix_id | integer
name_suffix_id | integer
inactive_reason_id | integer
school_id | integer
marital_status_id | integer

### Delete a Person

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/people/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/people/1`

## PhoneNumbers

A phone number represents a single telephone number and location.

### List Phone Numbers

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/people/1/phone_numbers"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people/1/phone_numbers`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[number] | _string_ | filter on a specific number
where[location] | _string_ | filter on a specific location
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Phone Number

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/people/1/phone_numbers/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "number": "string",
    "location": "string",
    "created_at": "2000-01-01T12:00:00Z",
    "updated_at": "2000-01-01T12:00:00Z"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people/1/phone_numbers/1`

#### URL Parameters

_none_

### Create a new Phone Number

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/people/1/phone_numbers"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/people/1/phone_numbers`

#### Resource Attributes

Attribute | Type
--------- | ----
number | string
location | string

### Update an existing Phone Number

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/people/1/phone_numbers/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/people/1/phone_numbers/1`

#### Resource Attributes

Attribute | Type
--------- | ----
number | string
location | string

### Delete a Phone Number

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/people/1/phone_numbers/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/people/1/phone_numbers/1`

## Reports

A report is editable liquid syntax that provides a powerful tool for presenting your Lists however you want.

### List Reports

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/reports"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/reports`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | filter on a specific name
where[body] | _text_ | filter on a specific body
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
include | created_by | include associated created_by
include | updated_by | include associated updated_by
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=created_by,updated_by</code></aside>

### Get a single Report

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/reports/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "name": "string",
    "body": "stuff",
    "created_at": "2000-01-01T12:00:00Z",
    "updated_at": "2000-01-01T12:00:00Z"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/reports/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | created_by | include associated created_by
include | updated_by | include associated updated_by

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=created_by,updated_by</code></aside>

### Associations for a Report

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
created_by | https://api.planningcenteronline.com/people/v1/reports/1/created_by
updated_by | https://api.planningcenteronline.com/people/v1/reports/1/updated_by

### Create a new Report

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/reports"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/reports`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
body | text

### Update an existing Report

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/reports/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/reports/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
body | text

### Delete a Report

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/reports/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/reports/1`

## Rules

A rule belongs to a List and groups conditions together.

### List Rules

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/lists/1/rules"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/lists/1/rules`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
include | conditions | include associated conditions
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Rule

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/lists/1/rules/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "created_at": "2000-01-01T12:00:00Z",
    "updated_at": "2000-01-01T12:00:00Z"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/lists/1/rules/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | conditions | include associated conditions

### Associations for a Rule

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
conditions | https://api.planningcenteronline.com/people/v1/lists/1/rules/1/conditions







## SchoolOptions

A school option represents a school name, school type, grades, etc. and can be added to a person.

### List School Options

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/school_options"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/school_options`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | filter on a specific value
where[school_types] | __ | filter on a specific school_types
where[beginning_grade] | __ | filter on a specific beginning_grade
where[ending_grade] | __ | filter on a specific ending_grade
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single School Option

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/school_options/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "value": "string",
    "school_types": "stuff",
    "beginning_grade": "stuff",
    "ending_grade": "stuff"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/school_options/1`

#### URL Parameters

_none_

### Associations for a School Option

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
promotes_to_school | https://api.planningcenteronline.com/people/v1/school_options/1/promotes_to_school

### Create a new School Option

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/school_options"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/school_options`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string
school_types | 
beginning_grade | 
ending_grade | 

### Update an existing School Option

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/school_options/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/school_options/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string
school_types | 
beginning_grade | 
ending_grade | 

### Delete a School Option

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/school_options/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/school_options/1`

## SocialProfiles

A social profile represents a members's Twitter, Facebook, or other social media account.

### List Social Profiles

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/social_profiles"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/social_profiles`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[site] | _string_ | filter on a specific site
where[url] | _string_ | filter on a specific url
where[verified] | _boolean_ | filter on a specific verified
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
include | person | include associated person
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Social Profile

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/social_profiles/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "site": "string",
    "url": "string",
    "verified": "stuff",
    "created_at": "2000-01-01T12:00:00Z",
    "updated_at": "2000-01-01T12:00:00Z"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/social_profiles/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person

### Associations for a Social Profile

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
person | https://api.planningcenteronline.com/people/v1/social_profiles/1/person

### Create a new Social Profile

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/people/1/social_profiles"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/people/1/social_profiles`

#### Resource Attributes

Attribute | Type
--------- | ----
site | string
url | string
verified | boolean

### Update an existing Social Profile

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/social_profiles/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/social_profiles/1`

#### Resource Attributes

Attribute | Type
--------- | ----
site | string
url | string
verified | boolean

### Delete a Social Profile

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/social_profiles/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/social_profiles/1`

## Tabs

A tab is a custom tab and groups like field definitions.

### List Tabs

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/tabs"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/tabs`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | filter on a specific name
where[sequence] | _integer_ | filter on a specific sequence
where[slug] | _string_ | filter on a specific slug
include | field_definitions | include associated field_definitions
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Tab

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v1/tabs/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "name": "string",
    "sequence": 1,
    "slug": "string"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/tabs/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | field_definitions | include associated field_definitions

### Associations for a Tab

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
field_definitions | https://api.planningcenteronline.com/people/v1/tabs/1/field_definitions

### Create a new Tab

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/tabs"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v1/tabs`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
sequence | integer
slug | string

### Update an existing Tab

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{...}}' "https://api.planningcenteronline.com/people/v1/tabs/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v1/tabs/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
sequence | integer
slug | string

### Delete a Tab

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v1/tabs/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v1/tabs/1`