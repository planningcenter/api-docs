# PCO People

PCO People helps you manage contact data, membership info, and everything you need to know about your people with confidence.

## Addresses

An address represents a physical and/or mailing address for a person.



### List Addresses

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/people/1/addresses"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/people/1/addresses`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[city] | _string_ | query on a specific city
where[state] | _string_ | query on a specific state
where[zip] | _string_ | query on a specific zip
where[street] | _string_ | query on a specific street
where[location] | _string_ | query on a specific location
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Address

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/people/1/addresses/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Address",
    "id": "primary_key",
    "attributes": {
      "city": "string",
      "location": "string",
      "state": "string",
      "street": "string",
      "zip": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/people/1/addresses/1`

#### URL Parameters

_none_

### Create a new Address

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Address","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/people/1/addresses"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/people/1/addresses`

#### Resource Attributes

Attribute | Type
--------- | ----
city | string
state | string
zip | string
street | string
location | string

### Update an existing Address

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Address","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/people/1/addresses/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/people/1/addresses/1`

#### Resource Attributes

Attribute | Type
--------- | ----
city | string
state | string
zip | string
street | string
location | string

### Delete an Address

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/people/1/addresses/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/people/1/addresses/1`

## Apps

An app is one of the handful of apps that PCO offers that organizations can subscribe to, e.g. Services, Registrations, etc.



### List Apps

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/apps"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/apps`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | query on a specific name
where[url] | _string_ | query on a specific url
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single App

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/apps/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "App",
    "id": "primary_key",
    "attributes": {
      "name": "string",
      "url": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/apps/1`

#### URL Parameters

_none_







## Campuses

A Campus is a location belonging to an Organization



### List Campuses

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/campuses"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/campuses`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Campus

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/campuses/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Campus",
    "id": "primary_key",
    "attributes": {
      "latitude": "unknown",
      "longitude": "unknown",
      "name": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/campuses/1`

#### URL Parameters

_none_







## Carriers



### List Carriers

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/carriers"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/carriers`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)







## Conditions

A condition is an individual criterion used by a List Rule.



### List Conditions

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/lists/1/rules/1/conditions"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/lists/1/rules/1/conditions`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[application] | _string_ | query on a specific application
where[definition_class] | _string_ | query on a specific definition_class
where[comparison] | _string_ | query on a specific comparison
where[settings] | _string_ | query on a specific settings
where[definition_identifier] | _string_ | query on a specific definition_identifier
where[description] | _string_ | query on a specific description
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Condition

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/lists/1/rules/1/conditions/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Condition",
    "id": "primary_key",
    "attributes": {
      "application": "string",
      "comparison": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "definition_class": "string",
      "definition_identifier": "string",
      "description": "string",
      "settings": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/lists/1/rules/1/conditions/1`

#### URL Parameters

_none_

### Associations for a Condition

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
results | https://api.planningcenteronline.com/people/v2/lists/1/rules/1/conditions/1/results | ConditionResult







## ConditionResults

A Condition Result represents a matched record for this Condition.



### List Condition Results

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/lists/1/rules/1/conditions/1/results"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/lists/1/rules/1/conditions/1/results`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Condition Result

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/lists/1/rules/1/conditions/1/results/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ConditionResult",
    "id": "primary_key",
    "attributes": {
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/lists/1/rules/1/conditions/1/results/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person

### Associations for a Condition Result

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
person | https://api.planningcenteronline.com/people/v2/lists/1/rules/1/conditions/1/results/1/person | Person







## ConnectedPeople

A Connected Person is an account from a different organization linked to an account in this organization.



### List Connected People

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/people/1/connected_people"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/people/1/connected_people`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Connected Person

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/people/1/connected_people/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ConnectedPerson",
    "id": "1",
    "attributes": {
      "first_name": "PiCO",
      "gender": "M",
      "goes_by_name": "P Riddy",
      "last_name": "Das Robot",
      "middle_name": "Ross",
      "organization_id": 1,
      "organization_name": "Ministry Centered Technologies",
      "type": "ConnectedPerson"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/people/1/connected_people/1`

#### URL Parameters

_none_







## Emails

An email represents an email address and location.



### List Emails

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/emails"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/emails`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[address] | _string_ | query on a specific address
where[location] | _string_ | query on a specific location
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Email

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/emails/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Email",
    "id": "primary_key",
    "attributes": {
      "address": "string",
      "location": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/emails/1`

#### URL Parameters

_none_

### Associations for an Email

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
person | https://api.planningcenteronline.com/people/v2/emails/1/person | Person

### Create a new Email

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Email","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/people/1/emails"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/people/1/emails`

#### Resource Attributes

Attribute | Type
--------- | ----
address | string
location | string

### Update an existing Email

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Email","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/emails/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/emails/1`

#### Resource Attributes

Attribute | Type
--------- | ----
address | string
location | string

### Delete an Email

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/emails/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/emails/1`

## FieldData

A field datum is an individual piece of data for a custom field.



### List Field Data

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/people/1/field_data"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/people/1/field_data`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | query on a specific value
where[file] | _string_ | query on a specific file
where[file_size] | _integer_ | query on a specific file_size
where[file_content_type] | _string_ | query on a specific file_content_type
where[file_name] | _graph/type_annotation/unknown_type_annotation_ | query on a specific file_name
include | field_definition | include associated field_definition
include | field_option | include associated field_option
include | tab | include associated tab
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=field_definition,field_option</code></aside>

### Get a single Field Datum

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/people/1/field_data/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "FieldDatum",
    "id": "primary_key",
    "attributes": {
      "file": "string",
      "file_content_type": "string",
      "file_name": "unknown",
      "file_size": 1,
      "value": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/people/1/field_data/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | field_definition | include associated field_definition
include | field_option | include associated field_option
include | tab | include associated tab

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=field_definition,field_option</code></aside>

### Associations for a Field Datum

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
field_definition | https://api.planningcenteronline.com/people/v2/people/1/field_data/1/field_definition | FieldDefinition
field_option | https://api.planningcenteronline.com/people/v2/people/1/field_data/1/field_option | FieldOption
tab | https://api.planningcenteronline.com/people/v2/people/1/field_data/1/tab | Tab

### Create a new Field Datum

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"FieldDatum","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/people/1/field_data"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/people/1/field_data`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Update an existing Field Datum

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"FieldDatum","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/people/1/field_data/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/people/1/field_data/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Delete a Field Datum

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/people/1/field_data/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/people/1/field_data/1`

## FieldDefinitions

A field definition represents a custom field -- its name, data type, etc.



### List Field Definitions

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/field_definitions"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/field_definitions`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[data_type] | _string_ | query on a specific data_type
where[name] | _string_ | query on a specific name
where[sequence] | _integer_ | query on a specific sequence
where[slug] | _string_ | query on a specific slug
where[deleted_at] | _date_time_ | query on a specific deleted_at
filter | include_deleted | By default, deleted fields are not included. Pass filter=include_deleted to include them.
include | field_options | include associated field_options
include | tab | include associated tab
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=field_options,tab</code></aside>

To exclude deleted field definitions, query with `where[deleted_at]=` (blank value).

### Get a single Field Definition

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/field_definitions/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "FieldDefinition",
    "id": "primary_key",
    "attributes": {
      "data_type": "string",
      "deleted_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "sequence": 1,
      "slug": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/field_definitions/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | field_options | include associated field_options
include | tab | include associated tab

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=field_options,tab</code></aside>

### Associations for a Field Definition

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
field_options | https://api.planningcenteronline.com/people/v2/field_definitions/1/field_options | FieldOption
tab | https://api.planningcenteronline.com/people/v2/field_definitions/1/tab | Tab

### Create a new Field Definition

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"FieldDefinition","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/tabs/1/field_definitions"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/tabs/1/field_definitions`

#### Resource Attributes

Attribute | Type
--------- | ----
data_type | string
name | string
sequence | integer
slug | string
deleted_at | date_time

### Update an existing Field Definition

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"FieldDefinition","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/field_definitions/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/field_definitions/1`

#### Resource Attributes

Attribute | Type
--------- | ----
data_type | string
name | string
sequence | integer
slug | string
deleted_at | date_time

### Delete a Field Definition

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/field_definitions/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/field_definitions/1`

Deleting a field definition internally sets its `deleted_at` attribute to the current time.

## FieldOptions

A field option represents an individual option for a custom field of type "select" or "checkboxes".



### List Field Options

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/field_definitions/1/field_options"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/field_definitions/1/field_options`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | query on a specific value
where[sequence] | _integer_ | query on a specific sequence
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Field Option

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/field_definitions/1/field_options/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "FieldOption",
    "id": "primary_key",
    "attributes": {
      "sequence": 1,
      "value": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/field_definitions/1/field_options/1`

#### URL Parameters

_none_

### Create a new Field Option

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"FieldOption","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/field_definitions/1/field_options"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/field_definitions/1/field_options`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string
sequence | integer

### Update an existing Field Option

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"FieldOption","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/field_definitions/1/field_options/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/field_definitions/1/field_options/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string
sequence | integer

### Delete a Field Option

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/field_definitions/1/field_options/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/field_definitions/1/field_options/1`

## Households

A household links people together and can have a primary contaact.



### List Households

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/households"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/households`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | query on a specific name
where[member_count] | _integer_ | query on a specific member_count
where[primary_contact_name] | _string_ | query on a specific primary_contact_name
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
include | people | include associated people
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Household

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/households/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Household",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "member_count": 1,
      "name": "string",
      "primary_contact_id": 1,
      "primary_contact_name": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/households/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | people | include associated people

### Associations for a Household

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
household_memberships | https://api.planningcenteronline.com/people/v2/households/1/household_memberships | HouseholdMembership
people | https://api.planningcenteronline.com/people/v2/households/1/people | Person

### Create a new Household

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Household","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/households"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/households`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
member_count | integer
primary_contact_id | integer

To create a new household, you must specify the primary contact and the people as relationships: `{"data":{"attributes":{"name":"Smith"},"relationships":{"people":{"data":[{"type":"Person","id":"1"},{"type":"Person","id":"2"}]},"primary_contact":{"data":{"type":"Person","id":"1"}}}}}`

### Update an existing Household

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Household","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/households/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/households/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
member_count | integer
primary_contact_id | integer

### Delete a Household

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/households/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/households/1`

## HouseholdMemberships

A household membership is the linking record between a household and a person.



### List Household Memberships

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/households/1/household_memberships"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/households/1/household_memberships`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[person_name] | _string_ | query on a specific person_name
where[pending] | _boolean_ | query on a specific pending
include | person | include associated person
include | household | include associated household
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=person,household</code></aside>

### Get a single Household Membership

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/households/1/household_memberships/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "HouseholdMembership",
    "id": "primary_key",
    "attributes": {
      "pending": true,
      "person_name": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/households/1/household_memberships/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person
include | household | include associated household

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=person,household</code></aside>

### Associations for a Household Membership

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
household | https://api.planningcenteronline.com/people/v2/households/1/household_memberships/1/household | Household
person | https://api.planningcenteronline.com/people/v2/households/1/household_memberships/1/person | Person

### Create a new Household Membership

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"HouseholdMembership","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/households/1/household_memberships"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/households/1/household_memberships`

#### Resource Attributes

Attribute | Type
--------- | ----
pending | boolean

### Update an existing Household Membership

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"HouseholdMembership","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/households/1/household_memberships/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/households/1/household_memberships/1`

#### Resource Attributes

Attribute | Type
--------- | ----
pending | boolean

### Delete a Household Membership

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/households/1/household_memberships/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/households/1/household_memberships/1`

## InactiveReasons

An inactive reason is a small bit of text indicating why a member is no longer active.



### List Inactive Reasons

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/inactive_reasons"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/inactive_reasons`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | query on a specific value
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Inactive Reason

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/inactive_reasons/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "InactiveReason",
    "id": "primary_key",
    "attributes": {
      "value": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/inactive_reasons/1`

#### URL Parameters

_none_

### Create a new Inactive Reason

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"InactiveReason","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/inactive_reasons"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/inactive_reasons`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Update an existing Inactive Reason

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"InactiveReason","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/inactive_reasons/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/inactive_reasons/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Delete an Inactive Reason

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/inactive_reasons/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/inactive_reasons/1`

## Lists

A list is a powerful tool for finding and grouping people together using any criteria imaginable.



### List Lists

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/lists"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/lists`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | query on a specific name
where[batch_completed_at] | _date_time_ | query on a specific batch_completed_at
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
include | created_by | include associated created_by
include | updated_by | include associated updated_by
include | owner | include associated owner
include | people | include associated people
include | rules | include associated rules
include | shares | include associated shares
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=created_by,updated_by</code></aside>

### Get a single List

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/lists/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "List",
    "id": "primary_key",
    "attributes": {
      "batch_completed_at": "2000-01-01T12:00:00Z",
      "created_at": "2000-01-01T12:00:00Z",
      "description": "unknown",
      "has_inactive_results": true,
      "include_inactive": true,
      "name": "string",
      "return_original_if_none": true,
      "returns": "string",
      "status": "string",
      "subset": "string",
      "total_people": "unknown",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/lists/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | created_by | include associated created_by
include | updated_by | include associated updated_by
include | owner | include associated owner
include | people | include associated people
include | rules | include associated rules
include | shares | include associated shares

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=created_by,updated_by</code></aside>

### Associations for a List

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
created_by | https://api.planningcenteronline.com/people/v2/lists/1/created_by | Person
owner | https://api.planningcenteronline.com/people/v2/lists/1/owner | Person
people | https://api.planningcenteronline.com/people/v2/lists/1/people | Person
rules | https://api.planningcenteronline.com/people/v2/lists/1/rules | Rule
shares | https://api.planningcenteronline.com/people/v2/lists/1/shares | ListShare
updated_by | https://api.planningcenteronline.com/people/v2/lists/1/updated_by | Person

### Actions for a List

You can perform the following actions on a List by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
run | https://api.planningcenteronline.com/people/v2/lists/1/run | Run a List to update its results.









## ListShares

A list share indicates who has access to edit a list.



### List List Shares

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/lists/1/shares"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/lists/1/shares`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _graph/type_annotation/unknown_type_annotation_ | query on a specific name
where[group] | _integer_ | query on a specific group
where[created_at] | _date_time_ | query on a specific created_at
include | person | include associated person
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single List Share

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/lists/1/shares/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ListShare",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "group": 1,
      "name": "unknown"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/lists/1/shares/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person

### Associations for a List Share

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
person | https://api.planningcenteronline.com/people/v2/lists/1/shares/1/person | Person







## MaritalStatuses

A martial status represents a member's current status, e.g. married, single, etc.



### List Marital Statuses

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/marital_statuses"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/marital_statuses`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | query on a specific value
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Marital Status

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/marital_statuses/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "MaritalStatus",
    "id": "primary_key",
    "attributes": {
      "value": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/marital_statuses/1`

#### URL Parameters

_none_

### Create a new Marital Status

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"MaritalStatus","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/marital_statuses"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/marital_statuses`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Update an existing Marital Status

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"MaritalStatus","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/marital_statuses/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/marital_statuses/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Delete a Marital Status

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/marital_statuses/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/marital_statuses/1`

## Messages

A message is an individual email or sms text sent to a member. Every message has a parent message group.



### List Messages

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/messages"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/messages`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[kind] | _integer_ | query on a specific kind
where[to_addresses] | _string_ | query on a specific to_addresses
where[subject] | _string_ | query on a specific subject
where[file] | _string_ | query on a specific file
where[app_name] | _graph/type_annotation/unknown_type_annotation_ | query on a specific app_name
where[delivery_status] | _string_ | query on a specific delivery_status
where[reject_reason] | _string_ | query on a specific reject_reason
where[from_name] | _graph/type_annotation/unknown_type_annotation_ | query on a specific from_name
where[from_address] | _graph/type_annotation/unknown_type_annotation_ | query on a specific from_address
where[created_at] | _date_time_ | query on a specific created_at
where[sent_at] | _date_time_ | query on a specific sent_at
where[bounced_at] | _date_time_ | query on a specific bounced_at
where[rejection_notification_sent_at] | _date_time_ | query on a specific rejection_notification_sent_at
where[app_name] | _graph/type_annotation/unknown_type_annotation_ | query on a specific app_name
include | message_group | include associated message_group
include | to | include associated to
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=message_group,to</code></aside>

### Get a single Message

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/messages/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Message",
    "id": "primary_key",
    "attributes": {
      "app_name": "unknown",
      "bounced_at": "2000-01-01T12:00:00Z",
      "created_at": "2000-01-01T12:00:00Z",
      "delivery_status": "string",
      "file": "string",
      "from_address": "unknown",
      "from_name": "unknown",
      "kind": 1,
      "reject_reason": "string",
      "rejection_notification_sent_at": "2000-01-01T12:00:00Z",
      "sent_at": "2000-01-01T12:00:00Z",
      "subject": "string",
      "to_addresses": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/messages/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | message_group | include associated message_group
include | to | include associated to

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=message_group,to</code></aside>

### Associations for a Message

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
message_group | https://api.planningcenteronline.com/people/v2/messages/1/message_group | MessageGroup
to | https://api.planningcenteronline.com/people/v2/messages/1/to | Person







## MessageGroups

A message group represents one or more emails or text messages sent from one of the PCO apps. The message group indicates the from person, app, etc.



### List Message Groups

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/message_groups"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/message_groups`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[uuid] | _string_ | query on a specific uuid
where[message_type] | _string_ | query on a specific message_type
where[from_address] | _string_ | query on a specific from_address
where[subject] | _string_ | query on a specific subject
where[message_count] | _integer_ | query on a specific message_count
where[system_message] | _boolean_ | query on a specific system_message
where[created_at] | _date_time_ | query on a specific created_at
include | messages | include associated messages
include | from | include associated from
include | app | include associated app
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=messages,from</code></aside>

### Get a single Message Group

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/message_groups/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "MessageGroup",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "from_address": "string",
      "message_count": 1,
      "message_type": "string",
      "subject": "string",
      "system_message": true,
      "uuid": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/message_groups/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | messages | include associated messages
include | from | include associated from
include | app | include associated app

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=messages,from</code></aside>

### Associations for a Message Group

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
app | https://api.planningcenteronline.com/people/v2/message_groups/1/app | App
from | https://api.planningcenteronline.com/people/v2/message_groups/1/from | Person
messages | https://api.planningcenteronline.com/people/v2/message_groups/1/messages | Message







## NamePrefixes

A name prefix is one of Mr., Mrs., etc.



### List Name Prefixes

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/name_prefixes"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/name_prefixes`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | query on a specific value
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Name Prefix

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/name_prefixes/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "NamePrefix",
    "id": "primary_key",
    "attributes": {
      "value": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/name_prefixes/1`

#### URL Parameters

_none_

### Create a new Name Prefix

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"NamePrefix","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/name_prefixes"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/name_prefixes`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Update an existing Name Prefix

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"NamePrefix","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/name_prefixes/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/name_prefixes/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Delete a Name Prefix

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/name_prefixes/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/name_prefixes/1`

## NameSuffixes

A name suffix is one of Sr., Jr., etc.



### List Name Suffixes

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/name_suffixes"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/name_suffixes`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | query on a specific value
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Name Suffix

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/name_suffixes/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "NameSuffix",
    "id": "primary_key",
    "attributes": {
      "value": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/name_suffixes/1`

#### URL Parameters

_none_

### Create a new Name Suffix

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"NameSuffix","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/name_suffixes"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/name_suffixes`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Update an existing Name Suffix

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"NameSuffix","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/name_suffixes/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/name_suffixes/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string

### Delete a Name Suffix

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/name_suffixes/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/name_suffixes/1`

## Organizations

The organization represents a single church. Every other resource is scoped to this record.



### Get a single Organization

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Organization",
    "id": "primary_key",
    "attributes": {
      "name": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2`

#### URL Parameters

_none_

### Associations for an Organization

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
apps | https://api.planningcenteronline.com/people/v2/apps | App
campuses | https://api.planningcenteronline.com/people/v2/campuses | Campus
carriers | https://api.planningcenteronline.com/people/v2/carriers | Carrier
emails | https://api.planningcenteronline.com/people/v2/emails | Email
field_definitions | https://api.planningcenteronline.com/people/v2/field_definitions | FieldDefinition
households | https://api.planningcenteronline.com/people/v2/households | Household
inactive_reasons | https://api.planningcenteronline.com/people/v2/inactive_reasons | InactiveReason
lists | https://api.planningcenteronline.com/people/v2/lists | List
marital_statuses | https://api.planningcenteronline.com/people/v2/marital_statuses | MaritalStatus
message_groups | https://api.planningcenteronline.com/people/v2/message_groups | MessageGroup
messages | https://api.planningcenteronline.com/people/v2/messages | Message
name_prefixes | https://api.planningcenteronline.com/people/v2/name_prefixes | NamePrefix
name_suffixes | https://api.planningcenteronline.com/people/v2/name_suffixes | NameSuffix
people | https://api.planningcenteronline.com/people/v2/people | Person
reports | https://api.planningcenteronline.com/people/v2/reports | Report
school_options | https://api.planningcenteronline.com/people/v2/school_options | SchoolOption
social_profiles | https://api.planningcenteronline.com/people/v2/social_profiles | SocialProfile
stats | https://api.planningcenteronline.com/people/v2/stats | OrganizationStatistics
tabs | https://api.planningcenteronline.com/people/v2/tabs | Tab
workflows | https://api.planningcenteronline.com/people/v2/workflows | Workflow







## OrganizationStatistics

Returns statistics for the organization.



### List Organization Statistics

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/stats"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/stats`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)







## People

A person record represents a single member/user of the application. Each person has different permissions that determine how the user can use this app (if at all).



### List People

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/people"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/people`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[first_name] | _string_ | query on a specific first_name
where[goes_by_name] | _string_ | query on a specific goes_by_name
where[middle_name] | _string_ | query on a specific middle_name
where[last_name] | _string_ | query on a specific last_name
where[birthdate] | _date_ | query on a specific birthdate
where[anniversary] | _date_ | query on a specific anniversary
where[gender] | _string_ | query on a specific gender
where[grade] | _integer_ | query on a specific grade
where[child] | _boolean_ | query on a specific child
where[status] | _string_ | query on a specific status
where[school_type] | _string_ | query on a specific school_type
where[graduation_year] | _integer_ | query on a specific graduation_year
where[site_administrator] | _boolean_ | query on a specific site_administrator
where[people_permissions] | _string_ | query on a specific people_permissions
where[membership] | _string_ | query on a specific membership
where[medical_notes] | _graph/type_annotation/unknown_type_annotation_ | query on a specific medical_notes
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
where[id] | _primary_key_ | query on a specific id
filter | created_since | filter people created in the last 24 hours; pass an additional `time` parameter in ISO 8601 format to specify your own timeframe
filter | admins | filter using the named scope "admins"
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
include | social_profiles | include associated social_profiles
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=emails,addresses</code></aside>

### Get a single Person

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/people/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Person",
    "id": "1",
    "attributes": {
      "anniversary": "2012-04-01",
      "avatar": "https://account-center-production.s3.amazonaws.com/uploads/person/1-1426707114/avatar.4.png",
      "birthdate": "1982-01-01",
      "child": false,
      "created_at": "2015-03-18T19:31:54Z",
      "first_name": "PiCO",
      "gender": "M",
      "goes_by_name": "P Riddy",
      "grade": null,
      "graduation_year": 2000,
      "last_name": "Das Robot",
      "middle_name": "Ross",
      "people_permissions": "Viewer",
      "school_type": "elementary",
      "site_administrator": true,
      "status": "active",
      "type": "Person",
      "updated_at": "2015-04-21T22:52:53Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/people/1`

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
include | social_profiles | include associated social_profiles

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=emails,addresses</code></aside>

### Associations for a Person

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
 |  | 
addresses | https://api.planningcenteronline.com/people/v2/people/1/addresses | Address
apps | https://api.planningcenteronline.com/people/v2/people/1/apps | App
connected_people | https://api.planningcenteronline.com/people/v2/people/1/connected_people | ConnectedPerson
emails | https://api.planningcenteronline.com/people/v2/people/1/emails | Email
field_data | https://api.planningcenteronline.com/people/v2/people/1/field_data | FieldDatum
household_memberships | https://api.planningcenteronline.com/people/v2/people/1/household_memberships | HouseholdMembership
households | https://api.planningcenteronline.com/people/v2/people/1/households | Household
inactive_reason | https://api.planningcenteronline.com/people/v2/people/1/inactive_reason | InactiveReason
marital_status | https://api.planningcenteronline.com/people/v2/people/1/marital_status | MaritalStatus
message_groups | https://api.planningcenteronline.com/people/v2/people/1/message_groups | MessageGroup
messages | https://api.planningcenteronline.com/people/v2/people/1/messages | Message
name_prefix | https://api.planningcenteronline.com/people/v2/people/1/name_prefix | NamePrefix
name_suffix | https://api.planningcenteronline.com/people/v2/people/1/name_suffix | NameSuffix
phone_numbers | https://api.planningcenteronline.com/people/v2/people/1/phone_numbers | PhoneNumber
school | https://api.planningcenteronline.com/people/v2/people/1/school | SchoolOption
social_profiles | https://api.planningcenteronline.com/people/v2/people/1/social_profiles | SocialProfile

### Create a new Person

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Person","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/people"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/people`

#### Resource Attributes

Attribute | Type
--------- | ----
first_name | string
goes_by_name | string
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
membership | string
medical_notes | graph/type_annotation/unknown_type_annotation

### Update an existing Person

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Person","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/people/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/people/1`

#### Resource Attributes

Attribute | Type
--------- | ----
first_name | string
goes_by_name | string
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
membership | string
medical_notes | graph/type_annotation/unknown_type_annotation

### Delete a Person

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/people/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/people/1`

## PhoneNumbers

A phone number represents a single telephone number and location.



### List Phone Numbers

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/people/1/phone_numbers"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/people/1/phone_numbers`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[number] | _string_ | query on a specific number
where[location] | _string_ | query on a specific location
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Phone Number

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/people/1/phone_numbers/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "PhoneNumber",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "location": "string",
      "number": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/people/1/phone_numbers/1`

#### URL Parameters

_none_

### Create a new Phone Number

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"PhoneNumber","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/people/1/phone_numbers"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/people/1/phone_numbers`

#### Resource Attributes

Attribute | Type
--------- | ----
number | string
location | string

### Update an existing Phone Number

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"PhoneNumber","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/people/1/phone_numbers/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/people/1/phone_numbers/1`

#### Resource Attributes

Attribute | Type
--------- | ----
number | string
location | string

### Delete a Phone Number

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/people/1/phone_numbers/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/people/1/phone_numbers/1`

## Reports

A report is editable liquid syntax that provides a powerful tool for presenting your Lists however you want.



### List Reports

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/reports"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/reports`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | query on a specific name
where[body] | _string_ | query on a specific body
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
include | created_by | include associated created_by
include | updated_by | include associated updated_by
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=created_by,updated_by</code></aside>

### Get a single Report

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/reports/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Report",
    "id": "primary_key",
    "attributes": {
      "body": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/reports/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | created_by | include associated created_by
include | updated_by | include associated updated_by

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=created_by,updated_by</code></aside>

### Associations for a Report

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
created_by | https://api.planningcenteronline.com/people/v2/reports/1/created_by | Person
updated_by | https://api.planningcenteronline.com/people/v2/reports/1/updated_by | Person

### Create a new Report

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Report","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/reports"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/reports`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
body | string

### Update an existing Report

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Report","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/reports/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/reports/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
body | string

### Delete a Report

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/reports/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/reports/1`

## Rules

A rule belongs to a List and groups conditions together.



### List Rules

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/lists/1/rules"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/lists/1/rules`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[subset] | _string_ | query on a specific subset
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
include | conditions | include associated conditions
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Rule

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/lists/1/rules/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Rule",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "subset": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/lists/1/rules/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | conditions | include associated conditions

### Associations for a Rule

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
conditions | https://api.planningcenteronline.com/people/v2/lists/1/rules/1/conditions | Condition
results | https://api.planningcenteronline.com/people/v2/lists/1/rules/1/results | RuleResult







## RuleResults

A Rule Result represents a matched record for any Condition belonging to this Rule.



### List Rule Results

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/lists/1/rules/1/results"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/lists/1/rules/1/results`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Rule Result

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/lists/1/rules/1/results/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "RuleResult",
    "id": "primary_key",
    "attributes": {
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/lists/1/rules/1/results/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person

### Associations for a Rule Result

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
person | https://api.planningcenteronline.com/people/v2/lists/1/rules/1/results/1/person | Person







## SchoolOptions

A school option represents a school name, school type, grades, etc. and can be added to a person.



### List School Options

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/school_options"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/school_options`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | query on a specific value
where[school_types] | _graph/type_annotation/unknown_type_annotation_ | query on a specific school_types
where[beginning_grade] | _graph/type_annotation/unknown_type_annotation_ | query on a specific beginning_grade
where[ending_grade] | _graph/type_annotation/unknown_type_annotation_ | query on a specific ending_grade
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single School Option

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/school_options/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "SchoolOption",
    "id": "1",
    "attributes": {
      "beginning_grade": "0",
      "ending_grade": "5",
      "school_types": [
        "elementary"
      ],
      "type": "SchoolOption",
      "value": "Colcord Elementary"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/school_options/1`

#### URL Parameters

_none_

### Associations for a School Option

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
promotes_to_school | https://api.planningcenteronline.com/people/v2/school_options/1/promotes_to_school | SchoolOption

### Create a new School Option

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"SchoolOption","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/school_options"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/school_options`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string
school_types | graph/type_annotation/unknown_type_annotation
beginning_grade | graph/type_annotation/unknown_type_annotation
ending_grade | graph/type_annotation/unknown_type_annotation

### Update an existing School Option

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"SchoolOption","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/school_options/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/school_options/1`

#### Resource Attributes

Attribute | Type
--------- | ----
value | string
school_types | graph/type_annotation/unknown_type_annotation
beginning_grade | graph/type_annotation/unknown_type_annotation
ending_grade | graph/type_annotation/unknown_type_annotation

### Delete a School Option

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/school_options/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/school_options/1`

## SocialProfiles

A social profile represents a members's Twitter, Facebook, or other social media account.



### List Social Profiles

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/social_profiles"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/social_profiles`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[site] | _string_ | query on a specific site
where[url] | _string_ | query on a specific url
where[verified] | _boolean_ | query on a specific verified
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
include | person | include associated person
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Social Profile

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/social_profiles/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "SocialProfile",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "site": "string",
      "updated_at": "2000-01-01T12:00:00Z",
      "url": "string",
      "verified": true
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/social_profiles/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person

### Associations for a Social Profile

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
person | https://api.planningcenteronline.com/people/v2/social_profiles/1/person | Person

### Create a new Social Profile

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"SocialProfile","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/people/1/social_profiles"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/people/1/social_profiles`

#### Resource Attributes

Attribute | Type
--------- | ----
site | string
url | string
verified | boolean

### Update an existing Social Profile

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"SocialProfile","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/social_profiles/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/social_profiles/1`

#### Resource Attributes

Attribute | Type
--------- | ----
site | string
url | string
verified | boolean

### Delete a Social Profile

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/social_profiles/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/social_profiles/1`

## Tabs

A tab is a custom tab and groups like field definitions.



### List Tabs

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/tabs"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/tabs`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | query on a specific name
where[sequence] | _integer_ | query on a specific sequence
where[slug] | _string_ | query on a specific slug
include | field_definitions | include associated field_definitions
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Tab

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/tabs/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Tab",
    "id": "primary_key",
    "attributes": {
      "name": "string",
      "sequence": 1,
      "slug": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/tabs/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | field_definitions | include associated field_definitions

### Associations for a Tab

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
field_definitions | https://api.planningcenteronline.com/people/v2/tabs/1/field_definitions | FieldDefinition

### Create a new Tab

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Tab","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/tabs"
```


<aside class='info'>Only users with the role <code>manager</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/tabs`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
sequence | integer
slug | string

### Update an existing Tab

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Tab","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/tabs/1"
```


<aside class='info'>Only users with the role <code>manager</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/tabs/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
sequence | integer
slug | string

### Delete a Tab

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/tabs/1"
```


<aside class='info'>Only users with the role <code>manager</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/tabs/1`

## Workflows

A Workflow



### List Workflows

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/workflows"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/workflows`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | query on a specific name
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
include | steps | include associated steps
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Workflow

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/workflows/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Workflow",
    "id": "primary_key",
    "attributes": {
      "completed_card_count": "unknown",
      "created_at": "2000-01-01T12:00:00Z",
      "my_ready_card_count": "unknown",
      "name": "string",
      "total_ready_card_count": "unknown",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/workflows/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | steps | include associated steps

### Associations for a Workflow

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
cards | https://api.planningcenteronline.com/people/v2/workflows/1/cards | WorkflowCard
steps | https://api.planningcenteronline.com/people/v2/workflows/1/steps | WorkflowStep







## WorkflowCards

A Card



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
assignee | Assignee | _false_ | 
current_step | CurrentStep | _false_ | 

### List Workflow Cards

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/workflows/1/cards"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/workflows/1/cards`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person
include | assignee | include associated assignee
include | tasks | include associated tasks
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=person,assignee</code></aside>

### Get a single Workflow Card

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/workflows/1/cards/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "WorkflowCard",
    "id": "primary_key",
    "attributes": {
      "completed_at": "2000-01-01T12:00:00Z",
      "created_at": "2000-01-01T12:00:00Z",
      "snooze_until": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "assignee": {
        "data": {
          "type": "Assignee",
          "id": "123"
        }
      },
      "current_step": {
        "data": {
          "type": "CurrentStep",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/workflows/1/cards/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person
include | assignee | include associated assignee
include | tasks | include associated tasks

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=person,assignee</code></aside>

### Associations for a Workflow Card

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
activities | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/activities | WorkflowCardActivity
assignee | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/assignee | Person
current_task | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/current_task | WorkflowTask
notes | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/notes | WorkflowCardNote
person | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/person | Person
tasks | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/tasks | WorkflowTask

### Actions for a Workflow Card

You can perform the following actions on a Workflow Card by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
go_back | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/go_back | Move a Workflow Card back to the previous step.
unsnooze | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/unsnooze | Unsnoozes a card
remove | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/remove | Removes a card
restore | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/restore | Restore a card
promote | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/promote | Move a Workflow Card to the next step.
send_email | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/send_email | Sends an email to the subject of the card
skip_step | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/skip_step | Move a Workflow Card to the next step without completing the current step.
snooze | https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/snooze | Snoozes a card for a specific duration

















### Create a new Workflow Card

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"WorkflowCard","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/workflows/1/cards"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/workflows/1/cards`

#### Resource Attributes

_none_

### Update an existing Workflow Card

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"WorkflowCard","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/workflows/1/cards/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/workflows/1/cards/1`

#### Resource Attributes

_none_



## WorkflowCardActivities

Workflow Card Activity is a record of an action performed on a card



### List Workflow Card Activities

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/activities"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/activities`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Workflow Card Activity

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/activities/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "WorkflowCardActivity",
    "id": "1",
    "attributes": {
      "comment": "unknown",
      "content": "unknown",
      "created_at": "2000-01-01T12:00:00Z",
      "person_avatar_url": "unknown",
      "person_name": "unknown",
      "reassigned_to_avatar_url": "unknown",
      "reassigned_to_name": "unknown",
      "subject": "unknown",
      "type": "unknown"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/activities/1`

#### URL Parameters

_none_





### Delete a Workflow Card Activity

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/activities/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/activities/1`

## WorkflowCardNotes

Workflow Note is a note that has been made on a Workflow Card



### List Workflow Card Notes

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/notes"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/notes`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Workflow Card Note

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/notes/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "WorkflowCardNote",
    "id": "1",
    "attributes": {
      "note": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/notes/1`

#### URL Parameters

_none_

### Create a new Workflow Card Note

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"WorkflowCardNote","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/notes"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/notes`

#### Resource Attributes

Attribute | Type
--------- | ----
note | string

### Update an existing Workflow Card Note

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"WorkflowCardNote","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/notes/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/notes/1`

#### Resource Attributes

Attribute | Type
--------- | ----
note | string



## WorkflowSteps

A Step



### List Workflow Steps

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/workflows/1/steps"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/workflows/1/steps`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | query on a specific name
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
include | default_assignee | include associated default_assignee
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Workflow Step

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/workflows/1/steps/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "WorkflowStep",
    "id": "primary_key",
    "attributes": {
      "auto_snooze_days": 1,
      "created_at": "2000-01-01T12:00:00Z",
      "description": "string",
      "my_ready_card_count": "unknown",
      "name": "string",
      "sequence": 1,
      "total_ready_card_count": "unknown",
      "total_snoozed_card_count": "unknown",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/workflows/1/steps/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | default_assignee | include associated default_assignee

### Associations for a Workflow Step

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
default_assignee | https://api.planningcenteronline.com/people/v2/workflows/1/steps/1/default_assignee | Person







## WorkflowTasks

A Task



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
step | Step | _false_ | 

### List Workflow Tasks

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/tasks"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/tasks`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
where[completed_at] | _date_time_ | query on a specific completed_at
include | card | include associated card
include | step | include associated step
include | completed_by | include associated completed_by
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=card,step</code></aside>

### Get a single Workflow Task

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/tasks/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "WorkflowTask",
    "id": "primary_key",
    "attributes": {
      "completed_at": "2000-01-01T12:00:00Z",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "step": {
        "data": {
          "type": "Step",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v2/workflows/1/cards/1/tasks/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | card | include associated card
include | step | include associated step
include | completed_by | include associated completed_by

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=card,step</code></aside>





