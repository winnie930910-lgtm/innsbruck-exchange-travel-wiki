# AGENTS.md — 歐洲交換學生旅遊 LLM Wiki

> 本文件定義 Agent 維護本 Wiki、處理使用者提供資料，以及產生教學 HTML 簡報時應遵守的規則。

---

## 1. Project Overview

本專案是一個以**歐洲交換學生旅遊規劃**為主題的 LLM Wiki，主要以 Innsbruck（茵斯布魯克）作為旅遊出發基地。

- **主要使用者**：交換學生
- **主要情境**：2027 年 2 月中至 7 月底在 Innsbruck 交換期間的歐洲旅行
- **範圍**：整個歐洲，依交通便利性與旅遊價值決定知識深度
- **風格**：預算有限、重視重要景點與體驗，不以深入歷史研究或高體力行程為主
- **核心目標**：建立可持續累積的旅遊知識，支援目的地比較與旅行決策

本 Wiki 不只是旅遊資料的集合，而是讓 AI 能夠將不同來源的知識互相連結、比較與整合。

---

## 2. Core Principles

### 2.1 Knowledge-first

Wiki 的結構應由知識本身逐漸形成，而非一開始建立過度僵化的分類。

現有資料夾與頁面只是目前的組織方式。Agent 可以依照新資料建立新的知識頁面、合併或調整相關內容，但必須維持：

- 可讀性
- 可追溯性
- 既有知識完整性
- 清楚的知識連結

不要為了符合固定分類而將知識硬塞進不適合的頁面。

### 2.2 Source Traceability

重要資訊必須能追溯至原始來源。

盡可能記錄：

- Source
- Publisher / Author
- Published / Updated date
- Retrieved date
- 適用期間
- 必要時的可信度或限制

不同來源若存在差異，不得自行隱藏其中一方。

### 2.3 User-provided Sources

目前 Wiki **只處理使用者提供的資料**。

Agent 不應自行搜尋或引入新的外部來源，除非使用者另外要求。

`raw/` 中的原始資料為唯讀，Agent 可以閱讀，但不得修改。

### 2.4 Controlled Autonomy

Agent 可以自主：

- 建立知識頁面
- 更新既有內容
- 建立頁面間的連結
- 更新索引
- 整合重複資訊
- 執行品質檢查

Agent 不得：

- 任意刪除既有知識
- 修改原始資料
- 將未證實資訊寫成事實
- 在來源衝突時自行掩蓋差異
- 大幅改變 Wiki 架構而不告知使用者

---

## 3. Directory Structure

```text
LLM Wiki Notes/
├── Assets/          # HTML 簡報素材，禁止修改
├── raw/             # 使用者提供的原始資料，唯讀
├── wiki/            # Agent 維護的知識層
├── index.md         # Wiki 索引
├── log.md           # 操作紀錄
└── AGENTS.md        # 本規範
```

### Directory Rules

- `Assets/`：Agent 不得讀取、修改或刪除其中檔案。
- `raw/`：只能讀取，不得修改原始資料。
- `wiki/`：Agent 可以建立與更新內容，但不得任意刪除既有知識。
- 檔名原則上使用英文小寫 kebab-case。
- 不強制所有知識必須符合固定的資料夾分類。
- `index.md` 應維持 Wiki 的主要入口與頁面索引。

### `index.md` 格式參考

```markdown
# 📚 Wiki 索引

> 最後更新：{日期} | 總頁數：{N}

## 🏠 基地
- [innsbruck.md](wiki/base/innsbruck.md) — 茵斯布魯克城市主頁
- ...

## 🏙️ 目的地
- [munich.md](wiki/destinations/munich.md) — München（慕尼黑），從 IBK 出發 2 小時
- ...

## 🚄 交通
- ...

## 🍽️ 美食
- ...

## 🎒 實用資訊
- ...

## 🗓️ 行程
- ...
```

索引的分類方式可隨 Wiki 成長調整，不限於上述範例。

---

## 4. Knowledge Ingest Workflow

當使用者提供新的資料時，遵循以下流程：

```text
User-provided Source
        ↓
Read & Extract
        ↓
Find Related Wiki Knowledge
        ↓
Compare New / Existing Information
        ↓
 ┌───────────────┐
 │ New / Update  │
 │ Conflict      │
 │ Duplicate     │
 └───────────────┘
        ↓
Integrate & Link
        ↓
Synthesize
        ↓
Quality Check
        ↓
Update Wiki + Index + Log
```

### 4.1 Read & Extract

完整閱讀資料，辨識：

- 重要事實
- 數據與價格
- 時間與季節資訊
- 交通資訊
- 目的地與活動
- 實用建議
- 與既有知識可能相關的概念

### 4.2 Compare

在寫入 Wiki 前，先確認：

- 是否已有相關頁面？
- 新資料是在補充、更新還是重複既有內容？
- 是否與現有資料衝突？
- 是否可以連結到其他知識？

### 4.3 Integrate

依照知識本身決定：

- 建立新頁面
- 更新既有頁面
- 合併重複內容
- 建立跨主題連結

不應為了固定分類而建立大量重複頁面。

### 4.4 Conflict Handling

若新舊資料衝突：

1. 保留相關來源。
2. 標示 `⚠️ 資訊衝突`。
3. 說明不同來源的差異。
4. 不自行猜測哪一個一定正確。
5. 必要時提醒使用者進一步確認。

### 4.5 Quality Check Loop

更新 Wiki 後必須檢查：

- 來源是否保留
- 是否產生無來源的資訊
- 是否有重複內容
- 頁面連結是否合理
- 是否有明顯矛盾
- 時間敏感資訊是否標示日期

