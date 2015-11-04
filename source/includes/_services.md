# PCO Services (BETA)

Schedule your teams, manage your music, and revolutionize the way you plan your worship services. Note that PCO Services endpoints are read-only during this phase of the beta.

## Activities

An action made by a person



### List Activities

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/activities"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/activities`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)







## AnnotationDrawings

A single pen stroke, highlighter stroke, or text annotation a user has added to a PDF in Music Stand.



### List Annotation Drawings

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/media/1/attachments/1/annotation_drawings"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/media/1/attachments/1/annotation_drawings`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Annotation Drawing

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/media/1/attachments/1/annotation_drawings/1"
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

`GET https://api.planningcenteronline.com/services/v2/media/1/attachments/1/annotation_drawings/1`

#### URL Parameters

_none_







## Arrangements

Each arrangement belongs to a song and is a different version of that song.

### Attribute Info

<span class='attribute-info-name'>chord_chart_fonts</span>

Possible Values:

- `Courier`

- `Helvetica`

- `Monaco`

- `Times-Roman`


<span class='attribute-info-name'>chord_chart_font_size</span>

Possible Values:

`10`, `11`, `12`, `13`, `14`, `15`, `16`, `18`, `20`, `24`, `28`, `32`, `36`, `42`, `48`


<span class='attribute-info-name'>meter</span>

Possible Values:

- `2/2`

- `2/4`

- `3/4`

- `4/4`

- `5/4`

- `6/4`

- `3/8`

- `6/8`

- `7/8`

- `9/8`

- `12/8`


### List Arrangements

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

### Get a single Arrangement

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Arrangement",
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

### Associations for an Arrangement

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
attachments | https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/attachments | Attachment
keys | https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys | Key

### Create a new Arrangement

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Arrangement","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/songs/1/arrangements"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/songs/1/arrangements`

#### Resource Attributes

Attribute | Type | Note
--------- | ---- | ----
name | string
bpm | float
length | integer
meter | string | Acceptable values are "2/2", "2/4", "3/4", "4/4", "5/4", "6/4", "3/8", "6/8", "7/8", "9/8", and "12/8".
notes | text
chord_chart | text
chord_chart_font | string | Acceptable values are "Courier", "Helvetica", "Monaco", and "Times-Roman".
chord_chart_key | string | Acceptable values are "Ab", "A", "A#", "Bb", "B", "C", "C#", "Db", "D", "D#", "Eb", "E", "F", "F#", "Gb", "G", "G#", "Abm", "Am", "A#m", "Bbm", "Bm", "Cm", "C#m", "Dbm", "Dm", "D#m", "Ebm", "Em", "Fm", "F#m", "Gbm", "Gm", and "G#m".
chord_chart_columns | integer
chord_chart_font_size | integer | Acceptable values are 10, 11, 12, 13, 14, 15, 16, 18, 20, 24, 28, 32, 36, 42, and 48.

### Update an existing Arrangement

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Arrangement","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1`

#### Resource Attributes

Attribute | Type | Note
--------- | ---- | ----
name | string
bpm | float
length | integer
meter | string | Acceptable values are "2/2", "2/4", "3/4", "4/4", "5/4", "6/4", "3/8", "6/8", "7/8", "9/8", and "12/8".
notes | text
chord_chart | text
chord_chart_font | string | Acceptable values are "Courier", "Helvetica", "Monaco", and "Times-Roman".
chord_chart_key | string | Acceptable values are "Ab", "A", "A#", "Bb", "B", "C", "C#", "Db", "D", "D#", "Eb", "E", "F", "F#", "Gb", "G", "G#", "Abm", "Am", "A#m", "Bbm", "Bm", "Cm", "C#m", "Dbm", "Dm", "D#m", "Ebm", "Em", "Fm", "F#m", "Gbm", "Gm", and "G#m".
chord_chart_columns | integer
chord_chart_font_size | integer | Acceptable values are 10, 11, 12, 13, 14, 15, 16, 18, 20, 24, 28, 32, 36, 42, and 48.

### Delete an Arrangement

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1`

## Attachments

A file, whether it's stored on Planning Center or linked from another location.



