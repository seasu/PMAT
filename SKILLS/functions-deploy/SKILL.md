# ⚡ Skill: Cloud Functions Deploy

## 📌 描述
部署 Firebase Cloud Functions 與 Firestore 安全規則。包含環境變數自動生成、Secret Manager 同步、以及部署後的健康檢查 (Smoke Test)。

## 🛠️ 觸發方式
-   **自動：** 當 `functions/**` 或 `firestore.rules` 有變動並推送至 `main` 分支時。
-   **手動：** 執行 `Deploy Cloud Functions` 工作流。

## 🚀 自動化流程
1.  **環境變數：** 從 GitHub Variables 自動生成 `functions/.env`。
2.  **Secret 同步：** 自動將 GitHub Secrets (如 `GEMINI_API_KEY`) 同步至 Google Cloud Secret Manager。
3.  **IAM 授權：** 自動配置 `roles/run.invoker` (allUsers) 確保 Function 可對外存取。
4.  **Smoke Test：** 部署後自動呼叫 `getConfig` 介面，驗證服務是否存活及其版本資訊。

## ⚙️ 必備密鑰 (Secrets)
-   `FIREBASE_SERVICE_ACCOUNT_JSON`: 具備 `roles/secretmanager.admin` 與 `roles/firebaserules.admin` 權限。
-   `GEMINI_API_KEY`: Gemini AI 服務金鑰。
-   `APP_STORE_CONNECT_*`: 用於驗證 iOS 訂閱/收據。

## 📝 開發者指令 (AI 指引)
當用戶要求「部署後端」或「更新 Function」時：
1.  確認修改位於 `functions/` 且 `package.json` 版本已遞增。
2.  執行 `git push origin main`。
3.  監控 CI 日誌，特別是 **Smoke test** 步驟，確認 HTTP 200 回傳。
