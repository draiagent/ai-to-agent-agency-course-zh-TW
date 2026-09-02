# 教學導引：MCP 建構者（mcp-builder）

- **模組**：18 — 跨域專業（也是整門課「AI to Agent」主題的技術收尾）
- **能力層**：L3→L4（會編 → 會養）
- **對應 Agent 定義**：[`AI-to-Agent-Agency-zh-TW` / `agents/specialized/mcp-builder.md`](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW/blob/main/agents/specialized/mcp-builder.md)

---

## 1. 定位：這個 Agent 解決什麼問題

整門課教「怎麼用 Agent」；MCP 建構者教**怎麼給 Agent 新能力**——建 Model Context
Protocol 伺服器，把自訂工具（API 整合、資料庫存取、工作流程自動化）接給 AI agent。

它的核心觀念呼應了 prompt-engineer（模組 1）：**工具描述像 UI 文案，每個字都重要**，
因為 agent 讀它們來決定要呼叫什麼。它的鐵律：**描述性工具名稱**（`search_users` 不是
`query1`）、**有型別的參數**（Zod/Pydantic）、**結構化輸出**、**優雅失敗**
（回 `isError: true` 不讓伺服器崩）、**無狀態工具**、**每個工具一個職責**、
**用真實 agent 測試**。

一句話：**它把「我寫了一個 API」提升到「一個 agent 光靠名稱與描述就會正確使用的工具」。**

### 什麼時候召喚它

- 要建 MCP 伺服器，給 agent 存取外部系統/資料的能力
- 要設計對 agent 友善的工具介面（命名、描述、參數 schema）
- agent 一直呼叫錯的工具，要診斷（通常是命名或描述問題）
- 要包裝既有 REST API 成 MCP 工具

### 什麼時候「不要」召喚它

- 是「怎麼用現有的工具/Agent」→ 前面 17 個模組
- 是一般後端 API 設計（不給 agent 用）→ backend-architect（模組 1）

---

## 2. Before / After 示範

**任務**：「幫我做一個讓 agent 能查工單的工具。」

### Before（無 Agent）

> 產出：一個叫 `query` 的工具，參數是一個字串 `q`，回傳一坨原始文字。
> agent 不知道什麼時候該用它、該傳什麼、回來的東西怎麼解讀。

### After（召喚 mcp-builder）

> 會產出：
> - 工具名 `search_tickets`，描述「告訴 agent **何時**該用它」而不只是它做什麼
> - 有型別的參數（`status` 是 enum、`limit` 有 min/max/default）+ 每個欄位的描述
> - 結構化輸出（JSON），錯誤回 `isError: true` + 可行動訊息
> - 一個 `ticket-stats` 資源，讓 agent 行動前先有脈絡
> - 用真實 agent 測完整迴圈：讀描述 → 挑工具 → 送參數 → 拿結果 → 行動

**課堂提問**：讓學員理解「為什麼工具命名是成敗的一半」——agent 靠名稱與描述挑工具。

---

## 3. 怎麼帶學員「驗收」它的產出

| 檢核點 | 有 / 無 |
|---|---|
| 工具名是 verb_noun、無歧義（不是 `query`/`tool1`） | |
| 描述告訴 agent「何時」用它，不只「做什麼」 | |
| 參數有型別、有預設、每個欄位有描述 | |
| 輸出結構化（資料 JSON、人類可讀 markdown） | |
| 錯誤回 `isError: true` + 可行動訊息，不崩伺服器 | |
| 每個工具一個職責（`get_user`/`update_user` 是兩個工具） | |
| 有用真實 agent 測過完整迴圈 | |

若工具叫 `query`、參數無型別、錯誤直接丟 stack trace → 退回。

---

## 4. 常見誤區

1. **工具名太籠統。** agent 靠名稱挑工具，`search_orders_by_date` 勝過 `query`。
2. **描述只寫「做什麼」。** 要寫「何時該用」，agent 才知道什麼情況呼叫。
3. **一個工具塞多個職責。** 用 `mode` 參數區分讀寫是壞設計，拆成兩個工具。
4. **通過單元測試就出貨。** 讓 agent 困惑的工具是壞的，要用真實 agent 測。

---

## 5. 銜接：這是「AI to Agent」的技術閉環

前 17 個模組：學員學會**編派**現成的 Agent。MCP 建構者讓學員能**擴充**——
當現成工具不夠用時，自己建。它跟 multi-agent-systems-architect（模組 1）是一對：
一個設計「多個 Agent 怎麼協作」，一個建「Agent 能呼叫的工具」。

到這裡，整門課從「會問」（L0）走到「會養」（L4）：不只會用 Agent、驗收 Agent、
編排 Agent，還能**造工具、造能力**，把整套系統當團隊資產持續演進。
