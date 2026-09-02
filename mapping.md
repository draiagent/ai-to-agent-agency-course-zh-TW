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
| devops-automator | L3 | 把「設計→實作→審查」的成果自動且安全地送上線 |
| project-manager-senior | L2→L3 | 忠於規格拆任務、每個任務可驗收、不範疇蔓延 |
| meeting-notes-specialist | L1→L2 | 把 AI 當擷取器不當創作者；決議≠討論；抗指令注入 |
| deal-strategist | L2→L3 | MEDDPICC 逐項評分、拆穿一廂情願、缺口配補救 |
| outbound-strategist | L2→L3 | 訊號驅動、可證偽的 ICP、序列每步加值不重複 |
| financial-analyst | L2 | 假設先於結論、一律情境分析、敏感度測試 |
| bookkeeper-controller | L2 | 流程紀律：結帳清單、逐科目對帳、職責分離 |
| ppc-strategist | L2 | 帳戶結構即策略、出價策略選型、擴量不犧牲效率 |
| creative-strategist | L2 | RSA 標題分類、廣告↔到達頁一致、素材當實驗 |
| appsec-engineer | L2→L4 | 威脅建模、安全審查、把 SAST 變流程關卡 |
| penetration-tester | L2→L4 | 僅授權情境；孤立弱點串成攻擊鏈＋業務影響 |
| test-automation-engineer | L2 | 決定性：零 sleep、測試自有資料、角色式選擇器 |
| accessibility-auditor | L2 | 綠燈≠無障礙；純鍵盤實測、對照 WCAG 準則 |
| support-responder | L2→L3 | 解決≠道歉、適當上呈、把客服變流程改善 |
| analytics-reporter | L2 | 圖表≠洞見；要基準、要信心、要可行動建議 |
| synthesist | L2 | 主張追溯一手來源、來源分級、誠實的證據缺口 |
| psychologist | L2 | 引用具名框架、不化約成診斷、承認框架侷限 |
| statistician | L2 | 設計先於資料、相關≠因果、報效果量與區間 |
| clinical-evidence-agent | L2→L4 | 主張要出處、不越診斷權威界線、一份證據多受眾 |
| game-designer | L2→L3 | GDD 化、無魔術數字、從玩家動機往外設計 |
| narrative-designer | L2→L3 | 「真人會這樣說嗎」、種類不同的選擇、敘事連玩法 |
| gis-analyst | L1→L2 | 垂直領域示範：先驗 CRS、記來源、對受眾有效 |
| xr-immersive-developer | L2 | 垂直領域示範：跨裝置、效能預算、優雅降級 |
| business-strategist | L3→L4 | 策略＝「不做什麼」的選擇；量化、取捨、可行動 |
| mcp-builder | L3→L4 | 造工具給 Agent 用：命名即介面、一職責一工具 |
| ecommerce-operator | L2→L3 | 🆕 每個 SKU 完整成本、檔期算真實利潤不追 GMV、回購率是核心 KPI |
| esg-sustainability-officer | L2→L4 | 沒有證據就沒有主張、漂綠是硬底線、目標要有有資金的路徑、雙重重大性 |
| pricing-analyst | L2 | 絕不在真空中定價、一律秀算式、利潤優先、每個建議附 ±20% 敏感度 |
| animal-welfare-advocate | L2→L4 | 🆕 用行為與生理證據不用可愛照片、福利約束凌駕商業最佳化、福利否決權 |
| public-policy-advocate | L3→L4 | 🆕 完整揭露、不碰暗錢、員工聲音≠公司方向、不做 astroturfing、方向是「影響」故護欄最硬 |
| agent-ops-manager | L3→L4 | 🆕 治理數位員工團隊本身：真人擁有者、預設零權限、稽核軌跡、事故回滾；L4「會養」的正式載體 |
| business-continuity-planner | L2→L3 | 🆕 從 BIA 出發、關鍵流程有 RTO/RPO、沒演練過的計畫不算數、標出單點故障 |

_（🆕 = 本 repo 原創新增角色，非上游衍生。每新增一個 Agent 就補一列。）_
