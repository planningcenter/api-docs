# PCO Check-Ins

Check kids & volunteers in to events and track attendance.

## AttendanceTypes

A kind of attendee which is tracked by _headcount_, not by check-in.




### List Attendance Types

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event | include associated event
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Attendance Type

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "AttendanceType",
    "id": "primary_key",
    "attributes": {
      "color": "string",
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

`GET https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event | include associated event

### Associations for an Attendance Type

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
event | https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types/1/event | Event
headcounts | https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types/1/headcounts | Headcount

### Create a new Attendance Type

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"AttendanceType","attributes":{...}}}' "https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
color | string
created_at | date_time
updated_at | date_time

### Update an existing Attendance Type

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"AttendanceType","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
color | string
created_at | date_time
updated_at | date_time



## CheckIns

An attendance record for an event.

If someone was checked out, `checked_out_at` will be present.

You can scope check-ins in a few ways:

- `regular`s, `guest`s, and `volunteer`s correspond to the option selected when checking in.
- `attendee`s are `regular`s and `guest`s together.
- `one_time_guest`s are check-ins which were created without a corresponding person record.
- `not_one_time_guest`s are check-ins which had a corresponding person record when they were created.
- `checked_out` are check-ins where `checked_out_at` is present (meaning they were checked out from a station).
- `first_time`s are check-ins which are the person's first for a given event. (One-time guests are not included here.)




### List Check Ins

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/check_ins"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/check_ins`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
filter | regular | filter using the named scope "regular"
filter | guest | filter using the named scope "guest"
filter | volunteer | filter using the named scope "volunteer"
filter | attendee | filter using the named scope "attendee"
filter | first_time | filter using the named scope "first_time"
filter | one_time_guest | filter using the named scope "one_time_guest"
filter | not_one_time_guest | filter using the named scope "not_one_time_guest"
filter | checked_out | filter using the named scope "checked_out"
include | location | include associated location
include | event | include associated event
include | event_period | include associated event_period
include | event_times | include associated event_times
include | person | include associated person
include | checked_in_at | include associated checked_in_at
include | checked_in_by | include associated checked_in_by
include | checked_out_by | include associated checked_out_by
include | options | include associated options
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)
order | first_name | prefix with a hyphen (-first_name) to reverse the order
order | last_name | prefix with a hyphen (-last_name) to reverse the order
order | number | prefix with a hyphen (-number) to reverse the order
order | created_at | prefix with a hyphen (-created_at) to reverse the order
order | updated_at | prefix with a hyphen (-updated_at) to reverse the order
order | checked_out_at | prefix with a hyphen (-checked_out_at) to reverse the order

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=location,event</code></aside>

