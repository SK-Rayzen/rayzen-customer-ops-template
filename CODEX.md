# Customer Ops Template — Codex 規範

## 1. 事實來源

- 每個客戶 repo 中，`inventory/*.yaml` 是結構化事實來源
- 文件若與 `inventory/` 衝突，以 `inventory/` 為準
- 密碼只能放 `secrets/`，其它檔案僅能用 `secret_ref`

## 2. Codex 工作方式

- 修改前先讀相關檔案
- 搜尋優先用 `rg`
- 編輯使用 `apply_patch`
- 保持變更範圍小
- 不要把臨時輸出放到 repo root

## 3. Repo 放置規範

- `inventory/`：設備 / 網段 / 帳號 metadata
- `secrets/`：敏感資訊
- `docs/sop/`：標準作業
- `docs/runbooks/`：故障排查
- `docs/projects/`：專案規劃
- `worklog/`：工作紀錄
- `todo/`：待辦
- `automation/schedules.yaml`：排程定義

## 4. 安全原則

- 任何會動設備的腳本應放在 `scripts/apply/`
- 真實客戶 repo 才能保存敏感資訊
- template repo 只放假資料與通用骨架
