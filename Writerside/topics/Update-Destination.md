# Update Destination

Update a destination

## Request

### Url

`/api/destination/v1`

### Method

`PUT`

### Request Parameters

#### URL Parameters

| Parameter Name | Type   | Description                                  | required |
|----------------|--------|----------------------------------------------|----------|
| id             | string | The destination uuid that need to be updated | yes      |

#### Query Parameters

`None`

#### Body Parameters

| Parameter Name | Type   | Description                 | required |
|----------------|--------|-----------------------------|----------|
| name           | string | The name of the destination | yes      |

Example:

```json
{
  "name": "Zone 10"
}
```

## Response

### Success Code

`200 OK`

### Content-Type

`application/json`

### Response Parameters

#### Success Response

| Parameter Name | Type   | Description                 |
|----------------|--------|-----------------------------|
| id             | string | The uuid of the destination |
| name           | string | The name of the destination |

Example:

```json
{
  "status": 200,
  "message": "Success",
  "data": [
    {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "name": "Zone 10"
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