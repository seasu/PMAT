# 🏚️ Poor Man's Agent Team (P.M.A.T.) 
### — 「手機開發、語音驅動、AI 接力」。最懂精算的硬核開發框架。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Device-Mobile-Only](https://img.shields.io/badge/Device-Mobile--Only-blue)](https://github.com)
[![AI-Relay-Strategy](https://img.shields.io/badge/AI--Strategy-Relay--Race-orange)](https://github.com)
[![Voice-First](https://img.shields.io/badge/Input-Voice--First-green)](https://github.com)

**P.M.A.T.** 是一套專為「行動端原生開發者」打造的調度框架。我們不當單一 AI 公司的提款機，而是透過訂閱各家 AI 工具的 **基礎方案 (Pro Base)**，建立一套跨平台的「靈魂轉生」機制，將 **Claude Code**、**Cursor** 與 **Codex/Gemini** 的配額聚合為無限的戰力。

> **「我的手機就是我的指揮中心，GitHub Actions 是我的自動化代工廠，而 AI 則是隨時待命的接力賽隊員。」**

---

## 📱 為什麼選擇 P.M.A.T.？

身為一個在手機上搞定 Flutter、Roblox 與 Web 開發的戰士，這套框架解決了你的三大痛點：
1. **配額牆 (Token Anxiety)：** 單一 AI 燒完了？立刻換下一家接手，進度永不中斷。
2. **切換失憶症 (Context Loss)：** 換工具不需要重新解釋，透過 `AGENT.md` 實現一鍵移交。
3. **輸入瓶頸 (Typing Hell)：** 透過 **Typeless** 與 iOS 語音輸入，用口說取代打字，讓 AI 將語音轉化為結構化代碼。

---

## 🏃‍♂️ AI 接力賽協議 (The Relay Protocol)

我們不迷信單一工具，我們只看剩餘配額。P.M.A.T. 的標準開發流：

| 棒次 | 工具 (Tool) | 擅長領域 (Specialty) | 切換時機 |
| :--- | :--- | :--- | :--- |
| **第一棒** | **Claude Code** | **戰略攻堅**：架構設計、複雜邏輯、重構。 | 任務初始化或遇到技術硬傷時。 |
| **第二棒** | **Cursor** | **戰術執行**：UI 調整、功能模組開發。 | Claude 配額告急，需進入大量編碼時。 |
| **第三棒** | **Codex / Gemini** | **後勤補給**：Unit Test、文檔、樣板代碼。 | 當高階模型配額用盡，執行重複性任務時。 |

---

## 🧠 框架核心組件

### 1. `AGENT.md` (SSOT 專案腦幹)
AI 團隊的「共同記憶體」。所有的工具啟動前必須讀取此檔案。
*   **[SAVE_POINT]**：記錄最後一次 Commit 與當前任務狀態。
*   **[HANDOVER]**：定義 `/shift` 指令，自動更新存檔點以便更換 AI。
*   **[VOICE_PROTOCOL]**：規範 AI 如何解析你的 Typeless 語音輸入。

### 2. `SKILLS/` (部署技能包)
將跨平台的部署邏輯（Flutter, Roblox, Web）模組化為 `SKILL.md`。
*   **AI 負責動口 (Git Push)**，**GitHub Actions 負責出汗 (Build/Deploy)**。
*   實現「手機下令，雲端發布」，無需在行動端配置複雜的編譯環境。

---

## 🎙️ 語音開發心法 (Voice-to-Code)

1. **語音輸入：** 使用 **Typeless** 或內建語音輸入功能描述邏輯。
2. **邏輯過濾：** AI 必須具備過濾口語贅字的能力，並將其結構化為符合 `AGENT.md` 規範的代碼。
3. **先確認後執行：** AI 接收語音後，應摘要「我理解的任務是...」，確認後再動手，節省寶貴的 Token。

---

## 🛠️ 如何開始？

1. **部署腦幹：** 將 `AGENT.md` 範本放入你的 Repo 根目錄。
2. **初始化技能：** 將你的 GitHub Actions YAML 內容提供給 AI，萃取成 `SKILLS/` 指令集。
3. **靈活調度：** 哪家配額多就用哪家，透過 `AGENT.md` 保持進度一致。
4. **手機發布：** 完成開發後，直接語音下令部署，讓 GitHub Actions 完成最後一哩路。

---

> **「我們並不窮，我們只是把 Token 用在了更聰明的地方。」**  
> — *P.M.A.T. 核心準則*

[⭐ Star This Repo](#) | [📖 閱讀 AGENT.md 手冊](./AGENT.md) | [📦 查看技能清單](./SKILLS/)