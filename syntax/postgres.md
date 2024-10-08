Postgres
---

### 1. **Create Database**
```sql
CREATE DATABASE mydb;
```
- **Note:** Creates a new database with the specified name.

### 2. **Drop Database**
```sql
DROP DATABASE mydb;
```
- **Note:** Deletes an existing database, removing all its data.

### 3. **Create Table**
```sql
CREATE TABLE users (id SERIAL, name VARCHAR(100));
```
- **Note:** Defines a new table and its columns.

### 4. **Drop Table**
```sql
DROP TABLE users;
```
- **Note:** Deletes an entire table and its data.

### 5. **Insert Into Table**
```sql
INSERT INTO users (name) VALUES ('John');
```
- **Note:** Adds new rows into a specified table.

### 6. **Select All Data**
```sql
SELECT * FROM users;
```
- **Note:** Retrieves all rows and columns from a table.

### 7. **Select Specific Columns**
```sql
SELECT name FROM users;
```
- **Note:** Retrieves only the specified columns from a table.

### 8. **Where Clause**
```sql
SELECT * FROM users WHERE id = 1;
```
- **Note:** Filters data by applying conditions.

### 9. **Update Table**
```sql
UPDATE users SET name = 'Jane' WHERE id = 1;
```
- **Note:** Modifies existing rows in a table.

### 10. **Delete Data from Table**
```sql
DELETE FROM users WHERE id = 1;
```
- **Note:** Removes rows based on conditions.

### 11. **Create a User**
```sql
CREATE USER myuser WITH PASSWORD 'mypassword';
```
- **Note:** Adds a new user to the PostgreSQL instance.

### 12. **Grant Privileges**
```sql
GRANT SELECT ON users TO myuser;
```
- **Note:** Gives permissions to a user for a table or database.

### 13. **Revoke Privileges**
```sql
REVOKE SELECT ON users FROM myuser;
```
- **Note:** Removes specific permissions from a user.

### 14. **Drop User**
```sql
DROP USER myuser;
```
- **Note:** Deletes a user from the PostgreSQL system.

### 15. **Join Tables**
```sql
SELECT * FROM users u JOIN orders o ON u.id = o.user_id;
```
- **Note:** Combines rows from multiple tables based on a related column.

### 16. **Left Join**
```sql
SELECT * FROM users u LEFT JOIN orders o ON u.id = o.user_id;
```
- **Note:** Retrieves all rows from the left table, and matching rows from the right.

### 17. **Right Join**
```sql
SELECT * FROM users u RIGHT JOIN orders o ON u.id = o.user_id;
```
- **Note:** Retrieves all rows from the right table, and matching rows from the left.

### 18. **Full Join**
```sql
SELECT * FROM users u FULL JOIN orders o ON u.id = o.user_id;
```
- **Note:** Returns all rows when there is a match in either table.

### 19. **Group By**
```sql
SELECT COUNT(*), name FROM users GROUP BY name;
```
- **Note:** Aggregates rows that share a column value.

### 20. **Having Clause**
```sql
SELECT COUNT(*), name FROM users GROUP BY name HAVING COUNT(*) > 1;
```
- **Note:** Filters groups after aggregation.

### 21. **Order By**
```sql
SELECT * FROM users ORDER BY name ASC;
```
- **Note:** Sorts the result set based on one or more columns.

### 22. **Limit**
```sql
SELECT * FROM users LIMIT 10;
```
- **Note:** Restricts the number of rows returned.

### 23. **Offset**
```sql
SELECT * FROM users OFFSET 5;
```
- **Note:** Skips a specified number of rows before returning results.

### 24. **Distinct**
```sql
SELECT DISTINCT name FROM users;
```
- **Note:** Returns only unique rows in the result set.

### 25. **Count**
```sql
SELECT COUNT(*) FROM users;
```
- **Note:** Counts the number of rows that match a condition.

### 26. **Min**
```sql
SELECT MIN(age) FROM users;
```
- **Note:** Finds the smallest value in a column.

