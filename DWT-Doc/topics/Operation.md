# Operation

## Description

Store information about the operation of a cargo.

## Database

### Table

`required`

### Columns

| Name        | Type      | Description                   | Foreign Key |
|-------------|-----------|-------------------------------|-------------|
| id          | UUID      | Primary Key of the operation. | No          |
| timestamp   | timestamp | Timestamp of the operation.   | No          |
| destination | UUID      | link to Destination Table     | Yes         |
| planId      | UUID      | link to Plan Table            | Yes         |
