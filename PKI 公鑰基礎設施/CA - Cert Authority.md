認證權威
- 簽發證書（寫入 [[LDAP 證書庫]]）
- 更新證書（寫入 [[LDAP 證書庫]]）
- 管理證書（讀取 [[LDAP 證書庫]]，避免重簽）
	- 查詢
	- 撤銷
	- 審計
	- 統計
- 認證
	- [[CRL - 證書黑名單]]：定期發布黑名單，列出哪些已經撤銷
	- 在線認證 (OCSP) ：即時查詢

---

The Chain of Trust:
Root CA
- Immediate CA
	- Certification

## 相關
- [[RA - Registry Authority]]
- [[PKI 公鑰基礎設施]]
- [[MAC vs HASH vs Digital Signature]]
- [[非對稱加密]]
