# wifi


https://github.com/6174/ppurl/blob/793fc9da09e11b1406760effa54c714aaad32e71/data/58.md?plain=1#L75
https://github.com/WHJWNAVY/WIFI-DOCS/blob/48d23a2ec8268a098b16e2fa3e14de3e0b966686/IEEE-802.11/



# wifi流程：

1、wep（4次auth）

2、2次auth -> 2次assoc -> eapol四次握手（personal）

3、2次auth -> 2次assoc -> 多次握手（enterprise、EAP之上的802.1X）（可能涉及到TLS）

4、SAE

        sim   4次auth（计算PMKID）       -> 2次assoc -> eapol四次握手（personal）
  
        open  2次auth（使用之前的PMKID） -> 2次assoc -> eapol四次握手（personal）


四次握手RSN：TKIP（WPA）、CCMP（WPA2）、SAE（WPA3）
  


# wpa_supplicant  
LL层、SUPP SM层、EAP SM层
