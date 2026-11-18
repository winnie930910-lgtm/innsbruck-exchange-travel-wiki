# 📝 操作日誌

## [2026-11-18] GRAPH REDESIGN & HTML RENDER | 知識圖譜導向之雜誌風簡報定案發布

Topic: 2027 茵斯布魯克交換生歐洲旅行手冊（Graph 決策拓撲架構 × 歐洲旅遊雜誌風格，11頁投影片式）
Methodology:
- 知識圖譜 4 階段推進：知識實體與約束建模 ➔ 大綱與敘事路徑定案 ➔ 雜誌化視覺呈現（畫面無生硬圖表，以 Editorial 排版具象化節點） ➔ 閉環品質檢核。
- 11 頁對應 Graph 拓撲：Root ➔ Base ➔ Constraints ➔ Timeline ➔ Transport ➔ Pricing State ➔ Sub-Network ➔ Decision Matrix (威尼斯對決) ➔ Targets ➔ Map Expansion ➔ Execution Blueprint。
Result:
- html/innsbruck-magazine-guide.html 正式更新。
- 全面維持數據真值核對（純車程 4h57m vs 5h00m，火車本島直達優勢）、法規精確化（奧地利學生居留證 vs 其他申根國 90 天限制）、學期限制（6/26 結課 ≠ 考完，考試期至 7/23 左右）、不確定性標記覆蓋率 100%、三層知識追溯鏈完整建立。

---

## [2026-11-18] LINT & HTML FIX | 雜誌風簡報品質檢查與核實修訂

Checked:
- html/innsbruck-magazine-guide.html
- wiki/practical/schengen.md
- wiki/travel-windows.md
- wiki/base/university-calendar.md

Result:
1. 【法規精確化】：釐清奧地利學生居留許可（Aufenthaltsbewilligung）在奧境內合法居留免計 90 天，但前往其他申根國觀光時，依申根邊境條例在奧地利以外的申根區仍受「每 180 天內最多停留 90 天」之限制。修訂簡報 Slide 03 與 wiki/practical/schengen.md。
2. 【時間數據一致性修復】：修正 Slide 08 威尼斯交通對決時間比較。RJ81 直達車程為 4h 57m，Flixbus 13:10 班次為 5h 00m，純車程時間幾乎相當（僅差 3 分鐘）。更正火車真正優勢為「直達本島 Santa Lucia 車站，省去 Mestre 轉車進島之 20~30 分鐘與換乘車資，且無公路塞車風險」，移除先前「省下近 2 小時」的不實推論。
3. 【學期限制補強】：於 Slide 04 及 Wiki 行事曆與時段頁面中，明確加入「授課結束 ≠ 考試結束」警告，提醒學生 6/26 結課後考試期（Prüfungszeit）通常延續至 7/23 左右，必須確認個人考程後方可安排 7 月長途旅行。
4. 【不確定性與來源追溯標記】：對所有社群推估與浮動價格（如 Duomo 門票、Innsbruck Card、Nordkette 纜車、easyJet 2027 票價、ETIAS 狀態）加上「⚠️ 待確認」警語。在各頁標籤加入 Wiki 錨點，並於 Slide 11 建立完整的「原始資料 ➔ Wiki 頁面 ➔ 簡報內容」三層知識追溯矩陣與連結。

---

## [2026-11-18] HTML | 雜誌風歐洲交換旅遊教學簡報（VOYAGE TYROL）

Topic: 2027 茵斯布魯克交換生歐洲旅行手冊（歐洲旅遊雜誌風格，11頁投影片式）
Target Audience: 2027 年 2～7 月在 University of Innsbruck 交換、預算有限且希望探索歐洲的交換學生
Design Style: 歐洲旅遊雜誌風格（米白暖沙基調、經典襯線字體、Editorial 排版、高質感留白、適量融入 Assets/ 既有素材）
Integration Case: 復活節 13 天長假（2027.03.22–04.03）IBK 往返威尼斯交通決策模擬（跨行事曆 × ÖBB 早鳥/當天價差 × Flixbus 站點與過夜車 × 威尼斯 Santa Lucia vs Mestre 車站差異 × 學生預算防線）
Sources:
- wiki/base/innsbruck.md
- wiki/base/university-calendar.md
- wiki/travel-windows.md
- wiki/practical/schengen.md
- wiki/transport/oebb.md
- wiki/transport/sparschiene.md
- wiki/transport/flixbus.md
- wiki/transport/budget-airlines.md
- wiki/destinations/venice.md
- wiki/destinations/milan.md
Result: html/innsbruck-magazine-guide.html（共 11 頁，支援鍵盤、導覽點與底部按鈕翻頁）

---

## [2026-11-18] HTML | 從茵斯布魯克出發歐洲旅遊總覽

Topic: 從茵斯布魯克出發的歐洲旅遊總覽（交通 + 目的地 + 時間窗口）
Sources:
- wiki/base/innsbruck.md
- wiki/travel-windows.md
- wiki/transport/oebb.md
- wiki/transport/sparschiene.md
- wiki/transport/flixbus.md
- wiki/transport/budget-airlines.md
- wiki/destinations/venice.md
- wiki/destinations/milan.md
- wiki/practical/schengen.md
Result: html/innsbruck-travel-guide.html（8頁投影片式，深色主題，支援鍵盤翻頁）

---

