# Operation

## Description

Store information about the operation of a cargo.

## Database

### Table

`required`

### Columns

| Name        | Type      | Description                   | Foreign Key | allowedNull |
|-------------|-----------|-------------------------------|-------------|-------------|
| id          | UUID      | Primary Key of the operation. | No          | No          |
| timestamp   | timestamp | Timestamp of the operation.   | No          | No          |
| from        | UUID      | link to Location Table        | Yes         | Yes         |
| destination | UUID      | link to Destination Table     | Yes         | Yes         |
| planName    | UUID      | link to Plan Table            | Yes         | No          |
| cargoId     | UUID      | link to Cargo Table           | Yes         | No          |
