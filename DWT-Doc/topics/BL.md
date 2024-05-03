# BL

## Description

Store information about the BL.

## Database

### Table

`required`

### Columns

| Name         | Type                | Description            | Foreign Key |
|--------------|---------------------|------------------------|-------------|
| id           | UUID                | Primary Key of the bl. | No          |
| blNumber     | string              | The number of the bl   | No          |
| string       | The bl id of the bl | No                     |
| sku          | string              | The sku of the bl      | NO          |
| name         | string              | The name of the bl     | No          |
| supplier     | string              | The supplier of the bl | No          |
| quantity     | int                 | The quantity of the bl | No          |
| quantityUnit | string              | The unit of the bl     | No          |