### List Attachments

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/media/1/attachments"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/media/1/attachments`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[created_by_id] | _integer_ | query on a specific created_by_id
where[updated_by_id] | _integer_ | query on a specific updated_by_id
where[created_at] | _datetime_ | query on a specific created_at
where[updated_at] | _datetime_ | query on a specific updated_at
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Attachment

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/media/1/attachments/1"
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
      "web_streamable": "unknown",
      "created_by_id": 1,
      "updated_by_id": 1
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/media/1/attachments/1`

#### URL Parameters

_none_

### Associations for an Attachment

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
annotation_drawings | https://api.planningcenteronline.com/services/v2/media/1/attachments/1/annotation_drawings | AnnotationDrawing
attachment_annotations | https://api.planningcenteronline.com/services/v2/media/1/attachments/1/attachment_annotations | AttachmentAnnotation







## AttachmentAnnotations

A set of annotation drawings that make up all annotations a user has added to a PDF in Music Stand.



### List Attachment Annotations

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/media/1/attachments/1/attachment_annotations"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/media/1/attachments/1/attachment_annotations`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[created_at] | _datetime_ | query on a specific created_at
where[updated_at] | _datetime_ | query on a specific updated_at
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Attachment Annotation

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/media/1/attachments/1/attachment_annotations/1"
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

`GET https://api.planningcenteronline.com/services/v2/media/1/attachments/1/attachment_annotations/1`

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

Association | URL | Endpoint
----------- | --- | --------
folders | https://api.planningcenteronline.com/services/v2/folders/1/folders | Folder
service_types | https://api.planningcenteronline.com/services/v2/folders/1/service_types | ServiceType

### Create a new Folder

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Folder","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/folders"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/folders`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Folder","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/folders/1/folders"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/folders/1/folders`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string

### Update an existing Folder

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Folder","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/folders/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/folders/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string

### Delete a Folder

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/folders/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/folders/1`

## Items

An item in a plan.

### Attribute Info

<span class='attribute-info-name'>item_type</span>

There are 4 possible values:

- `song`: The item is a song

- `header`: The item is a header

- `media`: The item is a piece of media

- `item`: The default item type

This value can only be set when an item is created.  The only value that you can pass is `header`.  If no value is passed then `item` will be used.  To create a media item you'll attach a video media to the item, and to create a song item, you'll attach a song.


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
include | media | include associated media
include | arrangement | include associated arrangement
include | key | include associated key
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
      "arrangement_id": 1,
      "key_id": 1,
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
include | media | include associated media
include | arrangement | include associated arrangement
include | key | include associated key

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=item_notes,song</code></aside>

### Associations for an Item

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
arrangement | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/arrangement | Arrangement
attachments | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments | Attachment
item_notes | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes | ItemNote
key | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/key | Key
media | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/media | Media
song | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/song | Song

### Create a new Item

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Item","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items`

#### Resource Attributes

Attribute | Type
--------- | ----
length | integer
description | 
title | string
service_position | 
song_id | integer
key_id | integer
arrangement_id | integer
item_type | 

### Update an existing Item

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Item","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1`

#### Resource Attributes

Attribute | Type
--------- | ----
length | integer
description | 
title | string
service_position | 
song_id | integer
key_id | integer
arrangement_id | integer
media_ids | 

### Delete an Item

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1`

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
where[created_at] | _datetime_ | query on a specific created_at
where[updated_at] | _datetime_ | query on a specific updated_at
where[category_id] | _integer_ | query on a specific category_id
where[category_name] | __ | query on a specific category_name
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







## Keys

Each song arrangement can have multiple keys. A key is the pitch center of the song.

### Attribute Info

<span class='attribute-info-name'>starting_key</span>

Possible Values:

`Ab`, `A`, `A#`, `Bb`, `B`, `C`, `C#`, `Db`, `D`, `D#`, `Eb`, `E`, `F`, `F#`, `Gb`, `G`, `G#`, `Abm`, `Am`, `A#m`, `Bbm`, `Bm`, `Cm`, `C#m`, `Dbm`, `Dm`, `D#m`, `Ebm`, `Em`, `Fm`, `F#m`, `Gbm`, `Gm`, `G#m`


<span class='attribute-info-name'>ending_key</span>

Possible Values:

