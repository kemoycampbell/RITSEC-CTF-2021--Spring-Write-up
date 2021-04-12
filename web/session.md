# Sessions
# Points: 100
#Description
Find the flag.

http://34.69.61.54:4777

Author: f1rehaz4rd

# Solution
Visit the link mentioned in the description. As general rule of thumb, start simple.
Check the web page if we can locate anything critical. By observing the page
we saw that we will need to login. However, we dont know the username and password.
Before we go all fancy, launch SQL injection and other attack vectors, we want to start
simple and work our way up.

With that being said, we decided to check the source code and surely there was this
```html
  <!--#remove comment later: login iroh:iroh-->
```

Surely enough the cred was in the html and we were able to login. After login
we search around for any useful information but there were not any on the pages
other than some distractions and some laughs :-)

However, as we continue to poke around, we eventually noticed that the session was
```yaml
    Cookie: sessiontoken=UlN7MG5seV9PbmVfczNzc2lvbl90b2szbn0=
```

After identifying the type of hash/cipher, it turned out to be base 64. You can use an
cipher identifier

After decoding the cookie we got the flag!

#Flag

```yml
RS{0nly_One_s3ssion_tok3n}
```