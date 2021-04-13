# Data Breach
# Point: 150
# Description
Data Breach
175
Please DO NOT subscribe Geno's email to data breach identification services! This includes AVAST HACK CHECK, AUTHLOGICS, HAVE I BEEN PWNED, SCATTERED SECRETS, INTELLIGENCE X, FIREFOX MONITOR, etc. These will not help you solve the challenge.

Please DO NOT attempt to reset the password for any accounts or social engineer the characters. We have taken action to prevent this in the future and your activity will likely be flagged as malicious by the account providers.

Please DO NOT like, follow, connect with, or contact any characters on any platforms. You will not get a response and it will not help you solve the challenge.

Oh no! Geno’s email was involved in a data breach! What was his password? Author: t0uc4n

# Solution
If you have been around for in cybersecurity or CTF for a while, you would know the go to would be password breach checker sites like
have I been pwnd and among other. However, for this challenge none of those work. It turned out that the solution is a much simpler one

copy geno's email from the linkedin that we obtained in [geno challenge](geno.md) then select google to set just geno email search result and
we get this [Ackaria National Security Service](https://nss.ackaria.xyz/)

By doing a quick find, we noticed his creds in the breach
```email=incogeno@gmail.com:password=StartedFromTheBottom! ```

# Flag
RS{StartedFromTheBottom!}