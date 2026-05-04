# 🎨 Skill: Preview Images Generation

## 📌 描述
使用 Gemini Image Model 自動生成 App 內的貼圖風格預覽圖 (Style×Emotion Preview)。支持 12 種風格與 24 種情緒的笛卡兒積組合。

## 🛠️ 觸發方式
-   **手動：** 執行 `Generate Style×Emotion Preview Images` 工作流。
-   **參數：** 可指定 `styles` (如 `chibi`) 或 `emotions` (如 `happy`)，以及是否 `force_regenerate`。

## 🤖 自動化邏輯
1.  **AI 產圖：** 呼叫 `scripts/generate_style_previews_ci.py` 透過 Gemini 產出 PNG。
2.  **格式轉換：** 自動將 PNG 轉為高效能 WebP 並刪除原檔。
3.  **自動版本更新：** 產圖後自動遞增 `pubspec.yaml` 版本號，並在 `PRD.md` 中更新版本記錄。
4.  **自動 PR：** 將新產生的圖片提交至新分支並開啟 Pull Request。

## ⚙️ 必備環境變數
-   `GEMINI_API_KEY`: 產圖核心權限。
-   `GEMINI_IMAGE_MODEL`: 指定模型版本 (default: `gemini-2.5-flash-image`)。

## 📝 開發者指令 (AI 指引)
當用戶說「幫我產生風格預覽圖」或「更新貼圖樣板」時：
1.  至 GitHub Actions 點選 `workflow_dispatch` 觸發。
2.  等待 CI 完成後，會出現一個由 `github-actions[bot]` 開啟的 PR。
3.  審查圖片質量後合併 PR。
