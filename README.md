# 0x1-XSS XSS tool exploitation and detection
------------------------------------------------------------

## the tool made for exploiting and detecting the xss vulnerability in URL Parametrs
---------------------------------------------------------------------------------------

# Installation & How to use?
1. `git clone https://github.com/0x1mahmoud/0x1-XSS.git`
2. `cd 0x1-XSS`
3. `python 0x1-xss.py`
4. `Enter The Target URL: Type here the full url with the vulnerable parameters such as: https://target.com?xss=1`
5. `Enter The Target URL: https://target.com?xss=1`
--------------------------------------------------------------------
## if you get something like this

```
[+] Detected 1 forms on https://www.facebook.com/profile.php?id=000000000.
False

```
### That 'cause the target url is not vulnerable
-----------------------------------------------------------------------------

## But this....

```
Enter The Target URL: http://php.testsparker.com/artist.php?id=q
[+] Detected 1 forms on http://php.testsparker.com/artist.php?id=q.
[+] XSS Detected on http://php.testsparker.com/artist.php?id=q
[*] Form details:
{'action': '/artist.php',
 'inputs': [{'name': 'id',
             'type': 'text',
             'value': "<Script>alert('hi')</scripT>"},
            {'name': None, 'type': 'submit'}],
 'method': 'get'}
True

```
### So here we have detect an xss vulnerability in parameter "?id"
# Support Me. on
#### mahmoudashrafxp@gmail.com
