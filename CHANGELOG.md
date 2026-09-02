# 更新紀錄（CHANGELOG）

日期為絕對日期（YYYY-MM-DD）。

## [未發佈]

### 2026-09-02 — 組織韌性治理席位 2 位教案（→ 46 位）

- `agent-notes/` + `labs/` × 2：agent-ops-manager、business-continuity-planner
  （對應姊妹 repo 原創新增的 2 位角色）。
  - **agent-ops-manager**（模組 18，🆕 原創）：治理數位員工團隊本身——真人擁有者、
    預設零權限、稽核軌跡、成本歸屬、事故回滾。整門課 L4「會養」的正式落點。
  - **business-continuity-planner**（模組 18，🆕 原創）：從 BIA 出發、關鍵流程有 RTO/RPO、
    沒演練過的計畫不算數、標出單點故障；與 `security/` 事件處理互補。
- 模組 18 治理席位改為兩組：「面對不在場的利害關係人」與「面對組織自身的韌性」。
- 更新 `mapping.md`（+2 列）、`ATTRIBUTION.md`、`curriculum/課程總覽.md`、`README.md`：進度 → 46 位。

### 2026-09-02 — 跨域專業與治理席位補課（→ 44 位）

- `agent-notes/` + `labs/` × 5：ecommerce-operator、esg-sustainability-officer、
  pricing-analyst、animal-welfare-advocate、public-policy-advocate —— 對應姊妹 repo
  補收錄與原創新增的 5 位角色。
  - **ecommerce-operator**（模組 4，🆕 原創）：每個 SKU 完整成本、檔期算真實利潤不追 GMV、
    回購率是核心 KPI、多通路要改製不是複製。
  - **esg-sustainability-officer**（模組 18）：沒有證據就沒有主張、漂綠是硬底線、
    淨零目標要有有資金的路徑、雙重重大性評估。
  - **pricing-analyst**（模組 18）：絕不在真空中定價、一律秀算式、利潤優先、
    每個定價建議附 ±20% 敏感度分析。
  - **animal-welfare-advocate**（模組 18，🆕 原創）：用行為與生理證據不用可愛照片、
    福利約束凌駕商業最佳化、福利否決權。
  - **public-policy-advocate**（模組 18，🆕 原創）：完整揭露、不碰暗錢、
    員工聲音≠公司方向、不做 astroturfing；方向是「影響」故護欄最硬。
    Lab 僅教「如何負責任地做政策倡議」，不教「如何有效遊說或影響選舉」。
- 模組 18 新增「治理席位群」說明：esg-sustainability-officer、animal-welfare-advocate、
  public-policy-advocate 三者分別是對外問責、對內代表、對外影響。
- 更新 `mapping.md`（+5 列）、`ATTRIBUTION.md`（新增「原創教學對象」段）、
  `curriculum/課程總覽.md`（模組 4／18 名單、進度 → 44 位）。

### 新增
- 專案骨架：`README.md`、`LICENSE`（CC BY-SA 4.0）、`ATTRIBUTION.md`、`mapping.md`。
- `curriculum/課程總覽.md` — 6 模組課程地圖與教學法說明。
- `agent-notes/backend-architect.md` — 後端架構師教學導引（定位、召喚時機、
  Before/After 示範、常見誤區）。
- `labs/backend-architect-lab.md` — 後端架構師動手練習 3 題 + 評分要點。
- `agent-notes/frontend-developer.md` + `labs/frontend-developer-lab.md` — 前端開發者
  教學導引與動手練習（效能／無障礙驗收、鍵盤實測）。
- `agent-notes/code-reviewer.md` + `labs/code-reviewer-lab.md` — 程式碼審查者
  教學導引與 Lab（完整審查、必須 vs 建議、把審查變成團隊關卡）。
- `agent-notes/devops-automator.md` + `labs/devops-automator-lab.md` — DevOps 自動化
  工程師教學導引與 Lab（手動→流水線、零停機與自動回滾、上線後可觀測）。
- `agent-notes/prompt-engineer.md` + `labs/prompt-engineer-lab.md` — 提示工程師教學
  導引與 Lab（一句話變規格、抓迴歸、提示 vs Agent 觀念題）。整門課的觀念起點。
- `agent-notes/ai-engineer.md` + `labs/ai-engineer-lab.md` — AI 工程師教學導引與 Lab
  （同一功能三種條件、擋下用大模型做小事、上線後漂移監控）。
- `agent-notes/multi-agent-systems-architect.md` + `labs/multi-agent-systems-architect-lab.md`
  — 多代理系統架構師教學導引與 Lab（先畫拓撲再問失敗、上下文預算、把 demo 變架構）。
  模組 1 的收尾與最高點。

- `agent-notes/ui-designer.md` + `labs/ui-designer-lab.md` — UI 設計師教學導引與 Lab
  （token 先行、狀態與無障礙盤點、交付給開發者）。
- `agent-notes/ux-researcher.md` + `labs/ux-researcher-lab.md` — UX 研究員教學導引與 Lab
  （先問題後方法、拆穿想像的 persona、把回饋變建議）。

- `agent-notes/product-manager.md` + `labs/product-manager-lab.md` — 產品經理教學導引與
  Lab（解法還原成問題、成功指標表、RICE 排序與說不）。
- `agent-notes/sprint-prioritizer.md` + `labs/sprint-prioritizer-lab.md` — Sprint 優先
  排序師教學導引與 Lab（框架排序、產能真相、sprint 目標 vs 待辦）。

- `agent-notes/` + `labs/` × 4：content-creator、growth-hacker、seo-specialist、
  ai-citation-strategist —— 行銷模組四位教學導引與 Lab（內容支柱、成長實驗、
  自我競食稽核、AI 引用稽核）。

### 里程碑
- ✅ **模組 1（工程）教案完成**：7 位
- ✅ **模組 2（設計）教案完成**：2 位
- ✅ **模組 3（產品）教案完成**：2 位
- ✅ **模組 4（行銷）教案完成**：4 位
- 🎉 **四個教案模組全數完成（15 位數位員工，各含教學導引 + Lab）**

### 待辦
- 各模組投影片大綱
- 視上游更新同步；其餘 14 個部門的教案（定義檔已在姊妹 repo）
- 模組 1、3、4、5、6
- 各模組投影片大綱
- 釘選上游 commit SHA
