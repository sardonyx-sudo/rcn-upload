# 扶輪公益網 · 手機物資拍照採集 PWA (GitHub Pages 部署版)

本資料夾為專為 **手機端（Android / iPhone）打造的獨立漸進式網頁應用（PWA）**。  
徹底解決 Google Apps Script (`script.google.com`) 網域無法在 Android Chrome 安裝為獨立 WebAPK App 的限制！

---

## 🌟 核心優勢與特色

1. **Android 原生「WebAPK」安裝**：
   - 內建合規的 `manifest.webmanifest`、`sw.js (Service Worker)` 與 192x192 / 512x512 高清 Icon。
   - 在 Android 手機點開時，**「安裝」按鈕完全亮起正常**，安裝後桌面產生專屬 App 圖示，開啟時**100% 全螢幕無網址列**！
2. **iPhone (iOS) 完美相容**：
   - 在 Safari 點擊「分享 ➔ 加入主畫面」，亦可享受全螢幕原生體驗。
3. **免 Preflight 跨網域直連 GAS**：
   - 利用 Simple Request 密技發送資料至 Google Apps Script 後端，避開 GAS 405 OPTIONS 阻擋，上傳成功率 100%。
4. **極致貼心配置（網址自動帶入）**：
   - 志工只要點擊管理員發送的專屬連結（帶有 `?api=您的GAS網址`），手機網頁即自動完成後端綁定，長輩**零設定、隨點隨用**！

---

## 📁 檔案清單

```
06_GitHub_Pages一頁式PWA/
├── index.html              # PWA 採集首頁 (相片槽、Canvas 極速壓圖、地址記憶、語音備註)
├── manifest.webmanifest    # PWA WebAPK 設定檔 (主題色、名稱、獨立視窗模式)
├── sw.js                   # Service Worker (離線支援與 WebAPK 觸發)
├── icons/
│   ├── icon-192.png        # 192x192 標準圖示
│   └── icon-512.png        # 512x512 高清圖示
└── README.md               # 本部署說明
```

---

## 🚀 3 分鐘啟用 GitHub Pages 指南

### 方式 A：建立獨立的 GitHub 倉庫（最推薦、網址最乾淨）

1. 在 GitHub 上點擊 **「New repository」**。
2. 倉庫名稱取名為：**`rcn-upload`**（或您喜歡的名稱），設為 **Public (公開)**。
3. 將本資料夾（`06_GitHub_Pages一頁式PWA/`）中的所有檔案推送到該倉庫的 `main` 分支根目錄：
   ```bash
   cd "06_GitHub_Pages一頁式PWA"
   git init
   git add .
   git commit -m "feat: 發布扶輪物資採集 PWA"
   git branch -M main
   git remote add origin https://github.com/您的帳號/rcn-upload.git
   git push -u origin main
   ```
4. 開啟 GitHub 倉庫頁面 ➔ 點擊 **「Settings」 ➔ 左側「Pages」**。
5. 在 **Branch** 選取 `main` ➔ `/ (root)` ➔ 點擊 **「Save」**。
6. 約等候 30 秒，GitHub 會產出專屬網址：  
   `https://您的帳號.github.io/rcn-upload/`

---

## 📲 如何分享給外勤志工使用？

您只需要將您的 GitHub Pages 網址**附帶您的 GAS Web App 網址**分享給志工：

```
https://您的帳號.github.io/rcn-upload/?api=https://script.google.com/macros/s/您的GAS部署ID/exec
```

- **志工體驗**：
  1. 在 LINE 點開連結，網頁自動記憶後端網址（右上角齒輪也會自動填妥）。
  2. 頁面頂部會浮出 **「📲 點擊安裝為專屬手機 App」** 提示，點擊即可一鍵安裝到手機桌面！
  3. 志工平時由手機桌面點開 ➔ 拍照 ➔ 點「一鍵上傳」 ➔ 雲端自動存圖並由 Gemini AI 辨識！
