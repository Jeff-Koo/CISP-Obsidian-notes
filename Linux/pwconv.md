> 歸屬：[[Linux Setting files]]

### 未同步修复（`pwconv` 命令）：
- 如果 `/etc/passwd` 中的密码占位符不小心被误改或未开启 Shadow，可以通过执行 `pwconv` 命令，重新将 `/etc/passwd` 中的密码抽离并同步映射到 `/etc/shadow` 中。
	- `pwunconv`: 把 `/etc/shadow` 里的加密密码**重新塞回** `/etc/passwd` 的第二列，并把 `/etc/shadow` 文件删掉
	- `pwconv`: 把 `/etc/passwd` 如有的加密密码塞到 `/etc/shadow`

## 相關
- [[etc passwd]]
- [[etc shadow]]
