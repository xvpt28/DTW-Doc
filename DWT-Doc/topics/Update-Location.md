# Update Location

## Request

### Url

`/api/location/v1`

### Method

`PUT`

### Request Parameters

#### URL Parameters

`None`

#### Query Parameters

`None`

#### Body Parameters

| Parameter Name | Type   | Description                 | Required |
|----------------|--------|-----------------------------|----------|
| id             | string | The uuid of the destination | No       |
| name           | string | The name of the destination | No       |
| destinations   | array  | The list of destinations    | No       |

Example:

```json
{
  "name": "Warehouse 1",
  "destinations": [
    "155af289-5c8a-4da7-91c2-fcf2b25297fe",
    "155af289-5c8a-4da7-91c2-fcf2b25297fe"
  ]
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
  "data": {
    "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
    "name": "Warehouse 1",
    "destinations": [
      {
        "id": "155af289-5c8a-4da7-91c2-fcf2b25297fe",
        "name": "Zone 10"
      }
    ],
    "commissionCameras": [
      {
        "commissionCameraName": "string"
      }
    ],
    "totalStockInPlans": {
      "pending": 10,
      "completed": 20
    },
    "totalStockOutPlans": {
      "pending": 10,
      "completed": 20
    },
    "totalStockTransferPlans": {
      "pending": 10,
      "completed": 20
    }
  }
}
```

#### Error Response

```json
{
  "status": 404,
  "message": "Location not found"
}
```