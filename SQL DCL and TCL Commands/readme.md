# SQL DCL and TCL Commands

Data Control Language (DCL) Commands:
DCL includes commands such as GRANT and REVOKE which mainlydeal
with the rights, permissions, and other controls of the database system. List of DCL commands:  GRANT: This command gives users access privilegestothedatabase. Syntax,
GRANT privileges_names ON object TO user;
Example:
Create user first identified by passwd;
Grant select on customers to first;  REVOKE: This command withdraws the user’s access privilegesgiven by using the GRANT command. Syntax,
REVOKE privileges ON object FROM user;
Example:
Revoke select on customers from first;
Transaction Control Language (TCL) Commands:  COMMIT: Commits a Transaction. Syntax:
COMMIT;
Example:
INSERT INTO customers
VALUES ('1006','2020-03-04',3200,'DL', '1008');
 Commit;
 Select * from customers;  ROLLBACK: Rollbacks a transaction in case of any error occurs. Syntax:
Rollback;
Example:
DELETE FROM customers
WHERE store_state = 'MH'
AND customer_id = '1002';
 Select * from customers;
 Rollback;
 Select * from customers;  SAVEPOINT:Sets a savepoint within a transaction. Syntax:
SAVEPOINT SAVEPOINT_NAME;
This command is used only in the creation of SAVEPOINT among all thetransactions.
In general ROLLBACK is used to undo a group of transactions. Syntax for rolling back to Savepoint command:
ROLLBACK TO SAVEPOINT_NAME;
Example:
SAVEPOINT SP1;
DELETE FROM customers
WHERE store_state = 'MH'
AND customer_id = '1002';
SAVEPOINT SP2;
ROLLBACK TO SP1;
Select * from customers;
Result:
Thus the DCL and TCL commands are used to modify or manipulate data
records present in the customer database tables.
