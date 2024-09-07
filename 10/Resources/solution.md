# Client Side URL Redirect

# Tools
Developer tools for web browser in code inspection

# How to solve it
By checking the links to social networks, it was identified a redirect variable
defined in tthe browser:
For example, the Facebook is:
index.php?page=redirect&site=facebook

We changed the name of the site to other and got the flag:
http://192.168.0.8/index.php?page=redirect&site=other

It seems that the site uses a dangerous redirect, as defined in the OWASP
cheatsheet for Unvalidated Redirects:

Dangerous URL Redirects
The following examples demonstrate unsafe redirect and forward code.

The following PHP code obtains a URL from the query string (via the parameter
named url) and then redirects the user to that URL. Additionally, the PHP code
after this header() function will continue to execute, so if the user configures
their browser to ignore the redirect, they may be able to access the rest of
the page.

```
$redirect_url = $_GET['url'];
header("Location: " . $redirect_url);
```

# Source
https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html