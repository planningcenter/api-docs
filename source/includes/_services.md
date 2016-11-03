# PCO Services (BETA)

Schedule your teams, manage your music, and revolutionize the way you plan your worship services.

## AnnotationDrawings

A single pen stroke, highlighter stroke, or text annotation a user has added to a PDF in Music Stand.



### List Annotation Drawings

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/attachments/1/annotation_drawings"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/attachments/1/annotation_drawings`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Annotation Drawing

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/attachments/1/annotation_drawings/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "AnnotationDrawing",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/attachments/1/annotation_drawings/1`

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


### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
updated_by | Person | _false_ | 
created_by | Person | _false_ | 
song | Song | _false_ | 

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
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "bpm": 1.42,
      "chord_chart": "string",
      "chord_chart_columns": 1,
      "chord_chart_font": "string",
      "chord_chart_font_size": 1,
      "chord_chart_key": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "has_chord_chart": true,
      "has_chords": true,
      "length": 1,
      "meter": "string",
      "name": "string",
      "notes": "string",
      "sequence": "string",
      "sequence_short": [

      ],
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "created_by": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "song": {
        "data": {
          "type": "Song",
          "id": "123"
        }
      },
      "updated_by": {
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

`GET https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1`

#### URL Parameters

_none_

### Associations for an Arrangement

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
attachments | https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/attachments | Attachment
keys | https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys | Key
tags | https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/tags | Tag

### Actions for an Arrangement

You can perform the following actions on an Arrangement by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
assign_tags | https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/assign_tags | Used to assign tags to an arrangement.

#### assign_tags

All tags will be replaced so the full data set must be sent.

It expects a body that looks like:

```json
{
	"data": {
		"type": "TagAssignment",
		"attributes": {},
		"relationships": {
			"tags": {
				"data": [
					{
						"type": "Tag",
						"id": "5"
					}
				]
			}
		}
	}
}
```

On success you will get back a `204 No Content`.


### Create a new Arrangement

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Arrangement","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/songs/1/arrangements"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/songs/1/arrangements`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
bpm | float
length | integer
meter | string
notes | string
chord_chart | string
chord_chart_font | string
chord_chart_key | string
chord_chart_columns | integer
chord_chart_font_size | integer

### Update an existing Arrangement

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Arrangement","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string
bpm | float
length | integer
meter | string
notes | string
chord_chart | string
chord_chart_font | string
chord_chart_key | string
chord_chart_columns | integer
chord_chart_font_size | integer

