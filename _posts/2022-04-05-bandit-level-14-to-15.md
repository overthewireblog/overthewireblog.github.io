---
layout: post
author: mike
series: bandit
categories: bandit 
---
### Level 14 -> 15
#### Game Instructions
> The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

This one we don't SSH into. We stay logged in from the last exercise and use that to send the string to port **30000** to see if we can get the next password.

Previous password: 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

Let's use `nc` to try to connect on port **30000**.
** Using `-v` flag to give us a little feedback
`nc localhost 30000`
You should get an **open** message.
Now we paste the password:
`4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e`
Hit enter and bam: `BfMYroe26WYalil77FoDi9qh59eK5xNr`