## [2026-11-18] INGEST | Reddit 社群討論 + 痞客邦遊記（2份 PDF）

Source:
- reddit-inns-to-venice.pdf — Reddit r/Europetravel 討論串（約 3 年前，機翻繁中），主題：「從因斯布魯克到威尼斯最後一刻買票有風險嗎？」（6頁）
- pixnet-12day-germany-austria-italy.pdf — 痞客邦 JR 旅行日誌，2023 年 2 月德奧義 12 天遊記下篇，途經 Innsbruck、Venice、Milan（4頁）

Updated:
- wiki/destinations/venice.md（新建）
- wiki/base/innsbruck.md（新建）
- wiki/destinations/milan.md（新建）
- wiki/transport/oebb.md（更新：新增當天票 €68.50、早鳥 €35–40 比較、座位預訂費 €3、區間車替代方案）
- index.md（更新：新增 3 頁，總頁數 7 → 11（含本次 oebb.md 修訂不計新頁，實際新建 3 頁））
- raw/community/ 新建目錄，存入 2 份原始 PDF

Summary:
社群資料（Reddit + 痞客邦遊記）提供了實際旅遊者的經驗。核心新知識：當天買 ÖBB 票高達 €68.50 vs 提早 €35–40（差距大），座位需額外付 €3 預訂，旺季週末容易售完；區間車可作備案。新建威尼斯目的地頁（含車站差異說明：Santa Lucia 為本島直達站），Innsbruck 城市主頁（Alpenzoo、Nordkette 纜車、Innsbruck card），米蘭目的地頁（Duomo 必須預票、Galleria、中央市場、Naviglio Grande）。

---

## [2026-11-18] INGEST | ÖBB 官方資料（4份 PDF）

Source:
- obb-1-train-connections-europe.pdf — ÖBB 歐洲鐵路路線總覽（官方網站截圖，10頁）
- obb-2-sparschiene.pdf — ÖBB Sparschiene 省錢票說明（官方網站截圖，8頁）
- obb-3-innsbruck-to-florence.pdf — 茵斯布魯克→佛羅倫斯時刻表查詢結果（2026/03/23，2頁）
- obb-3-innsbruck-to-venice.pdf — 茵斯布魯克→威尼斯時刻表查詢結果（2026/03/23，2頁）

Updated:
- wiki/transport/oebb.md（新建）
- wiki/transport/sparschiene.md（新建）
- index.md（新建）
- raw/official/ 存入 4 份原始 PDF

Summary:
建立 ÖBB 交通主頁，整合從茵斯布魯克出發前往義大利（威尼斯、佛羅倫斯）和德國的路線資訊，含具體時刻表與 Sparschiene 票價。建立 Sparschiene 省錢票專頁，詳列各票種差異與退款規則。

## [2026-11-18] INGEST | 廉價巴士 + 廉價航空 + 票價比較（3份 PDF）

Source:
- easyjet-innsbruck-to-london.pdf — easyJet 官網查詢，INN → London Gatwick，2026-12-14~16（3頁）
- flixbus-innsbruck-to-venice.pdf — Flixbus 官網查詢，茵斯布魯克 → 威尼斯，2027-03-22（2頁）
- 12go-innsbruck-to-venice-comparison.pdf — 12go.asia 聚合平台，茵斯布魯克 → 威尼斯多交通方式比較，2027-03-22（7頁）

Updated:
- wiki/transport/flixbus.md（新建）
- wiki/transport/budget-airlines.md（新建）
- wiki/transport/oebb.md（更新：新增 ÖBB vs Flixbus 比較段落）
- index.md（更新：新增 2 頁，總頁數 5 → 7）
- raw/official/ 存入 3 份原始 PDF

Summary:
建立 Flixbus 廉價巴士專頁，含茵斯布魯克→威尼斯 2027-03-22 班次資料（€27.48~28.98，共 7 班），標注重要的出發地點差異（Südbahnstraße 非 Hbf）。建立廉價航空總覽頁，整合 easyJet INN→倫敦路線（€52~106，行李政策、退票規則），以及 INN 機場已知廉航路線。在 oebb.md 新增 ÖBB vs Flixbus 比較表格，結論：Sparschiene 早鳥可競爭 Flixbus 票價且更舒適快速。

---



Source:
- summer_semester_period_holidays.pdf — 茵斯布魯克大學官方公告，2026/2027 學年夏季學期行事曆（2頁）
- summer_semester_screenshot.png — 同內容截圖（含「Periods without lectures」表格）
- travel_and_study_eeas.pdf — EEAS（歐盟對台辦公室）Travel & Study 頁面，台灣護照申根免簽說明（12頁，發布 2025-02-27）

Updated:
- wiki/base/university-calendar.md（新建）
- wiki/travel-windows.md（新建）
- wiki/practical/schengen.md（新建）
- index.md（更新）
- raw/calendar/ 存入行事曆 PDF 與截圖
- raw/official/ 存入 EEAS PDF

Summary:
建立大學行事曆頁面，整理夏季學期（2027.03.01~06.26）所有無課期間，重點包含復活節假期（03.22~04.03，約13天）與多個5月單日假期。建立「可旅遊時段總表」，對每個時段進行季節與自由度評分，提供具體旅遊建議。建立申根規定頁面，說明台灣護照90/180天規則、交換學生居留許可必要性、以及ETIAS尚未啟動的現況。
