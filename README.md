# Customer Ops Template

這個 repo 是客戶維運 repo 的公開範本。  
它只包含：

- 共用目錄骨架
- AI 協作規範
- inventory / docs / automation 的樣板
- 不含真實客戶資料的範例檔

> 🤖 Codex 入口請先看 [CODEX.md](CODEX.md)
> 🤖 Claude 入口請先看 [CLAUDE.md](CLAUDE.md)
> 👤 人類工程師先從本檔開始

---

## 這個 template 解決什麼問題

- 新客戶 repo 不用每次從舊客戶 repo 複製
- 客戶 repo 可維持一致結構
- AI agent 能快速理解每個客戶 repo 的檔案規範
- 共用工具、lint 與排程格式可以集中維護

---

## 使用方式

1. 複製這個 template 成為新客戶 repo
2. 填入客戶真實資料到 `inventory/`
3. 把密碼放進 `secrets/`
4. 寫客戶版 `CLAUDE.md`
5. 建立 `worklog/`、`todo/`、`docs/` 的客戶內容

---

## 目錄速查

| 想找的內容 | 看哪裡 |
|---|---|
| 客戶基本資料 | `inventory/customer.yaml` |
| 設備 / 網段 / IP | `inventory/*.yaml` |
| 真實密碼應放哪裡 | `secrets/README.md` |
| SOP / runbook / project 放哪裡 | `docs/README.md` |
| 排程格式 | `automation/schedules.yaml` |
| AI 工作規則 | `CODEX.md` / `CLAUDE.md` |

---

## 注意

- 本 template repo 不應包含任何真實客戶資訊
- 真實 IP、帳號、密碼、廠商聯絡資訊都只能存在客戶 private repo
- 公開 repo 只保留骨架、範例與通用工具
