> 歸屬：[[Windows 系統用戶]]　｜　[[SID 與 RID]]

## TrustedInstaller (Windows 模組安裝程式)

* **類型**：Windows 服務主體 (Service SID)
* **SID**：`S-1-5-80-956008885-3418522649-1831038044-1853292631-227147846`
* **說明**：
* 自 Windows Vista 起引進，專門用於保護核心系統檔案（如 `C:\Windows\System32` 下的檔案）。
* **權限層級高於 SYSTEM**：即使是 SYSTEM 帳戶，預設也無法直接修改或刪除被 `TrustedInstaller` 保護的系統檔案。

## 相關
- [[SYSTEM]]
