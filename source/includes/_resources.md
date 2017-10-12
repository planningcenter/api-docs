# PCO Resources (BETA)

Reserve rooms, publish event calendars, and revolutionize the way you allocate your church’s resources

## Conflicts

A Conflict between two events caused by overlapping event resource
requests.




### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
resource | Resource | _false_ | 

### List Conflicts

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/conflicts"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/conflicts`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | resource | include associated resource
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Conflict

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/conflicts/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Conflict",
    "id": "primary_key",
    "attributes": {
      "note": "string",
      "resolved_at": "2000-01-01T12:00:00Z",
      "resolved_by_id": 1,
      "winner_id": 1
    },
    "relationships": {
      "resource": {
        "data": {
          "type": "Resource",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/conflicts/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | resource | include associated resource

### Associations for a Conflict

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
 |  | 
resource | https://api.planningcenteronline.com/resources/v2/conflicts/1/resource | Resource







## Events

An event.




### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
owner | Person | _false_ | 

### List Events

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/events"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/events`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | query on a specific name
where[approval_status] | _string_ | query on a specific approval_status
where[percent_approved] | _integer_ | query on a specific percent_approved
where[percent_rejected] | _integer_ | query on a specific percent_rejected
include | owner | include associated owner
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Event

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/events/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Event",
    "id": "primary_key",
    "attributes": {
      "approval_status": "string",
      "archived_at": "2000-01-01T12:00:00Z",
      "details": "string",
      "name": "string",
      "percent_approved": 1,
      "percent_rejected": 1,
    },
    "relationships": {
      "owner": {
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

`GET https://api.planningcenteronline.com/resources/v2/events/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | owner | include associated owner

### Associations for an Event

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
 |  | 
conflicts | https://api.planningcenteronline.com/resources/v2/events/1/conflicts | Conflict
event_instances | https://api.planningcenteronline.com/resources/v2/events/1/event_instances | EventInstance
event_resource_requests | https://api.planningcenteronline.com/resources/v2/events/1/event_resource_requests | EventResourceRequest
resource_bookings | https://api.planningcenteronline.com/resources/v2/events/1/resource_bookings | ResourceBooking







## EventInstances

A specific occurence of an event.




### List Event Instances

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/event_instances"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/event_instances`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[starts_at] | _date_time_ | query on a specific starts_at
where[ends_at] | _date_time_ | query on a specific ends_at
where[event_id] | _integer_ | query on a specific event_id
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Event Instance

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/event_instances/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "EventInstance",
    "id": "primary_key",
    "attributes": {
      "ends_at": "2000-01-01T12:00:00Z",
      "event_id": 1,
      "starts_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/event_instances/1`

#### URL Parameters

_none_

### Associations for an Event Instance

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
event_times | https://api.planningcenteronline.com/resources/v2/event_instances/1/event_times | EventTime
resource_bookings | https://api.planningcenteronline.com/resources/v2/event_instances/1/resource_bookings | ResourceBooking







## EventResourceRequests

A request of a resource for a specific event.




### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
event_resource_request | EventResourceRequest | _false_ | 

### List Event Resource Requests

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/event_resource_requests"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/event_resource_requests`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[approval_status] | _string_ | query on a specific approval_status
where[resource_id] | _integer_ | query on a specific resource_id
where[created_by_id] | _integer_ | query on a specific created_by_id
where[event_id] | _integer_ | query on a specific event_id
where[percent_approved] | _integer_ | query on a specific percent_approved
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Event Resource Request

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/event_resource_requests/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "EventResourceRequest",
    "id": "primary_key",
    "attributes": {
      "approval_sent": true,
      "approval_status": "string",
      "created_by_id": 1,
      "event_id": 1,
      "percent_approved": 1,
      "quantity": 1,
      "resource_id": 1,
      "room_setup_id": 1,
      "room_setup_info": "string"
    },
    "relationships": {
      "event_resource_request": {
        "data": {
          "type": "EventResourceRequest",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/event_resource_requests/1`

#### URL Parameters

_none_

### Associations for an Event Resource Request

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
 |  | 
resource_bookings | https://api.planningcenteronline.com/resources/v2/event_resource_requests/1/resource_bookings | ResourceBooking







## EventTimes

Start and end times used for calendar and kiosk visibility for each
Event Instance.




### List Event Times

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/event_instances/1/event_times"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/event_instances/1/event_times`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[event_id] | _graph/type_annotation/unknown_type_annotation_ | query on a specific event_id
where[starts_at] | _graph/type_annotation/unknown_type_annotation_ | query on a specific starts_at
where[ends_at] | _graph/type_annotation/unknown_type_annotation_ | query on a specific ends_at
where[name] | _graph/type_annotation/unknown_type_annotation_ | query on a specific name
where[visible_on_website?] | _graph/type_annotation/unknown_type_annotation_ | query on a specific visible_on_website?
where[visible_on_kiosks?] | _graph/type_annotation/unknown_type_annotation_ | query on a specific visible_on_kiosks?
where[visible_on_door_signage?] | _graph/type_annotation/unknown_type_annotation_ | query on a specific visible_on_door_signage?
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)







## Organizations



### Get a single Organization

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Organization",
    "id": "1",
    "attributes": {
      "name": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2`

#### URL Parameters

_none_

### Associations for an Organization

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
 |  | 
conflicts | https://api.planningcenteronline.com/resources/v2/conflicts | Conflict
event_instances | https://api.planningcenteronline.com/resources/v2/event_instances | EventInstance
event_resource_requests | https://api.planningcenteronline.com/resources/v2/event_resource_requests | EventResourceRequest
events | https://api.planningcenteronline.com/resources/v2/events | Event
people | https://api.planningcenteronline.com/resources/v2/people | Person
resource_approval_groups | https://api.planningcenteronline.com/resources/v2/resource_approval_groups | ResourceApprovalGroup
resource_bookings | https://api.planningcenteronline.com/resources/v2/resource_bookings | ResourceBooking
resource_questions | https://api.planningcenteronline.com/resources/v2/resource_questions | ResourceQuestion
resources | https://api.planningcenteronline.com/resources/v2/resources | Resource
room_setups | https://api.planningcenteronline.com/resources/v2/room_setups | RoomSetup







## People

The people in your organization.




### List People

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/people"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/people`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[first_name] | _string_ | query on a specific first_name
where[last_name] | _string_ | query on a specific last_name
where[middle_name] | _string_ | query on a specific middle_name
where[account_center_id] | _integer_ | query on a specific account_center_id
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Person

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/people/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Person",
    "id": "primary_key",
    "attributes": {
      "account_center_id": 1,
      "avatar_url": "string",
      "child": true,
      "contact_data": "string",
      "facebook_id": 1,
      "first_name": "string",
      "gender": "string",
      "has_access": true,
      "last_name": "string",
      "middle_name": "string",
      "name_prefix": "string",
      "name_suffix": "string",
      "pending_request_count": 1,
      "permissions": 1,
      "remote_id": 1,
      "resolves_conflicts": true,
      "site_administrator": true,
      "status": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/people/1`

#### URL Parameters

_none_







## Resources

A room or resource (equipment) that can be requested for use as part of
an event.


### Attribute Info

<span class='attribute-info-name'>kind</span>

Possible values: `room`, `equipment`

### List Resources

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/resources"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/resources`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | query on a specific name
where[kind] | _string_ | query on a specific kind
where[resource_folder_id] | _integer_ | query on a specific resource_folder_id
where[serial_number] | _string_ | query on a specific serial_number
include | event_resource_requests | include associated event_resource_requests
include | resource_approval_groups | include associated resource_approval_groups
include | resource_questions | include associated resource_questions
include | conflicts | include associated conflicts
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event_resource_requests,resource_approval_groups</code></aside>

### Get a single Resource

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/resources/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Resource",
    "id": "primary_key",
    "attributes": {
      "created_by_id": 1,
      "description": "string",
      "expires_at": "2000-01-01T12:00:00Z",
      "home_location": "string",
      "image": "string",
      "kind": "string",
      "name": "string",
      "quantity": 1,
      "resource_folder_id": 1,
      "serial_number": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/resources/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | event_resource_requests | include associated event_resource_requests
include | resource_approval_groups | include associated resource_approval_groups
include | resource_questions | include associated resource_questions
include | conflicts | include associated conflicts

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=event_resource_requests,resource_approval_groups</code></aside>

### Associations for a Resource

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
conflicts | https://api.planningcenteronline.com/resources/v2/resources/1/conflicts | Conflict
event_resource_requests | https://api.planningcenteronline.com/resources/v2/resources/1/event_resource_requests | EventResourceRequest
resource_approval_groups | https://api.planningcenteronline.com/resources/v2/resources/1/resource_approval_groups | ResourceApprovalGroup
resource_bookings | https://api.planningcenteronline.com/resources/v2/resources/1/resource_bookings | ResourceBooking
resource_questions | https://api.planningcenteronline.com/resources/v2/resources/1/resource_questions | ResourceQuestion
room_setups | https://api.planningcenteronline.com/resources/v2/resources/1/room_setups | RoomSetup







## ResourceApprovalGroups

    A group of people that can be attached to resources in order to require
    their approval.




### List Resource Approval Groups

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/resource_approval_groups"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/resource_approval_groups`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | query on a specific name
include | approvers | include associated approvers
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Resource Approval Group

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/resource_approval_groups/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ResourceApprovalGroup",
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

`GET https://api.planningcenteronline.com/resources/v2/resource_approval_groups/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | approvers | include associated approvers

### Associations for a Resource Approval Group

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
approvers | https://api.planningcenteronline.com/resources/v2/resource_approval_groups/1/approvers | Person







## ResourceBookings

A specific booking of a resource for an event instance.




### List Resource Bookings

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/resource_bookings"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/resource_bookings`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[event_id] | _integer_ | query on a specific event_id
where[event_resource_request_id] | _integer_ | query on a specific event_resource_request_id
where[starts_at] | _date_time_ | query on a specific starts_at
where[ends_at] | _date_time_ | query on a specific ends_at
where[resource_id] | _integer_ | query on a specific resource_id
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Resource Booking

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/resource_bookings/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ResourceBooking",
    "id": "primary_key",
    "attributes": {
      "ends_at": "2000-01-01T12:00:00Z",
      "event_id": 1,
      "event_instance_id": 1,
      "event_resource_request_id": 1,
      "quantity": 1,
      "resource_id": 1,
      "starts_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/resource_bookings/1`

#### URL Parameters

_none_

### Associations for a Resource Booking

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
 |  | 







## ResourceQuestions

A question to answer when requesting to book a resource.




### List Resource Questions

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/resource_questions"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/resource_questions`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[kind] | _string_ | query on a specific kind
where[resource_id] | _integer_ | query on a specific resource_id
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Resource Question

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/resource_questions/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ResourceQuestion",
    "id": "primary_key",
    "attributes": {
      "choices": "string",
      "created_by_id": 1,
      "kind": "string",
      "multiple_select": true,
      "optional": true,
      "position": 1,
      "question": "string",
      "resource_id": 1
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/resource_questions/1`

#### URL Parameters

_none_







## RoomSetups

A diagram and list of suggested resources useful for predefined room
setups.




### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
room_setup | RoomSetup | _false_ | A linked shared room setup

### List Room Setups

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/room_setups"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/room_setups`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | query on a specific name
where[setupable_type] | _string_ | query on a specific setupable_type
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Room Setup

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/resources/v2/room_setups/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "RoomSetup",
    "id": "primary_key",
    "attributes": {
      "created_by_id": 1,
      "description": "string",
      "diagram": "string",
      "name": "string",
      "setupable_id": 1,
      "setupable_type": "string"
    },
    "relationships": {
      "room_setup": {
        "data": {
          "type": "RoomSetup",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/resources/v2/room_setups/1`

#### URL Parameters

_none_





