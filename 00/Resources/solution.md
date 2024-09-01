# Admin Password Crack

### Tools

CrackStation
url/robots.txt

### How to solve it
Access robots.txt and enter in the folders shown, get the first flag.

Get the flag and put in the crackstation to get the password.

Go to {url_addres}/admin page and put login :root and found passowrd qwerty123@

### How to avoid this problem
Do not leave your robots.txt public

Protect your htpassword

Web password files such as those managed by htpasswd should not be within the
Web server's URI space -- that is, they should not be fetchable with a browser.

This program is not safe as a setuid executable. Do not make it setuid.

The use of the -b option is discouraged, since when it is used the plaintext
password appears on the command line.

When using the crypt() algorithm, note that only the first 8 characters of the
password are used to form the password. If the supplied password is longer, the
extra characters will be silently discarded.

The SHA-1 hashing format does not use salting: for a given password, there is
only one hashed representation. The crypt() and MD5 formats permute the
representation by prepending a random salt string, to make dictionary attacks
against the passwords more difficult.

The SHA-1 and crypt() formats are insecure by today's standards.

The SHA-2-based crypt() formats (SHA-256 and SHA-512) are supported on most
modern Unix systems, and follow the specification at
https://www.akkadia.org/drepper/SHA-crypt.txt.

### Source
https://httpd.apache.org/docs/2.4/programs/htpasswd.html
