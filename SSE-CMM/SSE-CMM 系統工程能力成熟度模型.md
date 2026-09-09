---
tags:
  - Security/Framework
  - ISO/IEC-21827
  - Engineering/CMM
  - Note/MOC
aliases:
  - SSE-CMM
  - ISO 21827
date_created: 2026-09-09
---

# SSE-CMM (System Security Engineering CMM)

> **核心定義**：SSE-CMM（ISO/IEC 21827）是一個用於衡量「系統安全工程」能力成熟度的**二維正交模型**（Two-dimensional orthogonal model）。

---

## 核心理念

1. **安全貫穿系統工程全生命周期**  
   安全工程不能與軟體／硬體／網路通信工程割裂「分別規劃」；須融入整體開發、建設與運維，統一規劃實施。

2. **與專案干係方交互**  
   涵蓋組織內部，以及**外部開發商**、**集成商**、**第三方供應商**的協調配合。

3. **從經驗走向可量化學科**  
   推動安全工程由「憑經驗、不規範」轉為確定、成熟、可量化評估的工程學科。

4. **雙維度影響組織級活動**  
   「過程（Domain／域）」與「能力（Capability）」不只涵蓋技術安全，也延伸到管理機制、資源保障與過程改進。

---

## 📐 二維正交架構 (Architecture)

SSE-CMM 將「安全工程內容」與「管理能力品質」進行完全解耦：

```
Y-Axis: Capability Dimension (How well)
			▲
			│ Level 5: Continuously Improving
			│ Level 4: Quantitatively Controlled
			│ Level 3: Well-Defined
			│ Level 2: Planned & Tracked
			│ Level 1: Performed Informally
			└─────────────────────────────► X-Axis: Process Dimension (What)
			  PA01 ... PA04 Assess Risk ... PA21
```


### 1. X 軸：過程維度 (Process Dimension) — *做什麼 (What)*
* **目的**：定義系統安全工程的**業務範疇**。
* **組成**：
  * **[[Process Area (PA) | PA (過程域)]]**：共 21 個 PA（例如 `PA04 Assessment Security Risk`）。
  * **[[Base Practice (BP) | BP (基本實踐)]]**：組成 PA 的最小工程單元，回答「要做哪些具體動作」。

### 2. Y 軸：能力維度 (Capability Dimension) — *做得有多好 (How Well)*
* **目的**：衡量該 PA 的**管理成熟度與制度化深度**。
* **階層結構**：
  $$\text{Level (能力級別)} \longrightarrow \text{CF (通用特徵)} \longrightarrow \text{GP (通用實踐)}$$

> [!NOTE] 階層關係剖析
> * **Level (Level 0 ~ 5)**：整體成熟度門檻。
> * **CF (Common Features)**：Level 內部的**邏輯管理分類/目錄**（如：規劃、驗證、追蹤）。
> * **GP (Generic Practices)**：跨所有 PA **通用**的**硬性管理要求與評估標準**。

---

## 📊 縱軸 Capabilities (Level 0 ~ 5)

| Level | 名稱 | 關鍵特徵 | 包含的 CF (Common Features) |
| :--- | :--- | :--- | :--- |
| **Level 0** | **Non-Performed** | 未執行或成果不足 | 無 |
| **Level 1** | **Performed Informally** | 英雄主義，完成 BP 但無制度 | CF 1.1 基本執行 (Base Practices) |
| **Level 2** | **Planned & Tracked** | 有計畫、有資源、有監督與追蹤 | CF 2.1 規劃 / CF 2.2 規範 / CF 2.3 驗證 / CF 2.4 追蹤 |
| **Level 3** | **Well-Defined** | 組織級標準 SOP，資產化管理 | CF 3.1 定義標準過程 / CF 3.2 執行標準過程 |
| **Level 4** | **Quantitatively Controlled** | 量化與統計學管理過程品質 | CF 4.1 定量管理 / CF 4.2 定量評估 |
| **Level 5** | **Continuously Improving** | 預防性改善、持續優化與創新 | CF 5.1 優化過程 / CF 5.2 預防缺陷 |

---

## 🔍 評估交叉查核邏輯 (Assessment Rule)

在進行 SSE-CMM 審查時，評估員會使用 **BP (X軸) $\times$ GP (Y軸)** 進行矩陣式查核：

> [!IMPORTANT] 評估門檻法則
> 1. **全覆蓋法則**：某個 PA 要達到 Level $N$，該 PA 內部的**所有 BP** 都必須滿足 Level $N$ 的 **GP 要求**。
> 2. **木桶效應 (短板效應)**：若某個 BP 未能通過 Level $N$ 的 GP，整個 PA 的成熟度等級將回退至最低通過的等級。
> 3. **GP 屬硬性指標**：GP 不是「建議 (Guidance)」，而是判定 Level 升級的**必要合規條款**。

---

## 💡 關鍵概念辨析 & 演進

* **GP 是 PA 的單位嗎？**
  * **不是**。BP 是 PA 的工程內容單位；GP 是評量所有 PA 管理品質的通用標準尺。
* **CF 的實務定位？**
  * 身為中間橋樑，將抽象的 Level 拆解為具體的 PDCA 管理主題，方便評估時進行缺口診斷 (Gap Analysis)。
* **與後續 CMMI 模型設計之差異**：
  * SSE-CMM 追求**理論嚴謹的正交矩陣**（每個工程 PA 都要對齊 CF/GP）。
  * 後續 **CMMI V2.0** 取消了 CF/GP，改將通用管理要求抽取為獨立的實踐域（如 Governance PA），以**降低管理重覆性與文件負擔**。

---

## 🔗 相關筆記連結 (Links)

* [[SSE-CMM PA04 評估安全風險範例]]
