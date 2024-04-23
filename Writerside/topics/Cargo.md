# Cargo

## Description

Store information about the Cargo.

## Database

### Table

`required`

### Columns

| Name      | Type   | Description                              | Foreign Key | allowedNull |
|-----------|--------|------------------------------------------|-------------|-------------|
| id        | UUID   | Primary Key of the lot.                  | No          | No          |
| type      | string | The type of the cargo (pallet or carton) | No          | No          |
| virtualId | string | The virtual id of the cargo              | No          | No          |
| actualId  | string | The actual id of the cargo               | No          | Yes         |

