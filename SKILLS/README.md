# 🛠️ P.M.A.T. 技能系統使用手冊 (Skill Manual)

本資料夾存放了所有「由 AI 下令，由 GitHub Actions 執行」的自動化技能。在新專案中，你可以透過以下方式應用這些技能。

## 📖 如何應用於新專案？

1.  **複製結構：** 將整個 `SKILLS/` 資料夾與 `AGENT.md` 複製到新專案。
2.  **配置 Secrets：** 根據每個 `SKILL.md` 內的「必備密鑰 (Secrets)」列表，在 GitHub Repository Settings 中填入對應的 API Keys 與設定。
3.  **對齊路徑：** 確保新專案的檔案結構（如 `lib/`, `functions/`, `default.project.json`）與 `SKILL.md` 中的描述一致。

## 🛠️ 技能地圖與調度情境

| 調度指令 (語音/文字) | 對應技能檔案 | 執行動作 |
| :--- | :--- | :--- |
| 「發佈 App 新版本」 | `flutter-deploy/SKILL.md` | 檢查版本號、推送到 main 或打 Tag |
| 「部署後端功能」 | `functions-deploy/SKILL.md` | 部署 Firebase Functions 與 Secrets |
| 「更新官方網站/條款」| `hosting-deploy/SKILL.md` | 更新 Firebase Hosting 並注入指紋 |
| 「產出新的貼圖預覽」| `preview-gen/SKILL.md` | 觸發 Gemini 產圖並開啟 PR |
| 「我要合併代碼」 | `pr-check/SKILL.md` | 自動執行版本檢查與代碼分析 |
| 「更新遊戲內容」 | `roblox-deploy/SKILL.md` | 透過 Rojo 部署至 Roblox |

## 🎙️ AI 開發者作業指南

當你作為開發者接手此專案時：
1.  **先讀 AGENT.md：** 了解專案全貌。
2.  **按需讀取 SKILL.md：** 當用戶提到「部署」、「發佈」、「檢查」等關鍵字時，**必須**讀取對應的 `SKILL.md` 以獲取最新的執行步驟與參數限制。
3.  **主動回報：** 執行完 Git 操作後，告知用戶哪一個 GitHub Action 會被觸發，並提供 Action 連結以便追蹤進度。
