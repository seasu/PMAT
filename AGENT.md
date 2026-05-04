# 🏚️ Poor Man's Agent Team (P.M.A.T.) - Project Brain

## 📍 1. 當前會話快照 (Context Snapshot)
> **STATUS:** 任務進行中 - 框架初始化與技能萃取階段。
- **Last Sync:** 2026-05-04
- **Project Goal:** 建立一套跨工具 (Claude Code, Cursor, Gemini CLI)、跨平台 (Flutter, Roblox, Web)、低 Token 消耗的手機開發流程。
- **Current Task:** 正在準備從現有的 GitHub Repos 中萃取 GitHub Actions 部署邏輯，轉換為 `SKILLS/` 檔案。
- **Next Step:** 接收用戶貼上的 `.github/workflows/*.yml` 內容，並將其轉化為 `SKILLS/xxx/SKILL.md`。

---

## 🎭 2. AI 團隊角色定義 (Role Shifting Protocol)
本專案採用「角色動態切換」機制以節省 Token。請根據指令切換模式：

| 角色 (Role) | 職責描述 (Responsibilities) | 關注檔案 (Focus) |
| :--- | :--- | :--- |
| **Architect** | 全局架構、技術選型、撰寫規劃文檔。 | `AGENT.md`, `docs/`, `architecture.md` |
| **Developer** | 功能實作、撰寫代碼、確保符合風格規範。 | `src/`, `lib/`, `pubspec.yaml` |
| **Reviewer** | 程式碼審查、Debug、資安檢查。 | 變動的 Diff, Test Logs |
| **Skill Extractor**| 分析 CI/CD 配置，將部署邏輯模組化。 | `.github/workflows/`, `SKILLS/` |

---

## 🛠️ 3. 跨工具協作規範 (Cross-Tool Protocol)
1. **SSOT (唯一事實來源):** 本檔案 `AGENT.md` 是專案的大腦。任何工具在啟動時必須先讀取此檔案。
2. **存檔指令 (`/checkpoint`):** 在更換 AI 工具前，當前 AI 必須摘要進度並更新 `[CURRENT_STATE]` 區塊。
3. **移交指令 (`/shift`):** 當 Token 耗盡需更換工具時，生成「遺言摘要」並執行 `git commit`。
4. **手機優化:** 檔案模組化，單一檔案原則上不超過 200 行，以利手機閱讀與 Context 管理。

---

## 🚀 4. 技能描述框架 (Skill Framework)
所有的外部自動化與部署邏輯均存放於 `SKILLS/` 資料夾。

- **運作模式:** 核心大腦 (AGENT.md) 僅持有技能索引。當涉及特定平台（如 Flutter 或 Roblox）的部署時，AI 必須主動讀取 `SKILLS/platform/SKILL.md`。
- **現有技能索引預備:**
    - `SKILLS/flutter-deploy/`: 透過 GitHub Actions 處理 iOS/Android 部署。
    - `SKILLS/roblox-sync/`: 透過 Rojo 與 Open Cloud API 同步遊戲內容。
    - `SKILLS/web-deploy/`: 處理前端網站的 CI/CD。

---

## 📜 5. 給接手 AI (Gemini CLI) 的特別指令
1. **初始化:** 讀取此文件後，請先確認你是否具備操作檔案系統與執行 Git 指令的權限。
2. **接手任務:** 請主動詢問用戶：「請提供現有專案的 GitHub Action YAML 檔案內容，我將開始進行技能萃取 (Skill Extraction)。」
3. **保持自律:** 除非用戶要求，否則不要掃描全專案檔案。僅在需要時讀取特定 Module 的代碼，以節省用戶的 Token 支出。

## 🎙️ 6. 語音開發協議 (Voice-First Development)
為了克服手機輸入瓶頸，本專案優先採用「語音轉邏輯」模式：

1. **輸入來源：** 透過 Typeless 或 iOS 內建語音輸入。
2. **AI 處理邏輯：** 
   - 接手 AI 應自動過濾語音轉文字可能出現的贅字或口語慣用語。
   - 若語音指令邏輯模糊，AI 必須主動要求釐清，而非盲目執行。
3. **結構化輸出：** AI 接收到語音指令後，應先摘要「我理解的任務是...」，確認後再開始執行代碼變更。