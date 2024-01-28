# Cookie 

### Tools
Developer Tools from web browser in Storage tab

### How to solve it

1. Firt we access the page and check there is a cookie and then we click check in developer tools/storage page that we can change it:
```
I_am_admin=68934a3e9455fa72420237eb05902327
```
2. Later on we use Crackstation and get "false" string, so we do reverse and get true in MD5 and boom the flag shows up when you refresh it.
```
I_am_admin=b326b5062b2f0e69046810717534cb09
```
### How to protect it
Use HTTPS to encrypt or your data
If possible never put confidential information in the frontend

