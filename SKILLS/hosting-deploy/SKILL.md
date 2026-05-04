# 🌐 Skill: Firebase Hosting Deploy

## 📌 描述
部署靜態網頁與資產至 Firebase Hosting，特別處理 Android App Links (`assetlinks.json`) 與 iOS Universal Links (`apple-app-site-association`) 的動態指紋注入。

## 🛠️ 觸發方式
-   **自動：** 當 `public/**`、`firebase.json` 或 `.firebaserc` 有變動並推送至 `main` 分支時。
-   **手動：** 執行 `Deploy Hosting` 工作流。

## 🔐 動態注入邏輯
CI 會在部署前從 Secrets 提取資訊，動態更新 `.well-known/` 下的檔案：
-   **SHA-256 Fingerprint:** 從 Android Keystore 提取並注入 `assetlinks.json`。
-   **Apple Team ID:** 從 `APPLE_TEAM_ID` 提取並注入 `apple-app-site-association`。

## ⚙️ 必備密鑰 (Secrets)
-   `ANDROID_KEYSTORE_BASE64` / `ANDROID_STORE_PASSWORD` / `ANDROID_KEY_ALIAS`: 用於計算 SHA-256。
-   `APPLE_TEAM_ID`: 用於 iOS App ID 綁定。
-   `FIREBASE_SERVICE_ACCOUNT_JSON`: Firebase 部署權限。

## 📝 開發者指令 (AI 指引)
當用戶要求「更新網站」或「更新 App Links」時：
1.  確認修改位於 `public/` 資料夾。
2.  執行 `git push origin main`。
3.  若更新了 Android 簽署金鑰，需提醒用戶更新 GitHub Secrets 以確保 App Links 驗證不會失效。
