# 教學導引：應用程式安全工程師（appsec-engineer）

- **模組**：9 — 安全
- **能力層**：L2→L4（會驗 → 會養）
- **對應 Agent 定義**：[`AI-to-Agent-Agency-zh-TW` / `agents/security/appsec-engineer.md`](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW/blob/main/agents/security/appsec-engineer.md)

---

## 1. 定位：這個 Agent 解決什麼問題

code-reviewer（模組 1）審一般品質；應用程式安全工程師專審**安全**——注入、驗證繞過、
授權漏洞、加密誤用、資料暴露。它的信念是**開發者優先**：多數安全弱點是有才華的
開發者的誠實錯誤，因為沒被教過安全編碼。它修系統，不修人；講程式碼範例，不講政策文件。

它的核心動作：威脅建模（STRIDE）、安全程式碼審查、把 SAST/DAST 整合進 CI/CD、
開發者安全教育。它的名言：「『我們之後會修』意思是『我們會在遭入侵後修』。」

一句話：**它把「功能能動」提升到「威脅有被建模、關鍵路徑有被安全審查、弱點有 SLA 追蹤」。**

### 什麼時候召喚它

- 新功能/架構變更前要做威脅建模
- 安全關鍵程式碼（驗證、授權、加密、輸入處理）要審
- 要把 SAST/DAST/密鑰掃描整合進 CI/CD 並調校假陽性
- 要建開發者安全編碼指南與教育

### 什麼時候「不要」召喚它

- 是「模擬攻擊、找出攻擊鏈」→ penetration-tester
- 是一般程式碼品質 → code-reviewer

---

## 2. Before / After 示範

**任務**：「幫我看這個使用者資料 API 有沒有問題。」

### Before（無 Agent）

> 產出：「看起來還行，加點註解、變數名可以更清楚。」——沒抓到
> `/api/users/:id/profile` 沒有所有權檢查（任何人可看任何人的 profile）。

### After（召喚 appsec-engineer）

> 會產出：
> - 威脅模型（STRIDE）：信任邊界、每類威脅的緩解
> - 安全程式碼審查：IDOR、缺少授權中介層、mass assignment 風險，每個附「安全版」程式碼
> - 「合併前必修」vs「有空再強化」的區分
> - 弱點的 SLA（Critical 7 天、High 30 天）與追蹤
> - 建議用哪三個函式庫（Zod/helmet/bcrypt）自動處理 80% 常見弱點

**課堂提問**：讓學員理解「為什麼 SQL 注入的修正是一行改動、但沒抓到就是災難」。

---

## 3. 怎麼帶學員「驗收」它的產出

| 檢核點 | 有 / 無 |
|---|---|
| 每個發現都附「安全版」程式碼，不只標出不安全的 | |
| 有區分「合併前必修」與「強化機會」 | |
| 授權檢查在每個請求、每個資源都驗所有權 | |
| 不只靠自動掃描——有找邏輯錯誤與業務專屬弱點 | |
| 弱點依「可利用性 + 業務影響」分類，不只看 CVSS | |
| 密鑰不在程式碼/設定檔/環境變數，用密鑰管理器 | |

若只挑排版與命名、漏掉授權漏洞 → 退回。

---

## 4. 常見誤區

1. **把安全審查當風格糾察。** 聚焦正確性、注入、授權、加密，不是 tab 還是空格。
2. **只靠自動掃描。** 工具漏掉邏輯錯誤、授權缺陷、業務專屬弱點。
3. **相信「之後再修」。** Critical 有 SLA，不是「等有空」。
4. **只看 CVSS 分數。** 內部工具的 critical 和公開支付 API 的 medium 不一樣。

---

## 5. 銜接其他 Agent

backend-architect 出設計 → 有人實作 → code-reviewer 審品質 → **appsec-engineer 審安全** →
devops-automator 把安全掃描放進 CI/CD 管線。到模組 5、9、10 會把 code-reviewer、
appsec-engineer、test-automation-engineer 組成更完整的治理流程。
