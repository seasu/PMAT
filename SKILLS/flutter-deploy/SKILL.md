# 🚀 Skill: Flutter Full Deploy (Android & iOS)

## 📌 描述
本技能透過 GitHub Actions 自動執行 Flutter 專案的雙平台編譯與發佈。包含 Android (APK/AAB) 與 iOS (IPA)，並對接 Google Play, TestFlight, GitHub Release 與 Firebase App Distribution。

## 🛠️ 觸發方式
1.  **自動：** 推送至 `main` 分支或推送以 `v*` 開頭的 Tag。
2.  **手動：** 在 GitHub Actions 頁面手動執行 `Magic Sticker CI/CD` 工作流，可填寫 `release_notes`。

## 📦 產出物與發佈管道
-   **Android:**
    -   APK: 上傳至 GitHub Release 與 Firebase App Distribution。
    -   AAB: 上傳至 Google Play Console (Internal Track)。
-   **iOS:**
    -   IPA: 上傳至 TestFlight 與 Firebase App Distribution。

## ⚙️ 關鍵環境變數與密鑰 (Secrets/Vars)
| 名稱 | 類型 | 描述 |
| :--- | :--- | :--- |
| `GOOGLE_SERVICES_JSON_ANDROID` | Secret | Android Firebase 設定檔 |
| `GOOGLE_SERVICE_INFO_PLIST` | Secret | iOS Firebase 設定檔 |
| `ANDROID_KEYSTORE_BASE64` | Secret | Android 簽署金鑰 |
| `IOS_CERTIFICATE_BASE64` | Secret | iOS 發佈憑證 |
| `APP_STORE_CONNECT_API_KEY` | Secret | Apple Connect API Key (.p8) |
| `STICKER_BG_TRANSPARENT` | Var | 貼圖背景透明化開關 (default: true) |
| `DOMAIN_BASE` | Var | 後端 API 基礎路徑 |

## 📝 開發者指令 (AI 指引)
當用戶要求「部署 App」或「發佈版本」時：
1.  **檢查版本：** 確保 `pubspec.yaml` 中的 version 已遞增。
2.  **提交代碼：** `git add .` 並 `git commit -m "feat: [功能描述]"`。
3.  **執行部署：**
    -   方法 A (Tag 觸發)：`git tag v1.0.x+build && git push origin v1.0.x+build`。
    -   方法 B (Push 觸發)：直接 `git push origin main`。
4.  **回報進度：** 告知用戶「CI/CD 已啟動，請至 GitHub Actions 查看 Android 與 iOS 的建置進度」。

## ⚠️ 注意事項
-   **Android Version Code：** CI 會自動將 `run_number + 1000` 注入為 `versionCode` 以滿足 Play Store 遞增要求。
-   **iOS Xcode 版本：** 使用 Xcode 26 (iOS 26 SDK) 以符合 2026 Apple 規範。
-   **Version Guard：** 若 PR 修改了 `lib/` 但未動 `pubspec.yaml`，PR Check 會報錯。