### Get a single Check In

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/check_ins/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "CheckIn",
    "id": "primary_key",
    "attributes": {
      "checked_out_at": "2000-01-01T12:00:00Z",
      "created_at": "2000-01-01T12:00:00Z",
      "emergency_contact_name": "string",
      "emergency_contact_phone_number": "string",
      "first_name": "string",
      "kind": "string",
      "last_name": "string",
      "medical_notes": "string",
      "number": 1,
      "security_code": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/check_ins/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | location | include associated location
include | event | include associated event
include | event_period | include associated event_period
include | event_times | include associated event_times
include | person | include associated person
include | checked_in_at | include associated checked_in_at
include | checked_in_by | include associated checked_in_by
include | checked_out_by | include associated checked_out_by
include | options | include associated options

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=location,event</code></aside>

### Associations for a Check In

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
check_in_group | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/check_in_group | CheckInGroup
checked_in_at | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/checked_in_at | Station
checked_in_by | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/checked_in_by | Person
checked_out_by | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/checked_out_by | Person
event | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/event | Event
event_period | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/event_period | EventPeriod
event_times | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/event_times | EventTime
location | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location | Location
options | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/options | Option
person | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/person | Person







## CheckInGroups

When one or more people check in, they're grouped in a `CheckInGroup`.
These check-ins all have the same "checked-in by" person. `CheckInGroup` is also
the basis for label printing.

`print_status` may be:

- `ready`: This group isn't printed or canceled yet
- `printed`: This group was successfully printed at a station
- `canceled`: This group was canceled at a station
- `skipped`: This group had no labels to print, so it was never printed.




### List Check In Groups

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/check_ins/1/check_in_group"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/check_ins/1/check_in_group`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | check_ins | include associated check_ins
include | event_period | include associated event_period
include | print_station | include associated print_station
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=check_ins,event_period</code></aside>

### Get a single Check In Group

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/check_ins/1/check_in_group/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "CheckInGroup",
    "id": "primary_key",
    "attributes": {
      "check_ins_count": 1,
      "name_labels_count": 1,
      "print_status": 1,
      "security_labels_count": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/check_ins/1/check_in_group/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | check_ins | include associated check_ins
include | event_period | include associated event_period
include | print_station | include associated print_station

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=check_ins,event_period</code></aside>

### Associations for a Check In Group

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
check_ins | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/check_in_group/1/check_ins | CheckIn
event_period | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/check_in_group/1/event_period | EventPeriod
print_station | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/check_in_group/1/print_station | Station







## Events

A recurring event which people may attend.

Each recurrence is an _event period_ (which often corresponds to a week).

Event periods have _event times_ where people may actually check in.




### List Events

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/events"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
filter | archived | filter using the named scope "archived"
filter | not_archived | filter using the named scope "not_archived"
include | event_periods | include associated event_periods
include | attendance_types | include associated attendance_types
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)
order | name | prefix with a hyphen (-name) to reverse the order
order | created_at | prefix with a hyphen (-created_at) to reverse the order

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event_periods,attendance_types</code></aside>

### Get a single Event

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/events/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Event",
    "id": "primary_key",
    "attributes": {
      "archived_at": "2000-01-01T12:00:00Z",
      "created_at": "2000-01-01T12:00:00Z",
      "enable_services_integration": true,
      "frequency": "string",
      "name": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event_periods | include associated event_periods
include | attendance_types | include associated attendance_types

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event_periods,attendance_types</code></aside>

### Associations for an Event

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
attendance_types | https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types | AttendanceType
check_ins | https://api.planningcenteronline.com/check_ins/v2/events/1/check_ins | CheckIn
event_labels | https://api.planningcenteronline.com/check_ins/v2/events/1/event_labels | EventLabel
event_periods | https://api.planningcenteronline.com/check_ins/v2/events/1/event_periods | EventPeriod
 |  | 
locations | https://api.planningcenteronline.com/check_ins/v2/events/1/locations | Location
person_events | https://api.planningcenteronline.com/check_ins/v2/events/1/person_events | PersonEvent







## EventLabels

Says how many of a given label to print for this event and
whether to print it for regulars, guests, and/or volunteers.




### List Event Labels

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/events/1/event_labels"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events/1/event_labels`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event | include associated event
include | label | include associated label
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event,label</code></aside>

### Get a single Event Label

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/events/1/event_labels/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "EventLabel",
    "id": "primary_key",
    "attributes": {
      "for_guest": true,
      "for_regular": true,
      "for_volunteer": true,
      "quantity": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events/1/event_labels/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event | include associated event
include | label | include associated label

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event,label</code></aside>

### Associations for an Event Label

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
event | https://api.planningcenteronline.com/check_ins/v2/events/1/event_labels/1/event | Event
label | https://api.planningcenteronline.com/check_ins/v2/events/1/event_labels/1/label | Label







## EventPeriods

A recurrence of an event, sometimes called a "session".
For weekly events, an event period is a week. For daily events, an event period is a day.
An event period has event times, which is what people select
when they actually check in. When new sessions are created, times
are copied from one session to the next.




### List Event Periods

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/event_times/1/event_period"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/event_times/1/event_period`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event | include associated event
include | event_times | include associated event_times
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)
order | starts_at | prefix with a hyphen (-starts_at) to reverse the order

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event,event_times</code></aside>

### Get a single Event Period

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/event_times/1/event_period/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "EventPeriod",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "ends_at": "2000-01-01T12:00:00Z",
      "guest_count": 1,
      "regular_count": 1,
      "starts_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "volunteer_count": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/event_times/1/event_period/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event | include associated event
include | event_times | include associated event_times

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event,event_times</code></aside>

### Associations for an Event Period

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
check_ins | https://api.planningcenteronline.com/check_ins/v2/event_times/1/event_period/1/check_ins | CheckIn
event | https://api.planningcenteronline.com/check_ins/v2/event_times/1/event_period/1/event | Event
event_times | https://api.planningcenteronline.com/check_ins/v2/event_times/1/event_period/1/event_times | EventTime
location_event_periods | https://api.planningcenteronline.com/check_ins/v2/event_times/1/event_period/1/location_event_periods | LocationEventPeriod







## EventTimes

A time that someone may check in. Times are copied from session to session.




### List Event Times

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/event_times"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/event_times`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event_period | include associated event_period
include | event | include associated event
include | headcounts | include associated headcounts
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)
order | starts_at | prefix with a hyphen (-starts_at) to reverse the order
order | shows_at | prefix with a hyphen (-shows_at) to reverse the order

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event_period,event</code></aside>

### Get a single Event Time

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/event_times/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "EventTime",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "guest_count": 1,
      "hides_at": "2000-01-01T12:00:00Z",
      "regular_count": 1,
      "shows_at": "2000-01-01T12:00:00Z",
      "starts_at": "2000-01-01T12:00:00Z",
      "total_count": "unknown",
      "updated_at": "2000-01-01T12:00:00Z",
      "volunteer_count": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/event_times/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event_period | include associated event_period
include | event | include associated event
include | headcounts | include associated headcounts

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event_period,event</code></aside>

### Associations for an Event Time

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
check_ins | https://api.planningcenteronline.com/check_ins/v2/event_times/1/check_ins | CheckIn
event | https://api.planningcenteronline.com/check_ins/v2/event_times/1/event | Event
event_period | https://api.planningcenteronline.com/check_ins/v2/event_times/1/event_period | EventPeriod
headcounts | https://api.planningcenteronline.com/check_ins/v2/event_times/1/headcounts | Headcount
location_event_times | https://api.planningcenteronline.com/check_ins/v2/event_times/1/location_event_times | LocationEventTime







## Headcounts

A tally of attendees for a given event time and attendance type.
If one does not exist, the count may have been zero.




### List Headcounts

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/headcounts"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/headcounts`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event_time | include associated event_time
include | attendance_type | include associated attendance_type
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event_time,attendance_type</code></aside>

### Get a single Headcount

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/headcounts/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Headcount",
    "id": "primary_key",
    "attributes": {
      "total": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/headcounts/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event_time | include associated event_time
include | attendance_type | include associated attendance_type

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event_time,attendance_type</code></aside>

### Associations for a Headcount

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
attendance_type | https://api.planningcenteronline.com/check_ins/v2/headcounts/1/attendance_type | AttendanceType
event_time | https://api.planningcenteronline.com/check_ins/v2/headcounts/1/event_time | EventTime

### Create a new Headcount

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Headcount","attributes":{...}}}' "https://api.planningcenteronline.com/check_ins/v2/event_times/1/headcounts"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/check_ins/v2/event_times/1/headcounts`

#### Resource Attributes

Attribute | Type
--------- | ----
total | integer

### Update an existing Headcount

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Headcount","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/check_ins/v2/headcounts/1"
```


<aside class='info'>Only users with the role <code>editor</code> can update this resource.</aside>

#### HTTP Request

`PATCH https://api.planningcenteronline.com/check_ins/v2/headcounts/1`

#### Resource Attributes

Attribute | Type
--------- | ----
total | integer



## Labels

Labels can be set to print for events (through `EventLabel`s),
locations (through `LocationLabel`s) or options.
Label type (security label / name label) is expressed with the
`prints_for` attribute. `prints_for="Person"` is a name label,
`prints_for="Group"` is a security label.




### List Labels

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/labels"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/labels`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Label

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/labels/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Label",
    "id": "primary_key",
    "attributes": {
      "name": "string",
      "prints_for": "string",
      "roll": "string",
      "xml": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/labels/1`

#### URL Parameters

_none_

### Associations for a Label

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
event_labels | https://api.planningcenteronline.com/check_ins/v2/labels/1/event_labels | EventLabel
location_labels | https://api.planningcenteronline.com/check_ins/v2/labels/1/location_labels | LocationLabel







## Locations

A place where people may check in to for a given event.
Some locations have `kind="Folder"`, which means that people
can't check-in here, but this location contains other locations.
You can get its contents from the `locations` attribute.
You can get a location's parent folder from the `parent` attribute.
(If it's not in a folder, `parent` will be empty.)




### List Locations

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/events/1/locations"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events/1/locations`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | parent | include associated parent
include | event | include associated event
include | locations | include associated locations
include | options | include associated options
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)
order | kind | prefix with a hyphen (-kind) to reverse the order
order | name | prefix with a hyphen (-name) to reverse the order

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=parent,event</code></aside>

### Get a single Location

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Location",
    "id": "primary_key",
    "attributes": {
      "age_min_in_months": 1,
      "age_on": "2000-01-01",
      "age_range_by": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "grade_max": 1,
      "grade_min": 1,
      "kind": "string",
      "max_occupancy": 1,
      "name": "string",
      "opened": true,
      "position": 1,
      "questions": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | parent | include associated parent
include | event | include associated event
include | locations | include associated locations
include | options | include associated options

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=parent,event</code></aside>

### Associations for a Location

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
check_ins | https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/check_ins | CheckIn
event | https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/event | Event
location_event_periods | https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/location_event_periods | LocationEventPeriod
location_event_times | https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/location_event_times | LocationEventTime
location_labels | https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/location_labels | LocationLabel
locations | https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/locations | Location
options | https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/options | Option
parent | https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/parent | Location







## LocationEventPeriods

Counts check-ins for a location during a certain event period.




### List Location Event Periods

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/location_event_periods"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/location_event_periods`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | location | include associated location
include | event_period | include associated event_period
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=location,event_period</code></aside>

### Get a single Location Event Period

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/location_event_periods/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "LocationEventPeriod",
    "id": "primary_key",
    "attributes": {
      "guest_count": 1,
      "regular_count": 1,
      "volunteer_count": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/location_event_periods/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | location | include associated location
include | event_period | include associated event_period

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=location,event_period</code></aside>

### Associations for a Location Event Period

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
check_ins | https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/location_event_periods/1/check_ins | CheckIn
event_period | https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/location_event_periods/1/event_period | EventPeriod
location | https://api.planningcenteronline.com/check_ins/v2/events/1/locations/1/location_event_periods/1/location | Location







## LocationEventTimes

Counts check-ins for a location for a given event time.
This is useful for checking occupancy.




### List Location Event Times

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/event_times/1/location_event_times"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/event_times/1/location_event_times`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | location | include associated location
include | event_time | include associated event_time
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=location,event_time</code></aside>

### Get a single Location Event Time

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/event_times/1/location_event_times/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "LocationEventTime",
    "id": "primary_key",
    "attributes": {
      "guest_count": 1,
      "regular_count": 1,
      "volunteer_count": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/event_times/1/location_event_times/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | location | include associated location
include | event_time | include associated event_time

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=location,event_time</code></aside>

### Associations for a Location Event Time

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
check_ins | https://api.planningcenteronline.com/check_ins/v2/event_times/1/location_event_times/1/check_ins | CheckIn
event_time | https://api.planningcenteronline.com/check_ins/v2/event_times/1/location_event_times/1/event_time | EventTime
location | https://api.planningcenteronline.com/check_ins/v2/event_times/1/location_event_times/1/location | Location







## LocationLabels

Says how many of a given label to print for this location and
whether to print it for regulars, guests, and/or volunteers.




### List Location Labels

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/labels/1/location_labels"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/labels/1/location_labels`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | location | include associated location
include | label | include associated label
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=location,label</code></aside>

### Get a single Location Label

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/labels/1/location_labels/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "LocationLabel",
    "id": "primary_key",
    "attributes": {
      "for_guest": true,
      "for_regular": true,
      "for_volunteer": true,
      "quantity": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/labels/1/location_labels/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | location | include associated location
include | label | include associated label

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=location,label</code></aside>

### Associations for a Location Label

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
label | https://api.planningcenteronline.com/check_ins/v2/labels/1/location_labels/1/label | Label
location | https://api.planningcenteronline.com/check_ins/v2/labels/1/location_labels/1/location | Location







## Options

An option which an attendee may select when checking in.

Options may have extra labels associated with them, denoted by `label` and `quantity`.




### List Options

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/check_ins/1/options"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/check_ins/1/options`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | location | include associated location
include | check_ins | include associated check_ins
include | label | include associated label
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=location,check_ins</code></aside>

### Get a single Option

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/check_ins/1/options/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Option",
    "id": "primary_key",
    "attributes": {
      "body": "string",
      "quantity": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/check_ins/1/options/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | location | include associated location
include | check_ins | include associated check_ins
include | label | include associated label

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=location,check_ins</code></aside>

### Associations for an Option

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
label | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/options/1/label | Label







## Organizations

An organization which has people and events.
This contains its date format & time zone preferences.




### Get a single Organization

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Organization",
    "id": "primary_key",
    "attributes": {
      "daily_check_ins": 1,
      "date_format_pattern": "unknown",
      "name": "string",
      "time_zone": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2`

#### URL Parameters

_none_

### Associations for an Organization

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
check_ins | https://api.planningcenteronline.com/check_ins/v2/check_ins | CheckIn
event_times | https://api.planningcenteronline.com/check_ins/v2/event_times | EventTime
events | https://api.planningcenteronline.com/check_ins/v2/events | Event
headcounts | https://api.planningcenteronline.com/check_ins/v2/headcounts | Headcount
labels | https://api.planningcenteronline.com/check_ins/v2/labels | Label
passes | https://api.planningcenteronline.com/check_ins/v2/passes | Pass
people | https://api.planningcenteronline.com/check_ins/v2/people | Person
stations | https://api.planningcenteronline.com/check_ins/v2/stations | Station
themes | https://api.planningcenteronline.com/check_ins/v2/themes | Theme







## Passes

Enables quick lookup of a person via barcode reader.


### Attribute Info

<span class='attribute-info-name'>kind</span>

Possible values: `barcode` or `pkpass`.

Using the `pkpass` value creates a mobile pass and sends an email to the associated person.


### List Passes

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/passes"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/passes`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[code] | _string_ | query on a specific code
include | person | include associated person
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Pass

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/passes/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Pass",
    "id": "primary_key",
    "attributes": {
      "code": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "kind": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/passes/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person

### Associations for a Pass

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
person | https://api.planningcenteronline.com/check_ins/v2/passes/1/person | Person

### Create a new Pass

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Pass","attributes":{...}}}' "https://api.planningcenteronline.com/check_ins/v2/people/1/passes"
```


<aside class='info'>Only users with the role <code>editor</code> can create this resource.</aside>

#### HTTP Request

`POST https://api.planningcenteronline.com/check_ins/v2/people/1/passes`

#### Resource Attributes

Attribute | Type
--------- | ----
code | string
kind | string



### Delete a Pass

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/check_ins/v2/passes/1"
```


<aside class='info'>Only users with the role <code>editor</code> can delete this resource.</aside>

#### HTTP Request

`DELETE https://api.planningcenteronline.com/check_ins/v2/passes/1`

## People

An attendee, volunteer or administrator.

_Usually_, a person who checked in will be present as a `Person`. In some cases, they may not be present:
- The person was manually deleted from the admin interface
- The check-in was created as a "One-time guest" (which doesn't create a corresponding person record)





### List People

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/people"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/people`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | organization | include associated organization
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Person

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/people/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Person",
    "id": "primary_key",
    "attributes": {
      "addresses": "unknown",
      "avatar_url": "string",
      "birthdate": "2000-01-01",
      "check_in_count": 1,
      "child": true,
      "email_addresses": "unknown",
      "first_name": "string",
      "gender": "string",
      "grade": 1,
      "last_name": "string",
      "medical_notes": "string",
      "middle_name": "string",
      "name_prefix": "string",
      "name_suffix": "string",
      "permission": "string",
      "phone_numbers": "unknown"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/people/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | organization | include associated organization

### Associations for a Person

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
 |  | 
check_ins | https://api.planningcenteronline.com/check_ins/v2/people/1/check_ins | CheckIn
organization | https://api.planningcenteronline.com/check_ins/v2/people/1/organization | Organization
passes | https://api.planningcenteronline.com/check_ins/v2/people/1/passes | Pass
person_events | https://api.planningcenteronline.com/check_ins/v2/people/1/person_events | PersonEvent







## PersonEvents

Counts a person's attendence for a given event.




### List Person Events

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/events/1/person_events"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events/1/person_events`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person
include | event | include associated event
include | first_check_in | include associated first_check_in
include | last_check_in | include associated last_check_in
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=person,event</code></aside>

### Get a single Person Event

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/events/1/person_events/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "PersonEvent",
    "id": "primary_key",
    "attributes": {
      "check_in_count": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events/1/person_events/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person
include | event | include associated event
include | first_check_in | include associated first_check_in
include | last_check_in | include associated last_check_in

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=person,event</code></aside>

### Associations for a Person Event

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
event | https://api.planningcenteronline.com/check_ins/v2/events/1/person_events/1/event | Event
first_check_in | https://api.planningcenteronline.com/check_ins/v2/events/1/person_events/1/first_check_in | CheckIn
last_check_in | https://api.planningcenteronline.com/check_ins/v2/events/1/person_events/1/last_check_in | CheckIn
person | https://api.planningcenteronline.com/check_ins/v2/events/1/person_events/1/person | Person







## Stations

A device where people can be checked in.
A device may also be connected to a printer
and print labels for itself or other stations.




### List Stations

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/stations"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/stations`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | theme | include associated theme
include | event | include associated event
include | location | include associated location
include | print_station | include associated print_station
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=theme,event</code></aside>

### Get a single Station

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/stations/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Station",
    "id": "primary_key",
    "attributes": {
      "input_type": 1,
      "mode": 1,
      "name": "string",
      "online": "unknown",
      "show_scanner": true,
      "timeout_seconds": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/stations/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | theme | include associated theme
include | event | include associated event
include | location | include associated location
include | print_station | include associated print_station

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=theme,event</code></aside>

### Associations for a Station

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
check_in_groups | https://api.planningcenteronline.com/check_ins/v2/stations/1/check_in_groups | CheckInGroup
checked_in_at_check_ins | https://api.planningcenteronline.com/check_ins/v2/stations/1/checked_in_at_check_ins | CheckIn
event | https://api.planningcenteronline.com/check_ins/v2/stations/1/event | Event
location | https://api.planningcenteronline.com/check_ins/v2/stations/1/location | Location
print_station | https://api.planningcenteronline.com/check_ins/v2/stations/1/print_station | Station
theme | https://api.planningcenteronline.com/check_ins/v2/stations/1/theme | Theme







## Themes

A custom style which may be applied to stations.




### List Themes

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/themes"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/themes`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Theme

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/themes/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Theme",
    "id": "primary_key",
    "attributes": {
      "color": "string",
      "image": "string",
      "image_thumbnail": "unknown",
      "name": "string",
      "text_color": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/themes/1`

#### URL Parameters

_none_





