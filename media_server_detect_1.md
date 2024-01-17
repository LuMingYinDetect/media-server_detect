Affected Version
ireader media-server 1.0.0 0d60f4d784fe7f19365a5b1fcf6d05c7bc5633fb

Vulnerability Description
This vulnerability is a UAF (Use-After-Free) vulnerability discovered in the file /media-server/libsip/src/uac/sip-uac-transaction.c. It could be maliciously exploited, leading to a denial-of-service attack.

ireader media-server download address
https://github.com/ireader/media-server.git

1、A Use-After-Free (UAF) vulnerability was discovered at line 256 in the file /media-server/libsip/src/uac/sip-uac-transaction.c.
! [text ] (https://github.com/LuMingYinDetect/media-server_detect/blob/main/media-server_1.png)
