可撤銷性！

列出被撤銷證書的 序列號

- **產出者（Publisher）：CA**
    - [[CA - Cert Authority]] 會定期（如每 24 小時）或在撤銷發生時，使用自己的**私鑰對 CRL 檔案進行數位簽章**，確保黑名單不被竄改。

- **存放處（Repository）：LDAP / Web Server (HTTP)**
    - CA 簽署完成後，會將 CRL 發布至 [[LDAP 證書庫]]或 Web 伺服器上。

- **使用對象（Verifier）：Client / 驗證端**
    - 當 Client（如瀏覽器、VPN 伺服器）驗證一張證書時，會讀取證書內部的 **CDP（CRL Distribution Point，CRL 發布點）** 欄位 URL，下載並檢查該證書是否已被列入黑名單。

## 相關
- [[CA - Cert Authority]]
- [[LDAP 證書庫]]
- [[VPN]]
- [[MAC vs HASH vs Digital Signature]]
- [[PKI 公鑰基礎設施]]

