Protect Detect Response

技术与事件驱动

如果 Protection Time 夠長，能覆蓋 Detect Time + Response Time，代表系統是安全的。
$$
\underbrace{P_t}_{\substack{\text{Protection Time} \\\\\\\\\\\\\\\\ \text{防禦措施能保護的時長}} }> \underbrace{D_t}_{\substack{\text{Detect Time} \\\\\\\\\\\\\\\\ \text{偵測到威脅所用的時間}} } + \underbrace{R_t}_{\substack{\text{Response Time} \\\\\\\\\\\\\\\\ \text{響應、處理威脅所用的時間}} }
$$

- 當 **$P_t > D_t + R_t$**（即 $E_t \le 0$）時，代表在防線被攻破前已經完成偵測與響應，系統是**安全的**。


## 相關
- [[PPDR]]
- [[PDCERF]]
- [[信息保障技术框架 - IATF]]
- [[深度防御]]
- [[信息安全應急響應]]


