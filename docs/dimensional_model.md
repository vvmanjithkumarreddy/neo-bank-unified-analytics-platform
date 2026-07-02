# Dimensional Modelling Process

step1: list all the business process in the system

step2: list all source tables and mark them as event or entity
Event tables are potential fact tables
Entity tables are potential dimension tables

step3: Declare grain for each business process

step4: finalize the fact tables (decide which grains deserve their own fact table)

step5: identify dimensions
for each fact ask who, what, where, when, how

step6: consolidate and finalize dimension tables (combine dimensions discovered across all facts and finalize which becomes actual dimensions)

step7: identify measures for each event i.e what numeric values are recorded in
each event

step8: build stars i.e one star at a time
for each fact connet the related dimensions
do this for all the facts

step9: Identify confirmed dimensions (shared dimensions used by multiple facts)

step10: build the facts and dimensions

Above process is eloboration of Kimball's 4-step Design process

Kimballs 4-step dimensional modelling process:

1. select the business process
2. Declare the grain
3. Identify dimensions
4. Identify facts

---

# Dimensional modelling for neo-bank project

### Step1 - list all the business processes in the system

customers make transactions

### Step2 - list all the source tables and mark them as event or entity

Event/Fact - records something that happend at a point in time
Entity/Dimension - describes a business object

| Dataset               | Type   | Reason                                            |
| --------------------- | ------ | ------------------------------------------------- |
| branches              | Entity | describes branch attributes                       |
| customers             | Entity | describes customer attributes                     |
| accounts              | Entity | describes account attributes                      |
| transactions          | Event  | records a transaction occurance                   |
| payment_gateway_logs  | Event  | records processing activity for a transaction     |
| credit_bureau_reports | Event  | records a bureau report pulled at a specific time |

### Step3 - decleare grain for each business process

Fact transactions - one row per transaction
Fact payment_gateway_logs - one row per transaction processing activity
Fact credit_bureau_reports - one row per credit bureau report at a specific time

### Step4 - finalize the fact tables

Fact transactions
Fact payment_gateway_logs
Fact credit_bureau_reports

### Step5 - identify dimensions

Fact transactions:

who did the transaction - customer (dim customer)
what did he transact - money (same for all)
where did he transact - no specific location
when - date (dim date)
how did he do the transaction- through bank account (dim account)

Fact payment_gateway_logs:

who did the payment - customer (dim customer)
what did he paid - money (same for all)
where did he paid - geo_location measure present in the fact
when - date (dim date)
how did he do the payment - through bank account (dim account)

Fact credit_bureau_reports:

who does the report belong to - customer (dim customer)
when - date (dim date)

we have dim branches and it doesn't connect to facts directly but connects to the dim customers (through home branch key) and dim accounts (through account branch key) in