### 27. **Max**
```sql
SELECT MAX(age) FROM users;
```
- **Note:** Finds the largest value in a column.

### 28. **Sum**
```sql
SELECT SUM(salary) FROM users;
```
- **Note:** Adds up all the values in a column.

### 29. **Avg**
```sql
SELECT AVG(salary) FROM users;
```
- **Note:** Computes the average of the values in a column.

### 30. **Between**
```sql
SELECT * FROM users WHERE age BETWEEN 20 AND 30;
```
- **Note:** Selects values within a specified range.

### 31. **In**
```sql
SELECT * FROM users WHERE age IN (25, 30, 35);
```
- **Note:** Filters rows by checking if a value matches any in a list.

### 32. **Like**
```sql
SELECT * FROM users WHERE name LIKE 'J%';
```
- **Note:** Filters rows using a pattern match.

### 33. **Ilike (Case-insensitive Like)**
```sql
SELECT * FROM users WHERE name ILIKE 'j%';
```
- **Note:** Similar to LIKE, but case-insensitive.

### 34. **Union**
```sql
SELECT name FROM users UNION SELECT name FROM clients;
```
- **Note:** Combines the result sets of two queries, removing duplicates.

### 35. **Union All**
```sql
SELECT name FROM users UNION ALL SELECT name FROM clients;
```
- **Note:** Combines result sets of two queries without removing duplicates.

### 36. **Subquery**
```sql
SELECT * FROM users WHERE id IN (SELECT user_id FROM orders);
```
- **Note:** Embeds one query inside another.

### 37. **Exists**
```sql
SELECT * FROM users WHERE EXISTS (SELECT 1 FROM orders WHERE users.id = orders.user_id);
```
- **Note:** Checks if a subquery returns any rows.

### 38. **Not Exists**
```sql
SELECT * FROM users WHERE NOT EXISTS (SELECT 1 FROM orders WHERE users.id = orders.user_id);
```
- **Note:** Returns true if a subquery returns no rows.

### 39. **Create Index**
```sql
CREATE INDEX idx_name ON users(name);
```
- **Note:** Speeds up searches on a table by indexing a column.

### 40. **Drop Index**
```sql
DROP INDEX idx_name;
```
- **Note:** Removes an existing index from a table.

### 41. **Create Unique Index**
```sql
CREATE UNIQUE INDEX idx_unique_name ON users(name);
```
- **Note:** Ensures all values in a column are unique.

### 42. **Create View**
```sql
CREATE VIEW user_names AS SELECT id, name FROM users;
```
- **Note:** Defines a stored query that acts as a virtual table.

### 43. **Drop View**
```sql
DROP VIEW user_names;
```
- **Note:** Removes an existing view.

### 44. **Create Function**
```sql
CREATE FUNCTION get_user_count() RETURNS INTEGER AS $$ SELECT COUNT(*) FROM users $$ LANGUAGE SQL;
```
- **Note:** Defines a reusable function in the database.

### 45. **Drop Function**
```sql
DROP FUNCTION get_user_count;
```
- **Note:** Removes an existing function.

### 46. **Create Trigger**
```sql
CREATE TRIGGER update_timestamp BEFORE UPDATE ON users FOR EACH ROW EXECUTE FUNCTION update_modified_column();
```
- **Note:** Defines an action to occur when a specific event happens on a table.

### 47. **Drop Trigger**
```sql
DROP TRIGGER update_timestamp ON users;
```
- **Note:** Removes an existing trigger from a table.

### 48. **Current Date**
```sql
SELECT CURRENT_DATE;
```
- **Note:** Retrieves the current system date.

### 49. **Current Time**
```sql
SELECT CURRENT_TIME;
```
- **Note:** Retrieves the current system time.

### 50. **Current Timestamp**
```sql
SELECT CURRENT_TIMESTAMP;
```
- **Note:** Retrieves the current date and time.

### 51. **Interval**
```sql
SELECT CURRENT_DATE + INTERVAL '1 year';
```
- **Note:** Represents a span of time, useful for date calculations.

