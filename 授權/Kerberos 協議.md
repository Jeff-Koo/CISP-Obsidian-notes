Terms:
- **AS** - Authentication Service: 身份验证服务
- **KDC** - Key Distribution Center : 對稱式加密與金鑰分發中心，根據需求生成 TGT / SGT
- **TGT** - Ticket-Granting Ticket
- **SGT** - Service-Granting Ticket


Kerberos是一個使用對稱式加密與金鑰分發中心（KDC, Key Distribution Center）的網路身份驗證協定。

在 Kerberos 协议架构中，单点登录（SSO）的核心机制是用户在 KDC（密钥分发中心）通过一次身份认证后，获得由 KDC 颁发的**安全凭证（Ticket / 票据）**。

在标准的 **Kerberos v5** 协议认证体系中，主要涉及 **两类核心 Ticket（票据）**。

---

### 1. TGT（Ticket-Granting Ticket，票据授予票据）

* **生成者：** 由 KDC 中的 **AS（Authentication Service，身份验证服务）** 颁发。
* **作用：** 相当于用户的 **“初始通行证 / 入场券”**。
* **工作逻辑：** 用户输入密码完成初始身份认证后，AS 会发给客户端一个 TGT。持有有效 TGT 的用户，在后续申请访问各个具体业务服务（如文件共享、数据库等）时，**无需再次输入密码**，直接用 TGT 去找 TGS 换取具体的服务票据。
* **加密机制：** TGT 是用 **KDC 的密钥（krbtgt 账户的密码哈希）** 加密的，客户端无法解密或篡改，只能原封不动地交还给 KDC 进行验证。

---

### 2. ST / Service Ticket / SGT / Service-Granting Ticket（服务票据）

*(注：你提到的 Service Grant Ticket 在标准术语中通常直接称为 **Service Ticket (ST)** 或 **Service-Granting Ticket**)*

* **生成者：** 由 KDC 中的 **TGS（Ticket Granting Service，票据授予服务）** 颁发。
* **作用：** 针对 **某一个具体应用服务（如 HTTP、SMB、MSSQL 等）的专有门票**。
* **工作逻辑：** 当客户端想访问特定服务器 `Server-A` 时，会将 TGT 发送给 TGS，TGS 验证无误后，颁发一张专门针对 `Server-A` 的 ST。客户端拿到 ST 后，直接展示给 `Server-A` 完成身份鉴别并获取资源。
* **加密机制：** ST 是用 **目标服务账户（Service Account，即 SPN 对应的账户密码哈希）** 加密的。只有目标服务器能解密它，KDC 和目标服务器以外的任何人（包括客户端）都无法解密。

---

### 总结与交互流程对比

| 票据名称                       | 简称           | 颁发角色        | 接收/验证角色              | 核心用途                                  |
| -------------------------- | ------------ | ----------- | -------------------- | ------------------------------------- |
| **Ticket-Granting Ticket** | **TGT**      | AS（身份验证服务）  | TGS（票据授予服务）          | 证明用户已登录，用于换取各个服务的 ST（实现 **SSO 单点登录**） |
| **Service Ticket**         | **ST / SGT** | TGS（票据授予服务） | 应用服务器（Target Server） | 证明用户有权访问该具体服务，用于 **资源访问鉴权**           |

> **CISP 考点联想：**
> Kerberos 的核心优势就是利用 **TGT 实现了“一次登录，多次换票（ST）”**，从而避免了用户的明文密码在网络中频繁传输，也是 Windows Active Directory（AD 域）默认的集中身份认证协议。

## 相關
- [[對稱加密]]
- [[Windows 系統用戶]]
- [[Radius 協議]]
- [[TACACS+ 協議]]
- [[PKI 公鑰基礎設施]]



