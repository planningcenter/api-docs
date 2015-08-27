# PCO Services (BETA)

Schedule your teams, manage your music, and revolutionize the way you plan your worship services. Note that PCO Services endpoints are read-only during this phase of the beta.

## AnnotationDrawings

A single pen stroke, highlighter stroke, or text annotation a user has added to a PDF in Music Stand.



### List Annotation Drawings

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments/1/annotation_drawings"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments/1/annotation_drawings`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Annotation Drawing

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments/1/annotation_drawings/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "AnnotationDrawing",
    "id": "1",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments/1/annotation_drawings/1`

#### URL Parameters

_none_







## Attachments

A file, whether it's stored on Planning Center or linked from another location.



### List Attachments

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[created_by_id] | _integer_ | filter on a specific created_by_id
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Attachment

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Attachment",
    "id": "1",
    "attributes": {
      "remote_link": "string",
      "transposable": "unknown",
      "url": "unknown",
      "attachable_type": "string",
      "allow_mp3_download": true,
      "attachment_type_ids": "string",
      "content_type": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "downloadable": "unknown",
      "linked_type": "unknown",
      "linked_url": "unknown",
      "page_order": "string",
      "pco_type": "unknown",
      "streamable": "unknown",
      "updated_at": "2000-01-01T12:00:00Z",
      "web_streamable": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments/1`

#### URL Parameters

_none_

### Associations for an Attachment

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
annotation_drawings | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments/1/annotation_drawings
attachment_annotations | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments/1/attachment_annotations







## AttachmentAnnotations

A set of annotation drawings that make up all annotations a user has added to a PDF in Music Stand.



