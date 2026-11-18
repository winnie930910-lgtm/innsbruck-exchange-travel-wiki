# 🏔️ 歐洲交換學生旅遊 LLM Wiki (Innsbruck 2027)

> 以 **Innsbruck（茵斯布魯克）** 為基地的歐洲交換學生旅遊知識庫與決策手冊。  
> 適用情境：**2027.02.15 – 2027.07.31** 於 Universität Innsbruck 交換期間之歐洲旅行規劃。

---

## 📖 核心產出與導覽

- **📚 [Wiki 總索引 (index.md)](index.md)**：包含基地、旅遊時段、目的地、交通工具與實用法規。
- **🎨 [歐洲旅遊雜誌風 HTML 簡報 (html/innsbruck-magazine-guide.html)](html/innsbruck-magazine-guide.html)**：
  - 11 頁雜誌風格簡報（Condé Nast Traveller 風格），支援鍵盤 `←` / `→` 互動翻頁。
  - 涵蓋行事曆考程限制、ÖBB 早鳥與劃位、Flixbus 站點防線、威尼斯對決決策矩陣與完整來源追溯。
- **📝 [操作與變更日誌 (log.md)](log.md)**：完整記錄每次 Ingest、Lint 與 HTML 產出歷程。
- **📜 [Agent 行為規範 (AGENTS.md)](AGENTS.md)**：維護本 Wiki 所遵循的核心原則與品質迴圈規範。

---

## 📂 目錄結構

```text
LLM Wiki Notes/
├── Assets/         # 旅遊素材照片（禁止任意修改）
├── raw/            # 原始文檔庫（官方行事曆、時刻表、社群討論、遊記，唯讀）
├── wiki/           # 結構化知識層
│   ├── base/       # 基地資訊（茵斯布魯克城市主頁、大學行事曆）
│   ├── transport/  # 交通專頁（ÖBB、Sparschiene、Flixbus、廉航）
│   ├── destinations/ # 目的地專頁（威尼斯、米蘭等）
│   └── practical/  # 實用資訊（申根與居留許可法規）
├── html/           # 教學型 HTML 簡報輸出
├── index.md        # Wiki 索引入口
├── log.md          # 變更紀錄日誌
└── AGENTS.md       # Agent 治理規範
```
