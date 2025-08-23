# ️ Features / TODO
- [ ] Define Tables/Needs Per AS9100/ISO9001
- [ ] Basic login system
- [ ] Connect to SQL database
- [ ] Build dashboard screen
- [ ] Implement profile editing
- [ ] Add order tracking
- [ ] Add inspection tool tracking
- [ ] Materials
- [ ] Users
- [ ] Customers
- [ ] Suppliers
- [ ] Operations
- [ ] Parts
- [ ] Machines


# SQL Tables

## `users` Table
| Field           | Type         | Notes                                        |
|-----------------|--------------|----------------------------------------------|
| id              | INT (PK)     | Auto-increment primary key, hidden from user |
| username        | VARCHAR(50)  | Unique, required                             |
| email(optional) | VARCHAR(100) | Unique,                                      |
| password_hash   | VARCHAR(255) | Hashed password                              |
| display name    | VARCHAR(125) | Allow users to edit their display names      |
| Role Label      | VARCHAR(50)  | Required                                     |
| Role Int        | INT(3)       | Required                                     |



## Combo View For Gages Built From Following Tables:

### `Gage/Tool Description` 
| Field                       | Type           | Notes                                       |
|-----------------------------|----------------|---------------------------------------------|
| id                          | INT (PK)       | Auto-increment primary key                  |
| Gage Serial                 | VARCHAR(50)    | Unique, required                            |
| Gage Type Label             | VARCHAR(100)   | Unique, required                            |
| Gage Type Int               | INT(3)         | Unique                                      |
| Price                       | DECIMAL(10,2)  | required                                    |
| Accuracy                    | DECIMAL(1,10)  | required                                    |
| Calibration Frequency Label | VARCHAR(25)    | required                                    |
| Calibration Frequency Int   | INT(3)         | required                                    |
| Description                 | VARCHAR(500)   | optional                                    |
| Visual Reference            | VARBINARY(MAX) | optional                                    |


### `Gage Calbiration History (append only)` 
| Field                   | Type         | Notes                                    |
|-------------------------|--------------|------------------------------------------|
| id                      | INT (PK)     | Auto-increment primary key               |
| Calibration Date        | DATE         | required                                 |
| Last Calibration Date   | DATE         | required                                 |
| Next Calibration Date   | DATE         | required                                 |
| In Calibration          | BOOLEAN      | required                                 |
| Calibrator              | VARCHAR(125) | user who certified calibration, required |
| Results of Verification | FLOAT        | required                                 |

### `Gage Temporal History (day to day changes)` 
| Field            | Type         | Notes                                       |
|------------------|--------------|---------------------------------------------|
| id               | INT (PK)     | Auto-increment primary key                  |
| In Use           | BOOLEAN      | boolean, linked to current holder, required |
| Current Holder   | VARCHAR(125) | linked to date signed out                   |
| Date Signed Out  | DATE         | linked to current holder                    |
| Storage Location | VARCHAR(75)  | required                                    |
| Current Location | VARCHAR(75)  | required                                    |
| Condition Label  | VARCHAR(25)  | required                                    |
| Condition Int    | INT(3)       | required                                    |


## Material tables

### `Material Description`
| Field            | Type         | Notes                                       |
|------------------|--------------|---------------------------------------------|
| id               | INT (PK)     | Auto-increment primary key                  |


### Manufactured Parts
| Field            | Type         | Notes                                       |
|------------------|--------------|---------------------------------------------|
| id               | INT (PK)     | Auto-increment primary key                  |


### Ordered Parts
| Field            | Type         | Notes                                       |
|------------------|--------------|---------------------------------------------|
| id               | INT (PK)     | Auto-increment primary key                  |


## Documents 

### `Bill of materials`
| Field            | Type         | Notes                                       |
|------------------|--------------|---------------------------------------------|
| id               | INT (PK)     | Auto-increment primary key                  |

### `Specs`
| Field            | Type         | Notes                                       |
|------------------|--------------|---------------------------------------------|
| id               | INT (PK)     | Auto-increment primary key                  |

### `Purchase Order`
| Field            | Type         | Notes                                       |
|------------------|--------------|---------------------------------------------|
| id               | INT (PK)     | Auto-increment primary key                  |


## Processes 

### Operations Tables
| Field            | Type         | Notes                                       |
|------------------|--------------|---------------------------------------------|
| id               | INT (PK)     | Auto-increment primary key                  |


### Machine Tables
| Field            | Type         | Notes                                       |
|------------------|--------------|---------------------------------------------|
| id               | INT (PK)     | Auto-increment primary key                  |


## External Location

### Supplier Tables
| Field            | Type         | Notes                                       |
|------------------|--------------|---------------------------------------------|
| id               | INT (PK)     | Auto-increment primary key                  |


### Customer Tables
| Field            | Type         | Notes                                       |
|------------------|--------------|---------------------------------------------|
| id               | INT (PK)     | Auto-increment primary key                  |

### Shipping

