**Trusted** Computer System Evaluation Criteria
發布：美國國防部（DoD）
目的：圍繞**機密性（Confidentiality）**展開，旨在解決處理敏感或機密數據時的**安全需求**

## TCSEC 的四大核心評估要求

1. **安全策略（Security Policy）**
* 系統必須明確定義訪問控制規則，明確說明哪些主體（User/Process）對哪些客體（File/Resource）擁有何種操作權限。
* 支持**自主訪問控制（DAC）**和**強制訪問控制（MAC）**。


2. **可標記性 / 責任認定（Accountability）**
* 系統必須能夠識別並驗證每個用戶的身份（身份鑒別）。
* 必須包含審計（Audit）機制，記錄所有與安全相關的事件，確保用戶的行為可追蹤、可核查。


3. **安全保證（Security Assurance）**
* 系統必須通過嚴格的測試和分析，確保安全機制能夠按既定策略可靠運行，不被輕易繞過或破壞。
* 包含對可信計算基（TCB, Trusted Computing Base）的結構設計、測試及形式化驗證要求。


4. **文檔支持（Documentation）**
* 必須提供完整的安全文檔，包括：用戶安全指南、管理員規程、測試文檔、系統設計說明以及安全策略模型文檔。



---

## TCSEC 的安全等級分類（4類7級）


TCSEC 將計算機系統的安全等級從**低到高**劃分為 **D、C、B、A** 四個大類，共計 **7 個子級別**：

| 大類             | 級別     | 級別名稱                                          |
| -------------- | ------ | --------------------------------------------- |
| **D 類**        | **D**  | **Minimal Protection（最小保護 / 無保護級）**           |
| **C 類**(自主保護)  | **C1** | **Discretionary Security Protection（自主安全保護）** |
|                | **C2** | **Controlled Access Protection（受控訪問保護）**      |
| **B 類** (強制保護) | **B1** | **Labeled Security Protection（標記安全保護）**       |
|                | **B2** | **Structured Protection（結構化保護）**              |
|                | **B3** | **Security Domains（安全域）**                     |
| **A 類**(驗證保護)  | **A1** | **Verified Design（驗證設計級）**                    |