### 52. **Age Function**
```sql
SELECT AGE('2023-01-01');
```
- **Note:** Computes the difference between two dates.

### 53. **Coalesce**
```sql
SELECT COALESCE(NULL, 'default');
```
- **Note:** Returns the first non-null value from a list of arguments.

### 54. **Case Statement**
```sql
SELECT CASE WHEN age < 18 THEN 'Minor' ELSE 'Adult' END FROM users;
```
- **Note:** Implements conditional logic in SQL.

### 55. **Random Function**
```sql
SELECT RANDOM();
```
- **Note:** Returns a random floating-point number between 0 and 1.

### 56. **Generate Series**
```sql
SELECT * FROM GENERATE_SERIES(1, 5);
``

`
- **Note:** Creates a series of numbers or timestamps.

### 57. **Cast**
```sql
SELECT CAST('123' AS INTEGER);
```
- **Note:** Converts one data type into another.

### 58. **Create Sequence**
```sql
CREATE SEQUENCE my_sequence START 1;
```
- **Note:** Defines an auto-incrementing sequence.

### 59. **Nextval**
```sql
SELECT NEXTVAL('my_sequence');
```
- **Note:** Gets the next value from a sequence.

### 60. **Currval**
```sql
SELECT CURRVAL('my_sequence');
```
- **Note:** Retrieves the current value from a sequence.

### 61. **Setval**
```sql
SELECT SETVAL('my_sequence', 100);
```
- **Note:** Sets the current value of a sequence.

### 62. **String Length**
```sql
SELECT LENGTH('hello');
```
- **Note:** Returns the length of a string.

### 63. **Substring**
```sql
SELECT SUBSTRING('hello world' FROM 1 FOR 5);
```
- **Note:** Extracts a portion of a string.

### 64. **Trim**
```sql
SELECT TRIM(' hello ');
```
- **Note:** Removes spaces from the start and end of a string.

### 65. **Position**
```sql
SELECT POSITION('world' IN 'hello world');
```
- **Note:** Finds the location of a substring within a string.

### 66. **Upper Function**
```sql
SELECT UPPER('hello');
```
- **Note:** Converts a string to uppercase.

### 67. **Lower Function**
```sql
SELECT LOWER('HELLO');
```
- **Note:** Converts a string to lowercase.

### 68. **Replace**
```sql
SELECT REPLACE('hello world', 'world', 'there');
```
- **Note:** Substitutes a substring with another substring.

### 69. **Concatenate Strings**
```sql
SELECT 'hello' || ' ' || 'world';
```
- **Note:** Joins two or more strings together.

### 70. **Date Part Extraction**
```sql
SELECT EXTRACT(YEAR FROM CURRENT_DATE);
```
- **Note:** Extracts a specific part (like year, month) from a date.

### 71. **Date Add**
```sql
SELECT CURRENT_DATE + INTERVAL '10 days';
```
- **Note:** Adds an interval to a date.

### 72. **Date Subtract**
```sql
SELECT CURRENT_DATE - INTERVAL '10 days';
```
- **Note:** Subtracts an interval from a date.

### 73. **Extract Epoch**
```sql
SELECT EXTRACT(EPOCH FROM CURRENT_TIMESTAMP);
```
- **Note:** Gets the number of seconds since '1970-01-01'.

### 74. **To Timestamp**
```sql
SELECT TO_TIMESTAMP(1609459200);
```
- **Note:** Converts a Unix epoch to a timestamp.

### 75. **To Date**
```sql
SELECT TO_DATE('2023-01-01', 'YYYY-MM-DD');
```
- **Note:** Converts a string to a date.

### 76. **To Number**
```sql
SELECT TO_NUMBER('123', '999');
```
- **Note:** Converts a string to a numeric value.

### 77. **Nullif**
```sql
SELECT NULLIF(10, 10);
```
- **Note:** Returns NULL if two values are equal.

