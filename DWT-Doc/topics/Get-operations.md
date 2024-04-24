# Get-operations

## Request

### Url

`/api/operation/v1`

### Method

`GET`

### Request Parameters

#### URL Parameters

`None`

#### Query Parameters

| Parameter Name | Type   | Description | required | default     |
|----------------|--------|-------------|----------|-------------|
| search         | string | search      | no       | ""          |
| page           | int    | page number | no       | 0           |
| size           | int    | limit       | no       | 10          |
| sort           | string | sort        | no       | "timestamp" |
| order          | string | order       | no       | "dsc"       |
| filter         | obj    | filter      | no       | null        |

example:

```json
{
  "search": "zone",
  "page": 1,
  "size": 10,
  "sort": "name",
  "order": "asc",
  "filter": {
    "method": "stock-in",
    "startDate": "2020-01-01",
    "endDate": "2020-01-31"
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
    "count": 10,
    "data": [
      {
        "status": 200,
        "message": "Success",
        "data": {
          "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
          "timestamp": "1713781182",
          "destination": {
            "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
            "name": "Zone 10"
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
          },
          "cargoInfo": {
            "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
            "type": "pallet",
            "virtualId": "CAR-001",
            "actualId": "CAR-32315",
            "status": "pending"
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
  "message": "Operation not found"
}
```