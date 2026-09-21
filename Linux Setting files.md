# Linux Setting files

- [[etc passwd]]（`/etc/passwd`）
- [[etc shadow]]（`/etc/shadow`）
- [[pwconv]]

### CISP 高频考点与安全加固逻辑

1. **权限控制**：
    - `/etc/passwd` 的权限通常是 `644`（所有人都可读）。
    - `/etc/shadow` 的权限必须是 `000` 或 `600`（所有者通常为 `root` 或 `shadow` 组，严禁任何普通用户具有读权限）。

2. **防破解机制（加盐 Salt）**：
    - 密文中第二部分为**盐值（Salt）**。加盐的理论作用是：**防止针对相同明文密码生成相同的 Hash 结果**，彻底抵御预计算的“彩虹表（Rainbow Table）”攻击。

3. **未同步修复** → [[pwconv]]

## 相關
- [[Windows 系統用戶]]
- [[MAC vs HASH vs Digital Signature]]