`Ab`, `A`, `A#`, `Bb`, `B`, `C`, `C#`, `Db`, `D`, `D#`, `Eb`, `E`, `F`, `F#`, `Gb`, `G`, `G#`, `Abm`, `Am`, `A#m`, `Bbm`, `Bm`, `Cm`, `C#m`, `Dbm`, `Dm`, `D#m`, `Ebm`, `Em`, `Fm`, `F#m`, `Gbm`, `Gm`, `G#m`


<span class='attribute-info-name'>alternate_keys</span>

An array of objects.

`
{
  "name": "My Alternate Key",
  "key": "B"
}
`


### List Keys

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Key

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Key",
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

`GET https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys/1`

#### URL Parameters

_none_

### Create a new Key

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Key","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
starting_key | 
ending_key | 
alternate_keys | string

### Update an existing Key

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Key","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
starting_key | 
ending_key | 
alternate_keys | string

### Delete a Key

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys/1`

## Medias

A piece of media

### Attribute Info

<span class='attribute-info-name'>media_type</span>

Possible Values:

- `Audio`

- `Background Audio`

- `Background Image`

- `Background Video`

- `Countdown`

- `Document`

- `Drama`

- `Image`

- `Powerpoint`

- `Song Video`

- `Video`


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
filter | audio | filter using the named scope "audio"
filter | background_audio | filter using the named scope "background_audio"
filter | background_image | filter using the named scope "background_image"
filter | background_video | filter using the named scope "background_video"
filter | countdown | filter using the named scope "countdown"
filter | document | filter using the named scope "document"
filter | drama | filter using the named scope "drama"
filter | image | filter using the named scope "image"
filter | powerpoint | filter using the named scope "powerpoint"
filter | song_video | filter using the named scope "song_video"
filter | video | filter using the named scope "video"
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
      "title": "string",
      "thumbnail_file_name": "string",
      "thumbnail_content_type": "string",
      "thumbnail_file_size": 1,
      "thumbnail_updated_at": "2000-01-01T12:00:00Z",
      "thumbnail_url": "unknown",
      "preview_url": "unknown",
      "preview_file_name": "string",
      "preview_content_type": "string",
      "preview_file_size": 1,
      "preview_updated_at": "2000-01-01T12:00:00Z"
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

Association | URL | Endpoint
----------- | --- | --------
attachments | https://api.planningcenteronline.com/services/v2/medias/1/attachments | Attachment

### Create a new Media

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Media","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/medias"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/medias`

#### Resource Attributes

Attribute | Type | Note
--------- | ---- | ----
media_type | string | Acceptable values are "Audio", "Background Audio", "Background Image", "Background Video", "Countdown", "Document", "Drama", "Image", "Powerpoint", "Song Video", and "Video".
title | string
creator_name | 
themes | string

### Update an existing Media

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Media","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/medias/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/medias/1`

#### Resource Attributes

Attribute | Type | Note
--------- | ---- | ----
media_type | string | Acceptable values are "Audio", "Background Audio", "Background Image", "Background Video", "Countdown", "Document", "Drama", "Image", "Powerpoint", "Song Video", and "Video".
title | string
creator_name | 
themes | string

### Delete a Media

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/medias/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/medias/1`

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

Association | URL | Endpoint
----------- | --- | --------
team | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1/team | Team
time | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1/time | PlanTime







## Organizations

The root level of an organization where account-level settings are applied.

### Attribute Info

<span class='attribute-info-name'>date_format</span>

Two possible values, `US` `EU`

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

Association | URL | Endpoint
----------- | --- | --------
folders | https://api.planningcenteronline.com/services/v2/folders | Folder
media | https://api.planningcenteronline.com/services/v2/media | Media
people | https://api.planningcenteronline.com/services/v2/people | Person
series | https://api.planningcenteronline.com/services/v2/series | Series
service_types | https://api.planningcenteronline.com/services/v2/service_types | ServiceType
songs | https://api.planningcenteronline.com/services/v2/songs | Song
tag_groups | https://api.planningcenteronline.com/services/v2/tag_groups | TagGroup







## People

A person added to PCO Services.

### Attribute Info

<span class='attribute-info-name'>legacy_id</span>

If you've used Person.id from API v1 this attribute can be used to map from those old IDs to the new IDs used in API v2

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
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

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
      "legacy_id": "unknown",
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

_none_

