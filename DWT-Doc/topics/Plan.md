# Plan

## Description

Store Plan Information about the Cargo.

## Database

### Table

`required`

### Columns

| Name              | Type   | Description                            | Foreign Key | allowedNull |
|-------------------|--------|----------------------------------------|-------------|-------------|
| id                | UUID   | Primary Key of the lot.                | No          | No          |
| planId            | string | The plan id of the plan, auto generate | No          | No          |
| method            | string | The method of the plan                 | No          | No          |
| targetFrom        | obj    | The target destination of the plan     | No          | Yes         |
| targetDestination | uuid   | The target destination of the plan     | yes         | No          |
| targetDate        | string | The target timestamp of the plan       | No          | No          |
| lotId             | uuid   | The lot id of the plan                 | yes         | No          |
