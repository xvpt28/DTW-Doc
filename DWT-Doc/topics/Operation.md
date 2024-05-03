# Operation

## Description

Store information about the operation of a cargo.

## Database

### Table

`required`

### Columns

| Name                    | Type      | Description                   | Foreign Key | allowedNull |
|-------------------------|-----------|-------------------------------|-------------|-------------|
| id                      | UUID      | Primary Key of the operation. | No          | No          |
| timestamp               | timestamp | Timestamp of the operation.   | No          | No          |
| actualFromDestinationId | UUID      | link to Location Table        | Yes         | Yes         |
| actualToDestinationId   | UUID      | link to Destination Table     | Yes         | Yes         |
| planId                  | UUID      | link to Plan Table            | Yes         | No          |
| cargoId                 | UUID      | link to Cargo Table           | Yes         | No          |
