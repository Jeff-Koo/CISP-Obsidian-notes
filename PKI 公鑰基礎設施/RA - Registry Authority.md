註冊權威
- 驗證證書（讀取 [[LDAP 證書庫]]）

在正規安全架構下，**RA 不應該具備對 LDAP 證書庫的直接寫入權限**：
1. **職責分離（SoD）**：RA 只負責「審核」，不負責「簽發與發布」。證書必須經過 CA 的私鑰簽署後才具備法律與安全效力。
    
2. **工作流程**：RA 完成審核後，發送 API / RPC 請求通知 **CA** -> CA 生成並私鑰簽署證書 -> **CA** 將簽署好的證書寫入 LDAP 證書庫。


風險隔離 - 減低攻擊面



```mermaid
graph TD
    %% 节点定义
    RootCA["根 CA (Root CA)<br/><i>信任源头/通常离线</i>"]
    SubCA["中级 CA (Intermediate CA)<br/><i>负责底层证书签名与签发</i>"]
    RA["注册权威机构 (RA)<br/><i>负责身份核验与业务管理</i>"]
    EE["终端实体 (End Entity)<br/><i>用户 / 服务器 / 终端设备</i>"]
    LDAP[("LDAP / 证书库<br/><i>存储证书与 CRL 撤销列表</i>")]

    %% 关系与交互流程
    RootCA -- "① 签发中级证书 (构建信任链)" --> SubCA
    EE -- "② 提交身份认证材料与 CSR" --> RA
    RA -- "③ 审核通过，发送签发指令" --> SubCA
    SubCA -. "④ 返回已签发的数字证书" .-> RA
    
    %% RA 单向写入 LDAP
    RA -- "⑤ 写入/更新证书与 CRL 黑名单" --> LDAP
    
    RA -- "⑥ 交付数字证书" --> EE
    EE -- "⑦ 查询他人证书 / 检索 CRL 状态 (只读)" --> LDAP

    %% 样式美化
    style RootCA fill:#f9f,stroke:#333,stroke-width:2px
    style SubCA fill:#bbf,stroke:#333,stroke-width:2px
    style RA fill:#ffe6cc,stroke:#d79b00,stroke-width:2px
    style EE fill:#dae8fc,stroke:#6c8ebf,stroke-width:2px
    style LDAP fill:#d5e8d4,stroke:#82b366,stroke-width:2px
```

## 相關
- [[CA - Cert Authority]]
- [[LDAP 證書庫]]
- [[CRL - 證書黑名單]]
- [[PKI 公鑰基礎設施]]
- [[RBAC 模型 Role-Based Access Control]]
    