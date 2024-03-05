# Feedback XSS Injection

### Tools
Developer Tools from web browser

### How to solve it

1. Firt we access the feedback page and try to use cross site scripting in the message area
2. http://10.0.0.155/?page=feedback
3. Then we try <script>alert("xss")</script> and we can see that script tags are working someowhat being read.
4. Then we try : data:text/html,<script>alert("42")</script> and nothing happens.
5.  So now we are close, but now we put only , <script>alert</script> and it works.
7.  And then it gives the flag is : 0fbb54bbf7d099713ca4be297e1bc7da0173d8b3c21c1811b916a3a86652724e
```
<option value="165">1</option>
```
### How to protect it

Input invalidation is the best way to protect against it with a list of authorized words and tags.

