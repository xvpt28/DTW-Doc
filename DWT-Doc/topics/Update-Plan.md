# Update Plan

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

| Parameter Name        | Type   | Description                        | required |
|-----------------------|--------|------------------------------------|----------|
| method                | string | The method of the plan             | no       |
| targetFromDestination | uuid   | The target destination of the plan | no       |
| targetToDestination   | uuid   | The target destination of the plan | no       |
| targetDate            | string | The target timestamp of the plan   | no       |
| lotId                 | uuid   | The lot id of the plan             | yes      |
| status                | string | The status of the plan             | no       |

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

| Parameter Name        | Type   | Description                           |
|-----------------------|--------|---------------------------------------|
| id                    | UUID   | The id of the plan                    |
| planName              | string | The plan id of the plan               |
| method                | string | The method of the plan                |
| targetFromDestination | obj    | The target destination of the plan    |
| targetToDestination   | obj    | The target destination of the plan    |
| targetDate            | string | The target timestamp of the plan      |
| status                | string | The status of the plan                |
| blInfo                | obj    | The bl information of the plan        |
| lotInfo               | obj    | The lot information of the plan       |
| cargoInfo             | array  | The cargo information of the plan     |
| operationInfo         | obj    | The operation information of the plan |

Example:

```json
{
  "status": 200,
  "message": "Success",
  "data": {
    "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
    "planName": "Plan-001",
    "method": "stock-in",
    "targetFromDestination": null,
    "targetToDestination": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "name": "Zone 10"
    },
    "targetDate": "1713781182",
    "status": "pending",
    "blInfo": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "blNumber": "BL-001",
      "sku": "SKU-001",
      "name": "Coco",
      "supplier": "Supplier-001",
      "quantity": 100,
      "quantityUnit": "bags"
    },
    "lotInfo": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "lotName": "LOT-001",
      "financier": "OCBC",
      "quantity": 100,
      "quantityUnit": "bags",
      "numberOfCargo": {
          "pallet": 50,
          "carton": 10
        }
    },
    "cargoInfo": [
      {
        "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
        "type": "pallet",
        "cargoName": "CAR-001",
        "physicalId": "CAR-32315",
        "status": "pending",
        "commissionId": "cb521f04-0489-4fa0-befd-99ceb2c29803"
      }
    ],
    "operationInfo": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "timestamp": "1713781182",
      "targetFromDestination": null,
      "targetToDestination": {
        "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
        "name": "Zone 10"
      }
    }
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