### 78. **Greatest**
```sql
SELECT GREATEST(1, 5, 3);
```
- **Note:** Returns the largest value from a list.

### 79. **Least**
```sql
SELECT LEAST(1, 5, 3);
```
- **Note:** Returns the smallest value from a list.

### 80. **Table Inheritance**
```sql
CREATE TABLE employees (id SERIAL) INHERITS (users);
```
- **Note:** Allows a table to inherit columns from a parent table.

### 81. **Insert with Default Values**
```sql
INSERT INTO users DEFAULT VALUES;
```
- **Note:** Inserts default values for a row.

### 82. **On Delete Cascade**
```sql
CREATE TABLE orders (id SERIAL, user_id INT REFERENCES users(id) ON DELETE CASCADE);
```
- **Note:** Automatically deletes rows in child tables when parent rows are deleted.

### 83. **On Update Cascade**
```sql
CREATE TABLE orders (id SERIAL, user_id INT REFERENCES users(id) ON UPDATE CASCADE);
```
- **Note:** Automatically updates rows in child tables when parent rows are updated.

### 84. **Alter Table to Add Column**
```sql
ALTER TABLE users ADD COLUMN email VARCHAR(100);
```
- **Note:** Adds a new column to an existing table.

### 85. **Alter Table to Drop Column**
```sql
ALTER TABLE users DROP COLUMN email;
```
- **Note:** Removes a column from an existing table.

### 86. **Alter Table to Rename Column**
```sql
ALTER TABLE users RENAME COLUMN name TO full_name;
```
- **Note:** Renames a column in an existing table.

### 87. **Add Not Null Constraint**
```sql
ALTER TABLE users ALTER COLUMN name SET NOT NULL;
```
- **Note:** Ensures that a column cannot have NULL values.

### 88. **Add Unique Constraint**
```sql
ALTER TABLE users ADD CONSTRAINT unique_email UNIQUE (email);
```
- **Note:** Ensures all values in a column are unique.

### 89. **On Conflict (Upsert)**
```sql
INSERT INTO users (id, name) VALUES (1, 'John') ON CONFLICT (id) DO UPDATE SET name = EXCLUDED.name;
```
- **Note:** Inserts a row or updates it if a conflict occurs.

### 90. **Return Inserted Row**
```sql
INSERT INTO users (name) VALUES ('John') RETURNING id;
```
- **Note:** Returns the value of an inserted row.

### 91. **Return Updated Row**
```sql
UPDATE users SET name = 'Jane' WHERE id = 1 RETURNING name;
```
- **Note:** Returns the value of an updated row.

### 92. **Create Temporary Table**
```sql
CREATE TEMP TABLE temp_users (id SERIAL, name VARCHAR(100));
```
- **Note:** Defines a temporary table that exists for the duration of a session.

### 93. **Drop Temporary Table**
```sql
DROP TABLE IF EXISTS temp_users;
```
- **Note:** Deletes a temporary table.

### 94. **Get Table Size**
```sql
SELECT PG_TOTAL_RELATION_SIZE('users');
```
- **Note:** Retrieves the size of a table.

### 95. **Get Database Size**
```sql
SELECT PG_DATABASE_SIZE('mydb');
```
- **Note:** Retrieves the size of the entire database.

### 96. **Vacuum**
```sql
VACUUM FULL users;
```
- **Note:** Cleans up and reclaims storage for a table.

### 97. **Analyze**
```sql
ANALYZE users;
```
- **Note:** Updates statistics for query optimization.

### 98. **Explain**
```sql
EXPLAIN SELECT * FROM users;
```
- **Note:** Displays the execution plan of a query.

### 99. **Explain Analyze**
```sql
EXPLAIN ANALYZE SELECT * FROM users;
```
- **Note:** Displays the execution plan along with the actual run time.

### 100. **Set Search Path**
```sql
SET SEARCH_PATH TO myschema;
```
- **Note:** Changes the current schema search path.


