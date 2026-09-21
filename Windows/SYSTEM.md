> 歸屬：[[Windows 系統用戶]]　｜　[[SID 與 RID]]

## SYSTEM (本地系統帳戶 / LocalSystem)

* **類型**：內建系統服務帳戶 (Built-in Security Principal)
* **SID**：`S-1-5-18`
* **屬性**：
	* **改名**：❌ 不可修改名稱
	* **刪除**：❌ 不可刪除
	* **登入**：❌ **不允許互動式登入**（無法在 UI 畫面輸入密碼登入桌面）
	* **狀態**：始終啟用 (Always Enabled)
	
* **權限與特性**：
	* 擁有本機作業系統的**最高級別權限**（權限高於 Administrator）。
	* 負責執行 Windows 核心服務、驅動程式與系統級背景作業。
	* 可獲取大多數檔案與註冊表機碼的完全控制權（若遇到 `TrustedInstaller` 所有權保護，須先 Take Ownership）。
	* 在網域 (Active Directory) 環境中，SYSTEM 存取跨機網絡資源時，會映射為該台電腦的電腦帳號（`COMPUTERNAME$`）。
	
* **加固建議**：
	* 限制並審查以 SYSTEM 權限運行的第三方服務（遵循最小權限原則）。

## 相關
- [[TrustedInstaller]]
- [[Administrator]]
- [[Kerberos 協議]]
