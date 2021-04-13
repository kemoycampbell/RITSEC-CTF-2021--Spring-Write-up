# DababyWeb
# Point: 150
# Description

Dababy wanted to share a message, but he seemed to put it too high up...

34.72.118.158:6284

Author: Darkfowl

# Solution
Visit the IP in the browser, start with the simplest steps. Are there anything stands out?
Anything in the source codes? The thing stand out for us was when clicking on
the link 'Dababy's Images', we noticed this in the url ``` http://34.72.118.158:6284/fun1.php?file=suge```

This tells us that we might be able to manipulate the the file input and based
on the description a high up would be to go back one directory up hence we
were able to solve the challenge by manipulate the link as follow

``` http://34.72.118.158:6284/fun1.php?file=../flag.txt```

# Exploit / Vulnerablity
[Local File Inclusion(LFI)](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/07-Input_Validation_Testing/11.1-Testing_for_Local_File_Inclusion)

# Flag
```yaml
RS{J3TS0N_M4D3_4N0TH3R_0N3}
```