### 101. **Alter Table to Add Constraint**
```sql
ALTER TABLE users ADD CONSTRAINT chk_age CHECK (age >= 0);
```
- **Note:** Adds a constraint to ensure data integrity.

### 102. **Drop Constraint**
```sql
ALTER TABLE users DROP CONSTRAINT chk_age;
```
- **Note:** Removes an existing constraint from a table.

### 103. **Alter Table to Rename**
```sql
ALTER TABLE users RENAME TO customers;
```
- **Note:** Renames an existing table.

### 104. **Set Default Value**
```sql
ALTER TABLE users ALTER COLUMN age SET DEFAULT 18;
```
- **Note:** Sets a default value for a column.

### 105. **Show Current User**
```sql
SELECT CURRENT_USER;
```
- **Note:** Retrieves the name of the current user.

### 106. **Show User Roles**
```sql
SELECT rolname FROM pg_roles;
```
- **Note:** Lists all user roles in the database.

### 107. **Show All Databases**
```sql
\l
```
- **Note:** Lists all databases in the PostgreSQL instance.

### 108. **Show All Tables**
```sql
\dt
```
- **Note:** Lists all tables in the current database.

### 109. **Describe Table**
```sql
\d users
```
- **Note:** Displays the structure of a table.

### 110. **Use Database**
```sql
\c mydb
```
- **Note:** Connects to a specified database.

### 111. **Backup Database**
```sql
pg_dump mydb > mydb_backup.sql;
```
- **Note:** Creates a backup of the specified database.

### 112. **Restore Database**
```sql
psql mydb < mydb_backup.sql;
```
- **Note:** Restores a database from a backup file.

### 113. **Create Role**
```sql
CREATE ROLE myrole;
```
- **Note:** Defines a new role in the database.

### 114. **Drop Role**
```sql
DROP ROLE myrole;
```
- **Note:** Deletes a role from the database.

### 115. **Alter Role**
```sql
ALTER ROLE myrole WITH LOGIN;
```
- **Note:** Modifies properties of an existing role.

### 116. **Create Materialized View**
```sql
CREATE MATERIALIZED VIEW my_view AS SELECT * FROM users;
```
- **Note:** Defines a view that stores data physically.

### 117. **Refresh Materialized View**
```sql
REFRESH MATERIALIZED VIEW my_view;
```
- **Note:** Updates the data in a materialized view.

### 118. **Drop Materialized View**
```sql
DROP MATERIALIZED VIEW my_view;
```
- **Note:** Deletes a materialized view from the database.

### 119. **Create Aggregate Function**
```sql
CREATE AGGREGATE my_aggregate (sfunc = my_state_func, stype = my_state_type);
```
- **Note:** Defines a custom aggregate function.

### 120. **Create Domain**
```sql
CREATE DOMAIN email_domain AS VARCHAR(255) CHECK (VALUE LIKE '%@%');
```
- **Note:** Defines a custom data type with constraints.

### 121. **Drop Domain**
```sql
DROP DOMAIN email_domain;
```
- **Note:** Deletes a defined domain from the database.

### 122. **Alter Domain**
```sql
ALTER DOMAIN email_domain SET DEFAULT 'example@example.com';
```
- **Note:** Modifies properties of an existing domain.

### 123. **Create Trigger Function**
```sql
CREATE FUNCTION log_changes() RETURNS TRIGGER AS $$ BEGIN ... END; $$ LANGUAGE plpgsql;
```
- **Note:** Defines a function to be executed by a trigger.

### 124. **Alter Trigger**
```sql
ALTER TRIGGER my_trigger ON users DISABLE;
```
- **Note:** Modifies the properties of an existing trigger.

### 125. **Show Trigger**
```sql
SELECT tgname FROM pg_trigger WHERE tgrelid = 'users'::regclass;
```
- **Note:** Lists triggers associated with a table.

### 126. **Create Role with Permissions**
```sql
CREATE ROLE myrole WITH LOGIN CREATEDB;
```
- **Note:** Creates a role with specific permissions.

### 127. **Set Role**
```sql
SET ROLE myrole;
```
- **Note:** Changes the current role to another one.