若檢查發現問題，回到對應的 Compare / Integrate 步驟修正後重新檢查。

---

## 5. Query Workflow

使用者提問時：

```text
User Question
     ↓
Read Index
     ↓
Find Relevant Wiki Pages
     ↓
Combine Knowledge
     ↓
Answer
```

回答應以 Wiki 現有內容為主要依據，並指出相關來源。

Query 預設為 **read-only**，不應因為一般提問而自動修改 Wiki。

如果產生具有長期價值的新知識，例如完整的目的地比較或旅行規劃，可詢問使用者是否要保存至 Wiki。

---

## 6. Wiki Content Guidelines

所有 Wiki 頁面原則上使用**繁體中文**。

專有名詞第一次出現時使用：

> 原文（中文）

依類型範例：

- 景點：`Nordkette（北鏈山纜車）`
- 餐廳：`Stiftskeller（修道院地窖餐廳）`
- 交通：`ÖBB（奧地利聯邦鐵路）`
- 票券：`Klimaticket（氣候票，全奧交通年票）`
- 食物：`Wiener Schnitzel（維也納炸肉排）`
- 城市：`Salzburg（薩爾茨堡）`

後續出現可只用中文簡稱或原文擇一。

金額統一使用 `€`，必要時提供台幣概算。

時間敏感資訊，例如：

- 票價
- 開放時間
- 交通班次
- 活動日期
- 入境規定

應標示資料日期或適用期間，並在資訊可能變動時標示：

> ⚠️ 待確認

---

## 7. Time & Travel Context

主要應用情境為：

**2027.02.15～2027.07.31，Innsbruck 交換期間。**

### 季節旅遊對照表

| 時段 | 月份 | 旅遊意義 |
|------|------|----------|
| 冬末 | 2月中~3月 | 阿爾卑斯滑雪季尾聲，氣溫低、日照短，適合近距離城市遊或室內景點 |
| 春季 | 4月 | 復活節假期（歐洲長假），適合中程旅行，天氣漸暖 |
| 最佳旅遊季 | 5~6月 | 日照長、氣候宜人、尚未到暑假人潮高峰，性價比最高 |
| 夏季 | 7月 | 交換尾聲，可安排收尾長途行程，注意南歐高溫 |

Agent 在推薦目的地或評估行程時，應參照此表判斷季節適合度。

旅行建議應考量：

- 季節與氣候
- 學期與假期
- 交通時間
- 學生預算
- 旅行天數
- 體力需求

2027 年情境是本 Wiki 的主要應用案例，但基礎知識應盡可能保持長期可用。

---

## 8. Lint / Wiki Health Check

Lint 可由使用者要求，或在 Ingest 後需要時執行。

主要檢查：

- 資訊是否過期
- 不同來源是否衝突
- 是否有孤立頁面
- 是否有重複內容
- 是否有缺少來源的資訊
- Wiki 連結是否正常
- 重要頁面是否需要更新

檢查結果應簡單記錄於 `log.md`。

---

## 9. HTML Teaching Presentation

HTML 簡報是 Wiki 知識的**教學型輸出**，不是單純複製 Wiki 頁面。

生成流程：

```text
Wiki Knowledge
      ↓
Select Relevant Knowledge
      ↓
Organize Teaching Structure
      ↓
Content Verification
      ↓
Generate HTML
      ↓
Final Check
```

簡報應讓原本不了解主題的人能夠逐步理解。

基本結構可包含：

1. 主題介紹
2. 基本概念
3. 重要知識
4. 實際案例或比較
5. 旅行決策應用
6. 重點整理

### HTML Rules

- 所有內容必須有 Wiki 知識作為依據。
- 不得憑空加入未存在於 Wiki 的重要事實。
- 可以重新組織 Wiki 內容，使其更適合教學。
- `Assets/` 僅可作為既有視覺素材來源，不得修改其中檔案。
- 產生 HTML 後應檢查內容與 Wiki 是否一致。

---

## 10. Operation Log

重要操作記錄於 `log.md`，例如：

```text
[YYYY-MM-DD] INGEST
Source: {資料名稱}
Updated: {受影響頁面}
Summary: {簡短說明}

[YYYY-MM-DD] LINT
Checked: {檢查範圍}
Result: {發現的問題與處理方式}

[YYYY-MM-DD] HTML
Topic: {簡報主題}
Sources: {使用的 Wiki 頁面}
Result: {產生結果}
```

---

## 11. Agent Behavior

Agent 必須：

1. **先讀後寫**：修改頁面前先讀取現有內容。
2. **保留來源**：重要資訊必須可以追溯。
3. **區分事實與分析**：不要將推論寫成已確認事實。
4. **標示不確定性**：無法確認的資訊使用 `⚠️ 待確認`。
5. **維持知識連結**：建立合理的跨頁面關聯。
6. **優先整合而非複製**：新資料應補充 Wiki，而不是大量建立重複內容。
7. **保持 Wiki 可演化**：不要因預設分類限制新的知識結構。

Agent 不得：

1. 修改 `Assets/`。
2. 修改 `raw/`。
3. 修改 `AGENTS.md`，除非使用者明確要求。
4. 任意刪除既有 Wiki 知識。
5. 捏造不存在於來源中的重要資訊。

---

## 12. Quick Reference

```text
INGEST
Read → Compare → Integrate → Link → Verify → Update → Log

QUERY
Read Index → Retrieve Knowledge → Synthesize → Answer

LINT
Check → Find Problems → Fix → Re-check → Log

HTML
Select Wiki Knowledge → Teach → Verify → Generate → Check
```
