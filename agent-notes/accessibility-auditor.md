# 教學導引：無障礙稽核員（accessibility-auditor）

- **模組**：10 — 測試
- **能力層**：L2（會驗）
- **對應 Agent 定義**：[`AI-to-Agent-Agency-zh-TW` / `agents/testing/accessibility-auditor.md`](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW/blob/main/agents/testing/accessibility-auditor.md)

---

## 1. 定位：這個 Agent 解決什麼問題

自動化工具大約只抓到 30% 的無障礙問題。無障礙稽核員負責另外 70%——那些
「用眼睛看、用滑鼠操作的開發者」永遠不會注意到的障礙。

它的核心信念：**誠實評估勝於合規作秀**——綠色 Lighthouse 分數不代表無障礙。
它的鐵律：**一律同時做自動掃描與手動輔助科技測試**、**自訂元件在被證明無罪前都是有罪的**、
**「用滑鼠能動」不是測試——每個流程都要純鍵盤可用**。

一句話：**它把「Lighthouse 綠燈」提升到「螢幕報讀器使用者能獨立完成所有關鍵旅程」。**

### 什麼時候召喚它

- 要對照 WCAG 2.2 AA 稽核介面
- 要用螢幕報讀器（VoiceOver/NVDA/JAWS）、純鍵盤測試
- 自訂元件（分頁、對話框、輪播、日期選擇器）要驗 ARIA 與鍵盤模式
- 要把 axe-core 整合進 CI 做無障礙迴歸

### 什麼時候「不要」召喚它

- 是功能面的端對端測試 → test-automation-engineer
- 是視覺設計的對比/間距 → ui-designer（模組 2，兩者可協作）

---

## 2. Before / After 示範

**任務**：「幫我看這個表單無障礙有沒有問題。」

### Before（無 Agent）

> 產出：跑一次 Lighthouse，分數 92，說「沒問題」。實際上焦點順序亂、
> error 訊息螢幕報讀器讀不出來、focus 樣式看不見、送出按鈕鍵盤到不了。

### After（召喚 accessibility-auditor）

> 會產出：
> - 稽核報告：自動掃描 + 螢幕報讀器測試 + 鍵盤測試 + 200%/400% 縮放 + 高對比
> - 每個問題附：違反的 WCAG 準則（編號 + 名稱）、嚴重度、使用者影響、位置、
>   「現在的樣子」與「應該的樣子」程式碼
> - 補救優先序：Critical/Serious 發佈前修、Moderate 下個 sprint、Minor 日常維護
> - 「做得好的地方」（強化好模式）

**課堂提問**：讓學員理解「為什麼 Lighthouse 92 分卻完全不能用螢幕報讀器操作」。

---

## 3. 怎麼帶學員「驗收」它的產出

| 檢核點 | 有 / 無 |
|---|---|
| 同時有自動掃描**與**手動輔助科技測試 | |
| 每個問題引用具體 WCAG 準則（編號 + 名稱） | |
| 有純鍵盤測試（每個互動元素可 focus、focus 可見、順序合理） | |
| 自訂元件有驗 ARIA 角色/狀態與鍵盤模式 | |
| error/狀態/live region 有驗「螢幕報讀器會播報」 | |
| 依「使用者影響」排優先序，不只依合規等級 | |

若只有 Lighthouse 分數、沒有手動測試 → 退回。

---

## 4. 常見誤區

1. **綠色分數 = 無障礙。** 自動工具只抓 30%，剩下要手動。
2. **「用滑鼠能動」就過。** 每個流程都要純鍵盤走一遍。
3. **無障礙當事後補。** 要在每個階段倡議，把它建進基礎。
4. **在 ARIA 之前不先用語意化 HTML。** 最好的 ARIA 是你不需要的 ARIA。

---

## 5. 銜接其他 Agent

ui-designer（模組 2）把無障礙建進設計 token → frontend-developer（模組 1）實作 →
**accessibility-auditor 稽核** → test-automation-engineer 把 axe-core 接進 CI 做迴歸。
在模組 10，這位負責「讓產品對所有使用者可用」——一個常被當加分項、其實是關鍵規則的職能。
