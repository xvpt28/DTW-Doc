# Update-Cargo

## Request

### Url

`/api/cargo/v1`

### Method

`PUT`

### Request Parameters

#### URL Parameters

| Parameter Name | Type   | Description                      | required |
|----------------|--------|----------------------------------|----------|
| id             | string | The uuid that need to be updated | yes      |

#### Query Parameters

`None`

#### Body Parameters

| Parameter Name | Type   | Description           | required |
|----------------|--------|-----------------------|----------|
| type           | string | The type of the cargo | no       |
| actualId       | string | The actual id         | no       |

```json
{
  "type": "pallet",
  "actualId": "CAR-32315"
}
```

## Response

### Success Code

`200 OK`

### Content-Type

`application/json`

### Response Parameters

#### Success Response

| Parameter Name | Type   | Description               |
|----------------|--------|---------------------------|
| id             | string | The uuid of the operation |
| type           | string | The type of the cargo     |
| virtualId      | string | The virtual id            |
| actualId       | string | The actual id             |
| operationInfo  | obj    | The operation information |
| planInfo       | obj    | The plan information      |
| blInfo         | obj    | The bl information        |
| lotInfo        | obj    | The lot information       |

Example:

```json
{
  "status": 200,
  "message": "Success",
  "data": {
    "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
    "type": "pallet",
    "virtualId": "CAR-001",
    "actualId": "CAR-32315",
    "status": "pending",
    "operationInfo": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "timestamp": "1713781182",
      "destination": {
        "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
        "name": "Zone 10"
      }
    },
    "planInfo": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "planId": "Plan-001",
      "method": "stock-in",
      "targetFrom": null,
      "targetDestination": {
        "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
        "name": "Zone 10"
      },
      "targetDate": "1713781182",
      "status": "pending"
    },
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
    }
  }
}

```

#### Error Response

```json
{
  "status": 404,
  "message": "Cargo not found"
}
```