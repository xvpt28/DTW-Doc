# Get All Lot (Priority: 1)

## Request

### Url

`/api/lot/all/v1`

### Method

`GET`

### Request Parameters

#### URL Parameters

`None`

#### Query Parameters

| Parameter Name | Type   | Description              | required |
|----------------|--------|--------------------------|----------|
| bl             | string | Get all lots based on BL | yes      |

```json
{
  "bl": "cb521f04-0489-4fa0-befd-99ceb2c29801"
}
```

#### Body Parameters

`None`

## Response

### Success Code

`200 OK`

### Content-Type

`application/json`

### Response Parameters

#### Success Response

| Parameter Name | Type        | Description       |
|----------------|-------------|-------------------|
| id             | uuid        | primary key of bl |
| lotName        | string      | sku               |
| financier      | string      | name              |
| quantity       | int         | quantity          |
| quantityUnit   | string      | unit              |
| numberOfCargo  | int         | number of cargo   |
| planInfo       | obj or null | plan info         |

Example:

```json
{
  "status": 200,
  "message": "Success",
  "data": {
    "count": 10,
    "data": [
      {
        "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
        "lotName": "LOT-001",
        "financier": "OCBC",
        "quantity": 100,
        "quantityUnit": "bags",
        "numberOfCargo": {
          "pallet": 50,
          "carton": 10
        },
        "planInfo": {
          "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
          "planName": "Plan-001",
          "method": "stock-in",
          "targetFrom": null,
          "targetDestination": {
            "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
            "name": "Zone 10"
          },
          "targetDate": "1713781182",
          "status": "pending"
        }
      }
    ]
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