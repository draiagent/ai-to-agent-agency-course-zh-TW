# Agent ↔「AI to Agent」能力層對照

> 鬆耦合對照。本 repo 不綁定任何單一框架；下表只是幫助講師把每個 Agent
> 放進「從人工操作 → 交給 Agent」的能力光譜上。

## 能力光譜（由淺入深）

| 層 | 名稱 | 學員在這一層學會 |
|---|---|---|
| L0 | 會問 | 寫得出清楚的一次性 prompt |
| L1 | 會派 | 知道什麼任務該交給哪種專家角色 |
| L2 | 會驗 | 看得懂產出、能指出哪裡不對、要求修正 |
| L3 | 會編 | 把多個 Agent 串成一條有交付物的流程 |
| L4 | 會養 | 依專案回饋調整角色設定、沉澱成團隊資產 |

## 對照表

| Agent | 主要落點 | 教學重點 |
|---|---|---|
| prompt-engineer | L0→L1 | prompt 與「角色 + 流程 + 交付物」的差別 |
| ai-engineer | L1 | 什麼問題適合用 LLM、什麼不適合 |
| multi-agent-systems-architect | L3 | 多 Agent 分工、交接、避免互相打架 |
| rapid-prototyper | L1→L2 | 用 Agent 快速做出可驗證的原型 |
| **backend-architect** | **L2→L3** | **看得懂架構取捨、能驗收系統設計文件、把設計→實作→審查串起來** |
| frontend-developer | L2 | 驗收 UI 實作的效能與無障礙，用工具實測而非目測 |
| ux-researcher | L1→L2 | 判斷該做哪種研究、驗收研究是否有資料支撐（非想像的 persona） |
| ui-designer | L2 | 驗收設計是否成系統、無障礙是否達標、能否直接交付開發 |
| product-manager | L2→L3 | 從問題出發、把散落的職能編成一條有成功指標的產品線 |
| sprint-prioritizer | L3 | 在有限產能下排序、把「都要」變成「這個 sprint 做這幾個」 |
| content-creator | L1→L2 | 先有內容策略（受眾／支柱）再有內容；驗收成效指標 |
| growth-hacker | L2→L3 | 把行銷點子寫成實驗、看漏斗、算 CAC/LTV、排實驗排程 |
| seo-specialist | L2 | 先做自我競食稽核、判搜尋意圖、驗技術 SEO 與內容結構 |
| ai-citation-strategist | L2 | 多平台稽核 AI 引用、基準→修正包→複查、分清 AEO≠SEO |
| code-reviewer | L2 | 把「會驗」制度化成一道關卡 |
| devops-automator | L3 | 部署、CI/CD 交給 Agent 的邊界 |
| security-engineer | L2→L4 | 安全審查作為流程中的固定環節 |

_（每新增一個 Agent 就補一列。）_