### 128. **Get Current Transaction Isolation Level**
```sql
SHOW TRANSACTION ISOLATION;
```
- **Note:** Displays the current isolation level for transactions.

### 129. **Begin Transaction**
```sql
BEGIN;
```
- **Note:** Starts a new transaction block.

### 130. **Commit Transaction**
```sql
COMMIT;
```
- **Note:** Saves all changes made in the current transaction.

### 131. **Rollback Transaction**
```sql
ROLLBACK;
```
- **Note:** Reverts changes made in the current transaction.

### 132. **Savepoint**
```sql
SAVEPOINT my_savepoint;
```
- **Note:** Sets a point to which you can later roll back.

### 133. **Release Savepoint**
```sql
RELEASE SAVEPOINT my_savepoint;
```
- **Note:** Removes a defined savepoint.

### 134. **Set Transaction Isolation Level**
```sql
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
```
- **Note:** Specifies the isolation level for transactions.

### 135. **Get Lock**
```sql
LOCK TABLE users IN ACCESS EXCLUSIVE MODE;
```
- **Note:** Acquires a lock on a table to prevent concurrent access.

### 136. **Release Lock**
```sql
UNLOCK TABLE users;
```
- **Note:** Releases a lock on a table.

### 137. **Create Foreign Key Constraint**
```sql
ALTER TABLE orders ADD CONSTRAINT fk_user FOREIGN KEY (user_id) REFERENCES users(id);
```
- **Note:** Establishes a foreign key relationship between two tables.

### 138. **Create Composite Key**
```sql
ALTER TABLE orders ADD CONSTRAINT pk_orders PRIMARY KEY (order_id, user_id);
```
- **Note:** Defines a primary key that consists of multiple columns.

### 139. **Create Index Concurrently**
```sql
CREATE INDEX CONCURRENTLY idx_name ON users(name);
```
- **Note:** Creates an index without locking the table for writes.

### 140. **Drop Index Concurrently**
```sql
DROP INDEX CONCURRENTLY idx_name;
```
- **Note:** Removes an index without locking the table for writes.

### 141. **Create Check Constraint**
```sql
ALTER TABLE users ADD CONSTRAINT check_age CHECK (age >= 18);
```
- **Note:** Adds a constraint to ensure a column meets specific conditions.

### 142. **Add Column with Default**
```sql
ALTER TABLE users ADD COLUMN status VARCHAR(10) DEFAULT 'active';
```
- **Note:** Adds a new column with a default value.

### 143. **Set Transaction Mode**
```sql
SET SESSION CHARACTERISTICS AS TRANSACTION ISOLATION LEVEL READ COMMITTED;
```
- **Note:** Sets the transaction characteristics for the session.

### 144. **Enable/Disable Triggers**
```sql
ALTER TABLE users ENABLE TRIGGER ALL;
```
- **Note:** Enables or disables triggers on a table.

### 145. **Get Table Row Count**
```sql
SELECT COUNT(*) FROM users;
```
- **Note:** Retrieves the total number of rows in a table.

### 146. **Get Column Names**
```sql
SELECT column_name FROM information_schema.columns WHERE table_name = 'users';
```
- **Note:** Lists all column names of a table.

### 147. **Get Table Structure**
```sql
SELECT * FROM information_schema.columns WHERE table_name = 'users';
```
- **Note:** Provides details about the columns in a table.

### 148. **Check Constraints**
```sql
SELECT conname FROM pg_constraint WHERE conrelid = 'users'::regclass AND contype = 'c';
```
- **Note:** Lists all constraints on a table.

### 149. **Check Indexes**
```sql
SELECT * FROM pg_indexes WHERE tablename = 'users';
```
- **Note:** Lists all indexes on a specified table.

### 150. **Transaction Log**
```sql
SELECT * FROM pg_stat_activity;
```
- **Note:** Shows the current activity in the database, including transactions.

