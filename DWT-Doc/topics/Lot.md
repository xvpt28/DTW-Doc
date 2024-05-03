# Lot

## Description

Store information about the Lot.

## Database

### Table

`required`

### Columns

| Name          | Type   | Description              | Foreign Key |
|---------------|--------|--------------------------|-------------|
| id            | UUID   | Primary Key of the lot.  | No          |
| lotName       | string | The sku of the lot       | NO          |
| financier     | string | The name of the lot      | No          |
| quantity      | int    | The quantity of the lot  | No          |
| quantityUnit  | string | The unit of the lot      | No          |
| numberOfCargo | int    | The number of cargo      | No          |
| blId          | string | The BL number of the lot | Yes         |
