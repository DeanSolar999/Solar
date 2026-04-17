# 曜日天梯榜 - MAGI SYSTEM (Solar Cup League) 🌐

![Version](https://img.shields.io/badge/Version-2.0-blue)
![Status](https://img.shields.io/badge/Status-TACTICAL__OPS__READY-success)
![Tech Stack](https://img.shields.io/badge/Tech-HTML5%20|%20CSS3%20|%20Vanilla%20JS-orange)

「曜日天梯榜」是一個基於純前端技術打造的賽博龐克 / EVA 風格動態排行榜系統。系統可即時讀取 Google Sheets 資料，並透過專屬的「雙軌視覺系統」與「3D 戰術卡片」，將冰冷的試算表數據轉化為極具視覺張力的遊戲化天梯榜。

---

## ✨ 核心特色 (Core Features)

* **📡 雲端數據同步 (Live Data Sync)**：不需後端伺服器，直接解析已發布的 Google Sheets CSV 檔案，數據更新即時呈現。
* **🛡️ 雙軌視覺系統 (Dual-Track Hierarchy)**：完美分離選手的「所屬量級 (Tier)」與「實力排名 (Rank)」，提供多層次的視覺回饋（詳見下方說明）。
* **🎴 3D 戰術全息卡片 (3D Holographic Cards)**：點擊選手展開詳細數據卡片，支援滑鼠懸停 (Hover) 的 3D 傾斜透視效果。
* **📊 動態能力雷達圖 (Procedural Radar Chart)**：根據選手積分，透過演算法動態生成六芒星能力雷達圖（ATK, DEF, SPD, TEC 等）。
* **🤖 專屬機甲頭像 (Procedural Avatars)**：整合 Dicebear API，將選手 ID 進行 Hash 運算，自動為每位駕駛員生成獨一無二的像素機甲頭像。

---

## 🎖️ 階級與視覺系統 (The Hierarchy System)

為了提供極致的榮譽感與辨識度，本系統採用 **「雙軌視覺 (Tier vs. Rank)」** 設計：

### 1. 分組量級 (Tier) - 決定卡片「邊框顏色」
代表選手的報名量級與出身，顏色絕對固定，提供最直覺的清單分類。
* **PLATINUM (白金級)**：科技藍 (`#00bfff`)
* **GOLD (黃金級)**：榮耀金 (`#ffd700`)
* **SILVER (白銀級)**：戰術紅 (`#ff0f4f`)
* **BRONZE (青銅級)**：校準綠 (`#39ff14`)

### 2. 實力排名 (Rank) - 決定「背景環境、材質與浮水印」
代表選手在全體中的絕對實力，賦予不同等級的豪華視覺特效。

| Rank 區間 | 稱號 (Title) | 背景環境 (Environment) | 專屬浮水印 (Watermark) | 視覺特效描述 |
| :--- | :--- | :--- | :--- | :--- |
| **1 - 3** | **SSR // LEGEND** | 黃金都心 | 👑 皇冠 | 滿版金色聚光燈，卡片表面附帶彩虹雷射流光動畫。 |
| **4 - 10** | **SR // ELITE** | 核心機房 | 💠 鑽石 | 深藍色數據流背景，卡片附帶科技掃描線網格。 |
| **11 - 30** | **S-RANK // ACE** | 紫電通道 | ★ 五角星 | 放射狀速度線背景，卡片表面帶有紫色蜂巢力場。 |
| **31 - 60** | **A-RANK // MAIN** | 戰術雷達 | ❮ 軍階 V | 綠色雷達波擴散背景。 |
| **61 - 100**| **B-RANK // SUP** | 工業區 | ● 圓形 | 橘色工業警示斜紋背景。 |
| **100+** | **C-RANK // UNIT** | 靜默虛空 | 無 | 乾淨深黑背景，量產機標準配置。 |

---

## 🚀 安裝與執行 (Installation & Setup)

這是一個純前端 (Client-side) 的應用程式，**完全不需要安裝任何 Node.js 模組或建置工具 (No Build Process)**。

1. **取得原始碼**：將 `index.html` 下載到您的電腦中。
2. **直接執行**：使用任何現代瀏覽器 (Chrome, Edge, Safari, Firefox) 雙擊打開 `index.html` 即可運行。
3. **部署上線**：您可以直接將此檔案部署到任何靜態網頁代管服務（如 GitHub Pages, Vercel, Netlify, 或 AWS S3）。

### 📝 如何替換資料來源 (Data Source)

目前的數據來自一份公開的 Google Sheets CSV。如果要換成您的數據：
1. 準備一份 Google Sheets 試算表，欄位順序建議為：`ID` | `姓名` | `球團` | `分組` | `積分` | `歷史戰績1` | `歷史戰績2...`
2. 在 Google Sheets 中點選 **檔案 -> 共用 -> 發布到網路**，選擇 **CSV** 格式並複製連結。
3. 打開 `index.html`，找到第 523 行的 `CSV_URL` 變數：
```javascript
// 將此處的 URL 替換為您的 Google Sheets CSV 連結
const CSV_URL = "您的_GOOGLE_SHEET_CSV_連結";
