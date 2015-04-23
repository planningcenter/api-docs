# People

Our People app helps you manage contact data, membership info, and everything you need to know about your people with confidence.

## Addresses

An address represents a physical and/or mailing address for a person.

### Get all Addresses

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/people/1/addresses"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people/1/addresses`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id

### Get a single Address

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/people/1/addresses/1"
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

## Apps

An app is one of the handful of apps that PCO offers that organizations can subscribe to, e.g. Services, Registrations, etc.

### Get all Apps

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/apps"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/apps`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id

### Get a single App

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/apps/1"
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

### Get all Conditions

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/lists/1/rules/1/conditions"
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

### Get a single Condition

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/lists/1/rules/1/conditions/1"
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

## Emails

An email represents an email address and location.

### Get all Emails

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/emails"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/emails`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[address] | _string_ | filter on a specific address
where[location] | _string_ | filter on a specific location
after | _id_ | get page after the specified id

### Get a single Email

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/emails/1"
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

## FieldData

A field datum is an individual piece of data for a custom field.

### Get all Field Data

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/people/1/field_data"
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

_Note: you can specify multiple includes with a comma, e.g. `?include=field_definition,field_option`_

### Get a single Field Datum

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/people/1/field_data/1"
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

_Note: you can specify multiple includes with a comma, e.g. `?include=field_definition,field_option`_

## FieldDefinitions

A field definition represents a custom field -- its name, data type, etc.

### Get all Field Definitions

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/field_definitions"
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

### Get a single Field Definition

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/field_definitions/1"
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

## FieldOptions

A field option represents an individual option for a custom field of type "select" or "checkboxes".

### Get all Field Options

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | filter on a specific value
where[sequence] | _integer_ | filter on a specific sequence
after | _id_ | get page after the specified id

### Get a single Field Option

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/field_definitions/1/field_options/1"
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

## HouseholdMemberships

A household membership is the linking record between a household and a person.

### Get all Household Memberships

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/households/1/household_memberships"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/households/1/household_memberships`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person
include | household | include associated household
after | _id_ | get page after the specified id

_Note: you can specify multiple includes with a comma, e.g. `?include=person,household`_

### Get a single Household Membership

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/households/1/household_memberships/1"
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

_Note: you can specify multiple includes with a comma, e.g. `?include=person,household`_

## Households

A household links people together and can have a primary contaact.

### Get all Households

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/households"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/households`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | filter on a specific name
include | people | include associated people
after | _id_ | get page after the specified id

### Get a single Household

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/households/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "name": "string",
    "primary_contact_name": "string",
    "member_count": 1,
    "created_at": "2000-01-01T12:00:00Z",
    "updated_at": "2000-01-01T12:00:00Z"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/households/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | people | include associated people

## InactiveReasons

An inactive reason is a small bit of text indicating why a member is no longer active.

### Get all Inactive Reasons

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/inactive_reasons"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/inactive_reasons`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | filter on a specific value
after | _id_ | get page after the specified id

### Get a single Inactive Reason

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/inactive_reasons/1"
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

## Lists

A list (aka "filter") is a powerful tool for finding and grouping people together using any criteria imaginable.

### Get all Lists

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/lists"
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

_Note: you can specify multiple includes with a comma, e.g. `?include=created_by,updated_by,owner`_

### Get a single List

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/lists/1"
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

_Note: you can specify multiple includes with a comma, e.g. `?include=created_by,updated_by,owner`_

## MaritalStatuses

A martial status represents a member's current status, e.g. married, single, etc.

### Get all Marital Statuses

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/marital_statuses"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/marital_statuses`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | filter on a specific value
after | _id_ | get page after the specified id

### Get a single Marital Status

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/marital_statuses/1"
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

## MessageGroups

A message group represents one or more emails or text messages sent from one of the PCO apps. The message group indicates the from person, app, etc.

### Get all Message Groups

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/message_groups"
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

_Note: you can specify multiple includes with a comma, e.g. `?include=messages,from,app`_

### Get a single Message Group

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/message_groups/1"
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

_Note: you can specify multiple includes with a comma, e.g. `?include=messages,from,app`_

## Messages

A message is an individual email or sms text sent to a member. Every message has a parent message group.

### Get all Messages

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/messages"
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

_Note: you can specify multiple includes with a comma, e.g. `?include=message_group,to`_

