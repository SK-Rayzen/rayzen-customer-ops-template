# Secrets 說明

這個目錄在 template repo 中只保留說明，不放真實密碼。

客戶 private repo 中可建立：

- `credentials.yaml`
- `api-keys.yaml`

原則：

- 實際密碼只放這裡
- 其它檔案僅能引用 `secret_ref`
