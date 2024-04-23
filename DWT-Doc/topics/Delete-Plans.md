# Delete-Plans

## Request

### Url

`/api/plan/v1`

### Method

`DELETE`

### Request Parameters

#### URL Parameters

`None`

#### Query Parameters

`None`

#### Body Parameters

| Parameter Name | Type  | Description                      | required |
|----------------|-------|----------------------------------|----------|
| ids            | Array | Lists of uuid need to be deleted | yes      |

Example:

```json
{
  "ids": [
    "cb521f04-0489-4fa0-befd-99ceb2c29801",
    "155af289-5c8a-4da7-91c2-fcf2b25297fe"
  ]
}
```

## Response

### Success Code

`200 OK`

### Content-Type

`application/json`

### Response Parameters

#### Success Response

| Parameter Name | Type   | Description                |
|----------------|--------|----------------------------|
| count          | number | Number of deletion succeed |

Example:

```json
{
  "status": 200,
  "message": "Success",
  "data": {
    "count": 2
  }
}
```

#### Error Response

```json
{
  "status": 404,
  "message": "Plans not found"
}
```