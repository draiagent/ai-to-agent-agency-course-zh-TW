# ai-to-agent-agency-course-zh-TW

**「AI to Agent」公開教學與課程教案（繁體中文）**

一套可直接授課的完整教案，帶領學員從「會用 AI」升級為「能編派一支 AI Agent 團隊」。
教材以姊妹專案的繁體中文 AI 專家 Agent 角色庫為對象，涵蓋 18 個部門、46 位數位員工，
每位皆附一份教學導引與一份動手練習。

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](LICENSE)
[![Agent 定義](https://img.shields.io/badge/agents-AI--to--Agent--Agency--zh--TW-blue)](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW)
[![模組](https://img.shields.io/badge/modules-18%20departments%20%C2%B7%2046%20agents-informational)](curriculum/課程總覽.md)

---

## 目錄

- [關於本課程](#關於本課程)
- [內容結構](#內容結構)
- [適用對象](#適用對象)
- [能力光譜（L0–L4）](#能力光譜l0l4)
- [課程地圖](#課程地圖)
- [整合模組：垂直應用示範](#整合模組垂直應用示範)
- [授課方式](#授課方式)
- [致謝](#致謝)
- [授權](#授權)
- [維護者](#維護者)

---

## 關於本課程

生成式 AI 的教學多半停在「如何寫出好的提示詞」。本課程的目標是下一步：
**讓學員理解 Agent（角色 + 專業流程 + 交付物）與提示詞的本質差異，並具備編派、
驗收、迭代一支跨部門 AI Agent 團隊的能力。**

課程以一套結構完整的繁體中文 Agent 角色庫為教材，每位數位員工對應一個真實職能。
學員透過「定位 → Before/After 示範 → 動手練習 → 常見誤區」的固定節次，
逐步建立從 L0（會問）到 L4（會養）的能力。

- **Agent 定義檔**由姊妹專案
  [`AI-to-Agent-Agency-zh-TW`](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW)（MIT）維護。
- **本專案**僅包含教學內容：課綱、教學導引、動手練習、能力對照分析。
- 兩專案分離授權，可獨立使用，亦互相引用。

---

## 內容結構

| 目錄／檔案 | 內容 |
|---|---|
| [`curriculum/`](curriculum/) | 課程總覽、各模組學習目標與節次規劃、垂直應用整合模組 |
| [`agent-notes/`](agent-notes/) | 每位數位員工一份教學導引：定位、召喚時機、Before/After 示範、驗收檢核表、常見誤區、與其他角色的銜接 |
| [`labs/`](labs/) | 每位數位員工一份動手練習：3 題階梯式題目 + 評分要點 + 繳交規格，可直接作為課堂作業 |
| [`mapping.md`](mapping.md) | 46 位數位員工 ↔「AI to Agent」能力光譜（L0–L4）的鬆耦合對照 |

**不包含**：Agent 定義檔本身（在姊妹專案）、教學影片、簡報成品檔。

---

## 適用對象

- 開設生成式 AI／AI 應用課程、需要成熟教案的**講師與培訓單位**
- 希望從「單次對話式使用 AI」推進到「多 Agent 協作」的**企業團隊**
- 依 `curriculum/` 順序自學、搭配 `labs/` 練習的**個人學習者**

---

## 能力光譜（L0–L4）

本課程以下列五層能力描述學員的進程，完整對照見 [`mapping.md`](mapping.md)：

| 層級 | 名稱 | 學員在這一層學會 |
|---|---|---|
| L0 | 會問 | 寫得出清楚的一次性提示詞 |
| L1 | 會派 | 判斷什麼任務該交給哪一種專家角色 |
| L2 | 會驗 | 看得懂產出、能指出缺漏並要求修正 |
| L3 | 會編 | 把多個 Agent 串成一條有交付物的流程 |
| L4 | 會養 | 依專案回饋調整角色設定，沉澱為團隊可重用的資產 |

---

## 課程地圖

姊妹專案收錄 **18 個部門、46 位數位員工**（41 位翻譯 + 5 位原創）。
**本課程 18 個部門教案全數完成**，每位數位員工一份教學導引 + 一份 Lab。
完整模組表見 [`curriculum/課程總覽.md`](curriculum/課程總覽.md)。

| 模組群 | 部門 | 位數 |
|---|---|---|
| 1–4 | 工程、設計、產品、行銷 | 7 + 2 + 2 + 5 |
| 5–11 | 專案管理、銷售、財務、付費媒體、安全、測試、客戶支援 | 各 2 |
| 12–17 | 研究、學術、醫療、遊戲開發、GIS、空間運算 | 1／2／1／2／1／1 |
| 18 | 跨域專業 specialized（含 ESG 永續長、定價分析師、動物福利代言人 🆕、政府關係與公共政策 🆕、數位員工長 🆕、營運持續規劃師 🆕；電商營運 🆕 併入行銷模組） | 8 |

> 🆕 為姊妹專案原創新增角色（非上游衍生），詳見 [`ATTRIBUTION.md`](ATTRIBUTION.md)。
> 完成進度以 [`CHANGELOG.md`](CHANGELOG.md) 為準。

---

## 整合模組：垂直應用示範

除逐一介紹的部門模組外，本課程另設一個**整合模組**，示範 L3（會編）與 L4（會養）：

| 檔案 | 內容 |
|---|---|
| [`curriculum/垂直應用-益生寵愛寵物餐廳.md`](curriculum/垂直應用-益生寵愛寵物餐廳.md) | 以一家中小型寵物餐廳為例，用「資源整合 → 價值共創 → 線上線下整合 → 商業模式創新」四個理論主軸，將 20 餘位數位員工編組為 O2O 與 B2B OEM/ODM 雙軌經營團隊。搭配姊妹專案的 `rosters/` 團隊配方檔。 |

---

## 授課方式

每位數位員工建議一個節次（約 60 分鐘），結構固定：

| 時間 | 內容 |
|---|---|
| 0–10 分 | 定位：這個角色解決什麼問題、什麼時候不該用它 |
| 10–25 分 | Before/After 示範：同一任務，無 Agent 與有 Agent 的產出對照 |
| 25–50 分 | 動手 Lab（`labs/<slug>-lab.md`） |
| 50–60 分 | 常見誤區，以及與下一個角色的銜接 |

模組 1（工程）為觀念地基，建議先行；其餘部門模組彼此獨立，可依受眾需求選用。

### 快速開始

1. 閱讀 [`curriculum/課程總覽.md`](curriculum/課程總覽.md)，掌握全課架構。
2. 自姊妹專案安裝對應的 Agent 定義檔至你的 AI 工具。
3. 依模組順序，以 `agent-notes/<slug>.md` 授課、`labs/<slug>-lab.md` 出作業。

---

## 致謝

本教材的 Agent 角色設定、專業流程與方法論，多數源自開源專案，謹此致謝：

- **原始專案**：[The Agency — `agency-agents`](https://github.com/msitarzewski/agency-agents)
- **原始作者**：Michael Sitarzewski（[@msitarzewski](https://github.com/msitarzewski)）與 AgentLand Contributors
- **原始授權**：MIT License

繁體中文 Agent 定義檔由姊妹專案
[`AI-to-Agent-Agency-zh-TW`](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW) 維護。
逐項來源見 [`ATTRIBUTION.md`](ATTRIBUTION.md)。

---

## 授權

- **本專案教學文字**：CC BY-SA 4.0（見 [`LICENSE`](LICENSE)）。轉載或改作請標示來源，
  並以相同條款分享。
- **被引用的 Agent 原文片段**：MIT，著作權歸原作者，僅摘錄教學所需之最小段落。
- 逐項來源與原創標記見 [`ATTRIBUTION.md`](ATTRIBUTION.md)。

---

## 維護者

**AI Coach 益力康陳董｜2026 AI to Agent**

- Agent 定義檔專案：[`AI-to-Agent-Agency-zh-TW`](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW)（MIT）
- 議題、勘誤與貢獻：請透過本 repo 的 Issues 與 Pull Requests

> 「2026 AI to Agent」是本年度的方法論主張：從「會用 AI」邁向「讓 AI 自主完成工作」。
> 本課程是該主張的公開教學實作。
