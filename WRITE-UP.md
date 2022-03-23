# Chosen language

What language did you choose for the exercise?

- I've chosen Python

# \#1

## Description

Discovered Cross-Site Scripting (XSS) Vulnerability. Also, can be modified as Improper Neutralization of Input During Web Page Generation (Cross-site Scripting).
once I have created a user and then logged in. Then I review the source code of the "appsec-exercise.py" and i noticed that the username self parameter so i have executed the XSS payload by using "img" method example: `<img src=x onclick=alert(1)>` which I was able to print the "user cookie"
In CWE:
- CWE-79: Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')


## Impact

The Impact of XSS vulnerability is it can let the attacker control a script like JavaScript or HTML and executed a malicious javascript code
in the victim's browser then the attacker can fully compromise that user. For example, the attacker can steal the user's cookies.

## Exploitation

In XSS I've used the following payload:

```
http://127.0.0.1:8080/hackerone=%3Cimg%20src=pop%20onerror=alert(document.cookie)%3E
```

## Fix

A ways of fixing XSS Vulnerability:
- Sanitize data input and ensuring all data is validated, filtered or escaped before echoing anything back to the user.
- Give users the option to disable client-side scripts.
- Redirect invalid requests.
- Using the following: html.escape, render_template

# \#2


## Description

Discovered Server-Side Template Injection (SSTI) Vulnerability. Also, it can be modified as Improper Neutralization of Directives in Statically Saved Code (Static Code Injection).
i was a user and able to access the application configuration from templates "config" by executing the SSTI payload once I have entered.
As well as I confirm that it prints the "id" command and it's print "root".
In CWE:
- CWE-96: Improper Neutralization of Directives in Statically Saved Code ('Static Code Injection')

## Impact

The Impact of Server-Side Template Injection (SSTI) or Static Code Injection Vulnerability, The attacker can do a remote code execution (RCE) then he takes full control of the back-end server.
Even without the code execution, the attacker may be able to read sensitive data on the server.

## Exploitation

In Server-Side Template Injection (SSTI) or Static Code Injection I've used the following payload:

```
1- curl "http://127.0.0.1:8080/hackerone=%7B%7Bconfig%7D%7D"
2- curl "http://127.0.0.1:8080/hackerone=%7B%7Brequest.application.__globals__.__builtins__.__import__('os').popen('id').read()%7D%7D"
```

## Fix

Ways of fixing Server-Side Template Injection (SSTI) Vulnerability:

- The Templates should not be created from user-controlled input. User input should be passed to the template using template parameters.
- Sandboxing: execute user’s code in a sandboxed environment; though some of these environments can be bypassed, they are still considered a protection mechanism to reduce the risk of the SSTI vulnerability.
