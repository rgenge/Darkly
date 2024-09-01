# Forgot Password Request

# Tools
Developer tools for web browser in code inspection

# How to solve it
Replace the hardcoded email in hidden field of the recovery password form

# How to protect it
- Return a consistent message for both existent and non-existent accounts.
- Ensure that responses return in a consistent amount of time to prevent an
attacker enumerating which accounts exist. This could be achieved by using
asynchronous calls or by making sure that the same logic is followed, instead
of using a quick exit method.
- Implement protections against excessive automated submissions such as
rate-limiting on a per-account basis, requiring a CAPTCHA, or other controls.
Otherwise an attacker could make thousands of password reset requests per hour
for a given account, flooding the user's intake system (e.g., email inbox or
SMS) with useless requests.
- Employ normal security measures, such as SQL Injection Prevention methods and
Input Validation.