### Delete an Arrangement

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1`

## Attachments

A file, whether it's stored on Planning Center or linked from another location.



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
attachable | Plan | _false_ | 
attachment_types | AttachmentType | _true_ | 
created_by | Person | _false_ | 
updated_by | Person | _false_ | 

### List Attachments

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/attachments"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/attachments`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Attachment

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/attachments/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Attachment",
    "id": "primary_key",
    "attributes": {
      "allow_mp3_download": true,
      "content_type": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "downloadable": true,
      "file_size": 1,
      "filename": "string",
      "linked_url": "string",
      "page_order": "string",
      "pco_type": "string",
      "remote_link": "string",
      "streamable": true,
      "transposable": true,
      "updated_at": "2000-01-01T12:00:00Z",
      "url": "string",
      "web_streamable": true
    },
    "relationships": {
      "attachable": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "attachment_types": {
        "data": [
          {
            "type": "AttachmentType",
            "id": "123"
          }
        ]
      },
      "created_by": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "updated_by": {
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

`GET https://api.planningcenteronline.com/services/v2/songs/1/attachments/1`

#### URL Parameters

_none_

### Associations for an Attachment

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
annotation_drawings | https://api.planningcenteronline.com/services/v2/songs/1/attachments/1/annotation_drawings | AnnotationDrawing
attachment_annotations | https://api.planningcenteronline.com/services/v2/songs/1/attachments/1/attachment_annotations | AttachmentAnnotation

### Actions for an Attachment

You can perform the following actions on an Attachment by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
 |  | 
 |  | 
open | https://api.planningcenteronline.com/services/v2/songs/1/attachments/1/open | This action is used to get the attachment file URL.  It is accessed by `POST`ing to `.../attachments/1/open`

This will generate the URL and return it in the `attachment_url` attribute of the `AttachmentActivity`.








### Create a new Attachment

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Attachment","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/songs/1/attachments"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/songs/1/attachments`

#### Resource Attributes

Attribute | Type
--------- | ----
filename | string
remote_link | string

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Attachment","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/attachments"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/attachments`

#### Resource Attributes

Attribute | Type
--------- | ----
filename | string
remote_link | string

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Attachment","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys/1/attachments"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys/1/attachments`

#### Resource Attributes

Attribute | Type
--------- | ----
filename | string
remote_link | string

### Update an existing Attachment

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Attachment","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/songs/1/attachments/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/songs/1/attachments/1`

#### Resource Attributes

Attribute | Type
--------- | ----
filename | string
remote_link | string

### Delete an Attachment

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/songs/1/attachments/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/songs/1/attachments/1`

## AttachmentActivities

Returned from the `open` attachment action.



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
attachment | Attachment | _false_ | 

### List Attachment Activities

#### HTTP Request

`GET `

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)







## AttachmentAnnotations

A set of annotation drawings that make up all annotations a user has added to a PDF in Music Stand.



### List Attachment Annotations

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/attachments/1/attachment_annotations"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/attachments/1/attachment_annotations`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Attachment Annotation

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/attachments/1/attachment_annotations/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "AttachmentAnnotation",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z",
      "user_name": "string"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/attachments/1/attachment_annotations/1`

#### URL Parameters

_none_







## AttachmentTypes

Create an Attachment Type for each type of file you might want only specific people to see. When you attach a file, you can specify an attachment type to then be able to link the file to a position.



### List Attachment Types

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/attachment_types"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/attachment_types`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Attachment Type

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/attachment_types/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "AttachmentType",
    "id": "primary_key",
    "attributes": {
      "aliases": "string",
      "capoed_chord_charts": true,
      "chord_charts": true,
      "lyrics": true,
      "name": "string",
      "number_charts": true,
      "numeral_charts": true
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/attachment_types/1`

#### URL Parameters

_none_







## AvailableSignups

Signups that are available.



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
organization | Organization | _false_ | 
person | Person | _false_ | 
service_type | ServiceType | _false_ | 

### List Available Signups

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/available_signups"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/available_signups`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Available Signup

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/available_signups/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "AvailableSignup",
    "id": "primary_key",
    "attributes": {
      "organization_name": "string",
      "service_type_name": "string",
      "signups_available": true
    },
    "relationships": {
      "organization": {
        "data": {
          "type": "Organization",
          "id": "123"
        }
      },
      "person": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "service_type": {
        "data": {
          "type": "ServiceType",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/available_signups/1`

#### URL Parameters

_none_

### Associations for an Available Signup

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
signup_sheets | https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets | SignupSheet







## Blockouts

An object representing a blockout date, and an optional recurrence pattern

### Attribute Info

<span class='attribute-info-name'>repeat_frequency</span>

Possible values:

- no_repeat

- every_1

- every_2

- every_3

- every_4

- every_5

- every_6

- every_7

- every_8

<span class='attribute-info-name'>repeat_interval</span>

Possible values:

- exact_day_of_month

- week_of_month_1

- week_of_month_2

- week_of_month_3

- week_of_month_4

- week_of_month_last

<span class='attribute-info-name'>repeat_period</span>

Possible values:

- daily

- weekly

- monthly

- yearly

### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
person | Person | _false_ | 
organization | Organization | _false_ | 

### List Blockouts

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/blockouts"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/blockouts`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Blockout

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/blockouts/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Blockout",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "description": "string",
      "ends_at": "2000-01-01T12:00:00Z",
      "reason": "string",
      "repeat_frequency": "string",
      "repeat_interval": "string",
      "repeat_period": "string",
      "repeat_until": "2000-01-01",
      "settings": "string",
      "share": true,
      "starts_at": "2000-01-01T12:00:00Z",
      "time_zone": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "organization": {
        "data": {
          "type": "Organization",
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

`GET https://api.planningcenteronline.com/services/v2/people/1/blockouts/1`

#### URL Parameters

_none_

### Associations for a Blockout

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
blockout_dates | https://api.planningcenteronline.com/services/v2/people/1/blockouts/1/blockout_dates | BlockoutDate
blockout_exceptions | https://api.planningcenteronline.com/services/v2/people/1/blockouts/1/blockout_exceptions | BlockoutException

### Create a new Blockout

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Blockout","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/people/1/blockouts"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/people/1/blockouts`

#### Resource Attributes

Attribute | Type
--------- | ----
reason | string
repeat_frequency | string
repeat_interval | string
repeat_period | string
share | boolean
repeat_until | date
starts_at | date_time
ends_at | date_time

### Update an existing Blockout

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Blockout","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/people/1/blockouts/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/people/1/blockouts/1`

#### Resource Attributes

Attribute | Type
--------- | ----
reason | string
repeat_frequency | string
repeat_interval | string
repeat_period | string
share | boolean
repeat_until | date
starts_at | date_time
ends_at | date_time

### Delete a Blockout

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/people/1/blockouts/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/people/1/blockouts/1`

## BlockoutDates

The actual dates generated by the blockout or its recurrence pattern. Generated up to a year in advance



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
person | Person | _false_ | 
blockout | Blockout | _false_ | 

### List Blockout Dates

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/blockouts/1/blockout_dates"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/blockouts/1/blockout_dates`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Blockout Date

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/blockouts/1/blockout_dates/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "BlockoutDate",
    "id": "primary_key",
    "attributes": {
      "ends_at": "2000-01-01T12:00:00Z",
      "reason": "string",
      "share": true,
      "starts_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "blockout": {
        "data": {
          "type": "Blockout",
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

`GET https://api.planningcenteronline.com/services/v2/people/1/blockouts/1/blockout_dates/1`

#### URL Parameters

_none_







## BlockoutExceptions

A single exception for the dates generated from the blockout



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
blockout | Blockout | _false_ | 

### List Blockout Exceptions

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/blockouts/1/blockout_exceptions"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/blockouts/1/blockout_exceptions`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Blockout Exception

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/blockouts/1/blockout_exceptions/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "BlockoutException",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "date": "2000-01-01",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "blockout": {
        "data": {
          "type": "Blockout",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/blockouts/1/blockout_exceptions/1`

#### URL Parameters

_none_

### Create a new Blockout Exception

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"BlockoutException","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/people/1/blockouts/1/blockout_exceptions"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/people/1/blockouts/1/blockout_exceptions`

#### Resource Attributes

Attribute | Type
--------- | ----
date | date





## CheckIns



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
plan_time | PlanTime | _false_ | 
plan | Plan | _false_ | 
plan_person | PlanPerson | _false_ | 

### List Check Ins

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/check_ins"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/check_ins`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Check In

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/check_ins/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "CheckIn",
    "id": "primary_key",
    "attributes": {
      "check_ins_event_id": "primary_key",
      "check_ins_event_period_id": "primary_key",
      "checked_in_at": "time"
    },
    "relationships": {
      "plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "plan_person": {
        "data": {
          "type": "PlanPerson",
          "id": "123"
        }
      },
      "plan_time": {
        "data": {
          "type": "PlanTime",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/check_ins/1`

#### URL Parameters

_none_







## Contributors

A Contributor Resource



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
plan | Plan | _false_ | 
person | Person | _false_ | 

### List Contributors

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/contributors"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/contributors`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Contributor

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/contributors/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Contributor",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "full_name": "string",
      "photo_thumbnail_url": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "person": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/contributors/1`

#### URL Parameters

_none_







## EmailTemplates

A EmailTemplate Resource

### Attribute Info

<span class='attribute-info-name'>template_owner</span>

Who owns the template.  Will either be a Person or Organization.  System supplied templates will be null.

### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
template_owner | Organization | _false_ | 

### List Email Templates

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/email_templates"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/email_templates`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Email Template

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/email_templates/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "EmailTemplate",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "html_body": "string",
      "kind": "string",
      "subject": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "template_owner": {
        "data": {
          "type": "Organization",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/email_templates/1`

#### URL Parameters

_none_

### Actions for an Email Template

You can perform the following actions on an Email Template by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
render | https://api.planningcenteronline.com/services/v2/email_templates/1/render | Render an email template and fill in the persons details

#### render

Render the template with information from the person.

```json
{
  "data": {
    "attributes": {
      "format": "html|text"
    },
    "relationships": {
      "person": {
        "data": {
          "type": "Person",
          "id": "1"
        }
      }
    }
  }
}
```


### Create a new Email Template

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"EmailTemplate","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/email_templates"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/email_templates`

#### Resource Attributes

Attribute | Type
--------- | ----
html_body | string
subject | string
kind | string

### Update an existing Email Template

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"EmailTemplate","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/email_templates/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/email_templates/1`

#### Resource Attributes

Attribute | Type
--------- | ----
html_body | string
subject | string

### Delete an Email Template

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/email_templates/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/email_templates/1`

## EmailTemplateRenderedResponses

A EmailTemplateRenderedResponse Resource



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
person | Person | _false_ | 
email_template | EmailTemplate | _false_ | 

### List Email Template Rendered Responses

#### HTTP Request

`GET `

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)







## Folders

A folder is a container used to organize multiple Service Types or other Folders.



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
parent | Folder | _false_ | 

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
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "container": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "parent": {
        "data": {
          "type": "Folder",
          "id": "123"
        }
      }
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
curl -v -u token:secret -X POST -d '{"data":{"type":"Folder","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/service_types`

#### Resource Attributes

Attribute | Type
--------- | ----
name | string

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Folder","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/folders/1/service_types"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/folders/1/service_types`

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


### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
plan | Plan | _false_ | 
song | Song | _false_ | 
arrangement | Arrangement | _false_ | 
key | Key | _false_ | 

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
include | item_times | include associated item_times
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "description": "string",
      "html_details": "string",
      "item_type": "string",
      "length": 1,
      "sequence": 1,
      "service_position": "string",
      "title": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "arrangement": {
        "data": {
          "type": "Arrangement",
          "id": "123"
        }
      },
      "key": {
        "data": {
          "type": "Key",
          "id": "123"
        }
      },
      "plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "song": {
        "data": {
          "type": "Song",
          "id": "123"
        }
      }
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
include | item_times | include associated item_times

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=item_notes,song</code></aside>

### Associations for an Item

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
arrangement | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/arrangement | Arrangement
attachments | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/attachments | Attachment
item_notes | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes | ItemNote
item_times | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_times | ItemTime
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
description | string
title | string
service_position | string
item_type | string

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
description | string
title | string
service_position | string

### Delete an Item

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1`

## ItemNotes

A plan item note that belongs to a category.

Note: You can only assign the category on create.  If you want to change category; delete the current note, and create a new one passing in the `category_id` then.




### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
item_note_category | ItemNoteCategory | _false_ | 

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
include | item_note_category | include associated item_note_category
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "category_name": "string",
      "content": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "item_note_category": {
        "data": {
          "type": "ItemNoteCategory",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | item_note_category | include associated item_note_category

### Associations for an Item Note

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
item_note_category | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes/1/item_note_category | ItemNoteCategory

### Create a new Item Note

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"ItemNote","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes`

#### Resource Attributes

Attribute | Type
--------- | ----
content | string

### Update an existing Item Note

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"ItemNote","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes/1`

#### Resource Attributes

Attribute | Type
--------- | ----
content | string

### Delete an Item Note

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_notes/1`

## ItemNoteCategories

A category of plan item notes for an entire Service Type.



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
service_type | ServiceType | _false_ | 

### List Item Note Categories

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/item_note_categories"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/item_note_categories`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Item Note Category

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/item_note_categories/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ItemNoteCategory",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "sequence": 1,
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "service_type": {
        "data": {
          "type": "ServiceType",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/item_note_categories/1`

#### URL Parameters

_none_







## ItemTimes



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
item | Item | _false_ | 
plan_time | PlanTime | _false_ | 
plan | Plan | _false_ | 

### List Item Times

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_times"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_times`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Item Time

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_times/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ItemTime",
    "id": "primary_key",
    "attributes": {
      "exclude": true,
      "length_offset": 1,
      "live_end_at": "2000-01-01T12:00:00Z",
      "live_start_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "item": {
        "data": {
          "type": "Item",
          "id": "123"
        }
      },
      "plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "plan_time": {
        "data": {
          "type": "PlanTime",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items/1/item_times/1`

#### URL Parameters

_none_







## Keys

Each song arrangement can have multiple keys. A key is the pitch center of the song.

### Attribute Info

<span class='attribute-info-name'>starting_key</span>

Possible Values:

`Ab`, `A`, `A#`, `Bb`, `B`, `C`, `C#`, `Db`, `D`, `D#`, `Eb`, `E`, `F`, `F#`, `Gb`, `G`, `G#`, `Abm`, `Am`, `A#m`, `Bbm`, `Bm`, `Cm`, `C#m`, `Dbm`, `Dm`, `D#m`, `Ebm`, `Em`, `Fm`, `F#m`, `Gbm`, `Gm`, `G#m`

To set the key to minor append `m` to the key. e.g. `Cm`


<span class='attribute-info-name'>ending_key</span>

Possible Values:

`Ab`, `A`, `A#`, `Bb`, `B`, `C`, `C#`, `Db`, `D`, `D#`, `Eb`, `E`, `F`, `F#`, `Gb`, `G`, `G#`, `Abm`, `Am`, `A#m`, `Bbm`, `Bm`, `Cm`, `C#m`, `Dbm`, `Dm`, `D#m`, `Ebm`, `Em`, `Fm`, `F#m`, `Gbm`, `Gm`, `G#m`

To set the key to minor append `m` to the key. e.g. `Cm`


<span class='attribute-info-name'>alternate_keys</span>

An array of objects.

`
{
  "name": "My Alternate Key",
  "key": "B"
}
`


### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
arrangement | Arrangement | _false_ | 

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
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "alternate_keys": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "ending_key": "string",
      "ending_minor": true,
      "name": "string",
      "starting_key": "string",
      "starting_minor": true,
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "arrangement": {
        "data": {
          "type": "Arrangement",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys/1`

#### URL Parameters

_none_

### Associations for a Key

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
attachments | https://api.planningcenteronline.com/services/v2/songs/1/arrangements/1/keys/1/attachments | Attachment

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
starting_key | string
ending_key | string
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
starting_key | string
ending_key | string
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
include | attachments | include associated attachments
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "creator_name": "string",
      "image_url": "string",
      "length": 1,
      "media_type": "string",
      "media_type_name": "string",
      "preview_content_type": "string",
      "preview_file_name": "string",
      "preview_file_size": 1,
      "preview_updated_at": "2000-01-01T12:00:00Z",
      "preview_url": "string",
      "themes": "string",
      "thumbnail_content_type": "string",
      "thumbnail_file_name": "string",
      "thumbnail_file_size": 1,
      "thumbnail_updated_at": "2000-01-01T12:00:00Z",
      "thumbnail_url": "string",
      "title": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/medias/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | attachments | include associated attachments

### Associations for a Media

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
attachments | https://api.planningcenteronline.com/services/v2/medias/1/attachments | Attachment
media_schedules | https://api.planningcenteronline.com/services/v2/medias/1/media_schedules | MediaSchedule
tags | https://api.planningcenteronline.com/services/v2/medias/1/tags | Tag

### Actions for a Media

You can perform the following actions on a Media by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
assign_tags | https://api.planningcenteronline.com/services/v2/medias/1/assign_tags | Used to assign tags to a media.

#### assign_tags

All tags will be replaced so the full data set must be sent.

It expects a body that looks like:

```json
{
	"data": {
		"type": "TagAssignment",
		"attributes": {},
		"relationships": {
			"tags": {
				"data": [
					{
						"type": "Tag",
						"id": "5"
					}
				]
			}
		}
	}
}
```

On success you will get back a `204 No Content`.


### Create a new Media

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"Media","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/medias"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/medias`

#### Resource Attributes

Attribute | Type
--------- | ----
media_type | string
title | string
creator_name | string
themes | string

### Update an existing Media

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Media","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/medias/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/medias/1`

#### Resource Attributes

Attribute | Type
--------- | ----
media_type | string
title | string
creator_name | string
themes | string

### Delete a Media

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/medias/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/medias/1`

## MediaSchedules



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
plan | Plan | _false_ | 
service_type | ServiceType | _false_ | 

### List Media Schedules

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/media/1/media_schedules"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/media/1/media_schedules`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Media Schedule

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/media/1/media_schedules/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "MediaSchedule",
    "id": "primary_key",
    "attributes": {
      "plan_dates": "string",
      "plan_short_dates": "string",
      "plan_sort_date": "2000-01-01T12:00:00Z",
      "service_type_name": "string"
    },
    "relationships": {
      "plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "service_type": {
        "data": {
          "type": "ServiceType",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/media/1/media_schedules/1`

#### URL Parameters

_none_







## NeededPositions

An amount of unfilled positions needed within a team in a plan.



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
team | Team | _false_ | 
time | PlanTime | _false_ | 
plan | Plan | _false_ | 

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
include | team | include associated team
include | time | include associated time
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=team,time</code></aside>

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
    "id": "primary_key",
    "attributes": {
      "quantity": 1,
      "scheduled_to": "string",
      "team_position_name": "string"
    },
    "relationships": {
      "plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "team": {
        "data": {
          "type": "Team",
          "id": "123"
        }
      },
      "time": {
        "data": {
          "type": "PlanTime",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | team | include associated team
include | time | include associated time

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=team,time</code></aside>

### Associations for a Needed Position

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
team | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1/team | Team
time | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1/time | PlanTime

### Create a new Needed Position

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"NeededPosition","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions`

#### Resource Attributes

Attribute | Type
--------- | ----
quantity | integer

### Update an existing Needed Position

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"NeededPosition","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1`

#### Resource Attributes

Attribute | Type
--------- | ----
quantity | integer

### Delete a Needed Position

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions/1`

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
    "id": "primary_key",
    "attributes": {
      "beta": true,
      "ccli": "string",
      "ccli_connected": true,
      "created_at": "2000-01-01T12:00:00Z",
      "date_format": 1,
      "legacy_id": "primary_key",
      "music_stand_enabled": true,
      "name": "string",
      "owner_name": "string",
      "projector_enabled": true,
      "secret": "string",
      "time_zone": "string",
      "twenty_four_hour_time": true,
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
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
attachment_types | https://api.planningcenteronline.com/services/v2/attachment_types | AttachmentType
 |  | 
email_templates | https://api.planningcenteronline.com/services/v2/email_templates | EmailTemplate
folders | https://api.planningcenteronline.com/services/v2/folders | Folder
media | https://api.planningcenteronline.com/services/v2/media | Media
people | https://api.planningcenteronline.com/services/v2/people | Person
 |  | 
 |  | 
series | https://api.planningcenteronline.com/services/v2/series | Series
service_types | https://api.planningcenteronline.com/services/v2/service_types | ServiceType
songs | https://api.planningcenteronline.com/services/v2/songs | Song
tag_groups | https://api.planningcenteronline.com/services/v2/tag_groups | TagGroup
 |  | 

### Actions for an Organization

You can perform the following actions on an Organization by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
 |  | 









## People

A person added to PCO Services.

### Attribute Info

<span class='attribute-info-name'>legacy_id</span>

If you've used Person.id from API v1 this attribute can be used to map from those old IDs to the new IDs used in API v2

### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
created_by | Person | _false_ | 
updated_by | Person | _false_ | 

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
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "anniversary": "2000-01-01T12:00:00Z",
      "birthdate": "2000-01-01T12:00:00Z",
      "created_at": "2000-01-01T12:00:00Z",
      "facebook_id": 1,
      "first_name": "string",
      "ical_code": "string",
      "last_name": "string",
      "legacy_id": "primary_key",
      "logged_in_at": "2000-01-01T12:00:00Z",
      "max_permissions": "string",
      "me_tab": "string",
      "media_tab": "string",
      "middle_name": "string",
      "notes": "string",
      "people_tab": "string",
      "permissions": "string",
      "photo_thumbnail_url": "string",
      "photo_url": "string",
      "plans_tab": "string",
      "site_administrator": true,
      "songs_tab": "string",
      "status": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "created_by": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "updated_by": {
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

`GET https://api.planningcenteronline.com/services/v2/people/1`

#### URL Parameters

_none_

### Associations for a Person

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
 |  | 
available_signups | https://api.planningcenteronline.com/services/v2/people/1/available_signups | AvailableSignup
blockouts | https://api.planningcenteronline.com/services/v2/people/1/blockouts | Blockout
person_team_position_assignments | https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments | PersonTeamPositionAssignment
plan_people | https://api.planningcenteronline.com/services/v2/people/1/plan_people | PlanPerson
schedules | https://api.planningcenteronline.com/services/v2/people/1/schedules | Schedule
tags | https://api.planningcenteronline.com/services/v2/people/1/tags | Tag
team_leaders | https://api.planningcenteronline.com/services/v2/people/1/team_leaders | TeamLeader
 |  | 
text_settings | https://api.planningcenteronline.com/services/v2/people/1/text_settings | TextSetting

### Actions for a Person

You can perform the following actions on a Person by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
assign_tags | https://api.planningcenteronline.com/services/v2/people/1/assign_tags | Used to assign tags to a person.
 |  | 
 |  | 
 |  | 

#### assign_tags

All tags will be replaced so the full data set must be sent.

It expects a body that looks like:

```json
{
	"data": {
		"type": "TagAssignment",
		"attributes": {},
		"relationships": {
			"tags": {
				"data": [
					{
						"type": "Tag",
						"id": "5"
					}
				]
			}
		}
	}
}
```

On success you will get back a `204 No Content`.










### Update an existing Person

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"Person","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/people/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/people/1`

#### Resource Attributes

Attribute | Type
--------- | ----
permissions | string



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

### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
person | Person | _false_ | 
time_preference_options | TimePreferenceOption | _true_ | 

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
include | person | include associated person
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "preferred_weeks": [

      ],
      "schedule_preference": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "person": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "time_preference_options": {
        "data": [
          {
            "type": "TimePreferenceOption",
            "id": "123"
          }
        ]
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | person | include associated person

### Associations for a Person Team Position Assignment

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
person | https://api.planningcenteronline.com/services/v2/people/1/person_team_position_assignments/1/person | Person

### Create a new Person Team Position Assignment

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"PersonTeamPositionAssignment","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/people/1/teams/1/team_positions/1/person_team_position_assignments"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/people/1/teams/1/team_positions/1/person_team_position_assignments`

#### Resource Attributes

Attribute | Type
--------- | ----
schedule_preference | string
preferred_weeks | array

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
schedule_preference | string
preferred_weeks | array



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

### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
service_type | ServiceType | _false_ | 
next_plan | Plan | _false_ | 
previous_plan | Plan | _false_ | 
attachment_types | AttachmentType | _true_ | 
series | Series | _false_ | 

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
where[title] | _string_ | query on a specific title
filter | future | filter using the named scope "future"
filter | past | filter using the named scope "past"
include | series | include associated series
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "dates": "string",
      "files_expire_at": "2000-01-01T12:00:00Z",
      "items_count": 1,
      "last_time_at": "2000-01-01T12:00:00Z",
      "multi_day": true,
      "needed_positions_count": 1,
      "other_time_count": 1,
      "permissions": "string",
      "plan_notes_count": 1,
      "plan_people_count": 1,
      "public": true,
      "rehearsal_time_count": 1,
      "series_title": "string",
      "service_time_count": 1,
      "short_dates": "string",
      "sort_date": "2000-01-01T12:00:00Z",
      "title": "string",
      "total_length": 1,
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "attachment_types": {
        "data": [
          {
            "type": "AttachmentType",
            "id": "123"
          }
        ]
      },
      "next_plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "previous_plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "series": {
        "data": {
          "type": "Series",
          "id": "123"
        }
      },
      "service_type": {
        "data": {
          "type": "ServiceType",
          "id": "123"
        }
      }
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
all_attachments | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/all_attachments | Attachment
attachments | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/attachments | Attachment
contributors | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/contributors | Contributor
items | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/items | Item
needed_positions | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/needed_positions | NeededPosition
next_plan | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/next_plan | Plan
notes | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes | PlanNote
plan_times | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/plan_times | PlanTime
previous_plan | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/previous_plan | Plan
series | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/series | Series
team_members | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/team_members | PlanPerson

### Actions for a Plan

You can perform the following actions on a Plan by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
item_reorder | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/item_reorder | Reorder plan items in one request.
 |  | 
 |  | 
 |  | 

#### item_reorder

This can be used to reorder all items in a plan in one request.

It expects a `POST` body with a `sequence` of `Item` ids in order.  E.G.

```json
{
  "data": {
    "type": "PlanItemReorder",
    "attributes": {
      "sequence": [
        "5",
        "1",
        "3"
      ]
    }
  }
}
```

On success you will get back a `204 No Content`.








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

### Delete a Plan

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/service_types/1/plans/1`

## PlanNotes

A specific plan note within a single plan.



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
plan_note_category | PlanNoteCategory | _false_ | 

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
where[created_at] | _date_time_ | query on a specific created_at
where[updated_at] | _date_time_ | query on a specific updated_at
include | plan_note_category | include associated plan_note_category
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "category_name": "string",
      "content": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "plan_note_category": {
        "data": {
          "type": "PlanNoteCategory",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | plan_note_category | include associated plan_note_category

### Associations for a Plan Note

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
plan_note_category | https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes/1/plan_note_category | PlanNoteCategory

### Create a new Plan Note

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"PlanNote","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes`

#### Resource Attributes

Attribute | Type
--------- | ----
content | string

### Update an existing Plan Note

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"PlanNote","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes/1`

#### Resource Attributes

Attribute | Type
--------- | ----
content | string

### Delete a Plan Note

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/notes/1`

## PlanNoteCategories

A category of plan notes for an entire Service Type.



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
service_type | ServiceType | _false_ | 

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
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "sequence": 1,
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "service_type": {
        "data": {
          "type": "ServiceType",
          "id": "123"
        }
      }
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

### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
person | Person | _false_ | 
plan | Plan | _false_ | 
service_type | ServiceType | _false_ | 
team | Team | _false_ | 
responds_to | Person | _false_ | 
times | PlanTime | _true_ | 

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
include | declined_plan_times | include associated declined_plan_times
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "can_accept_partial": true,
      "created_at": "2000-01-01T12:00:00Z",
      "decline_reason": "string",
      "name": "string",
      "notes": "string",
      "notification_sent_at": "2000-01-01T12:00:00Z",
      "photo_thumbnail": "string",
      "prepare_notification": true,
      "status": "string",
      "status_updated_at": "2000-01-01T12:00:00Z",
      "team_position_name": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "person": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "responds_to": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "service_type": {
        "data": {
          "type": "ServiceType",
          "id": "123"
        }
      },
      "team": {
        "data": {
          "type": "Team",
          "id": "123"
        }
      },
      "times": {
        "data": [
          {
            "type": "PlanTime",
            "id": "123"
          }
        ]
      }
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
include | declined_plan_times | include associated declined_plan_times

<aside class='info'>You can specify multiple includes with a comma, e.g. <code>?include=team,person</code></aside>

### Associations for a Plan Person

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
check_ins | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/check_ins | CheckIn
declined_plan_times | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times | PlanTime
person | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/person | Person
plan | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan | Plan
plan_person_times | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_person_times | PlanPersonTime
plan_times | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_times | PlanTime
team | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/team | Team

### Actions for a Plan Person

You can perform the following actions on a Plan Person by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
 |  | 



### Create a new Plan Person

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"PlanPerson","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/team_members"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/team_members`

#### Resource Attributes

Attribute | Type
--------- | ----
status | string
decline_reason | string
notes | string
team_position_name | string
prepare_notification | boolean

### Update an existing Plan Person

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"PlanPerson","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/people/1/plan_people/1`

#### Resource Attributes

Attribute | Type
--------- | ----
status | string
decline_reason | string
notes | string
team_position_name | string
prepare_notification | boolean

### Delete a Plan Person

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/people/1/plan_people/1`

## PlanPersonTimes



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
plan_time | PlanTime | _false_ | 
plan | Plan | _false_ | 
plan_person | PlanPerson | _false_ | 

### List Plan Person Times

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_person_times"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_person_times`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Plan Person Time

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_person_times/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "PlanPersonTime",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "status": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "plan_person": {
        "data": {
          "type": "PlanPerson",
          "id": "123"
        }
      },
      "plan_time": {
        "data": {
          "type": "PlanTime",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/plan_person_times/1`

#### URL Parameters

_none_







## PlanTemplates

A PlanTemplate Resource



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
service_type | ServiceType | _false_ | 
created_by | Person | _false_ | 
updated_by | Person | _false_ | 

### List Plan Templates

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plan_templates"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plan_templates`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Plan Template

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/service_types/1/plan_templates/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "PlanTemplate",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "created_by": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "service_type": {
        "data": {
          "type": "ServiceType",
          "id": "123"
        }
      },
      "updated_by": {
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

`GET https://api.planningcenteronline.com/services/v2/service_types/1/plan_templates/1`

#### URL Parameters

_none_







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

Possible values are:

- rehearsal

- service

- other


### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
assigned_teams | Team | _true_ | 

### List Plan Times

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | split_team_rehearsal_assignments | include associated split_team_rehearsal_assignments
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Plan Time

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "PlanTime",
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "ends_at": "2000-01-01T12:00:00Z",
      "live_ends_at": "2000-01-01T12:00:00Z",
      "live_starts_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "starts_at": "2000-01-01T12:00:00Z",
      "team_reminders": [

      ],
      "time_type": 1,
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "assigned_teams": {
        "data": [
          {
            "type": "Team",
            "id": "123"
          }
        ]
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | split_team_rehearsal_assignments | include associated split_team_rehearsal_assignments

### Associations for a Plan Time

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
split_team_rehearsal_assignments | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1/split_team_rehearsal_assignments | SplitTeamRehearsalAssignment

### Create a new Plan Time

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"PlanTime","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/plan_times"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/service_types/1/plans/1/plan_times`

#### Resource Attributes

Attribute | Type
--------- | ----
starts_at | date_time
ends_at | date_time
name | string
time_type | integer
team_reminders | array

### Update an existing Plan Time

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"PlanTime","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1`

#### Resource Attributes

Attribute | Type
--------- | ----
starts_at | date_time
ends_at | date_time
name | string
time_type | integer
team_reminders | array

### Delete a Plan Time

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1`

## Schedules

An instance of a PlanPerson with included data for displaying in a user's schedule



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
person | Person | _false_ | 
service_type | ServiceType | _false_ | 
organization | Organization | _false_ | 
plan_person | PlanPerson | _false_ | 
plan | Plan | _false_ | 
responds_to_person | Person | _false_ | 
times | PlanTime | _true_ | 

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
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "can_accept_partial": true,
      "dates": "string",
      "decline_reason": "string",
      "organization_name": "string",
      "organization_time_zone": "string",
      "person_name": "string",
      "position_display_times": "string",
      "service_type_name": "string",
      "short_dates": "string",
      "sort_date": "2000-01-01T12:00:00Z",
      "status": "string",
      "team_name": "string",
      "team_position_name": "string"
    },
    "relationships": {
      "organization": {
        "data": {
          "type": "Organization",
          "id": "123"
        }
      },
      "person": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "plan_person": {
        "data": {
          "type": "PlanPerson",
          "id": "123"
        }
      },
      "responds_to_person": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "service_type": {
        "data": {
          "type": "ServiceType",
          "id": "123"
        }
      },
      "times": {
        "data": [
          {
            "type": "PlanTime",
            "id": "123"
          }
        ]
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/schedules/1`

#### URL Parameters

_none_

### Associations for a Schedule

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
declined_plan_times | https://api.planningcenteronline.com/services/v2/people/1/schedules/1/declined_plan_times | PlanTime
plan_times | https://api.planningcenteronline.com/services/v2/people/1/schedules/1/plan_times | PlanTime
respond_to | https://api.planningcenteronline.com/services/v2/people/1/schedules/1/respond_to | Person
team | https://api.planningcenteronline.com/services/v2/people/1/schedules/1/team | Team

### Actions for a Schedule

You can perform the following actions on a Schedule by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
accept | https://api.planningcenteronline.com/services/v2/people/1/schedules/1/accept | Accept a Schedule
decline | https://api.planningcenteronline.com/services/v2/people/1/schedules/1/decline | Decline a Schedule

#### accept

If this isn't a split time schedule, or you want to accept all times, an empty JSON body is accepted.

If the user wants to decline specific times you'll need to send the declined time IDs & a reason.

A POST body should be formated...

```json
{
	"data": {
		"type": "ScheduleAccept",
		"attributes": {
			"reason": "Because reasons"
		},
		"relationships": {
			"declined_plan_times": {
				"data": [
          {
					  "type": "PlanTime",
					  "id": "1"
				  }
        ]
			}
		}
	}
}
```


#### decline

If this is a split time request, all times will be declined.

If you want to decline specific times see ScheduleAcceptAction.

A POST body should be formated...

```json
{
	"data": {
		"type": "ScheduleDecline",
		"attributes": {
			"reason": "A user supplied reason for declining the request or an empty string."
		},
		"relationships": null
	}
}
```








## ScheduledPeople

A person already scheduled to a SignupSheet



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
person | Person | _false_ | 
signup_sheet | SignupSheet | _false_ | 

### List Scheduled People

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets/1/scheduled_people"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets/1/scheduled_people`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Scheduled Person

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets/1/scheduled_people/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "ScheduledPerson",
    "id": "primary_key",
    "attributes": {
      "full_name": "string",
      "status": "string",
      "thumbnail": "string"
    },
    "relationships": {
      "person": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "signup_sheet": {
        "data": {
          "type": "SignupSheet",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets/1/scheduled_people/1`

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
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "artwork_content_type": "string",
      "artwork_file_name": "string",
      "artwork_file_size": 1,
      "artwork_for_dashboard": "string",
      "artwork_for_mobile": "string",
      "artwork_for_plan": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "title": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
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







## ServiceTypes

A Service Type is a container for plans.



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
parent | Folder | _false_ | 

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
include | time_preference_options | include associated time_preference_options
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "attachment_types_enabled": true,
      "created_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "permissions": "string",
      "sequence": 1,
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "parent": {
        "data": {
          "type": "Folder",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | time_preference_options | include associated time_preference_options

### Associations for a Service Type

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
attachments | https://api.planningcenteronline.com/services/v2/service_types/1/attachments | Attachment
item_note_categories | https://api.planningcenteronline.com/services/v2/service_types/1/item_note_categories | ItemNoteCategory
plan_note_categories | https://api.planningcenteronline.com/services/v2/service_types/1/plan_note_categories | PlanNoteCategory
plan_templates | https://api.planningcenteronline.com/services/v2/service_types/1/plan_templates | PlanTemplate
plans | https://api.planningcenteronline.com/services/v2/service_types/1/plans | Plan
teams | https://api.planningcenteronline.com/services/v2/service_types/1/teams | Team
time_preference_options | https://api.planningcenteronline.com/services/v2/service_types/1/time_preference_options | TimePreferenceOption

### Actions for a Service Type

You can perform the following actions on a Service Type by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
create_plans | https://api.planningcenteronline.com/services/v2/service_types/1/create_plans | Create multiple plans
 |  | 

#### create_plans

This action provides the abillity to create multiple plans with a single API request.

Accepted attributes:

- `count` (Integer) The number of plans to create. (max 10, default 1)

- `copy_items` (Boolean) Copy Items from another plan. (default false)

- `copy_people` (Boolean) Copy People from another plan. (default false)

- `copy_notes` (Boolean) Copy Notes from another plan. (default false)

- `as_template` (Boolean) Create the new plans as templates (default false)

- `base_date` (ISO 8601 Date) The date to start buiding the plans from. (default false)

Accepted Relationships

- `plan` The plan to copy items, people and notes from.  (These items will only be copied if you supply a valid plan relationship)




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

## SignupSheets

Available positions to sign up for



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
plan | Plan | _false_ | 
team_position | TeamPosition | _false_ | 
team | Team | _false_ | 

### List Signup Sheets

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | scheduled_people | include associated scheduled_people
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Signup Sheet

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "SignupSheet",
    "id": "primary_key",
    "attributes": {
      "display_times": "string",
      "group_key": "string",
      "position_name": "string",
      "sort_date": "2000-01-01T12:00:00Z",
      "sort_index": 1,
      "team_name": "string",
      "title": "string"
    },
    "relationships": {
      "plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "team": {
        "data": {
          "type": "Team",
          "id": "123"
        }
      },
      "team_position": {
        "data": {
          "type": "TeamPosition",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | scheduled_people | include associated scheduled_people

### Associations for a Signup Sheet

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
scheduled_people | https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets/1/scheduled_people | ScheduledPerson
signup_sheet_metadata | https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets/1/signup_sheet_metadata | SignupSheetMetadata

### Actions for a Signup Sheet

You can perform the following actions on a Signup Sheet by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
accept | https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets/1/accept | Accept a signup sheet









## SignupSheetMetadata

A SignupSheetMetadata Resource



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
plan_time | PlanTime | _false_ | 

### List Signup Sheet Metadata

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets/1/signup_sheet_metadata"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/available_signups/1/signup_sheets/1/signup_sheet_metadata`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)







## SkippedAttachments

a skipped attachment



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
person | Person | _false_ | 
attachment | Attachment | _false_ | 

### List Skipped Attachments

#### HTTP Request

`GET `

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Skipped Attachment

> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "SkippedAttachment",
    "id": "primary_key",
    "attributes": {
      "skipped": true
    },
    "relationships": {
      "attachment": {
        "data": {
          "type": "Attachment",
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

`GET `

#### URL Parameters

_none_







## Songs

A song

### Attribute Info

<span class='attribute-info-name'>title</span>

The name of the song.

When setting this value on a create you can pass a CCLI number and Services will fetch the song metadata for you.


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
where[author] | _string_ | query on a specific author
where[hidden] | _boolean_ | query on a specific hidden
where[themes] | _string_ | query on a specific themes
where[title] | _string_ | query on a specific title
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "admin": "string",
      "author": "string",
      "ccli_number": 1,
      "copyright": "string",
      "created_at": "2000-01-01T12:00:00Z",
      "hidden": true,
      "themes": "string",
      "title": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
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
attachments | https://api.planningcenteronline.com/services/v2/songs/1/attachments | Attachment
song_schedules | https://api.planningcenteronline.com/services/v2/songs/1/song_schedules | SongSchedule
tags | https://api.planningcenteronline.com/services/v2/songs/1/tags | Tag

### Actions for a Song

You can perform the following actions on a Song by POSTing to the specified URL.

Action | URL | Description
------ | --- | -----------
assign_tags | https://api.planningcenteronline.com/services/v2/songs/1/assign_tags | Used to assign tags to a song.

#### assign_tags

All tags will be replaced so the full data set must be sent.

It expects a body that looks like:

```json
{
	"data": {
		"type": "TagAssignment",
		"attributes": {},
		"relationships": {
			"tags": {
				"data": [
					{
						"type": "Tag",
						"id": "5"
					}
				]
			}
		}
	}
}
```

On success you will get back a `204 No Content`.


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
ccli_number | integer
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
ccli_number | integer
hidden | boolean
themes | string

### Delete a Song

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/songs/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/songs/1`

## SongSchedules

A upcoming schedule for a song



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
arrangement | Arrangement | _false_ | 
key | Key | _false_ | 
plan | Plan | _false_ | 
service_type | ServiceType | _false_ | 
item | Item | _false_ | 

### List Song Schedules

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/song_schedules"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/song_schedules`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Song Schedule

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/songs/1/song_schedules/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "SongSchedule",
    "id": "primary_key",
    "attributes": {
      "arrangement_name": "string",
      "key_name": "string",
      "plan_dates": "string",
      "plan_sort_date": "string",
      "service_type_name": "string"
    },
    "relationships": {
      "arrangement": {
        "data": {
          "type": "Arrangement",
          "id": "123"
        }
      },
      "item": {
        "data": {
          "type": "Item",
          "id": "123"
        }
      },
      "key": {
        "data": {
          "type": "Key",
          "id": "123"
        }
      },
      "plan": {
        "data": {
          "type": "Plan",
          "id": "123"
        }
      },
      "service_type": {
        "data": {
          "type": "ServiceType",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/songs/1/song_schedules/1`

#### URL Parameters

_none_







## SplitTeamRehearsalAssignments

For Rehearsal/Other Times, maps a Split Team to selected Time Preference Options. For example, used to assign 8am Ushers to 7:30 call time, and 11am Ushers to 10:30 call time.

### Attribute Info

<span class='attribute-info-name'>assigned_to</span>

Either 'team' or 'time_preferences'

<span class='attribute-info-name'>time_preference_ids</span>

The IDs of the assigned time preference options.

### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
team | Team | _false_ | 
time_preference_options | TimePreferenceOption | _true_ | 

### List Split Team Rehearsal Assignments

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1/split_team_rehearsal_assignments"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1/split_team_rehearsal_assignments`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Split Team Rehearsal Assignment

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1/split_team_rehearsal_assignments/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "SplitTeamRehearsalAssignment",
    "id": "primary_key",
    "attributes": {
      "assigned_to": "string"
    },
    "relationships": {
      "team": {
        "data": {
          "type": "Team",
          "id": "123"
        }
      },
      "time_preference_options": {
        "data": [
          {
            "type": "TimePreferenceOption",
            "id": "123"
          }
        ]
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1/split_team_rehearsal_assignments/1`

#### URL Parameters

_none_

### Associations for a Split Team Rehearsal Assignment

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
team | https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1/split_team_rehearsal_assignments/1/team | Team

### Create a new Split Team Rehearsal Assignment

```shell
# to create a record...
curl -v -u token:secret -X POST -d '{"data":{"type":"SplitTeamRehearsalAssignment","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1/split_team_rehearsal_assignments"
```


#### HTTP Request

`POST https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1/split_team_rehearsal_assignments`

#### Resource Attributes

Attribute | Type
--------- | ----
assigned_to | string

### Update an existing Split Team Rehearsal Assignment

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"SplitTeamRehearsalAssignment","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1/split_team_rehearsal_assignments/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1/split_team_rehearsal_assignments/1`

#### Resource Attributes

Attribute | Type
--------- | ----
assigned_to | string

### Delete a Split Team Rehearsal Assignment

```shell
# to delete a record...
curl -v -u token:secret -X DELETE "https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1/split_team_rehearsal_assignments/1"
```


#### HTTP Request

`DELETE https://api.planningcenteronline.com/services/v2/people/1/plan_people/1/declined_plan_times/1/split_team_rehearsal_assignments/1`

## Tags

A tag belonging to a tag group.



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
tag_group | TagGroup | _false_ | 

### List Tags

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/tag_groups/1/tags"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/tag_groups/1/tags`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Tag

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/tag_groups/1/tags/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Tag",
    "id": "primary_key",
    "attributes": {
      "name": "string"
    },
    "relationships": {
      "tag_group": {
        "data": {
          "type": "TagGroup",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/tag_groups/1/tags/1`

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
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "allow_multiple_selections": true,
      "name": "string",
      "required": true,
      "service_type_folder_name": "string",
      "tags_for": "string"
    },
    "relationships": {
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



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
service_type | ServiceType | _false_ | 

### List Teams

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/teams"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/teams`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | team_positions | include associated team_positions
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Team

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/teams/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "Team",
    "id": "primary_key",
    "attributes": {
      "assigned_directly": true,
      "created_at": "2000-01-01T12:00:00Z",
      "name": "string",
      "schedule_to": "string",
      "sequence": 1,
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
      "service_type": {
        "data": {
          "type": "ServiceType",
          "id": "123"
        }
      }
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/teams/1`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
include | team_positions | include associated team_positions

### Associations for a Team

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
plan_people | https://api.planningcenteronline.com/services/v2/people/1/teams/1/plan_people | PlanPerson
team_leaders | https://api.planningcenteronline.com/services/v2/people/1/teams/1/team_leaders | TeamLeader
team_positions | https://api.planningcenteronline.com/services/v2/people/1/teams/1/team_positions | TeamPosition







## TeamLeaders

A leader of a specific Team in a Service Type.



### Relationships


Name | Type | To Many | Description
---- | ---- | ------- | -----------
person | Person | _false_ | 
team | Team | _false_ | 

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
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "send_responses_for_accepts": true,
      "send_responses_for_blockouts": true,
      "send_responses_for_declines": true
    },
    "relationships": {
      "person": {
        "data": {
          "type": "Person",
          "id": "123"
        }
      },
      "team": {
        "data": {
          "type": "Team",
          "id": "123"
        }
      }
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
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/teams/1/team_positions"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/teams/1/team_positions`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Team Position

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/teams/1/team_positions/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "TeamPosition",
    "id": "primary_key",
    "attributes": {
      "name": "string",
      "negative_tag_groups": [

      ],
      "tag_groups": [

      ],
      "tags": [

      ]
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/teams/1/team_positions/1`

#### URL Parameters

_none_

### Associations for a Team Position

You can append one of the following associations onto this resource URL to jump to an associated record.

Association | URL | Endpoint
----------- | --- | --------
person_team_position_assignments | https://api.planningcenteronline.com/services/v2/people/1/teams/1/team_positions/1/person_team_position_assignments | PersonTeamPositionAssignment







## TextSettings



### List Text Settings

```shell
# to list records...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/text_settings"
```


#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/text_settings`

#### URL Parameters

Parameter | Value | Description
--------- | ----- | -----------
offset | _integer_ | get results from given offset
per_page | _integer_ | how many records to return per page (min=1, max=100, default=25)

### Get a single Text Setting

```shell
# to show...
curl -v -u token:secret "https://api.planningcenteronline.com/services/v2/people/1/text_settings/1"
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "type": "TextSetting",
    "id": "primary_key",
    "attributes": {
      "carrier": "string",
      "display_number": "string",
      "general_emails_enabled": true,
      "normalized_number": "string",
      "reminders_enabled": true,
      "scheduling_replies_enabled": true,
      "scheduling_requests_enabled": true
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/people/1/text_settings/1`

#### URL Parameters

_none_



### Update an existing Text Setting

```shell
# to update a record...
curl -v -u token:secret -X PATCH -d '{"data":{"type":"TextSetting","id":"1","attributes":{...}}}' "https://api.planningcenteronline.com/services/v2/people/1/text_settings/1"
```


#### HTTP Request

`PATCH https://api.planningcenteronline.com/services/v2/people/1/text_settings/1`

#### Resource Attributes

Attribute | Type
--------- | ----
general_emails_enabled | boolean
reminders_enabled | boolean
scheduling_replies_enabled | boolean
scheduling_requests_enabled | boolean



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
offset | _integer_ | get results from given offset
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
    "id": "primary_key",
    "attributes": {
      "created_at": "2000-01-01T12:00:00Z",
      "day_of_week": 1,
      "description": "string",
      "minute_of_day": 1,
      "sort_index": "string",
      "updated_at": "2000-01-01T12:00:00Z"
    },
    "relationships": {
    }
  }
}
```

#### HTTP Request

`GET https://api.planningcenteronline.com/services/v2/service_types/1/time_preference_options/1`

#### URL Parameters

_none_





