### 四种 Header 核心属性对比表

| **Header 名称**               | **协议层级**            | **核心作用与职责**               | **是否包含端口号？** | **是否包含加密/安全字段？** |
| --------------------------- | ------------------- | ------------------------- | ------------ | ---------------- |
| **IP Header** _(IPv4/IPv6)_ | **网络层（Layer 3）**    | 负责**跨网段路由寻址**与数据包的分片重组    | ❌            | ❌（仅提供基础校验和）      |
| **AH Header** _(IPsec)_     | **网络层（Layer 3 拓展）** | 提供**数据完整性校验、数据源身份认证、防重放** | ❌            | ✅（但不包含数据加密功能）    |
| **TCP Header**              | **传输层（Layer 4）**    | 提供**面向连接、可靠的、按序**的端到端流控制  | ✅            | ❌                |
| **UDP Header**              | **传输层（Layer 4）**    | 提供**无连接、不可靠、低延迟**的数据报传输   | ✅            | ❌                |

### 各 Header 关键字段与结构解析

#### IP Header - *IPv4 IPv6*（Layer 3）

- **标准长度：** 20 字节（不含 Options 选项）。
- **关键字段：**
    - **Source IP / Destination IP（源/目的 IP）：** 标识通信两端的网络地址。
    - **Protocol（协议号）：** 标识上层载荷类型（如 `6` 代表 TCP，`17` 代表 UDP，`51` 代表 AH，`50` 代表 ESP）。
    - **TTL（Time to Live，生存时间）：** 防止数据包在路由器间死循环，每经过一个路由器减 1。

#### AH Header - *IPsec* （Layer 3 Extension）

- **标准长度：** 通常为 24 字节或 32 字节（取决于生成的 ICV 哈希长度）。
- **关键字段：**
    - **Next Header（下一个头）：** 标识 AH 后面紧跟的是什么协议（如 TCP/UDP 或 ESP）。
    - **SPI（Security Parameters Index，安全参数索引）：** 结合目的 IP 和协议号，**唯一标识一条 IPsec SA**。
    - **Sequence Number（序列号）：** 递增数字，用于**防重放攻击（Anti-Replay Attack）**。
    - **ICV（Integrity Check Value，完整性校验值）：** 使用 HMAC（如 HMAC-SHA256）对 **整个 IP 报文（除去传输中会变的 TTL/Checksum 字段）** 计算得出的哈希摘要，用于**防篡改**。

#### TCP Header（Layer 4）
- **标准长度：** 20 字节（不含 Options 选项）。
- **关键字段：**
    - **Source Port / Destination Port（源/目的端口）：** 标识具体的上层应用程序（如 80、443）。
    - **Sequence Number / Acknowledgment Number（序号 / 确认号）：** 保障数据的顺序传输与可靠确认。
    - **Flags（控制标志位）：** `SYN`（建立连接）、`ACK`（确认）、`FIN`（释放连接）、`RST`（重置）等。
    - **Window Size（滑动窗口大小）：** 用于流量控制。

#### UDP Header（Layer 4）
- **标准长度：** 仅 **8 字节**（非常精简，开销极小）。
- **关键字段：**
    - **Source Port / Destination Port（源/目的端口）：** 区分应用进程。
    - **Length（长度）：** Header + Data 的总字节数。
    - **Checksum（校验和）：** 可选的基础数据错误检测。

### 在 IPsec 中的封装顺序（经典考点）

当数据从传输层向下传递，并启用 **AH 协议（传输模式 Transport Mode）** 时，报文头的嵌套结构如下：

```
+------------------+-----------------+------------------+-----------------+
|  原 IP Header    |    AH Header    |   TCP/UDP Header |    Payload      |
| (Protocol = 51)  | (NextHeader=6/17|                  |    (Data)       |
+------------------+-----------------+------------------+-----------------+
|<---------------------- AH 校验范围（防篡改） -------------------------->|
```

> **注意：**
> 1. AH Header 会插入在 **原 IP Header** 与 **传输层 Header（TCP/UDP）** 之间。
> 2. AH 对**包括外层 IP 头在内的绝大部分报文**计算 ICV 签名，因此它**不允许改变 IP 地址（与 NAT 冲突，即 NAT 穿透不兼容）**，且**不提供数据加密（明文可见）**。

## 相關
- [[OSI 七層 與 TCPIP 四層]]
- [[TCP vs UDP vs IP]]
- [[AH vs ESP]]
- [[IPsec]]
- [[Security Association]]
