# Data Dictionary

## Source Datasets

| Dataset               | Description                        | PrimaryKey  |
| --------------------- | ---------------------------------- | ----------- |
| branches              | contains bank branches details     | branch_code |
| customers             | contains customers details         | customer_id |
| accounts              | contains bank account details      | account_id  |
| transactions          | contians transaction details       | txn_id      |
| credit_bureau_reports | contins the customer credit report | customer_id |
| payment_gateway_logs  | contains the payment gateway logs  | txn_id      |

## Dataset Detailed Descriptions:

### 1. branches table

This contains details of each bank branch

1. branch_code: contains the branch code
2. branch_name: contains the branch name
3. city: contains the city where the branch is located
4. state: contains the state where the branch is located
5. region: contains the region of the branch

### 2. customers table

This contains all the customers details in the bank

1. customer_id: contains id of the customer
2. first_name: first name of the customer
3. last_name: last name of the customer
4. date_of_birth: DOB of the customer
5. pan_number: pan number of the customer
6. email: email address of the customer
7. phone_number: phone number of the customer
8. kyc_status: kyc status of the customer
9. branch_code: branch code of the customers account

### 3. accounts table

This contains all the bank accounts details

1. account_id: id of the bank account
2. customer_id: id of the customer to whom the account belongs to
3. account_type: type of the bank account
4. balance: account balance
5. currency: type of currency stored in the bank account
6. branch_code: branch code to which the account belongs to
7. status: account status
8. opened_date: account opened date

### 4. transactions table

This contains all the transaction details

1. txn_id: transaction_id
2. account_id: account_id from which the transaction was made
3. txn_type: type of the transaction
4. amount: transaction amount
5. txn_timestamp: transaction happend time
6. channel: payment channel through which transaction happened
7. status: status of the transaction

### 5. credit_bureau_reports

This contains credit bureau reports of the customers

1. customer_id: customer id
2. credit_score: customer credit score
3. risk_grade: customer risk grade
4. external_active_loans: customer external activel loans
5. external_overdue_amount: customer external overdue amount
6. bureau_pull_date: credit bureau report pulled date

### 6. payment_gateway_logs

This contains the transaction payment gateway logs

1. txn_id: transaction id
2. gateway_name: payment gateway name
3. gateway_status: gateway status
4. response_code: gateway response code
5. processing_time_ms: processing time for the payment
6. device_type: type of the device from which the payment was done
7. geo_location: location from which the payment was done
8. processed_timestamp: the time at which the payment was done
