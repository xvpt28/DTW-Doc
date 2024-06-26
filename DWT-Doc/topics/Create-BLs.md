# Create BLs

## Request

### Url

`/api/bl/v1`

### Method

`POST`

### Request Parameters

#### URL Parameters

`None`

#### Query Parameters

`None`

#### Body Parameters

| Parameter Name | Type   | Description            | required |
|----------------|--------|------------------------|----------|
| sku            | string | The sku of the bl      | yes      |
| name           | string | The name of the bl     | yes      |
| supplier       | string | The supplier of the bl | yes      |
| quantity       | int    | The quantity of the bl | yes      |
| quantityUnit   | string | The unit of the bl     | yes      |

```json
{
  "sku": "SKU-001",
  "name": "Coco",
  "supplier": "Supplier-001",
  "quantity": 100,
  "quantityUnit": "bags"
}
```

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
    "id": "cb521f04-0489-4fa0-befd-99ceb2c29801",
    "blNumber": "BL-001",
    "sku": "SKU-001",
    "name": "Coco",
    "supplier": "Supplier-001",
    "quantity": 100,
    "quantityUnit": "bags"
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