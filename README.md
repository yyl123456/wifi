# wifi


https://github.com/6174/ppurl/blob/793fc9da09e11b1406760effa54c714aaad32e71/data/58.md?plain=1#L75
https://github.com/WHJWNAVY/WIFI-DOCS/blob/48d23a2ec8268a098b16e2fa3e14de3e0b966686/IEEE-802.11/



wifi流程：

1、wep（4次auth）

2、2次auth -> 2次assoc -> eapol四次握手（personal）

3、2次auth -> 2次assoc -> 多次握手（enterprise、EAP之上的802.1X）（可能涉及到TLS）


四次握手RSN：TKIP（WPA）、CCMP（WPA2）、SAE（WPA3）
  



1、LL层和SUPP SM层交互变量
LL层和SUPP SM层的交互比较简单，主要包括三个步骤。

LL层收到EAP数据包后，将其保存在eapReqData变量中，然后设置eapReq变量为TRUE。这个变量的改变对SUPP SM层来说是一个触发信号（signal）。SUPP SM可能会发生状态转换。
SUPP SM层从eapReqData中取出数据后进行处理。如果有需要回复的数据，则设置eapResp值为TRUE，否则设置eapNoResp值为TRUE。回复数据存储在eapRespData中。LL层将发送此回复包。
如果SUPP SM完成身份验证后，它将设置eapSuccess或eapFailure变量以告知LL层其验证结果。eapSuccess为TRUE，表明验证成功。eapFailure为TRUE，则验证失败。
