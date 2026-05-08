# 🌟 曜日獵人星級排位總榜 (HUNTER ASSOC. DB)
> **MAGI SYSTEM VER.2.0 - TACTICAL OPS READY**

這是一個專為「曜日羽球團」打造的專屬星級積分排行榜系統。結合了《獵人》的念能力階級設定與《EVA》MAGI 系統的賽博龐克（Cyberpunk）視覺風格。系統會自動讀取 Google 試算表（Google Sheets）的即時資料，將枯燥的羽球積分轉化為熱血的「獵人考核檔案」。

## ✨ 核心特色 (Key Features)

* **☁️ 雲端資料同步 (Cloud Sync):** 直接讀取 Google Sheets 發佈的 CSV 檔案，不需架設後端資料庫。更新表單，網頁即時生效。
* **🎴 戰術級玩家卡片 (Tactical Player Cards):** 點擊玩家即可呼叫出精美的 3D 傾斜特效卡片（支援電腦版滑鼠互動）。
* **💎 動態特效分級 (Dynamic Tier Visuals):** 依據白金 (SSR)、黃金 (SR)、白銀 (S)、青銅 (A/B) 給予不同的全螢幕氣場背景特效與光影渲染。
* **🤖 專屬念能力生成 (Procedural Generation):** 根據每位玩家的專屬 ID，利用雜湊演算法（Hash）與 `DiceBear API`，自動隨機生成獨一無二的「機甲頭像」、「念能力系別」與「專屬稱號」。
* **🔍 即時戰術雷達 (Real-time Search & Filter):** 支援按階級篩選，以及關鍵字（執照號碼、姓名、常駐地）即時搜尋。

## 🛠️ 技術棧 (Tech Stack)

* **前端:** 100% 純 HTML5, CSS3 (Glassmorphism, CSS Animations, CSS Variables), Vanilla JavaScript.
* **資料解析:** `SheetJS (xlsx.js)` 用於解析從 Google 取回的 CSV 字串。
* **頭像 API:** [DiceBear Bottts API](https://www.dicebear.com/styles/bottts) (機甲風格頭像)。
* **字體:** Google Fonts (`Noto Sans TC` 思源黑體, `Orbitron` 科技字體)。

## 📊 資料庫設定指南 (Database Setup)

系統依賴 Google 試算表運作，請確保你的表單欄位符合以下順序（系統預設忽略第一列標題列）：

| A欄 (ID) | B欄 (Name) | C欄 (Team) | D欄 (Tier) | E欄 (Score) | F欄以後 (History/Mission Log) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 獵人執照號碼 | 姓名/暱稱 | 常駐地 (如: 週一中壢) | 階級 (包含白金, 黃金等字眼) | 總積分 (純數字) | 參與過的賽事名稱或成績 |
| 1001 | 阿定 | 星期一中壢 | 白金級 | 450 | 死滅回游 冠軍, 春季盃 四強 |
| 1002 | 小安 | 星期四建國 | 白銀級 | 120 | 歲末神仙盃 八強 |

### ⚠️ 重要：如何發佈 Google 試算表
為了讓網頁能順利讀取資料，**必須將 Google 試算表發佈為 CSV 格式**：
1. 打開你的 Google 試算表。
2. 點擊左上角 `檔案 (File)` > `共用 (Share)` > `發佈到網路 (Publish to web)`。
3. 連結類型選擇 `整份文件` 或 `特定工作表`。
4. **【關鍵步驟】** 格式下拉選單請務必選擇 **`逗號分隔值 (.csv)`** (絕對不能選網頁/HTML)。
5. 點擊「發佈」，並將獲得的連結替換到 HTML 檔案中 `<script>` 區塊的 `CSV_URL` 變數中。

## 🎨 系統進階設定 (Customization)

如果你想調整系統的氛圍或設定，可以修改 `<script>` 中的這兩個陣列：

* **戰鬥系別 (`types`):** 目前為強化系、具現化系、變化系、操作系。可以自由新增其他屬性。
* **隨機稱號 (`titles` & `titles2`):** 前綴詞與後綴詞。你可以加入更多羽球社群的內梗，例如「殺球的」、「掛網的」、「幻獸獵人」、「十二支」等，系統會自動幫玩家組合出超中二的稱號！

## 📱 裝置支援 (Responsiveness)

* 已針對行動裝置 (Mobile) 進行優化，隱藏不必要的捲軸並優化卡片點擊觸控範圍。
* 電腦版 (Desktop) 支援游標懸停的 3D 視角卡片傾斜物理特效。

---
*System Log: NEN RADAR ONLINE. ALL HUNTERS STANDBY.*
