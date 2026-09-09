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


**ARP (Address Resolution Protocol，地址解析協議)：** **IP 地址** ➡️ **MAC 地址**。
**RARP (Reverse ARP，反向地址解析協議)：** **MAC 地址** ➡️ **IP 地址**。

假設在同一個 LAN 本地局域網（`192.168.50.0/24`）裡有兩台電腦，我們給它們設定具體的 MAC 地址：
- **電腦 A：** IP = `192.168.50.11` | MAC = `AA:AA:AA:11:11:11`
- **電腦 B：** IP = `192.168.50.44` | MAC = `BB:BB:BB:44:44:44`

使用 **ARP：** 「我是 `192.168.50.11`，請問 **`192.168.50.44` 的 MAC** 是多少？」
使用 **RARP：** 「我是 **`BB:BB:BB:44:44:44`**，請問**我的 IP** 是多少？」


### 解析与 IPsec 理论对比

#### 1. 为什么 D 选项错误（符合题意）？

IPsec 提供的核心安全服务包含三大项：
1. **保密性（Confidentiality）**：通过 ESP 算法加密数据。
2. **可认证性/数据源鉴别（Authentication）**：验证数据来源是否合法。
3. **完整性（Integrity）与防重放（Anti-Replay）**：防止数据在传输过程中被篡改，并利用序列号机制阻断重放攻击（Replay Attacks）。


IPsec 的两大核心协议 **AH（认证头协议）** 和 **ESP（封装安全载荷协议）**，均可以与 **传输模式（Transport Mode）** 和 **隧道模式（Tunnel Mode）** 自由组合搭配使用。


### IPsec 模式对比速记表

| **维度**     | **传输模式 (Transport Mode)** | **隧道模式 (Tunnel Mode)**                      |
| ---------- | ------------------------- | ------------------------------------------- |
| **保护范围**   | 仅保护 **IP Payload**        | 保护 **整个原始 IP 数据包（IP Header + Payload）**     |
| **IP 头处理** | 保留原 IP 头                  | 隐藏原 IP 头，叠加 **新 IP 头（New IP Header）**       |
| **典型场景**   | 主机到主机（Host-to-Host）直接加密通信 | 站点到站点（Site-to-Site / Gateway-to-Gateway）VPN |
