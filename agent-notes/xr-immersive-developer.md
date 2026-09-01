# 教學導引：XR 沉浸式開發者（xr-immersive-developer）

- **模組**：17 — 空間運算
- **能力層**：L2（會驗）
- **對應 Agent 定義**：[`AI-to-Agent-Agency-zh-TW` / `agents/spatial-computing/xr-immersive-developer.md`](https://github.com/draiagent/AI-to-Agent-Agency-zh-TW/blob/main/agents/spatial-computing/xr-immersive-developer.md)

> 這是第二個「垂直領域示範」——WebXR / AR / VR。重點不是教學員做 XR，
> 而是示範「即使是很新、很專門的技術領域，Agent 的驗收原則（跨平台相容、
> 效能、備援）依然成立」。

---

## 1. 定位：這個 Agent 解決什麼問題

XR 沉浸式開發者用 WebXR 技術（A-Frame、Three.js、Babylon.js）打造瀏覽器端的
AR/VR/XR 應用。它的價值是在「尖端瀏覽器 API」與「直覺的沉浸式設計」之間搭橋。

它關注的驗收面向跟其他工程模組一致：**跨裝置相容**（Meta Quest、Vision Pro、
HoloLens、行動 AR）、**效能**（遮擋剔除、著色器調校、LOD）、**優雅降級與備援**
（不支援 WebXR 時的 fallback）、**無障礙**。

一句話：**它把「一個能在我的頭盔上跑的 demo」提升到「跨裝置、有效能預算、有備援的 XR 體驗」。**

### 什麼時候召喚它

- 要用 WebXR 建瀏覽器端的 AR/VR/XR 應用
- 要整合手部追蹤、捏合、注視、控制器輸入
- 要做效能最佳化（遮擋剔除、LOD、著色器）
- 要除錯跨瀏覽器/跨執行環境的空間輸入問題

### 什麼時候「不要」召喚它

- 是原生 iOS/Android XR（非 Web）→ 需要別的專門角色
- 是一般 3D UI（非沉浸式）→ frontend-developer（模組 1）

---

## 2. Before / After 示範

**任務**：「幫我做一個 WebXR 的產品展示。」

### Before（無 Agent）

> 產出：一個在開發者自己的 Quest 上能跑的場景。換到手機 AR 就崩、
> 場景太重掉幀、不支援 WebXR 的瀏覽器直接白畫面。

### After（召喚 xr-immersive-developer）

> 會產出：
> - 用效能與無障礙最佳實務建立的專案骨架
> - 跨裝置相容層（Quest / Vision Pro / HoloLens / 行動 AR）
> - 效能設計：遮擋剔除、LOD 系統、著色器調校，附效能預算
> - 輸入抽象：手部追蹤 / 捏合 / 注視 / 控制器，統一介面
> - 優雅降級：不支援 WebXR 時的 2D fallback

**課堂提問**：讓學員理解「demo 能跑」與「跨裝置能跑」的差別——這跟
test-automation-engineer（模組 10）的「demo 過 vs 正式環境過」是同一個道理。

---

## 3. 怎麼帶學員「驗收」它的產出

| 檢核點 | 有 / 無 |
|---|---|
| 有跨裝置相容層，不是只在一種頭盔上測過 | |
| 有效能設計（遮擋剔除 / LOD / 著色器）與效能預算 | |
| 輸入是抽象的（手部/捏合/注視/控制器統一介面），不是綁死一種 | |
| 有優雅降級 / 備援（不支援 WebXR 時的 fallback） | |
| 有無障礙考量 | |
| 場景是模組化、元件驅動的 | |

若只在開發者自己的裝置上測過、沒有 fallback → 退回。

---

## 4. 常見誤區

1. **「我的頭盔能跑」= 完成。** 跨裝置相容才是。
2. **場景不做效能設計。** VR 掉幀會讓人不適，效能不是選配。
3. **綁死一種輸入。** 手部追蹤與控制器要抽象成統一介面。
4. **沒有 fallback。** 不支援 WebXR 的瀏覽器不該白畫面。

---

## 5. 銜接其他 Agent

xr-immersive-developer 跟 frontend-developer（模組 1）共用「效能 + 無障礙 + 備援」
的驗收原則，跟 ui-designer（模組 2）共用「設計系統」思維（只是換成 3D 互動表面）。
在模組 17，這位示範「最新的技術領域，Agent 的驗收框架依然適用」。
