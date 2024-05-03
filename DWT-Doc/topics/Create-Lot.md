# Create Lot

## Request

### Url

`/api/lot/v1`

### Method

`POST`

### Request Parameters

#### URL Parameters

`None`

#### Query Parameters

`None`

#### Body Parameters

**Required to auto generate Cargo Info based on number of cargo**

| Parameter Name | Type   | Description     | required |
|----------------|--------|-----------------|----------|
| sku            | string | sku             | yes      |
| name           | string | name            | yes      |
| supplier       | string | supplier        | yes      |
| quantity       | int    | quantity        | yes      |
| quantityUnit   | string | unit            | yes      |
| numberOfCargo  | obj    | number of cargo | no       |
| blId           | string | bl number       | yes      |

```json
{
  "sku": "SKU-001",
  "name": "Coco",
  "supplier": "Supplier-001",
  "quantity": 100,
  "quantityUnit": "bags",
  "numberOfCargo": {
    "pallet": 50,
    "carton": 10
  },
  "blId": "cb521f04-0489-4fa0-befd-99ceb2c29801"
}
```

`None`

## Response

### Success Code

`200 OK`

### Content-Type

`application/json`

### Response Parameters

#### Success Response

| Parameter Name | Type   | Description       |
|----------------|--------|-------------------|
| id             | uuid   | primary key of bl |
| lotName        | string | sku               |
| financier      | string | name              |
| quantity       | int    | quantity          |
| quantityUnit   | string | unit              |
| numberOfCargo  | int    | number of cargo   |
| blInfo         | obj    | bl info           |
| planInfo       | obj    | plan info         |
| cargoInfo      | array  | cargo info        |
| operationInfo  | obj    | operation info    |

Example:

```json
{
  "status": 200,
  "message": "Success",
  "data": {
    "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
    "lotName": "LOT-001",
    "financier": "OCBC",
    "quantity": 100,
    "quantityUnit": "bags",
    "numberOfCargo": {
     "pallet": 50,
     "carton": 50
},
    "commissionId": "cb521f04-0489-4fa0-befd-99ceb2c29803",
    "blInfo": {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "blNumber": "BL-001",
      "sku": "SKU-001",
      "name": "Coco",
      "supplier": "Supplier-001",
      "quantity": 100,
      "quantityUnit": "bags"
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
      "actualFromDestination": null,
      "actualToDestination": {
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
  "message": "Lot not found"
}
```