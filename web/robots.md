# Robots
# Points: 100

# Description
Robots are taking over. Find out more.

34.69.61.54:5247

Author: f1rehaz4rd

# Solution
Open 34.69.61.54:5247 in the browser then read the page for any clues.
As a rule of thumbs, I like to start simple first so I decided to view the page
source code. There was a flag.txt and I decided to append that to the url
to see if it could yield anything. Turned out it was just a distraction that was 
encoded with base64 twice which reads 'Robots are taking over...'

After looking around a bit, it clicks to check for robots.txt. In the robots.txt
we see a bunch of what is allowed and what is not allowed. There was
one particular line that stood out

        Allow: /flag/UlN7UjBib3RzX2FyM19iNGR9

My teammate was able to figure out that this is a base64 so decrypted that we get
the true flag

# Flag
```yaml
    RS{R0bots_ar3_b4d}
```