| **OSI 七層** | **層級名稱 (Layer)**          | **主要功能**                         | **常見協議 / 技術**                                  | **數據單位 (PDU)**                 | **TCP/IP 四層**                                      |
| ---------- | ------------------------- | -------------------------------- | ---------------------------------------------- | ------------------------------ | -------------------------------------------------- |
| **L7**     | **應用層**<br>(Application)  | 直接為用戶或應用程式提供網絡服務與接口。             | HTTP, HTTPS, FTP, SSH, DNS, SMTP               | 數據 (Data)                      | **應用層**<br><br>  <br>  <br><br>(Application Layer) |
| **L6**     | **表示層**<br>(Presentation) | 負責數據格式轉換、加密解密及數據壓縮，確保系統間數據可讀。    | SSL/TLS, JPEG, ASCII, JSON, XML                | 數據 (Data)                      | ^                                                  |
| **L5**     | **會話層**<br>(Session)      | 建立、管理與終止應用程式之間的通信會話與連接。          | NetBIOS, RPC, PPTP                             | 數據 (Data)                      | ^                                                  |
| **L4**     | **傳輸層**<br>(Transport)    | 提供端到端的數據傳輸服務、流量控制、重傳機制與端口定址。     | TCP, UDP, socket                               | 數據包 (Segment) / 數據報 (Datagram) | **傳輸層**<br>(Transport Layer)                       |
|            |                           | ⬆️ 主機                            |                                                |                                |                                                    |
|            |                           | ⬇️ 網路                            |                                                |                                |                                                    |
| **L3**     | **網絡層**<br>(Network)      | 負責跨網絡的路徑選擇（路由）與邏輯定址。             | IPv4, IPv6, ICMP, OSPF, BGP<br><br>_(設備: 路由器)_ | 封包 (Packet)                    | **互聯網際層**<br>(Internet Layer)                      |
| **L2**     | **數據鏈路層**<br>(Data Link)  | 負責同一局域網絡內的實體定址（MAC 地址）、幀同步與差錯檢測。 | Ethernet, Wi-Fi (802.11), ARP, RARP, VLAN      | 幀 (Frame)                      | **網絡接口層**<br>(Network Access Layer)                |
| **L1**     | **物理層**<br>(Physical)     | 負責在實體介面上传輸原始的二進制位元流（Bitstream）。  | 光纖, 雙絞線 (RJ45), 藍芽, 交換機, 集線器                   | 位元 (Bit)                       | ^                                                  |

## 相關原子筆記
- [[ARP 與 RARP]]
- [[TCP vs UDP vs IP]]
- [[協定 Header]]
- [[網絡安全問題]]
- [[VPN]]
- [[IPsec]]