### Associations for a Person

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
activities | https://api.planningcenteronline.com/services/v2/people/1/activities | Activity
person_team_position_assignments | https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments | PersonTeamPositionAssignment
plan_people | https://api.planningcenteronline.com/services/v2/people/1/plan_people | PlanPerson
schedules | https://api.planningcenteronline.com/services/v2/people/1/schedules | Schedule
tags | https://api.planningcenteronline.com/services/v2/people/1/tags | Tag
team_leaders | https://api.planningcenteronline.com/services/v2/people/1/team_leaders | TeamLeader







## PersonTeamPositionAssignments

A person's assignment to a position within a team.

### Attribute Info

<span class='attribute-info-name'>schedule_preference</span>

Possible Values:
  "Every week"
  "Every other week"
  "Every 3rd week"
  "Every 4th week"
  "Every 5th week"
  "Every 6th week"
  "Once a month"
  "Twice a month"
  "Three times a month"
  "Choose Weeks"


<span class='attribute-info-name'>preferred_weeks</span>

When `schedule_preference` is set to "Choose Weeks" then this
indicates which weeks are preferred (checked).

e.g. ['1', '3', '5'] to prefer odd numbered weeks.


<span class='attribute-info-name'>time_preference_option_ids</span>

Indicates which Time Preference Options are preferred (checked).

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
      "person_id": 1,
      "schedule_preference": "unknown",
      "preferred_weeks": "unknown",
      "time_preference_option_ids": "unknown",
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

### Create a new Person Team Position Assignment

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"PersonTeamPositionAssignment","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/teams/1/team_positions/1/person_team_position_assignments"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/service_types/1/teams/1/team_positions/1/person_team_position_assignments`

#### Resource Attributes

Attribute | Type
--------- | ----
schedule_preference | 
preferred_weeks | 
time_preference_option_ids | 
person_id | integer

### Update an existing Person Team Position Assignment

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"PersonTeamPositionAssignment","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments/1`

#### Resource Attributes

Attribute | Type
--------- | ----
schedule_preference | 
preferred_weeks | 
time_preference_option_ids | 

### Delete a Person Team Position Assignment

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments/1`

## Plans

A single plan within a Service Type.

### Attribute Info

<span class='attribute-info-name'>attachment_type_ids</span>

The attachment type IDs assigned to the current user based on what positions they are scheduled to in this plan. This determines what files they can see.

<span class='attribute-info-name'>files_expire_at</span>

A date 1 month after the last service time.

<span class='attribute-info-name'>items_count</span>

The total number of items, including regular items, songs, media, and headers, that the current user can see in the plan.

<span class='attribute-info-name'>next_plan_id</span>

The ID of the next chronological plan within the current Service Type.

<span class='attribute-info-name'>previous_plan_id</span>

The ID of the previous chronological plan within the current Service Type.

<span class='attribute-info-name'>permissions</span>

The current user's permissions for this plan's Service Type.

<span class='attribute-info-name'>total_length</span>

The total of length of all items, excluding pre-service and post-service items.

<span class='attribute-info-name'>short_dates</span>

The shortened date string representing all Service Time dates. Months are abbreviated, and the year is omitted.

<span class='attribute-info-name'>sort_date</span>

A time representing the chronological first Service Time, used to sort plan chronologically. If no Service Times exist, it uses Rehearsal Times, then Other Times, then NOW.

<span class='attribute-info-name'>starts_at</span>

A time representing the chronological last Time (Service, Rehearsal, or Other). Once this passes, a plan is considered to be in the past.

<span class='attribute-info-name'>dates</span>

The full date string representing all Service Time dates.

<span class='attribute-info-name'>public</span>

True if Public Access has been enabled.

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
where[last_time_at] | __ | query on a specific last_time_at
where[title] | _string_ | query on a specific title
filter | future | filter using the named scope "future"
filter | past | filter using the named scope "past"
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
      "attachments_count": "unknown",
      "series_title": "string"
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

Association | URL | Endpoint
----------- | --- | --------
attachments | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/attachments | Attachment
items | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items | Item
needed_positions | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions | NeededPosition
next_plan | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/next_plan | Plan
notes | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes | PlanNote
plan_times | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/plan_times | PlanTime
previous_plan | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/previous_plan | Plan
series | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/series | Series
team_member | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/team_member | PlanPerson

### Create a new Plan

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Plan","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/plans"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/service_types/1/plans`

