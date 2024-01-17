Affected Version
ireader media-server 1.0.0 0d60f4d784fe7f19365a5b1fcf6d05c7bc5633fb

Vulnerability Description
This vulnerability is a UAF (Use-After-Free) vulnerability discovered in the file /media-server/libsip/src/uac/sip-uac-transaction.c. It could be maliciously exploited, leading to a denial-of-service attack.

ireader media-server download address
https://github.com/ireader/media-server.git

1、A Use-After-Free (UAF) vulnerability was discovered at line 256 in the file /media-server/libsip/src/uac/sip-uac-transaction.c.
A struct pointer named t is passed as the second parameter to the function named sip_uac_stop_timer, as shown in the diagram below.
![image](https://github.com/LuMingYinDetect/media-server_detect/blob/main/media-server_1.png)
Subsequently, within the sip_uac_stop_timer function, the pointer t is passed to the sip_uac_transaction_release function.
![image](https://github.com/LuMingYinDetect/media-server_detect/blob/main/media-server_2.png)
In the sip_uac_transaction_release function, the memory space pointed to by the t pointer is released at line 59.
![image](https://github.com/LuMingYinDetect/media-server_detect/blob/main/media-server_3.png)
After the pointer t is released, the program uses t->status at line 256, resulting in a Use-After-Free (UAF) vulnerability.
![image](https://github.com/LuMingYinDetect/media-server_detect/blob/main/media-server_4.png)
