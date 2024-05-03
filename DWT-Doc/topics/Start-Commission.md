# Start Commission

## Request

### Url

`/api/Commission/SaaS`

### Method

`PUT`

### Request Parameters

#### URL Parameters

`None`

#### Query Parameters

`None`

#### Body Parameters

| Parameter Name      | Type   | Description                     |
|---------------------|--------|---------------------------------|
| locationId          | string | The uuid of the location        |
| cameraId            | string | The uuid of the camera          |
| cargoId             | string | The uuid of the cargo           |
| commissionTimestamp | string | The timestamp of the commission |

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
  "data": null
}
```

#### Error Response

```json
{
  "status": 404,
  "message": "Location not found"
}
```