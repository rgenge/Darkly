# Traversal Path 

### Tools
Traversal Path using dirbuster, wfuzz and manually after not finding anything with automated tools.

### How to solve it

1. Firt we use ?page=../ and we get a message.
```
 SERVER_URL/?page=../
```
2. Later on we keep trying it until we get a different message, so we trye /etc/passswd and there is the flag! 
```
 5 UNION SELECT TABLE_NAME,NULL FROM information_schema.tables--
```
