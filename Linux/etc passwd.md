## `/etc/passwd`
Linux 系统中存储用户账户基本信息的配置文件。
文件中**每一行代表一个用户**，每行用冒号（`:`）划分为 **7 个字段**。
权限通常是 `644`（所有人都可读）。

### 1. 用户名（Username）

- **示例**：`root`
- **含义**：用户登录系统时输入的账号名称，必须在系统中保持唯一（通常由小写字母、数字和下划线组成）。


### 2. 密码占位符（Password）

- **示例**：`x`
- **含义**：早期的 Linux 将加密后的密码 Hash 直接存放在此处，极易被非特权用户读取。现在的 Linux 引入了 **Shadow 密码机制**，把真正的加密密码迁移到了只有超管权限可读的 `/etc/shadow` 文件中。
- **常见取值**：
    - `x`：表示加密密码已保存在 `/etc/shadow` 中。
    - `*` ：表示该帳號**沒有可用密碼**或**被永久停用**。
    - `!`：表示该账户**被暫時锁定**或禁止密码登录（或可用 SSH Key 登入）。


### 3. 用户标识号（UID - User ID）

- **示例**：`0`
- **含义**：Linux 内核识别和管理用户的数字 ID。
- **约定分布规则**：
    - **`0`**：超级管理员（Root），拥有系统最高特权。
    - **`1 ~ 999`**：系统伪账户（System Users），供系统服务（如 `nobody`, `daemon`, `nginx` 等）后台运行使用，通常不允许登录。
    - **`1000+`**：普通用户账号（如手动使用 `useradd` 创建的个人账号）。


### 4. 组标识号（GID - Group ID）

- **示例**：`0`
- **含义**：该用户所属的主要用户组（Primary Group）的数字 ID，对应 `/etc/group` 文件中的记录。


### 5. 用户注释/描述信息（GECOS / Comment）

- **示例**：`root`
- **含义**：用户的附加信息或备注（如全名、办公电话、部门等）。通常为空或与用户名相同，主要用于供管理员标识或某些系统服务参考，对系统安全和权限无影响。


### 6. 主目录/家目录（Home Directory）

- **示例**：`/root`
- **含义**：用户成功登录系统后默认进入的工作目录（用户在该目录下拥有完整的读写控制权）。
    - `root` 用户通常为 `/root`。
    - 普通用户通常为 `/home/用户名`。


### 7. 登录 Shell（Login Shell）

- **示例**：`/bin/bash`
- **含义**：用户登录后系统为其启动的命令行解释器环境。
- **常见取值**：
    - `/bin/bash` 或 `/bin/zsh`：正常的交互式 Shell，允许用户登录并执行命令。
    - `/sbin/nologin` 或 `/bin/false`：**禁止交互式登录**。被停用的帳戶、系统伪账户、服务账号（如 `mysql`, `www-data`）通常配置为此项，即使攻击者获得了密码也无法通过 SSH 等方式登录拿到终端环境。


### 总结图解
$$\underbrace{\texttt{root}}_{\text{1. 用户名}} : \underbrace{\texttt{x}}_{\text{2. 密码占位}} : \underbrace{\texttt{0}}_{\text{3. UID}} : \underbrace{\texttt{0}}_{\text{4. GID}} : \underbrace{\texttt{root}}_{\text{5. 描述注释}} : \underbrace{\texttt{/root}}_{\text{6. 家目录}} : \underbrace{\texttt{/bin/bash}}_{\text{7. 登录 Shell}}$$

## 相關
- [[etc shadow]]
- [[pwconv]]
- [[Linux Setting files]]
- [[Windows 系統用戶]]
