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
### How to protect it

Input invalidation is the best way to protect against it with a list of authorized words and tags.

Cross-Site Scripting (XSS) is a misnomer. Originally this term was derived from early versions of the attack that were primarily focused on stealing data cross-site. Since then, the term has widened to include injection of basically any content. XSS attacks are serious and can lead to account impersonation, observing user behaviour, loading external content, stealing sensitive data, and more.

Framework Security

Fortunately, applications built with modern web frameworks have fewer XSS bugs, because these frameworks steer developers towards good security practices and help mitigate XSS by using templating, auto-escaping, and more. However, developers need to know that problems can occur if frameworks are used insecurely, such as:

    escape hatches that frameworks use to directly manipulate the DOM
    React’s dangerouslySetInnerHTML without sanitising the HTML
    React cannot handle javascript: or data: URLs without specialized validation
    Angular’s bypassSecurityTrustAs* functions
    Lit's unsafeHTML function
    Polymer's inner-h-t-m-l attribute and htmlLiteral function
    Template injection
    Out of date framework plugins or components
    and more

When you use a modern web framework, you need to know how your framework prevents XSS and where it has gaps. There will be times where you need to do something outside the protection provided by your framework, which means that Output Encoding and HTML Sanitization can be critical. OWASP will be producing framework specific cheatsheets for React, Vue, and Angular.

# Source
https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html
