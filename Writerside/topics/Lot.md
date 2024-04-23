# Lot

## Description

Store information about the Lot.

## Database

### Table

`required`

### Columns

| Name          | Type   | Description             | Foreign Key |
|---------------|--------|-------------------------|-------------|
| id            | UUID   | Primary Key of the lot. | No          |
| lotId         | string | The sku of the lot      | NO          |
| financier     | string | The name of the lot     | No          |
| quantity      | int    | The quantity of the lot | No          |
| quantityUnit  | string | The unit of the lot     | No          |
| blId          | UUID   | Foreign Key to BL       | Yes         |
| numberOfCargo | int    | The number of cargo     | No          |