### 核心定位与概念

- **协议层级：** 运行于 **网络层（Layer 3）**，对上层应用（TCP/UDP/HTTP 等）透明。
- **核心目的：** 在不安全的网络（如互联网）上建立安全的通信管道（VPN 隧道），提供**机密性（Confidentiality）、完整性（Integrity）、身份鉴别（Authentication）与防重放攻击（Anti-Replay）**。
- **本质架构：** **IPsec 不是单一协议，而是一个协议族（Framework）**，由安全协议（AH/ESP）、密钥协商协议（IKE）及密码算法组合而成。

IPsec 提供的核心安全服务包含三大项：
1. **保密性（Confidentiality）**：通过 ESP 算法加密数据。
2. **可认证性/数据源鉴别（Authentication）**：验证数据来源是否合法。
3. **完整性（Integrity）与防重放（Anti-Replay）**：防止数据在传输过程中被篡改，并利用序列号机制阻断重放攻击（Replay Attacks）。

## 原子筆記
- [[AH vs ESP]]
- [[IPsec 工作模式]]
- [[IKE 協議]]
- [[Security Association]]
- [[協定 Header]]

## 相關
- [[VPN]]
- [[OSI 七層 與 TCPIP 四層]]
- [[信息安全 - 要素]]
- [[對稱加密]]
- [[非對稱加密]]
