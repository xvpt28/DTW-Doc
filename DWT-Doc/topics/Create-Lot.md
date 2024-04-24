# Create-Lot

Create a lot

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

| Parameter Name | Type   | Description         | required |
|----------------|--------|---------------------|----------|
| sku            | string | sku                 | yes      |
| name           | string | name                | yes      |
| supplier       | string | supplier            | yes      |
| quantity       | int    | quantity            | yes      |
| quantityUnit   | string | unit                | yes      |
| numberOfCargo  | int    | number of cargo     | no       |
| blId           | uuid   | foreigner key to BL | yes      |

```json
{
  "sku": "SKU-001",
  "name": "Coco",
  "supplier": "Supplier-001",
  "quantity": 100,
  "quantityUnit": "bags",
  "numberOfCargo": 50,
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
| lotId          | string | sku               |
| financier      | string | name              |
| quantity       | int    | quantity          |
| quantityUnit   | string | unit              |
| blInfo         | obj    | bl info           |
| planInfo       | obj    | plan info         |
| cargoInfo      | array  | cargo info        |
| operationInfo  | obj    | operation info    |

Example:

```json
{
  "status": 200,
  "message": "Success",
  "data": [
    {
      "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
      "lotId": "LOT-001",
      "financier": "OCBC",
      "quantity": 100,
      "quantityUnit": "bags",
      "numberOfCargo": 50,
      "blInfo": {
        "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
        "sku": "SKU-001",
        "name": "Coco",
        "supplier": "Supplier-001",
        "quantity": 100,
        "quantityUnit": "bags"
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
      "cargoInfo": [
        {
          "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
          "type": "pallet",
          "virtualId": "CAR-001",
          "actualId": "CAR-32315",
          "status": "pending"
        }
      ],
      "operationInfo": {
        "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
        "timestamp": "1713781182",
        "destination": {
          "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
          "name": "Zone 10"
        }
      }
    }
  ]
}
```

#### Error Response

```json
{
  "status": 404,
  "message": "Lot not found"
}
```