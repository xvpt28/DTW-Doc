# Destination

## Description

Store All the destination of the cargo.

## Database

### Table

`required`

### Columns

| Name       | Type   | Description                  | Foreign Key |
|------------|--------|------------------------------|-------------|
| id         | UUID   | Primary Key of the operation | No          |
| name       | string | Name of the destination      | No          |
| locationId | UUID   | Foreign Key of the location  | Yes         |
