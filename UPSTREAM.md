# 上游對應（UPSTREAM）

本 repo 是教學教材，**不直接消費上游** `msitarzewski/agency-agents`。
Agent 定義檔的翻譯與上游同步，由姊妹 repo 負責。

| 項目 | 值 |
|---|---|
| 教材對象 | 姊妹 repo [`AI-to-Agent-Agency-zh-TW`](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW) 的繁體中文定義檔 |
| 上游專案 | https://github.com/msitarzewski/agency-agents（MIT） |
| 上游釘選 commit | `3c9588880b7cafaec325a104899fd8bbe27e7d72`（與姊妹 repo 一致，另見 `ATTRIBUTION.md`） |
| 上游最後更新 | 2026-08-26 |

## 同步原則

1. **定義檔的上游同步由姊妹 repo 負責**（見其 `UPSTREAM.md` 與 `CHANGELOG.md`）。
2. 姊妹 repo 因上游語意變更而重譯某角色時，檢查本 repo 對應的 `agent-notes/<slug>.md`
   與 `labs/<slug>-lab.md` 是否需要跟著調整，並於 `CHANGELOG.md` 記錄。
3. 姊妹 repo 釘選 commit 更新時，同步更新本 repo `ATTRIBUTION.md` 的「上游快照」表與本檔。
4. **檢視頻率**：每季一次，或當姊妹 repo 發佈重大版本時。

## 同步檢查清單

- [ ] 對照姊妹 repo `CHANGELOG.md`，找出自上次同步後有語意變更的角色
- [ ] 逐一檢查對應的 `agent-notes/` 與 `labs/` 是否需要更新
- [ ] 更新 `mapping.md`（若能力層定位改變）
- [ ] 更新 `ATTRIBUTION.md` 上游快照表與本檔的釘選 commit
- [ ] 更新 `CHANGELOG.md`
