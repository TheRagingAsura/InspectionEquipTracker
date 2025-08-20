# ️ Features / TODO
- [ ] Basic login system
- [ ] Connect to SQL database
- [ ] Build dashboard screen
- [ ] Implement profile editing
- [ ] Add order tracking






# SQL Tables

### `users` Table
| Field           | Type         | Notes          |
|-----------------|--------------|----------------|
| id              | INT (PK)     | Auto-increment primary key |
| username        | VARCHAR(50)  | Unique, required |
| email(optional) | VARCHAR(100) | Unique,        |
| password_hash   | VARCHAR(255) | Hashed password |
| display name    | VARCHAR(50)  |  |


### `Gage/Tool` Table
| Field                   | Type         | Notes                                       |
|-------------------------|--------------|---------------------------------------------|
| id                      | INT (PK)     | Auto-increment primary key                  |
| Gage ID                 | VARCHAR(50)  | Unique, required                            |
| Gage Type               | VARCHAR(100) | Unique, required                            |
| Last Calibration Date   | DATE         | required                                    |
| Next Calibration Date   | DATE         | required                                    |
| In Calibration          | BOOLEAN      | required                                    |
| Calibrator              | VARCHAR(50)  | user who certified calibration, required    |
| In Use                  | BOOLEAN      | boolean, linked to current holder, required |
| Current Holder          | VARCHAR(50)  | linked to date signed out                   |
| Date Signed Out         | DATE         | linked to current holder                    |
| Storage Location        | VARCHAR(75)  | required                                    |
| Current                 | VARCHAR(75)  | required                                    |
| Price                   | int          | required                                    |
| Accuracy                | int          | required                                    |
| Condition               | int          | required                                    |
| Results of Verification | int          | required                                    |
| Calibration Frequency   | int          | required                                    |

| Description   | varchar(500)        | optional |
