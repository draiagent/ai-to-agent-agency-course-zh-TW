# 貢獻指南（CONTRIBUTING）

維護：**AI Coach 益力康陳董｜2026 AI to Agent**（draiagent）。

本 repo 是**教學教材**，不含 Agent 定義檔。
若你要修的是 Agent 定義本身（翻譯錯誤、frontmatter 壞掉、角色設定），
請到姊妹 repo
[`AI-to-Agent-Agency-zh-TW`](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW)
開 issue／PR。

---

## 你可以貢獻什麼

- 既有教學導引（`agent-notes/`）或 Lab（`labs/`）的勘誤與補強
- 尚未涵蓋角色的教案（對象一律是姊妹 repo 已存在的定義檔）
- `curriculum/` 的模組規劃、垂直應用整合模組
- `mapping.md` 能力光譜對照的修正

---

## 教學導引 `agent-notes/<slug>.md` 結構

固定六段：

1. **抬頭** — 模組、能力層（L0–L4）、對應定義檔連結
2. **定位** — 解決什麼問題、什麼時候召喚它、什麼時候不要
3. **Before / After 示範** — 同一任務，無 Agent 與有 Agent 的產出對照 + 課堂提問
4. **驗收檢核表** — 帶學員逐項檢查產出的表格
5. **常見誤區** — 3–5 條
6. **銜接其他 Agent** — 與上下游角色如何串接

## Lab `labs/<slug>-lab.md` 結構

- **抬頭** — 模組、能力層、建議時間、前置條件
- **練習 1／2／3** — 階梯式（會驗 → 會編），每題附「評分要點」（✅ 對的樣子 / ❌ 要退回的樣子）
- **繳交** — 明確列出要交的產物 + 一題 100–150 字反思

> 風格：介面語言繁體中文、台灣用語；適合課堂投影（重點清楚、表格化）。
> 對「影響力／權限」類角色（政策倡議、滲透測試等），Lab 一律使用靶機／紙上推演，
> 絕不對真實、未授權的系統操作。

### 術語

技術術語一律以姊妹 repo 的
[`docs/術語對照表.md`](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW/blob/main/docs/術語對照表.md)
為準（該表為兩個 repo 共用的單一來源）。遇到表上沒有的新術語，先到姊妹 repo 補進對照表再用。

---

## 流程

1. 認領一個角色（對照 [`curriculum/課程總覽.md`](curriculum/課程總覽.md)）。
2. 確認姊妹 repo 已有該定義檔；`agent-notes/` 的抬頭連結指向它。
3. 撰寫 note + lab，**slug 與定義檔完全一致**（例：定義檔 `agents/gis/analyst.md` → 教案 `agent-notes/analyst.md`）。
4. 更新對照與索引：
   - `ATTRIBUTION.md`（「逐項對應」或「原創教學對象」表）
   - `mapping.md`（能力光譜補一列）
   - `curriculum/課程總覽.md`（模組名單）
   - `CHANGELOG.md`
5. 一個角色一個 PR，方便審。

---

## 授權

送出貢獻即表示同意你的教學文字以 **CC BY-SA 4.0** 釋出（見 [`LICENSE`](LICENSE)）。
引用 Agent 原文時，僅摘錄教學所需之最小段落並標明出處。
