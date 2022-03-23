# Chosen language

What language did you choose for the exercise?

- I've chosen Python

# \#1

## Description

I've discovered Cross-Site Scripting (XSS) Vulnerability. Also, can be modified as Improper Neutralization of Input During Web Page Generation (Cross-site Scripting).
once I have created a user and then logged in. I saw I can access the other users by just typing their username Instead of my username.
Then I saw the source code the username self parameter so i have executed the XSS payload which I was able to print the "user cookie" in the attached picture
In CWE:
- CWE-79: Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')


## Impact

The Impact of XSS vulnerability is it can let the attacker control a script like JavaScript or HTML and executed a malicious javascript code
in the victim's browser then the attacker can fully compromise that user. For example, the attacker can steal the user's cookies.

## Exploitation

1- In XSS I've used the following payload:

```
http://127.0.0.1:8080/hackerone=%3Cimg%20src=pop%20onerror=alert(document.cookie)%3E
```

## Fix

How would you fix this vulnerability? Provide a code snippet.

# \#2


## Description

I discovered Server-Side Template Injection (SSTI) Vulnerability. Also, it can be modified as Improper Neutralization of Directives in Statically Saved Code (Static Code Injection).
i was a user and able to see the DB config by executing the SSTI payload once I have entered I saw the configuration
As well as I confirm that it prints the ID command and I saw it's a "root" in the attached picture
In CWE:
- CWE-96: Improper Neutralization of Directives in Statically Saved Code ('Static Code Injection')

## Impact

The Impact of Server-Side Template Injection (SSTI) or Static Code Injection, The attacker can do a remote code execution (RCE) then he takes full control of the back-end server.
Even without the code execution, the attacker may be able to read sensitive data on the server.

## Exploitation

In Server-Side Template Injection (SSTI) or Static Code Injection I've used the following payload:

```
1- curl "http://127.0.0.1:8080/hackerone=%7B%7Bconfig%7D%7D"
2- curl "http://127.0.0.1:8080/hackerone=%7B%7Brequest.application.__globals__.__builtins__.__import__('os').popen('id').read()%7D%7D"
```

## Fix

How would you fix this vulnerability? Provide a code snippet.
