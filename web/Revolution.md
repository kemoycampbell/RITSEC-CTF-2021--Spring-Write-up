# Revolution
# Points: 250
# Description

The robots are taking over. They are posting their propaganda everywhere. Go here to find out more about it.

34.69.61.54:8799

You will need a valuable piece of information from the 'robots' challenge.

All the other information you should need is on the root page. You need to craft a message to send to the leaders of the revolution to let them know your safe to talk to. They have made it sort of cryptic so that not everyone can access it. You will need to use the words on the page in order to figure out how to get a response from them.

They expect a special type of request and only have the ability to read plain text from a special agent. ONLY SEND PLAIN TEXT DATA.

THE HINTS ARE FREE.

Author: f1rehaz4rd

# Solution
This challenge requires solving the [robots challenge](robots.md). First thing first,
we always start with the basic by visiting the IP provides, check out the pages, source codes
to see if there is anything we could exploit or use to our advantage.

When we read the description, we are told that
- only a specific agent is accepted and we got that from the robots challenge
    - ``User-agent: Robot-Queto-v1.2``
- only accepting PLAIN TEXT
  - ```Content-Type: text/plain```
    
- Crafted message and part of the hint was to use your 'head 2'
    - head 2 was actually a coded message for send what is in h2 on the web page
    - ```FriendlyCaringLawsProtectNote```
    
The url to sent was some guess work
```/revolution```

In my case, I simple craft the response using Curl, I had to try POST and was shown 
that only specific request was accepted namely OPTION and UNLOCK so I set my curl accordingly

```curl -v -X UNLOCK 'http://34.69.61.54:8799/revolution' -H 'Content-Type:plain/text' -A 'Robot-Queto-v1.2' --data "FriendlyCaringLawsProtectNote"```

# Exploit / Vulnerability
This is one is probably a combination of weak authentication/poor authentication/authorization and disclosure

[Poor Authorization & Authentication](https://owasp.org/www-project-mobile-top-10/2014-risks/m5-poor-authorization-and-authentication)

# Flag
```RS{W3lc0me_t0_th3_R3volut1on} ```


