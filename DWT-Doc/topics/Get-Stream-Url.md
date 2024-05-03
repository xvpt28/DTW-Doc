# Get Stream Url

## Request

### Url

`/api/Commission/hlsStream/:locationId/:cameraId`

### Method

`GET`

### Request Parameters

#### URL Parameters

| Parameter Name | Type   | Description              |
|----------------|--------|--------------------------|
| locationId     | string | The uuid of the location |
| cameraId       | string | The uuid of the camera   |

#### Query Parameters

`None`

#### Body Parameters

`None`

## Response

### Success Code

`200 OK`

### Content-Type

`application/json`

### Response Parameters

#### Success Response

| Parameter Name | Type   | Description               |
|----------------|--------|---------------------------|
| hlsUrl         | string | The hls url of the camera |

Example:

```json
{
  "status": 200,
  "message": "Success",
  "data": [
    {
      "hlsUrl": "http://example.com/hls/stream.m3u8"
    }
  ]
}
```

#### Error Response

```json
{
  "status": 404,
  "message": "Location not found"
}
```