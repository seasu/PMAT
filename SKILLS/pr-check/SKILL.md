# 🛡️ Skill: PR Quality & Version Guard

## 📌 描述
在 Pull Request 階段執行的品質守衛。包含程式碼靜態分析、單元測試、以及嚴格的「版本遞增檢查」。

## 🛡️ 守衛項目
1.  **Version Guard (App):** 
    - 若 `lib/`, `android/`, `ios/` 有改動，則 `pubspec.yaml` 的版本號必須高於最後一個 Git Tag。
2.  **Version Guard (Functions):** 
    - 若 `functions/` 有改動，則 `functions/package.json` 的版本號必須高於 `main` 分支。
3.  **Code Analysis:** 執行 `dart analyze --fatal-infos` 確保代碼符合 Lint 規範。
4.  **Unit Tests:** 執行 `flutter test` 確保無功能衰退。

## 📝 開發者指令 (AI 指引)
當 AI 輔助用戶開發並準備提交 PR 時：
1.  **務必檢查版本號：** 不要等 CI 報錯。在 commit 前主動詢問或自動幫用戶遞增 `pubspec.yaml` 或 `functions/package.json`。
2.  **執行本地測試：** 若環境允許，先跑 `flutter test`。
3.  **回報狀態：** 若 PR Check 失敗，AI 應讀取失敗日誌並精準指出是「未遞增版本」還是「代碼分析錯誤」。
