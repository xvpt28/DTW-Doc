# Update-Plan

## Request

### Url

`/api/plan/v1`

### Method

`PUT`

### Request Parameters

#### URL Parameters

`None`

#### Query Parameters

`None`

#### Body Parameters

| Parameter Name    | Type   | Description                        | required |
|-------------------|--------|------------------------------------|----------|
| method            | string | The method of the plan             | no       |
| targetFrom        | obj    | The target destination of the plan | no       |
| targetDestination | uuid   | The target destination of the plan | no       |
| targetDate        | string | The target timestamp of the plan   | no       |

Example:

```json
{
  "method": "stock-in"
}
```

## Response

### Success Code

`200 OK`

### Content-Type

`application/json`

### Response Parameters

#### Success Response

| Parameter Name    | Type   | Description                        |
|-------------------|--------|------------------------------------|
| id                | UUID   | The id of the plan                 |
| planId            | string | The plan id of the plan            |
| method            | string | The method of the plan             |
| targetFrom        | obj    | The target destination of the plan |
| targetDestination | uuid   | The target destination of the plan |
| targetDate        | string | The target timestamp of the plan   |
| blInfo            | obj    | The bl information of the plan     |
| lotInfo           | obj    | The lot information of the plan    |
| cargoInfo         | array  | The cargo information of the plan  |

Example:

```json
{
  "status": 200,
  "message": "Success",
  "data": {
    "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
    "planId": "Plan-001",
    "method": "stock-in",
    "targetFrom": null,
    "targetDestination": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "name": "Zone 10"
    },
    "targetDate": "1713781182",
    "status": "pending",
    "blInfo": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "sku": "SKU-001",
      "name": "Coco",
      "supplier": "Supplier-001",
      "quantity": 100,
      "quantityUnit": "bags"
    },
    "lotInfo": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "lotId": "LOT-001",
      "financier": "OCBC",
      "quantity": 100,
      "quantityUnit": "bags",
      "numberOfCargo": 50
    },
    "cargoInfo": [
      {
        "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
        "type": "pallet",
        "virtualId": "CAR-001",
        "actualId": "CAR-32315",
        "status": "pending"
      }
    ]
  }
}
```

#### Error Response

```json
{
  "status": 404,
  "message": "Plan not found"
}
```