### Get a single Message

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/messages/1"
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

_Note: you can specify multiple includes with a comma, e.g. `?include=message_group,to`_

## NamePrefixes

A name prefix is one of Mr., Mrs., etc.

### Get all Name Prefixes

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/name_prefixes"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/name_prefixes`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | filter on a specific value
after | _id_ | get page after the specified id

### Get a single Name Prefix

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/name_prefixes/1"
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

## NameSuffixes

A name suffix is one of Sr., Jr., etc.

### Get all Name Suffixes

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/name_suffixes"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/name_suffixes`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[value] | _string_ | filter on a specific value
after | _id_ | get page after the specified id

### Get a single Name Suffix

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/name_suffixes/1"
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

## Organizations

The organization represents a single church. Every other resource is scoped to this record.

### Get all Organizations

#### HTTP Request

`GET `

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id

### Get a single Organization

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1"
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

## People

A person record represents a single member/user of the application. Each person has different permissions that determine how the user can use this app (if at all).

### Get all People

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/people"
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

_Note: you can specify multiple includes with a comma, e.g. `?include=emails,addresses,phone_numbers`_

### Get a single Person

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/people/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "first_name": "string",
    "middle_name": "string",
    "last_name": "string",
    "birthdate": "2000-01-01",
    "anniversary": "2000-01-01",
    "gender": "string",
    "grade": 1,
    "child": "stuff",
    "status": "string",
    "school_type": "string",
    "graduation_year": 1,
    "site_administrator": "stuff",
    "people_permissions": "string",
    "avatar": "string",
    "created_at": "2000-01-01T12:00:00Z",
    "updated_at": "2000-01-01T12:00:00Z"
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

_Note: you can specify multiple includes with a comma, e.g. `?include=emails,addresses,phone_numbers`_

## PhoneNumbers

A phone number represents a single telephone number and location.

### Get all Phone Numbers

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/people/1/phone_numbers"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people/1/phone_numbers`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id

### Get a single Phone Number

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/people/1/phone_numbers/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "number": "string",
    "location": "string"
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/people/1/phone_numbers/1`

#### URL Parameters

_none_

## Reports

A report is editable liquid syntax that provides a powerful tool for presenting your Lists however you want.

### Get all Reports

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/reports"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/reports`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | filter on a specific name
where[settings] | _text_ | filter on a specific settings
where[body] | _text_ | filter on a specific body
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
include | created_by | include associated created_by
include | updated_by | include associated updated_by
after | _id_ | get page after the specified id

_Note: you can specify multiple includes with a comma, e.g. `?include=created_by,updated_by`_

### Get a single Report

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/reports/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "name": "string",
    "settings": "stuff",
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

_Note: you can specify multiple includes with a comma, e.g. `?include=created_by,updated_by`_

## Rules

A rule belongs to a List and groups conditions together.

### Get all Rules

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/lists/1/rules"
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

### Get a single Rule

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/lists/1/rules/1"
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

## SchoolOptions

A school option represents a school name, school type, grades, etc. and can be added to a person.

### Get all School Options

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/school_options"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/school_options`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | __ | filter on a specific name
where[school_types] | __ | filter on a specific school_types
where[beginning_grade] | __ | filter on a specific beginning_grade
where[ending_grade] | __ | filter on a specific ending_grade
after | _id_ | get page after the specified id

### Get a single School Option

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/school_options/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "name": "stuff",
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

## SocialProfiles

A social profile represents a members's Twitter, Facebook, or other social media account.

### Get all Social Profiles

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/social_profiles"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/people/v1/social_profiles`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[site] | _string_ | filter on a specific site
where[profile_identifier] | _string_ | filter on a specific profile_identifier
where[username] | _string_ | filter on a specific username
where[url] | _string_ | filter on a specific url
where[verified] | _boolean_ | filter on a specific verified
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
include | person | include associated person
after | _id_ | get page after the specified id

### Get a single Social Profile

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/social_profiles/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "site": "string",
    "profile_identifier": "string",
    "username": "string",
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

## Tabs

A tab is a custom tab and groups like field definitions.

### Get all Tabs

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/tabs"
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

### Get a single Tab

```shell
curl -v -u token:secret           "https://api.planningcenteronline.com/people/v1/tabs/1"
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