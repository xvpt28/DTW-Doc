# Get All BLs (Priority: 1)

## Request

### Url

`/api/bl/all/v1`

### Method

`GET`

### Request Parameters

#### URL Parameters

`None`

#### Query Parameters

`None`

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
| sku            | string | sku               |
| name           | string | name              |
| supplier       | string | supplier          |
| quantity       | int    | quantity          |
| quantityUnit   | string | quantity unit     |

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
        "sku": "SKU-001",
        "name": "Coco",
        "supplier": "Supplier-001",
        "quantity": 100,
        "quantityUnit": "bags"
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