### 151. **Get User Permissions**
```sql
SELECT * FROM information_schema.role_table_grants WHERE table_name = 'users';
```
- **Note:** Lists permissions granted on a table.

### 152. **Create Event Trigger**
```sql
CREATE EVENT TRIGGER my_event_trigger ON ddl_command_start EXECUTE FUNCTION my_function();
```
- **Note:** Defines a trigger that fires on specific database events.

### 153. **Drop Event Trigger**
```sql
DROP EVENT TRIGGER my_event_trigger;
```
- **Note:** Deletes an existing event trigger.

### 154. **Set Session Variable**
```sql
SET my_variable = 'value';
```
- **Note:** Sets a session-specific variable.

### 155. **Show Current Settings**
```sql
SHOW ALL;
```
- **Note:** Displays all configuration parameters.

### 156. **Set Configuration Parameter**
```sql
SET work_mem = '64MB';
```
- **Note:** Changes a configuration parameter for the current session.

### 157. **Get Configuration Parameter**
```sql
SHOW work_mem;
```
-

 **Note:** Displays the value of a specific configuration parameter.

### 158. **Check Database Encoding**
```sql
SHOW SERVER_ENCODING;
```
- **Note:** Displays the character encoding of the database.

### 159. **Create Partitioned Table**
```sql
CREATE TABLE users_part (id SERIAL, name VARCHAR) PARTITION BY RANGE (id);
```
- **Note:** Defines a table that will be partitioned by a specific column.

### 160. **Add Partition**
```sql
CREATE TABLE users_part_1 PARTITION OF users_part FOR VALUES FROM (1) TO (100);
```
- **Note:** Creates a specific partition for a partitioned table.

### 161. **Create Function**
```sql
CREATE FUNCTION my_function() RETURNS VOID AS $$ BEGIN ... END; $$ LANGUAGE plpgsql;
```
- **Note:** Defines a new function in PostgreSQL.

### 162. **Drop Function**
```sql
DROP FUNCTION my_function();
```
- **Note:** Deletes an existing function.

### 163. **Execute Function**
```sql
SELECT my_function();
```
- **Note:** Calls an existing function.

### 164. **Get Function Information**
```sql
SELECT proname, proargtypes FROM pg_proc WHERE proname = 'my_function';
```
- **Note:** Retrieves information about a specific function.

### 165. **Create View**
```sql
CREATE VIEW my_view AS SELECT name FROM users WHERE age >= 18;
```
- **Note:** Defines a view based on a query.

### 166. **Drop View**
```sql
DROP VIEW my_view;
```
- **Note:** Deletes a view from the database.

### 167. **Update View**
```sql
CREATE OR REPLACE VIEW my_view AS SELECT name, age FROM users WHERE age >= 18;
```
- **Note:** Modifies an existing view.

### 168. **Create Schema**
```sql
CREATE SCHEMA my_schema;
```
- **Note:** Defines a new schema in the database.

### 169. **Drop Schema**
```sql
DROP SCHEMA my_schema CASCADE;
```
- **Note:** Deletes a schema and all its contained objects.

### 170. **Show Current Schema**
```sql
SELECT current_schema();
```
- **Note:** Displays the current schema being used.

### 171. **Set Search Path for Schema**
```sql
SET search_path TO my_schema, public;
```
- **Note:** Changes the schema search path.

### 172. **Get Index Size**
```sql
SELECT pg_size_pretty(pg_indexes_size('users'));
```
- **Note:** Retrieves the size of indexes on a specified table.

### 173. **Get Table Size**
```sql
SELECT pg_size_pretty(pg_total_relation_size('users'));
```
- **Note:** Retrieves the size of a table including its indexes.

### 174. **Set Connection Timeout**
```sql
SET statement_timeout = '5s';
```
- **Note:** Sets a timeout for statements to execute.

### 175. **Set Idle Timeout**
```sql
SET idle_in_transaction_session_timeout = '10s';
```
- **Note:** Defines how long a session can remain idle.

