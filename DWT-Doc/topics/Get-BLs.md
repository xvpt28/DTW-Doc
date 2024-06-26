# Get BLs (Priority: 1)

## Request

### Url

`/api/bl/v1`

### Method

`GET`

### Request Parameters

#### URL Parameters

`None`

#### Query Parameters

| Parameter Name | Type   | Description | required | default |
|----------------|--------|-------------|----------|---------|
| location       | string | location    | yes      |         |
| search         | string | search      | no       | ""      |
| page           | int    | page number | no       | 0       |
| size           | int    | limit       | no       | 10      |
| sort           | string | sort        | no       | "sku"   |
| order          | string | order       | no       | "asc"   |
| filter         | obj    | filter      | no       | null    |

example:

```json
{
  "location": "Zone 10",
  "search": "zone",
  "page": 1,
  "size": 10,
  "sort": "name",
  "order": "asc",
  "filter": {
    "location": "cb521f04-0489-4fa0-befd-99ceb2c29801",
    "supplier": "Supplier-001",
    "name": "Coco"
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

| Parameter Name | Type   | Description                          |
|----------------|--------|--------------------------------------|
| id             | uuid   | primary key of bl                    |
| sku            | string | sku                                  |
| name           | string | name                                 |
| supplier       | string | supplier                             |
| quantity       | int    | quantity                             |
| quantityUnit   | string | quantity unit                        |
| planInfo       | array  | Get all plans from Plan DB           |
| lotInfo        | array  | Get all lots from Lot DB             |
| cargoInfo      | array  | Get all cargos from Cargo DB         |
| operationInfo  | array  | Get all operations from Operation DB |

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
        "blNumber": "BL-001",
        "sku": "SKU-001",
        "name": "Coco",
        "supplier": "Supplier-001",
        "quantity": 100,
        "quantityUnit": "bags",
        "planInfo": [
          {
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
          }
        ],
        "lotInfo": [
          {
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
        ],
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
        "operationInfo": [
          {
            "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
            "timestamp": "1713781182",
            "targetFromDestination": null,
            "targetToDestination": {
              "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
              "name": "Zone 10"
            }
          }
        ]
      }
    ]
  }
}
```

#### Error Response

```json
{
  "status": 404,
  "message": "BL not found"
}
```