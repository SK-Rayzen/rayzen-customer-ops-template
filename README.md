# Rayzen Customer Ops Template

這個 repo 是 **瑞翔資訊科技有限公司（Rayzen）** 內部使用的客戶維運 repo 公開範本。

它的核心目標，是把一個企業的 IT infrastructure 用 **repo 化** 的方式整理起來，讓：

- 人類工程師可以有組織地維護設備、網段、帳號、SOP、工作日誌與排程
- AI agent 可以在新對話開始時，用最少摩擦快速理解環境現況
- 團隊在長期維運中，盡可能維持資訊一致、可追蹤、可交接、可持續更新

簡單說，這不是單純的文件模板，而是一個讓 **human + AI agent** 共同管理企業 IT infra 的工作方式。

> 🤖 Codex 入口請先看 [CODEX.md](CODEX.md)
> 🤖 Claude 入口請先看 [CLAUDE.md](CLAUDE.md)
> 👤 人類工程師先從本檔開始

---

## Why

在實際維運現場，資訊常常散落在：

- Excel
- OneDrive / NAS
- 記事本
- 工程師個人經驗
- 聊天記錄

這會導致幾個常見問題：

- 新對話開始時，AI agent 很難快速掌握脈絡
- 同一份資訊可能在多個地方不一致
- 維運知識無法累積成可重用的結構
- 新人接手成本高
- 工程師與 AI 都要花很多時間重新理解現況

這個 template 的目的，就是把這些資訊整理成適合：

- 人類閱讀
- Git 版本控制
- AI agent 理解
- 團隊交接與長期維護

的共同格式。

---

## 這個 template 解決什麼問題

- 新客戶 repo 不用每次從零開始設計結構
- 客戶 repo 可維持一致格式，降低跨客戶切換成本
- AI agent 能快速理解每個客戶 repo 的資料放置規則
- 透過 `inventory + docs + worklog + automation` 的分層，保持資訊正確性
- 共用工具、lint 與排程格式可以集中演進

---

## 設計原則

這份 template 的核心原則是：

1. **單一真理來源**
   - 結構化事實應集中在 `inventory/`
2. **敏感資訊分離**
   - 真實密碼只放 `secrets/`
3. **文件與事實分層**
   - `docs/` 描述流程與背景，`inventory/` 保存事實
4. **AI 可讀**
   - 讓 AI agent 在新 session 開始時，也能快速進入狀況
5. **可版本化**
   - 每次調整都有 git 歷史可追蹤
6. **可交接**
   - 降低單一工程師記憶依賴

---

## 密碼與敏感資訊

這份 template 預設保留了 `secrets/` 目錄，原因是很多實際維運場景裡，團隊需要先把資訊集中，才有辦法開始建立可用的 repo 化流程。

但要明確說明：

- **這不是我們理想中的最終方案**
- **也不是最安全的 secrets 管理方式**

在較成熟的設計裡，密碼、API keys、VPN shared secrets 等敏感資訊，應該交由專門的密碼庫或 secrets manager 管理，例如：

- 1Password
- Bitwarden / Vaultwarden
- HashiCorp Vault
- 其他可稽核、可分權、可輪替的 secrets solution

之所以在目前 template 裡仍保留 `secrets/`，是因為在某些團隊導入初期，會先採用「把敏感資訊集中到單一位置、避免散落」的過渡做法，等流程穩定後，再逐步切換到更安全的管理方式。

因此建議是：

1. **如果團隊已有成熟的密碼庫，優先使用密碼庫，不要把真實密碼放進 repo**
2. **如果現階段暫時無法導入 secrets manager，至少要把密碼集中在 `secrets/`，不要散落在 `inventory/`、`docs/`、`worklog/`**
3. **所有正式客戶 repo 都應維持 private，並限制存取權限**
4. **一旦條件允許，應優先規劃從 repo 內明文 secrets 過渡到更安全的方案**

簡單說，`secrets/` 在這個 template 裡代表的是：

- 一種現階段可落地的過渡方案
- 不是最終推薦的安全架構

---

## 使用方式

1. 複製這個 template 成為新的客戶 private repo
2. 填入客戶真實資料到 `inventory/`
3. 把真實密碼放進 `secrets/`
4. 寫客戶版 `CLAUDE.md`
5. 建立 `docs/`、`worklog/`、`todo/` 的客戶內容
6. 視需要加入 `automation/` 與通用腳本

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

## 開放協作

這個 repo 是公開的 template repo。

如果你對這種「用 repo 管理企業 IT infra，並讓人類與 AI agent 共同維運」的方式有興趣，歡迎：

- fork
- 提 issue
- 送出 PR

我會參考相關意見，持續調整這份 template 的結構、規範與工具設計。

---

## 注意

- 本 template repo 不應包含任何真實客戶資訊
- 真實 IP、帳號、密碼、廠商聯絡資訊都只能存在客戶 private repo
- 公開 repo 只保留骨架、範例與通用工具
- `secrets/` 是過渡方案設計，不代表明文 secrets 存 repo 是最佳實務
