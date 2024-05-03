# Update operation

## Request

### Url

`/api/operation/v1`

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

| Parameter Name          | Type   | Description                 | required |
|-------------------------|--------|-----------------------------|----------|
| planName                | string | The plan uuid               | no       |
| timestamp               | string | The timestamp of the cargo  | no       |
| actualFromDestinationId | string | The actual id of the source | no       |
| actualToDestination     | string | The destination information | no       |
| physicalId              | string | The actual id of the cargo  | no       |
| cargoName               | string | The virtual id of the cargo | no       |

```json
{
  "planName": "cb521f04-0489-4fa0-befd-99ceb2c29801",
  "timestamp": "1713781182",
  "actualFromDestinationId": null,
  "actualToDestination": "cb521f04-0489-4fa0-befd-99ceb2c29801",
  "physicalId": "CAR-32315",
  "cargoName": "CAR-001"
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
| id             | string | The uuid of the operation   |
| timestamp      | string | The timestamp of the cargo  |
| destination    | obj    | The destination information |
| planInfo       | obj    | The plan information        |
| blInfo         | obj    | The bl information          |
| lotInfo        | obj    | The lot information         |
| cargoInfo      | obj    | The cargo information       |

Example:

```json
{
  "status": 200,
  "message": "Success",
  "data": {
    "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
    "timestamp": "1713781182",
    "actualFromDestination": null,
    "actualToDestination": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "name": "Zone 10"
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
      },
      "commissionId": "cb521f04-0489-4fa0-befd-99ceb2c29803"
    },
    "cargoInfo": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "type": "pallet",
      "cargoName": "CAR-001",
      "physicalId": "CAR-32315",
      "status": "pending",
      "commissionId": "cb521f04-0489-4fa0-befd-99ceb2c29803"
    }
  }
}

```

#### Error Response

```json
{
  "status": 404,
  "message": "Operation not found"
}
```