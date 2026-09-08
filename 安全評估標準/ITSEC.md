Information Technology **Security** Evaluation Criteria
發布：歐洲四國 / 歐盟
目的：
- 改進 [[TCSEC]]  橙皮書只關注 機密性（Confidentiality）的問題
- 提出 CIA （Confidentiality, Integrity, Availability)
- 安全概念細分成 **10級 安全功能類別（Functionality Class, F）** 与 **6 級安全保證級別（Evaluation Level, E）


--- 

## 安全功能類別（Functionality Class, F）

| **編號**  | **別名 / 代號**          | **英文名稱**                                    | **核心功能需求描述**                                         |
| ------- | -------------------- | ------------------------------------------- | ---------------------------------------------------- |
| **F1**  | **F-C1**             | Discretionary Security                      | 基本自主存取控制（對應 TCSEC C1）                                |
| **F2**  | **F-C2**             | Controlled Access                           | 受控存取與審計跟踪（對應 TCSEC C2）                               |
| **F3**  | **F-B1**             | Labeled Security                            | 強制安全標記（MAC，對應 TCSEC B1）                              |
| **F4**  | **F-B2**             | Structured Protection                       | 結構化 MAC 與隱蔽通道分析（對應 TCSEC B2）                         |
| **F5**  | **F-B3**             | Security Domains                            | 高抗入侵性與安全域隔離（對應 TCSEC B3 / A1）                        |
| **F6**  | **F-IN**             | High Integrity Systems                      | **高完整性**：防止數據被未授權篡改，維護資料一致性（如數據庫 Constraints 与交易事務）。 |
| **F7**  | **F-DX** / **F-AV**  | High Availability Systems                   | **高可用性**：保障系統在中斷或故障時仍能正常運作、快速復原（適用於關鍵任務系統）。          |
| **F8**  | **F-DI**             | Data Integrity in Communications            | **通信數據完整性**：保障資料在網絡傳輸過程中的完整性與真實性（如電子簽章、防篡改）。         |
| **F9**  | **F-DC**             | High Confidentiality Communications         | **通信數據高機密性**：專注於傳輸數據的保密（如端到端加密、密鑰管理）。                |
| **F10** | **F-NX** / **F-NET** | High Confidentiality and Integrity Networks | **高安全網絡**：針對整體網絡環境，同時要求嚴格的傳輸機密性与完整性。                 |

---
## 安全保證級別（Evaluation Level, E）

| **ITSEC 級別** | **描述**                                                  |
| ------------ | ------------------------------------------------------- |
| E0           | （不合格，不計算）                                               |
| **E1**       | 功能測試（Functional Testing）                                |
| **E2**       | 方法化測試與檢查（Methodically Tested and Checked）               |
| **E3**       | 方法化設計、測試與檢驗（Methodically Designed, Tested and Reviewed） |
| **E4**       | 半形式化設計与測試（Semi-formally Designed and Tested）            |
| **E5**       | 半形式化核驗設計与測試（Semi-formally Verified Design and Tested）   |
| **E6**       | 形式化核驗設計与測試（Formally Verified Design and Tested）         |

---

## Comparison to [[TCSEC]]

| **TCSEC 等級** | **ITSEC 對應組合 (F+E)** | **說明**                  |
| ------------ | -------------------- | ----------------------- |
| **D**        | **E0**               | 無任何有效保護                 |
| **C1**       | **F1, E1**           | 自主存取控制 + 基本測試           |
| **C2**       | **F2, E2**           | 受控存取與審計 + 方法化測試与配置管理    |
| **B1**       | **F3, E3**           | 強制標記存取 + 詳細代碼與架構審查      |
| **B2**       | **F4, E4**           | 結構化 MAC + 半形式化設計        |
| **B3**       | **F5, E5**           | 安全域與高抗抗性 + 高度模組化與結構化    |
| **A1**       | **F5, E6**           | B3 級功能 + **E6 形式化數學驗證** |
