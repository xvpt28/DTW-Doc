# Get Plans (Priority: 1)

## Request

### Url

`/api/plan/v1`

### Method

`GET`

### Request Parameters

#### URL Parameters

`None`

#### Query Parameters

| Parameter Name | Type   | Description | required | default      |
|----------------|--------|-------------|----------|--------------|
| search         | string | search      | no       | ""           |
| page           | int    | page number | no       | 0            |
| size           | int    | limit       | no       | 10           |
| sort           | string | sort        | no       | "targetDate" |
| order          | string | order       | no       | "dsc"        |
| filter         | obj    | filter      | no       | null         |

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
    "status": "pending",
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

| Parameter Name    | Type   | Description                           |
|-------------------|--------|---------------------------------------|
| id                | UUID   | The id of the plan                    |
| planName          | string | The plan id of the plan               |
| method            | string | The method of the plan                |
| targetFrom        | obj    | The target destination of the plan    |
| targetDestination | obj    | The target destination of the plan    |
| targetDate        | string | The target timestamp of the plan      |
| status            | string | The status of the plan                |
| blInfo            | obj    | The bl information of the plan        |
| lotInfo           | obj    | The lot information of the plan       |
| cargoInfo         | array  | The cargo information of the plan     |
| operationInfo     | obj    | The operation information of the plan |

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
        "planName": "Plan-001",
        "method": "stock-in",
        "targetFrom": null,
        "targetDestination": {
          "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
          "name": "Zone 10"
        },
        "targetDate": "1713781182",
        "status": "pending",
        "blInfo": {
          "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
          "blId": "BL-001",
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
          "numberOfCargo": 50,
          "commissionId": "cb521f04-0489-4fa0-befd-99ceb2c29803"
        },
        "cargoInfo": [
          {
            "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
            "type": "pallet",
            "cargoName": "CAR-001",
            "physicalId": "CAR-32315",
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
}
```

#### Error Response

```json
{
  "status": 404,
  "message": "Plan not found"
}
```