# Get Lot (Priority: 1)

## Request

### Url

`/api/lot/v1`

### Method

`GET`

### Request Parameters

#### URL Parameters

`None`

#### Query Parameters

| Parameter Name | Type   | Description | required | default   |
|----------------|--------|-------------|----------|-----------|
| search         | string | search      | no       | ""        |
| page           | int    | page number | no       | 0         |
| size           | int    | limit       | no       | 10        |
| sort           | string | sort        | no       | "lotName" |
| order          | string | order       | no       | "asc"     |
| filter         | obj    | filter      | no       | null      |

example:

```json
{
  "search": "zone",
  "page": 1,
  "size": 10,
  "sort": "name",
  "order": "asc",
  "filter": {
    "location": "cb521f04-0489-4fa0-befd-99ceb2c29801",
    "financier": "OCBC"
  }
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