### 176. **Grant Permission**
```sql
GRANT SELECT ON users TO myrole;
```
- **Note:** Grants specific permissions to a role on an object.

### 177. **Revoke Permission**
```sql
REVOKE SELECT ON users FROM myrole;
```
- **Note:** Removes specific permissions from a role.

### 178. **Set Default Transaction Isolation**
```sql
ALTER ROLE myrole SET transaction_isolation TO 'read committed';
```
- **Note:** Sets a default isolation level for a role.

### 179. **Add Comment to Column**
```sql
COMMENT ON COLUMN users.age IS 'Age of the user';
```
- **Note:** Adds a comment to a specific column.

### 180. **Add Comment to Table**
```sql
COMMENT ON TABLE users IS 'Table of users';
```
- **Note:** Adds a comment to a specific table.

### 181. **Show Comments**
```sql
SELECT obj_description('users'::regclass);
```
- **Note:** Retrieves comments associated with a table or column.

### 182. **Create Foreign Data Wrapper**
```sql
CREATE FOREIGN DATA WRAPPER my_fdw;
```
- **Note:** Defines a wrapper for foreign data sources.

### 183. **Create Server for Foreign Data**
```sql
CREATE SERVER my_server FOREIGN DATA WRAPPER my_fdw;
```
- **Note:** Specifies a foreign server for accessing data.

### 184. **Create User Mapping**
```sql
CREATE USER MAPPING FOR myuser SERVER my_server OPTIONS (user 'myuser', password 'mypassword');
```
- **Note:** Maps a database user to a foreign server.

### 185. **Create Foreign Table**
```sql
CREATE FOREIGN TABLE my_foreign_table (id INT, name TEXT) SERVER my_server OPTIONS (table_name 'remote_table');
```
- **Note:** Defines a foreign table that references a table on a foreign server.

### 186. **Drop Foreign Table**
```sql
DROP FOREIGN TABLE my_foreign_table;
```
- **Note:** Deletes a foreign table.

### 187. **Select from Foreign Table**
```sql
SELECT * FROM my_foreign_table;
```
- **Note:** Queries data from a foreign table.

### 188. **Create Language**
```sql
CREATE LANGUAGE plpgsql;
```
- **Note:** Defines a new procedural language.

### 189. **Drop Language**
```sql
DROP LANGUAGE plpgsql;
```
- **Note:** Deletes a procedural language.

### 190. **Create Extension**
```sql
CREATE EXTENSION hstore;
```
- **Note:** Installs a PostgreSQL extension.

### 191. **Drop Extension**
```sql
DROP EXTENSION hstore;
```
- **Note:** Removes an installed extension.

### 192. **Use Extension Functions**
```sql
SELECT 'foo'::hstore;
```
- **Note:** Uses a function provided by an extension.

### 193. **Create Type**
```sql
CREATE TYPE my_type AS (field1 INT, field2 TEXT);
```
- **Note:** Defines a new composite data type.

### 194. **Drop Type**
```sql
DROP TYPE my_type;
```
- **Note:** Deletes a defined composite data type.

### 195. **Create View with Aggregation**
```sql
CREATE VIEW avg_age AS SELECT AVG(age) FROM users;
```
- **Note:** Defines a view that includes an aggregation.

### 196. **Create Rule**
```sql
CREATE RULE my_rule AS ON INSERT TO users DO INSTEAD INSERT INTO audit_log (user_id) VALUES (NEW.id);
```
- **Note:** Defines a rule for redirecting specific SQL operations.

### 197. **Drop Rule**
```sql
DROP RULE my_rule ON users;
```
- **Note:** Deletes an existing rule.

### 198. **Check Database Version**
```sql
SELECT version();
```
- **Note:** Displays the version of the PostgreSQL database.

### 199. **Set Role to Superuser**
```sql
ALTER ROLE myrole WITH SUPERUSER;
```
- **Note:** Modifies a role to have superuser privileges.

### 200. **Get System Information**
```sql
SELECT * FROM pg_settings;
```
- **Note:** Displays the current system configuration settings.

---

