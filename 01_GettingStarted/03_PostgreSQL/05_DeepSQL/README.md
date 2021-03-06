# Introduction
This tutorial will help you understand deeply about SQL Command on PostgreSQL.

# Table of Contents
1. What is a database transaction? How do you demo a transaction?
2. How do you commit a transaction? And why to use it?
3. What is rollback ? How do you demo it?
# Reference
* The difference between Transaction Mode and Session Mode. More details: [here](https://qurosity.com/oracle-session-transaction/)
* Understand deeply about transaction. More details: [here](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-transaction/)

### Database Transaction

```sql
-- start a transaction <<<<<<<<<<<<<<<<<<<<<<<<<<=========================
BEGIN;

-- insert a new row into the accounts table
INSERT INTO accounts(name,balance)
VALUES('Alice',10000);

```

### Commit for transaction
```sql
-- start a transaction
BEGIN;

-- deduct 1000 from account 1
UPDATE accounts 
SET balance = balance - 1000
WHERE id = 1;

-- add 1000 to account 2
UPDATE accounts
SET balance = balance + 1000
WHERE id = 2; 

-- select the data from accounts
SELECT id, name, balance
FROM accounts;

-- commit the transaction <<<<<<<<<<<<<<<<<<<<<<<<<<=========================
COMMIT;
```
#### Why do we use a commit for a transaction?

### Rollback a transaction
```sql
-- start a transaction
BEGIN;

-- deduct 1000 from account 1
UPDATE accounts 
SET balance = balance - 1000
WHERE id = 1;

-- add 1000 to account 2
UPDATE accounts
SET balance = balance + 1000
WHERE id = 2; 

-- select the data from accounts
SELECT id, name, balance
FROM accounts;

-- roll back the transaction <<<<<<<<<<<<<<<<<<<<<<<<<<=========================
ROLLBACK;
```