#### Resource Attributes

Attribute | Type
--------- | ----
title | string
public | boolean
series_id | integer

### Update an existing Plan

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Plan","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/service_types/1/plans/1`

#### Resource Attributes

Attribute | Type
--------- | ----
title | string
public | boolean
series_id | integer

### Delete a Plan

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/service_types/1/plans/1`

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
where[created_at] | _datetime_ | query on a specific created_at
where[updated_at] | _datetime_ | query on a specific updated_at
where[category_name] | __ | query on a specific category_name
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

Association | URL | Endpoint
----------- | --- | --------
plan_note_category | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes/1/plan_note_category | PlanNoteCategory







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

### Attribute Info

<span class='attribute-info-name'>can_accept_partial</span>

If the person is scheduled to a split team where they could potentially accept 1 time and decline another.

<span class='attribute-info-name'>excluded_times</span>

Scheduled people are assigned to all service, rehearsal, and other times, unless you exclude them. Exclude any times the person is not assigned to for that plan.

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
      "team_position_name": "unknown",
      "status": "string",
      "status_updated_at": "unknown",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "plan_id": "unknown",
      "service_type_id": "unknown",
      "person_id": 1,
      "prepare_notification": "unknown",
      "photo_thumbnail": "unknown",
      "name": "unknown",
      "notes": "string",
      "decline_reason": "string",
      "can_accept_partial": "unknown",
      "responds_to_id": "unknown",
      "excluded_time_ids": "unknown"
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

Association | URL | Endpoint
----------- | --- | --------
person | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/person | Person
plan | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan | Plan
plan_times | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times | PlanTime
team | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/team | Team







## PlanTimes

A time in a plan.

### Attribute Info

<span class='attribute-info-name'>starts_at</span>

Planned start time.

<span class='attribute-info-name'>ends_at</span>

Planned end time.

<span class='attribute-info-name'>live_starts_at</span>

Start time as recorded by Services LIVE.

<span class='attribute-info-name'>live_ends_at</span>

End time as recorded by Services LIVE.

<span class='attribute-info-name'>team_reminders</span>

A Hash that maps a Team ID to a reminder value. If nothing is specified, no reminder is set for that team. A reminder value is an integer (0-7) equal to the number of days before the selected time a reminder should be sent.

<span class='attribute-info-name'>included_category_ids</span>

The IDs of each Team assigned to this time.

<span class='attribute-info-name'>time_type</span>

There are 3 possible 'time_type' values:

- Service

- Rehearsal

- Other


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

Association | URL | Endpoint
----------- | --- | --------
split_team_rehearsal_assignments | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times/1/split_team_rehearsal_assignments | SplitTeamRehearsalAssignment







## Schedules

An instance of a PlanPerson with included data for displaying in a user's schedule



