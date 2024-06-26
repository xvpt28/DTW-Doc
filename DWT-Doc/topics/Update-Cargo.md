# Update Cargo

## Request

### Url

`/api/cargo/v1/:id`

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

| Parameter Name | Type   | Description   | required |
|----------------|--------|---------------|----------|
| physicalId     | string | The actual id | no       |

```json
{
  "physicalId": "CAR-32315"
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
| cargoName      | string | The virtual id            |
| physicalId     | string | The actual id             |
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
    "cargoName": "CAR-001",
    "physicalId": "CAR-32315",
    "status": "pending",
    "commissionId": "cb521f04-0489-4fa0-befd-99ceb2c29803",
    "operationInfo": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "timestamp": "1713781182",
      "actualFromDestination": null,
      "actualToDestination": {
        "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
        "name": "Zone 10"
      }
    },
    "planInfo": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "planName": "Plan-001",
      "method": "stock-in",
      "targetFromDestination": null,
      "targetToDestination": {
        "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
        "name": "Zone 10"
      },
      "targetDate": "1713781182",
      "status": "pending"
    },
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