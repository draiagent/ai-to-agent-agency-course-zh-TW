# 教學導引：前端開發者（frontend-developer）

- **模組**：2 — 工程實作四人組
- **能力層**：L2（會驗）
- **對應 Agent 定義**：[`AI-to-Agent-Agency-zh-TW` / `agents/engineering/frontend-developer.md`](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW/blob/main/agents/engineering/frontend-developer.md)

---

## 1. 定位：這個 Agent 解決什麼問題

學員請 AI「做個頁面」通常能拿到「看起來對」的結果，但看不出三件事會不會出問題：
**效能**（首屏多久、打包多大）、**無障礙**（鍵盤能不能操作、螢幕報讀器讀不讀得出來）、
**可維護性**（元件能不能重用、型別完不完整）。前端開發者這個角色的價值，是把「畫面出得來」
提升到「量得出來、驗得過」——它交付的是**帶指標的實作**：Core Web Vitals、Lighthouse 分數、
WCAG 準則、元件重用率。

一句話：**它把「看起來對」提升到「量得出來對」。**

### 什麼時候召喚它

- 要把設計稿實作成元件，且在意效能與無障礙
- 頁面載入慢、互動卡，要做程式碼分割／延遲載入／圖片最佳化
- 要建元件庫或設計系統
- 既有頁面要補無障礙（ARIA、鍵盤操作、語意化 HTML）

### 什麼時候「不要」召喚它

- 只是要一張靜態說明頁、一次性 demo → rapid-prototyper
- 問題其實在資料模型或 API 設計 → backend-architect
- 純視覺方向、還沒到實作 → design-ui-designer（模組 3）

---

## 2. Before / After 示範

**任務**：「把這個商品列表設計稿做成 React 元件。」

### Before（無 Agent）

> 產出：一個 `.map()` 直接渲染整包資料的元件。1000 筆就開始掉幀，
> `<div onClick>` 沒有 `role`／`tabIndex`，鍵盤完全用不了，圖片沒 lazy load。

### After（召喚 frontend-developer）

> 產出會包含：
> - 列表虛擬化（`useVirtualizer`），只渲染可見列
> - `role="table/row/cell"`、`tabIndex`、`aria-label`
> - 圖片 WebP/AVIF + 響應式尺寸 + 延遲載入
> - TypeScript 型別完整、`memo`/`useCallback` 避免多餘渲染
> - 一份交付摘要：LCP/CLS 目標、Lighthouse 目標、WCAG AA 對照

**課堂提問**：讓學員指出 After 版本裡「哪兩項是效能相關、哪兩項是無障礙相關」，
並說明 Before 版本在什麼情況下才會爆（提示：資料量、只用滑鼠的假設）。

---

## 3. 怎麼帶學員「驗收」它的產出

| 檢核點 | 有 / 無 |
|---|---|
| 有明確的效能目標（LCP、CLS 或 Lighthouse 分數），不是「應該很快」 | |
| 大型列表有虛擬化或分頁，不是一次渲染全部 | |
| 互動元素可用鍵盤操作（`tabIndex`、Enter/Space、focus 樣式） | |
| 有語意化角色或 ARIA，螢幕報讀器讀得出結構 | |
| 圖片有現代格式 + 響應式尺寸 + 延遲載入 | |
| 元件有 TypeScript 型別；有單元測試或至少測試計畫 | |
| 尊重 `prefers-reduced-motion` 等偏好設定 | |

少於 5 項打勾 → 退回要求補齊。

---

## 4. 常見誤區

1. **只看畫面對不對。** 學員驗收時眼睛看得到的才會檢查；效能與無障礙要用
   Lighthouse／鍵盤 Tab 實測，不能用「看起來」判斷。
2. **無障礙當成加分項。** Agent 定義把 WCAG 2.1 AA 列為**關鍵規則**，不是選配。
   產出若沒提無障礙，是要退的訊號。
3. **過度追新框架特性。** Suspense、並行、WebAssembly 是進階能力，不是每個任務都要用。
   看它有沒有「為了用而用」。
4. **忽略 `prefers-reduced-motion`。** 動畫做很滿卻沒有降級路徑，對前庭敏感使用者不友善。

---

## 5. 銜接其他 Agent

design-ui-designer（模組 3）給視覺方向 → **frontend-developer** 實作並補效能／無障礙 →
**code-reviewer** 審實作是否符合設計與規則 → **devops-automator** 處理建置與部署。
在模組 2，前端開發者是「把設計變成可驗收前端」的那一棒。