### List Attachment Annotations

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments/1/attachment_annotations"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments/1/attachment_annotations`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Attachment Annotation

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments/1/attachment_annotations/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "AttachmentAnnotation",
    "id": "1",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "user_name": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments/1/attachment_annotations/1`

#### URL Parameters

_none_







## Folders

A folder is a container used to organize multiple Service Types or other Folders.



### List Folders

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/folders"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/folders`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | service_types | include associated service_types
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Folder

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/folders/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Folder",
    "id": "1",
    "attributes": {
      "name": "string",
      "container": "unknown",
      "created_at": "2000-01-01T12:00:00Z",
      "parent_id": 1,
      "updated_at": "2000-01-01T12:00:00Z"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/folders/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | service_types | include associated service_types

### Associations for a Folder

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
service_types | https://api.planningcenteronline.com/services/v2/folders/1/service_types







## Items

An item in a plan.

### Attribute Info

<span class='attribute-info-name'>item_type</span>

There are 4 possible values:

- `song`: The item is a song

- `header`: The item is a header

- `media`: The item is a piece of media

- `item`: The default item type


<span class='attribute-info-name'>service_position</span>

There are 3 possible values:

- `pre`: the item happens before the service starts

- `post`: the item happens after the service ends

- `during`: the item happens during the service


### List Items

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | item_notes | include associated item_notes
include | song | include associated song
include | item_media | include associated item_media
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=item_notes,song</code></aside>

### Get a single Item

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Item",
    "id": "1",
    "attributes": {
      "title": "string",
      "sequence": 1,
      "service_position": "unknown",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "item_type": "unknown",
      "length": 1,
      "song_id": 1,
      "description": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | item_notes | include associated item_notes
include | song | include associated song
include | item_media | include associated item_media

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=item_notes,song</code></aside>

### Associations for an Item

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
attachments | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments
item_media | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_media
item_notes | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes
song | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/song







## ItemMedias

A media item attached to a plan item



### List Item Medias

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_medias"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_medias`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
where[media_id] | _integer_ | filter on a specific media_id
include | media | include associated media
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Item Media

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_medias/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ItemMedia",
    "id": "1",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "media_id": 1
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_medias/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | media | include associated media

### Associations for an Item Media

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
media | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_medias/1/media







## ItemNotes

A plan item note that belongs to a category



### List Item Notes

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
where[category_id] | _integer_ | filter on a specific category_id
where[category_name] | __ | filter on a specific category_name
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Item Note

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ItemNote",
    "id": "1",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "category_id": 1,
      "category_name": "unknown",
      "content": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes/1`

#### URL Parameters

_none_







## Medias

A piece of media



### List Medias

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/medias"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/medias`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Media

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/medias/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Media",
    "id": "1",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "creator_name": "unknown",
      "media_type": "string",
      "themes": "string",
      "title": "string"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/medias/1`

#### URL Parameters

_none_

### Associations for a Media

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
attachments | https://api.planningcenteronline.com/services/v2/medias/1/attachments







## NeededPositions

An amount of unfilled positions needed within a team in a plan.



### List Needed Positions

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Needed Position

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "NeededPosition",
    "id": "1",
    "attributes": {
      "quantity": 1,
      "scheduled_to": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1`

#### URL Parameters

_none_

### Associations for a Needed Position

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
team | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1/team
time | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1/time







## Organizations

The root level of an organization where account-level settings are applied.



### Get a single Organization

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Organization",
    "id": "1",
    "attributes": {
      "ccli": "string",
      "ccli_connected": "unknown",
      "created_at": "2000-01-01T12:00:00Z",
      "date_format": 1,
      "music_stand_enabled": true,
      "name": "string",
      "owner_name": "unknown",
      "projector_enabled": true,
      "secret": "unknown",
      "time_zone": "string",
      "twenty_four_hour_time": true,
      "updated_at": "2000-01-01T12:00:00Z",
      "beta": true
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2`

#### URL Parameters

_none_

### Associations for an Organization

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
folders | https://api.planningcenteronline.com/services/v2/folders
media | https://api.planningcenteronline.com/services/v2/media
people | https://api.planningcenteronline.com/services/v2/people
service_types | https://api.planningcenteronline.com/services/v2/service_types
songs | https://api.planningcenteronline.com/services/v2/songs
tag_groups | https://api.planningcenteronline.com/services/v2/tag_groups







## People

A person added to PCO Services.



### List People

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | addresses | include associated addresses
include | email_addresses | include associated email_addresses
include | team_leaders | include associated team_leaders
include | phone_numbers | include associated phone_numbers
include | properties | include associated properties
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=addresses,email_addresses</code></aside>

### Get a single Person

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Person",
    "id": "1",
    "attributes": {
      "first_name": "string",
      "middle_name": "string",
      "last_name": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "accounts_id": "unknown",
      "photo_thumbnail_url": "unknown",
      "photo_url": "unknown",
      "permissions": "unknown",
      "status": "unknown",
      "notes": "string",
      "created_by_id": 1,
      "updated_by_id": 1,
      "facebook_id": 1,
      "birthdate": "2000-01-01T12:00:00Z",
      "anniversary": "2000-01-01T12:00:00Z",
      "ical_code": "string",
      "site_administrator": true,
      "max_permissions": "unknown",
      "logged_in_at": "2000-01-01T12:00:00Z",
      "me_tab": "unknown",
      "plans_tab": "unknown",
      "songs_tab": "unknown",
      "media_tab": "unknown",
      "people_tab": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | addresses | include associated addresses
include | email_addresses | include associated email_addresses
include | team_leaders | include associated team_leaders
include | phone_numbers | include associated phone_numbers
include | properties | include associated properties

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=addresses,email_addresses</code></aside>

### Associations for a Person

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
person_team_position_assignments | https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments
plan_people | https://api.planningcenteronline.com/services/v2/people/1/plan_people
tags | https://api.planningcenteronline.com/services/v2/people/1/tags
team_leaders | https://api.planningcenteronline.com/services/v2/people/1/team_leaders







## PersonTeamPositionAssignments

A person's assignment to a position within a team.



### List Person Team Position Assignments

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Person Team Position Assignment

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "PersonTeamPositionAssignment",
    "id": "1",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments/1`

#### URL Parameters

_none_







## Plans

A single plan within a Service Type.

Potentially confusing attributes:
  - attachment_type_ids: The attachment type IDs assigned to the current user based on what positions they are scheduled to in this plan. This determines what files they can see.
  - files_expire_at: A date 1 month after the last service time.
  - items_count: The total number of items, including regular items, songs, media, and headers, that the current user can see in the plan.
  - next_plan_id: The ID of the next chronological plan within the current Service Type.
  - previous_plan_id: The ID of the previous chronological plan within the current Service Type.
  - permissions: The current user's permissions for this plan's Service Type.
  - total_length: The total of length of all items, excluding pre-service and post-service items.
  - display_dates: The shortened date string representing all Service Time dates. Months are abbreviated, and the year is omitted.
  - sort_date: A time representing the chronological first Service Time, used to sort plan chronologically. If no Service Times exist, it uses Rehearsal Times, then Other Times, then NOW.
  - starts_at: A time representing the chronological last Time (Service, Rehearsal, or Other). Once this passes, a plan is considered to be in the past.
  - dates: The full date string representing all Service Time dates.
  - public: True if Public Access has been enabled.




### List Plans

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[plan_title] | __ | filter on a specific plan_title
where[starts_at] | __ | filter on a specific starts_at
include | series | include associated series
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Plan

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Plan",
    "id": "1",
    "attributes": {
      "attachment_type_ids": "unknown",
      "created_at": "2000-01-01T12:00:00Z",
      "files_expire_at": "unknown",
      "items_count": "unknown",
      "title": "string",
      "next_plan_id": "unknown",
      "other_time_count": "unknown",
      "permissions": "unknown",
      "plan_notes_count": "unknown",
      "previous_plan_id": "unknown",
      "rehearsal_time_count": "unknown",
      "service_time_count": "unknown",
      "plan_people_count": "unknown",
      "total_length": "unknown",
      "short_dates": "unknown",
      "sort_date": "unknown",
      "updated_at": "2000-01-01T12:00:00Z",
      "last_time_at": "unknown",
      "dates": "unknown",
      "public": true,
      "needed_positions_count": "unknown",
      "attachments_count": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | series | include associated series

### Associations for a Plan

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
attachments | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/attachments
items | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items
needed_positions | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions
next_plan | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/next_plan
notes | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes
plan_times | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/plan_times
previous_plan | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/previous_plan
series | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/series
team_member | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/team_member







## PlanNotes

A specific plan note within a single plan.



### List Plan Notes

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[created_at] | _datetime_ | filter on a specific created_at
where[updated_at] | _datetime_ | filter on a specific updated_at
where[category_name] | __ | filter on a specific category_name
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Plan Note

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "PlanNote",
    "id": "1",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "category_name": "unknown",
      "content": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes/1`

#### URL Parameters

_none_

### Associations for a Plan Note

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
plan_note_category | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes/1/plan_note_category







## PlanNoteCategories

A category of plan notes for an entire Service Type.



### List Plan Note Categories

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plan_note_categories"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plan_note_categories`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Plan Note Category

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plan_note_categories/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "PlanNoteCategory",
    "id": "1",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "name": "string"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plan_note_categories/1`

#### URL Parameters

_none_







## PlanPeople

A person scheduled within a specific plan.
The potentially confusing attributes are:
  - can_accept_partial: If the person is scheduled to a split team where they could potentially accept 1 time and decline another.
  - excluded_times: Scheduled people are assigned to all service, rehearsal, and other times, unless you exclude them. Exclude any times the person is not assigned to for that plan.




### List Plan People

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | team | include associated team
include | person | include associated person
include | plan | include associated plan
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=team,person</code></aside>

### Get a single Plan Person

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "PlanPerson",
    "id": "1",
    "attributes": {
      "position": "string",
      "status": "string",
      "status_updated_at": "unknown",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "plan_id": "unknown",
      "prepare_notification": "unknown",
      "photo_thumbnail": "unknown",
      "name": "unknown",
      "notes": "string",
      "decline_reason": "string",
      "can_accept_partial": "unknown",
      "responds_to_id": "unknown",
      "excluded_times": "string"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | team | include associated team
include | person | include associated person
include | plan | include associated plan

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=team,person</code></aside>

### Associations for a Plan Person

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
person | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/person
plan | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan
plan_times | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times
team | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/team







## PlanTimes

A time in a plan.

There are 3 possible 'time_type' values:
  - Service
  - Rehearsal
  - Other

Potentially confusing attributes:
  - starts_at: Planned start time.
  - ends_at: Planned end time.
  - live_start: Start time as recorded by Services LIVE.
  - live_end: End time as recorded by Services LIVE.
  - team_reminders: A Hash that maps a Team ID to a reminder value. If nothing is specified, no reminder is set for that team. A reminder value is an integer (0-7) equal to the number of days before the selected time a reminder should be sent.
  - included_category_ids: The IDs of each Team assigned to this time.




### List Plan Times

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Plan Time

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "PlanTime",
    "id": "1",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "live_starts_at": "unknown",
      "live_ends_at": "unknown",
      "starts_at": "2000-01-01T12:00:00Z",
      "ends_at": "2000-01-01T12:00:00Z",
      "time_type": 1,
      "team_reminders": "unknown",
      "included_category_ids": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times/1`

#### URL Parameters

_none_

### Associations for a Plan Time

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
split_team_rehearsal_assignments | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times/1/split_team_rehearsal_assignments







## Series

A Series can be specified for each plan to tie plans with similar messages together, even across Service Types.



### List Series

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/series"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/series`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Series

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/series/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Series",
    "id": "1",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "title": "unknown",
      "artwork_file_name": "string",
      "artwork_content_type": "string",
      "artwork_file_size": 1,
      "artwork_for_plan": "unknown",
      "artwork_for_mobile": "unknown",
      "artwork_for_dashboard": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/series/1`

#### URL Parameters

_none_







## ServiceTypes

A Service Type is a container for plans.



### List Service Types

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Service Type

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ServiceType",
    "id": "1",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "permissions": "unknown",
      "updated_at": "2000-01-01T12:00:00Z",
      "parent_id": 1,
      "sequence": 1
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1`

#### URL Parameters

_none_

### Associations for a Service Type

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
plan_note_categories | https://api.planningcenteronline.com/services/v2/service_types/1/plan_note_categories
plans | https://api.planningcenteronline.com/services/v2/service_types/1/plans
teams | https://api.planningcenteronline.com/services/v2/service_types/1/teams







## Songs

A song



### List Songs

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[title] | _string_ | filter on a specific title
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Song

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Song",
    "id": "1",
    "attributes": {
      "title": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "admin": "string",
      "author": "string",
      "copyright": "string",
      "ccli_number": "unknown",
      "hidden": true,
      "themes": "string"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1`

#### URL Parameters

_none_

### Associations for a Song

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
arrangements | https://api.planningcenteronline.com/services/v2/songs/1/arrangements







## SongArrangements

Each arrangement belongs to a song and is a different version of that song.



### List Song Arrangements

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/arrangements"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/arrangements`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Song Arrangement

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "SongArrangement",
    "id": "1",
    "attributes": {
      "name": "string",
      "bpm": 1,
      "has_chords": true,
      "has_chord_chart": "unknown",
      "length": 1,
      "meter": "string",
      "updated_by_id": "unknown",
      "created_by_id": 1,
      "notes": "string",
      "chord_chart": "string",
      "chord_chart_font": "string",
      "chord_chart_key": "string",
      "chord_chart_columns": 1,
      "chord_chart_font_size": 1,
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1`

#### URL Parameters

_none_

### Associations for a Song Arrangement

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
attachments | https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/attachments
song_keys | https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/song_keys







## SongKeys

Each song arrangement can have multiple keys. A key is the pitch center of the song.



### List Song Keys

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/song_keys"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/song_keys`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Song Key

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/song_keys/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "SongKey",
    "id": "1",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "starting_key": "unknown",
      "ending_key": "unknown",
      "alternate_keys": "string"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/song_keys/1`

#### URL Parameters

_none_







## SplitTeamRehearsalAssignments

For Rehearsal/Other Times, maps a Split Team to selected Time Preference Options. For example, used to assign 8am Ushers to 7:30 call time, and 11am Ushers to 10:30 call time.

Potentially confusing attributes:
- assigned_to: Either 'team' or 'time_preferences'
- time_preference_ids: The IDs of the assigned time preference options.




### List Split Team Rehearsal Assignments

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times/1/split_team_rehearsal_assignments"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times/1/split_team_rehearsal_assignments`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Split Team Rehearsal Assignment

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times/1/split_team_rehearsal_assignments/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "SplitTeamRehearsalAssignment",
    "id": "1",
    "attributes": {
      "assigned_to": "unknown",
      "team_id": "unknown",
      "time_preference_ids": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times/1/split_team_rehearsal_assignments/1`

#### URL Parameters

_none_

### Associations for a Split Team Rehearsal Assignment

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
team | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times/1/split_team_rehearsal_assignments/1/team







## Tags

A tag belonging to a tag group.



### List Tags

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/tags"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/tags`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Tag

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/tags/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Tag",
    "id": "1",
    "attributes": {
      "name": "string",
      "group_id": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/tags/1`

#### URL Parameters

_none_







## TagGroups

A tag group contains tags

tags_for scopes a tag group to
- person
- song
- arrangement
- media




### List Tag Groups

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/tag_groups"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/tag_groups`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[name] | _string_ | filter on a specific name
include | tags | include associated tags
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Tag Group

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/tag_groups/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "TagGroup",
    "id": "1",
    "attributes": {
      "name": "string",
      "allow_multiple_selections": true,
      "tags_for": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/tag_groups/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | tags | include associated tags

### Associations for a Tag Group

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
tags | https://api.planningcenteronline.com/services/v2/tag_groups/1/tags







## Teams

A Team within a Service Type.



### List Teams

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/teams"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/teams`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | team_positions | include associated team_positions
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Team

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/teams/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Team",
    "id": "1",
    "attributes": {
      "name": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "sequence": 1,
      "schedule_to": "string"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/teams/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | team_positions | include associated team_positions

### Associations for a Team

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL
----------- | ---
plan_people | https://api.planningcenteronline.com/services/v2/service_types/1/teams/1/plan_people
team_positions | https://api.planningcenteronline.com/services/v2/service_types/1/teams/1/team_positions







## TeamLeaders

A leader of a specific Team in a Service Type.



### List Team Leaders

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/team_leaders"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/team_leaders`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Team Leader

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/team_leaders/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "TeamLeader",
    "id": "1",
    "attributes": {
      "send_responses_for_accepts": true,
      "send_responses_for_declines": true
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/team_leaders/1`

#### URL Parameters

_none_







## TeamPositions

A position within a team.

Potentially confusing attributes:
  - negative_tag_groups: If the Team is assigned via tags, these are Tags where the option "None" is specified. 
  - tag_groups: If the Team is assigned via tags, these are Tags where the option "Any" is specified.
  - tags: If the Team is assigned via tags, these are specific Tags that are specified.




### List Team Positions

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/teams/1/team_positions"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/teams/1/team_positions`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Team Position

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/teams/1/team_positions/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "TeamPosition",
    "id": "1",
    "attributes": {
      "name": "string",
      "negative_tag_groups": "unknown",
      "tag_groups": "unknown",
      "tags": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/teams/1/team_positions/1`

#### URL Parameters

_none_





