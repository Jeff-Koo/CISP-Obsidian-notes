Common Criteria 2.0 版

#### **第一部分：簡介與一般模型（Part 1: Introduction and General Model）**
- **TOE（Target of Evaluation，評估目標）**：
	- 指被拿來做安全評估的 IT 產品或系統
- **PP（Protection Profile，保護輪廓）**：
	- 文檔類型
	- 買方或行業協會提出的「出題卷」
	- 說明針對「某一類產品 TOE」的安全要求
- **ST（Security Target，安全目標）**：
	- 文檔類型
	- 賣方 / 廠商的「答題卷與安全承諾書」
	- 說明該 TOE 如何滿足特定的 PP 或需求

#### **第二部分：安全功能要求（Part 2: Security Functional Requirements, SFR）**
- 承襲了 ITSEC 的安全功能理念，建立了一套極其龐大且結構化的 **安全功能組件庫**
- 9 Class / 64 Family (CC 2.0)

#### **第三部分：安全保證要求（Part 3: Security Assurance Requirements, SAR）**
- 承襲了 FC 的 E1~E7 理念，定義了安全保證的組件，並組合出了全球通用的 **EAL1 ～ EAL7（Evaluation Assurance Levels，評估保證級別）**
- 7 Class / 29 Family (CC 2.0)
- 常用 **EAL4** 作為商用分水嶺

| **EAL 級別** | **名稱**                                                       | **相當於前身標準**            | **核心要求**                                            |
| ---------- | ------------------------------------------------------------ | ---------------------- | --------------------------------------------------- |
| **EAL 1**  | **Functional Tested（功能測試級）**                                 | _(CC 獨有)_              | 基本的產品安全性分析，無須廠商提供原始碼。                               |
| **EAL 2**  | **Structurally Tested（結構化測試級）**                              | ITSEC E1 / FC E1       | 需求配置管理，進行基本的功能與架構測試。                                |
| **EAL 3**  | **Methodically Tested and Checked（方法化測試與檢查級）**               | ITSEC E2 / FC E2       | 加入環境控制、發布流程控制與漏洞分析。                                 |
| **EAL 4**  | **Methodically Designed, Tested and Reviewed（方法化設計、測試與審查級）** | ITSEC E3 / FC E3       | **商業產品最高常用等級**（如 Windows, Linux），需要全面的原始碼抽查與獨立穿透測試。 |
| **EAL 5**  | **Semi-formally Designed and Tested（半形式化設計與測試級）**            | ITSEC E4-E5 / FC E4-E5 | 引入半形式化模型，進行嚴苛的模組化與獨立性分析。                            |
| **EAL 6**  | **Semi-formally Verified Design and Tested（半形式化核驗設計與測試級）**   | FC E6                  | 全系統半形式化分析，針對高風險環境的模組化結構控制。                          |
| **EAL 7**  | **Formally Verified Design and Tested（形式化核驗設計與測試級）**         | ITSEC E6 / FC E7       | 最高等級，必須經過嚴格的**數學邏輯形式化證明（Formal Verification）**。     |

## 相關
- [[FC]]
- [[ITSEC]]
- [[TCSEC]]
- [[常見分級]]
- [[安全評估標準]]



