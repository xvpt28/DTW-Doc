# Get Destinations (Priority: 1)

## Request

### Url

`/api/destination/v1`

### Method

`GET`

### Request Parameters

#### URL Parameters

`None`

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

| Parameter Name | Type   | Description                     |
|----------------|--------|---------------------------------|
| id             | string | The uuid of the destination     |
| name           | string | The name of the destination     |
| location       | obj    | The location of the destination |

Example:

```json
{
  "status": 200,
  "message": "Success",
  "data": [
    {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "name": "Zone 10",
      "location": {
        "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
        "name": "WareHouse 1"
      }
    },
    {
      "id": "155af289-5c8a-4da7-91c2-fcf2b25297fe",
      "name": "Zone 10",
      "location": {
        "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
        "name": "WareHouse 1"
      }
    }
  ]
}
```

#### Error Response

```json
{
  "status": 404,
  "message": "Destination not found"
}
```