# Manus Lite（PWA 版）

## 檔案結構（請整個資料夾內容一起放到 GitHub 儲存庫根目錄）
```
index.html              主程式
manifest.webmanifest    App 資訊（名稱、圖示、主題色、捷徑）
sw.js                   Service Worker（離線開啟介面、更新提示）
icons/                  圖示（192、512、maskable、Apple、favicon）
```

## 部署到 GitHub Pages
1. 建立儲存庫，把上面所有檔案（含 `icons/` 資料夾）上傳到根目錄。
2. Settings → Pages → Source 選 `Deploy from a branch`，Branch 選 `main` / `(root)`。
3. 開啟 `https://<帳號>.github.io/<儲存庫名>/`，用瀏覽器安裝：
   - 電腦 Chrome / Edge：網址列右側的安裝圖示，或頁面內「LLM 設定」最下方的「安裝 Manus Lite」按鈕
   - Android Chrome：選單 →「安裝應用程式」
   - iPhone / iPad Safari：分享 →「加入主畫面」
   - macOS Safari 17+：檔案 →「加入 Dock」

> 必須是 HTTPS（GitHub Pages 預設就是）或 localhost；直接雙擊 `file://` 開啟無法安裝。
> 本機測試：在資料夾內執行 `python3 -m http.server 8000`，開啟 http://localhost:8000

## 更新版本
改了 `index.html` 之後，把 `sw.js` 第一行附近的 `VERSION = 'manus-lite-v1'` 改成 `v2`、`v3`……
使用者下次開啟時會看到「有新版本可用」，按「立即更新」即可。

## 注意
- 離線時介面可以開啟，但 LLM 對話需要網路（只有「瀏覽器本機 LLM」模式可離線）。
- 對話紀錄與設定存在各自裝置的瀏覽器儲存空間，網頁版與已安裝的 App 之間**不會互通**。
- 請勿把 API Key 寫進程式碼再上傳 GitHub；Key 只在使用者自己的設定頁輸入。
