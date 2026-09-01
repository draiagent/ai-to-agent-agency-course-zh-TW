# 教學導引：測試自動化工程師（test-automation-engineer）

- **模組**：10 — 測試
- **能力層**：L2（會驗）
- **對應 Agent 定義**：[`AI-to-Agent-Agency-zh-TW` / `agents/testing/test-automation-engineer.md`](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW/blob/main/agents/testing/test-automation-engineer.md)

---

## 1. 定位：這個 Agent 解決什麼問題

學員請 AI「幫我寫端對端測試」通常拿到一堆用 `sleep()` 等畫面、選擇器脆弱、
測試之間共用資料的測試——跑十次過三次。測試自動化工程師的核心信念是**決定性**：
每個測試擁有自己的資料、等待條件而非時鐘，並留下讓失敗不必重跑就能除錯的產物。

它的鐵律：**不要硬性 sleep（永遠不要）**、**測試擁有自己的資料**、
**像使用者一樣選取（角色/標籤優先，脆弱 CSS 鏈永不使用）**、
**E2E 是金字塔頂端，不是整座金字塔**。

一句話：**它把「跑十次過三次的測試套件」提升到「決定性、隔離、快速、可除錯的守門套件」。**

### 什麼時候召喚它

- 要建端對端測試套件（Playwright/Cypress）
- 測試「不穩定」（flaky），跑 CI 時好時壞
- CI 測試太慢，要分片平行化
- 要建「失敗自動附 trace/截圖/影片」的除錯機制

### 什麼時候「不要」召喚它

- 是單元測試/API 測試（金字塔下層）→ 直接請工程數位員工
- 是無障礙測試 → accessibility-auditor

---

## 2. Before / After 示範

**任務**：「幫我寫一個結帳流程的端對端測試。」

### Before（無 Agent）

> 產出：透過登入表單登入、`waitForTimeout(3000)` 等畫面、選擇器是
> `div.cart > div:nth-child(3) button`。改版就壞、CI 慢就 flaky。

### After（召喚 test-automation-engineer）

> 會產出：
> - 透過 **API** 建立測試資料（快速、決定性、平行安全）
> - 角色式選擇器（`getByRole('button', { name: 'Checkout' })`）
> - 等待**網路回應**而非時間（`waitForResponse`）
> - Web-first 斷言（重試到成立或逾時，不手動輪詢）
> - CI 分片 + 首次重試才開 trace + 擋合併
> - 不穩定分流表：症狀 → 根因 → 修正（不是繞過）

**課堂提問**：讓學員指出 Before 的三個 flaky 來源（時間式等待、共用狀態、脆弱選擇器）。

---

## 3. 怎麼帶學員「驗收」它的產出

| 檢核點 | 有 / 無 |
|---|---|
| **零硬性 sleep**——等待條件（元素狀態/網路/URL），不等時鐘 | |
| 每個測試透過 API 建立自己的資料，不依賴 seed 或其他測試殘留 | |
| 選擇器用角色/標籤，不用脆弱 CSS 鏈 | |
| E2E 只用在「整合本身就是風險」的旅程，不是所有東西 | |
| 失敗會附 trace/截圖/影片，能不重現就除錯 | |
| 重試是「量測不穩定」，不是「讓測試過」 | |

若測試裡有 `waitForTimeout`、或依賴「seed 使用者」→ 退回。

---

## 4. 常見誤區

1. **用 sleep 等畫面。** `waitForTimeout(3000)` 是帶倒數計時器的不穩定。
2. **測試共用資料。** 一個測試依賴另一個的殘留，已經壞了。
3. **什麼都塞進 E2E。** 能用單元/API 證明的，不該進瀏覽器。
4. **靠重試讓測試過。** 需要重試才過的測試，永遠不算「完成」。

---

## 5. 銜接其他 Agent

frontend-developer（模組 1）產出可測試的前端 → **test-automation-engineer 建守門套件** →
devops-automator 把它接進 CI 擋合併。accessibility-auditor 則負責另一條「無障礙」通道。
在模組 10，這位負責「讓測試套件值得信任」。