### List Schedules

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/schedules"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/schedules`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Schedule

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/schedules/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Schedule",
    "id": "1",
    "attributes": {
      "plan_person_id": "unknown",
      "status": "string",
      "plan_id": "unknown",
      "sort_date": "unknown",
      "service_type_id": "unknown",
      "service_type_name": "unknown",
      "person_id": 1,
      "person_name": "unknown",
      "team_name": "unknown",
      "team_position_name": "unknown",
      "short_dates": "unknown",
      "organization_id": "unknown",
      "organization_name": "unknown",
      "excluded_time_ids": "unknown",
      "can_accept_partial": "unknown"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/schedules/1`

#### URL Parameters

_none_







## Series

A Series can be specified for each plan to tie plans with similar messages together, even across Service Types.

*Note*: A series is not created until artwork is added from the plan.  You can use `series_title` included in `Plan` attributes to get titles for series without artwork.




### List Series

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/series"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/series`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Series

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/series/1"
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

`GET https://api.planningcenteronline.com/services/v2/series/1`

#### URL Parameters

_none_

### Associations for a Series

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
plans | https://api.planningcenteronline.com/services/v2/series/1/plans | Plan

### Create a new Series

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Series","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/series"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/series`

#### Resource Attributes

_none_

### Update an existing Series

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Series","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/series/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/series/1`

#### Resource Attributes

_none_

### Delete a Series

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/series/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/series/1`

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

Association | URL | Endpoint
----------- | --- | --------
plan_note_categories | https://api.planningcenteronline.com/services/v2/service_types/1/plan_note_categories | PlanNoteCategory
plans | https://api.planningcenteronline.com/services/v2/service_types/1/plans | Plan
teams | https://api.planningcenteronline.com/services/v2/service_types/1/teams | Team
time_preference_options | https://api.planningcenteronline.com/services/v2/service_types/1/time_preference_options | TimePreferenceOption

### Create a new Service Type

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"ServiceType","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/service_types`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
sequence | integer

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"ServiceType","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/folders/1/service_types"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/folders/1/service_types`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
sequence | integer

### Update an existing Service Type

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"ServiceType","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/service_types/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
sequence | integer

### Delete a Service Type

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/service_types/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/service_types/1`

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
where[title] | _string_ | query on a specific title
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

Association | URL | Endpoint
----------- | --- | --------
arrangements | https://api.planningcenteronline.com/services/v2/songs/1/arrangements | Arrangement

### Create a new Song

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Song","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/songs"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/songs`

#### Resource Attributes

Attribute | Type
--------- | ----
title | string
admin | string
author | string
copyright | string
ccli_number | 
hidden | boolean
themes | string

### Update an existing Song

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Song","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/songs/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/songs/1`

#### Resource Attributes

Attribute | Type
--------- | ----
title | string
admin | string
author | string
copyright | string
ccli_number | 
hidden | boolean
themes | string

### Delete a Song

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/songs/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/songs/1`

## SplitTeamRehearsalAssignments

For Rehearsal/Other Times, maps a Split Team to selected Time Preference Options. For example, used to assign 8am Ushers to 7:30 call time, and 11am Ushers to 10:30 call time.

### Attribute Info

<span class='attribute-info-name'>assigned_to</span>

Either 'team' or 'time_preferences'

<span class='attribute-info-name'>time_preference_ids</span>

The IDs of the assigned time preference options.

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

Association | URL | Endpoint
----------- | --- | --------
team | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times/1/split_team_rehearsal_assignments/1/team | Team







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

### Attribute Info

<span class='attribute-info-name'>tags_for</span>

Scopes a tag group to `person`, `song`, `arrangement`, `media`

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
where[name] | _string_ | query on a specific name
filter | song | filter using the named scope "song"
filter | arrangement | filter using the named scope "arrangement"
filter | person | filter using the named scope "person"
filter | media | filter using the named scope "media"
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

Association | URL | Endpoint
----------- | --- | --------
tags | https://api.planningcenteronline.com/services/v2/tag_groups/1/tags | Tag







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
      "sequence": 1,
      "schedule_to": "string",
      "assigned_directly": "unknown",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
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

Association | URL | Endpoint
----------- | --- | --------
plan_people | https://api.planningcenteronline.com/services/v2/service_types/1/teams/1/plan_people | PlanPerson
team_positions | https://api.planningcenteronline.com/services/v2/service_types/1/teams/1/team_positions | TeamPosition







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
      "send_responses_for_declines": true,
      "send_responses_for_blockouts": true
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

### Attribute Info

<span class='attribute-info-name'>negative_tag_groups</span>

If the Team is assigned via tags, these are Tags where the option "None" is specified.

<span class='attribute-info-name'>tag_groups</span>

If the Team is assigned via tags, these are Tags where the option "Any" is specified.

<span class='attribute-info-name'>tags</span>

If the Team is assigned via tags, these are specific Tags that are specified.

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

### Associations for a Team Position

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
person_team_position_assignments | https://api.planningcenteronline.com/services/v2/service_types/1/teams/1/team_positions/1/person_team_position_assignments | PersonTeamPositionAssignment







## TimePreferenceOptions

A Service Time a person prefers to be scheduled to.

### Attribute Info

<span class='attribute-info-name'>minute_of_day</span>

0 for 12:00 am, 1 for 12:01 am, 100 for 1:00 am, through 2359 for 11:59pm

### List Time Preference Options

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/time_preference_options"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/time_preference_options`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
after | _id_ | get page after the specified id
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Time Preference Option

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/time_preference_options/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "TimePreferenceOption",
    "id": "1",
    "attributes": {
      "day_of_week": 1,
      "minute_of_day": "unknown",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/time_preference_options/1`

#### URL Parameters

_none_





