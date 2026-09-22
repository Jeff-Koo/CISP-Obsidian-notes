**Policy-based** Protect Detect Response

安全策略驱动（Policy-driven）

如果 Protection Time 夠長，能覆蓋 Detect Time + Response Time，代表系統是安全的。(與 PDR 同樣)

$$
\underbrace{P_t}_{\substack{\text{Protection Time} \\\\\\\\\\\\\\\\ \text{防禦措施能保護的時長}} }> \underbrace{D_t}_{\substack{\text{Detect Time} \\\\\\\\\\\\\\\\ \text{偵測到威脅所用的時間}} } + \underbrace{R_t}_{\substack{\text{Response Time} \\\\\\\\\\\\\\\\ \text{響應、處理威脅所用的時間}} }
$$
但若 Protection Time 不夠長，即是 Pt < Dt + Rt

$$
\underbrace{E_t}_{\substack{\text{Exposure Time} \\\\\\\\\\\\\\\\ \text{暴露時間 系統處於不安全的時長}} } = （\underbrace{D_t}_{\substack{\text{Detect Time} \\\\\\\\\\\\\\\\ \text{偵測到威脅所用的時間}} } + \underbrace{R_t}_{\substack{\text{Response Time} \\\\\\\\\\\\\\\\ \text{響應、處理威脅所用的時間}} }） - \underbrace{P_t}_{\substack{\text{Protection Time} \\\\\\\\\\\\\\\\ \text{防禦措施能保護的時長}} }
$$


- 當 **$P_t > D_t + R_t$**（即 $E_t \le 0$）時，代表在防線被攻破前已經完成偵測與響應，系統是**安全的**。
- 當 **$P_t < D_t + R_t$**（即 $E_t > 0$）時，代表攻擊者在被阻斷前已經成功入侵，系統處於**暴露與危險中**

## 相關
- [[PDR]]
- [[PDCA 循环模型]]
- [[信息安全管理體系 - ISMS]]
- [[深度防御]]