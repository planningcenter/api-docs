# PCO Check-Ins

Check kids & volunteers in to events and track attendance.

## Activities

An action made by a person



### List Activities

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/people/1/activities"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/people/1/activities`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)







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
after | _id_ | get page after the specified id
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
    "id": "1",
    "attributes": {
      "name": "string",
      "color": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types/1`

#### URL Parameters

_none_

### Associations for an Attendance Type

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
headcounts | https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types/1/headcounts | Headcount







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
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

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
    "id": "1",
    "attributes": {
      "first_name": "string",
      "last_name": "string",
      "medical_notes": "string",
      "kind": "string",
      "number": 1,
      "security_code": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "checked_out_at": "2000-01-01T12:00:00Z",
      "emergency_contact_name": "string",
      "emergency_contact_phone_number": "string"
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
after | _id_ | get page after the specified id
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
    "id": "1",
    "attributes": {
      "name_labels_count": 1,
      "security_labels_count": 1,
      "check_ins_count": 1,
      "print_status": 1
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
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

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
    "id": "1",
    "attributes": {
      "name": "string",
      "frequency": "string",
      "enable_services_integration": true,
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "archived_at": "2000-01-01T12:00:00Z"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/events/1`

#### URL Parameters

_none_

### Associations for an Event

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
attendance_types | https://api.planningcenteronline.com/check_ins/v2/events/1/attendance_types | AttendanceType
check_ins | https://api.planningcenteronline.com/check_ins/v2/events/1/check_ins | CheckIn
event_labels | https://api.planningcenteronline.com/check_ins/v2/events/1/event_labels | EventLabel
event_periods | https://api.planningcenteronline.com/check_ins/v2/events/1/event_periods | EventPeriod
locations | https://api.planningcenteronline.com/check_ins/v2/events/1/locations | Location
person_events | https://api.planningcenteronline.com/check_ins/v2/events/1/person_events | PersonEvent







## EventLabels

Says how many of a given label to print for this event and
whether to print it for regulars, guests, and/or volunteers.




### List Event Labels

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/labels/1/event_labels"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/labels/1/event_labels`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event | include associated event
include | label | include associated label
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event,label</code></aside>

### Get a single Event Label

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/labels/1/event_labels/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "EventLabel",
    "id": "1",
    "attributes": {
      "quantity": 1,
      "for_regular": true,
      "for_guest": true,
      "for_volunteer": true
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/labels/1/event_labels/1`

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
event | https://api.planningcenteronline.com/check_ins/v2/labels/1/event_labels/1/event | Event
label | https://api.planningcenteronline.com/check_ins/v2/labels/1/event_labels/1/label | Label







## EventPeriods

A recurrence of an event, sometimes called a "session".
For weekly events, an event period is a week.
An event period has event times, which is what people select
when they actually check in. When new sessions are created, times
are copied from one session to the next.




### List Event Periods

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/check_ins/1/event_period"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/check_ins/1/event_period`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event | include associated event
include | event_times | include associated event_times
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event,event_times</code></aside>

### Get a single Event Period

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/check_ins/1/event_period/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "EventPeriod",
    "id": "1",
    "attributes": {
      "starts_at": "2000-01-01T12:00:00Z",
      "ends_at": "2000-01-01T12:00:00Z",
      "regular_count": 1,
      "guest_count": 1,
      "volunteer_count": 1,
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/check_ins/1/event_period/1`

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
check_ins | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/event_period/1/check_ins | CheckIn
event | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/event_period/1/event | Event
event_times | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/event_period/1/event_times | EventTime
location_event_periods | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/event_period/1/location_event_periods | LocationEventPeriod







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
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

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
    "id": "1",
    "attributes": {
      "starts_at": "2000-01-01T12:00:00Z",
      "shows_at": "2000-01-01T12:00:00Z",
      "hides_at": "2000-01-01T12:00:00Z",
      "regular_count": 1,
      "guest_count": 1,
      "volunteer_count": 1,
      "total_count": "unknown",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
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
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/event_times/1/headcounts"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/event_times/1/headcounts`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event_time | include associated event_time
include | attendance_type | include associated attendance_type
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event_time,attendance_type</code></aside>

### Get a single Headcount

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/event_times/1/headcounts/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Headcount",
    "id": "1",
    "attributes": {
      "total": 1
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/event_times/1/headcounts/1`

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
attendance_type | https://api.planningcenteronline.com/check_ins/v2/event_times/1/headcounts/1/attendance_type | AttendanceType
event_time | https://api.planningcenteronline.com/check_ins/v2/event_times/1/headcounts/1/event_time | EventTime







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
after | _id_ | get page after the specified id
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
    "id": "1",
    "attributes": {
      "name": "string",
      "xml": "string",
      "prints_for": "string",
      "roll": "string"
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
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | parent | include associated parent
include | event | include associated event
include | locations | include associated locations
include | options | include associated options
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=parent,event</code></aside>

### Get a single Location

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Location",
    "id": "1",
    "attributes": {
      "name": "string",
      "kind": "string",
      "opened": true,
      "questions": "string",
      "age_min_in_months": 1,
      "age_range_by": "string",
      "age_on": "2000-01-01",
      "grade_min": 1,
      "grade_max": 1,
      "max_occupancy": 1,
      "position": 1,
      "updated_at": "2000-01-01T12:00:00Z",
      "created_at": "2000-01-01T12:00:00Z"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1`

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
check_ins | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/check_ins | CheckIn
event | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/event | Event
location_event_periods | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/location_event_periods | LocationEventPeriod
location_event_times | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/location_event_times | LocationEventTime
location_labels | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/location_labels | LocationLabel
locations | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/locations | Location
options | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/options | Option
parent | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/parent | Location







## LocationEventPeriods

Counts check-ins for a location during a certain event period.




### List Location Event Periods

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/location_event_periods"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/location_event_periods`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | location | include associated location
include | event_period | include associated event_period
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=location,event_period</code></aside>

### Get a single Location Event Period

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/location_event_periods/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "LocationEventPeriod",
    "id": "1",
    "attributes": {
      "regular_count": 1,
      "guest_count": 1,
      "volunteer_count": 1
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/location_event_periods/1`

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
check_ins | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/location_event_periods/1/check_ins | CheckIn
event_period | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/location_event_periods/1/event_period | EventPeriod
location | https://api.planningcenteronline.com/check_ins/v2/check_ins/1/location/1/location_event_periods/1/location | Location







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
after | _id_ | get page after the specified id
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
    "id": "1",
    "attributes": {
      "regular_count": 1,
      "guest_count": 1,
      "volunteer_count": 1
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
after | _id_ | get page after the specified id
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
    "id": "1",
    "attributes": {
      "quantity": 1,
      "for_regular": true,
      "for_guest": true,
      "for_volunteer": true
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
after | _id_ | get page after the specified id
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
    "id": "1",
    "attributes": {
      "body": "string",
      "quantity": 1
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
    "id": "1",
    "attributes": {
      "name": "string",
      "daily_check_ins": 1,
      "date_format_pattern": "unknown",
      "time_zone": "string"
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
labels | https://api.planningcenteronline.com/check_ins/v2/labels | Label
passes | https://api.planningcenteronline.com/check_ins/v2/passes | Pass
people | https://api.planningcenteronline.com/check_ins/v2/people | Person
stations | https://api.planningcenteronline.com/check_ins/v2/stations | Station
themes | https://api.planningcenteronline.com/check_ins/v2/themes | Theme







## Passes

Enables quick lookup of a person via barcode reader.




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
include | person | include associated person
after | _id_ | get page after the specified id
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
    "id": "1",
    "attributes": {
      "code": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
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
after | _id_ | get page after the specified id
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
    "id": "1",
    "attributes": {
      "avatar_url": "string",
      "name_prefix": "string",
      "first_name": "string",
      "middle_name": "string",
      "last_name": "string",
      "name_suffix": "string",
      "birthdate": "2000-01-01",
      "grade": 1,
      "gender": "string",
      "medical_notes": "string",
      "child": true,
      "addresses": "unknown",
      "phone_numbers": "unknown",
      "email_addresses": "unknown",
      "permission": "string",
      "check_in_count": 1
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/people/1`

#### URL Parameters

_none_

### Associations for a Person

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
activities | https://api.planningcenteronline.com/check_ins/v2/people/1/activities | Activity
check_ins | https://api.planningcenteronline.com/check_ins/v2/people/1/check_ins | CheckIn
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
after | _id_ | get page after the specified id
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
    "id": "1",
    "attributes": {
      "check_in_count": 1
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
after | _id_ | get page after the specified id
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
    "id": "1",
    "attributes": {
      "mode": 1,
      "name": "string",
      "timeout_seconds": 1,
      "input_type": 1,
      "show_scanner": true,
      "online": "unknown"
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
after | _id_ | get page after the specified id
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
    "id": "1",
    "attributes": {
      "name": "string",
      "color": "string",
      "text_color": "string",
      "image": "string",
      "image_thumbnail": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/check_ins/v2/themes/1`

#### URL Parameters

_none_





