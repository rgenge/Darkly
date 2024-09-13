# Unrestricted file upload

# Tools
Developer Tools from web browser

# How to solve it

In OWASP was found the follwing warning:

“Content-Type” Header Validation

“Content-Type” entity in the header of the request indicates the Internet media
type of the message content. Sometimes web applications use this parameter in
order to recognise a file as a valid one. For instance, they only accept the
files with the “Content-Type” of “text/plain”.

It is possible to bypass this protection by changing this parameter in the
request header using a web proxy.

When inspecting the request of an invalid file (php file in this case), the
content type was edited in the reques and the request was resend, which
activated the flag.
