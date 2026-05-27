# Customer Ops Template — Claude 入口模板

> 這是客戶專屬 `CLAUDE.md` 的模板，請於新客戶 repo 中填入真實內容。

## 1. 客戶背景與目標

- 客戶名稱：
- 維運範圍：
- 主要目標：

## 2. 設備總表

完整見 `inventory/devices.yaml`。

| 角色 | 設備 | IP | 備註 |
|---|---|---|---|
| 範例 | example-device | 192.0.2.10 | 示例 |

## 3. 網段與 VLAN

完整見 `inventory/networks.yaml`。

| 名稱 | 網段 | 用途 |
|---|---|---|
| management | 192.0.2.0/24 | 示例管理網段 |

## 4. 管理連線

| 目標 | 方式 |
|---|---|
| example-device | SSH / Web UI |

## 5. Repo 結構與檔案放置規範

- `inventory/`：結構化事實來源
- `secrets/`：敏感資料
- `docs/`：SOP / runbook / 專案
- `automation/`：排程

## 6. 常用腳本 / 重要資料

- `automation/schedules.yaml`
- `docs/architecture/`
- `docs/projects/`

## 7. 自動排程清單

- 待客戶實際需求填入

## 8. 操作注意事項與禁忌

1. 營業時間避免中斷式操作
2. 動核心設備前先備份
3. 寫入型腳本需明確授權
