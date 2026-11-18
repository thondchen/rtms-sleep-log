# rTMS 失眠治療日誌

一個專為接受 rTMS（重複經顱磁刺激）治療慢性失眠患者設計的靜態網頁應用程式。所有資料儲存在瀏覽器的 localStorage 中，無需後端伺服器，適合在手機上使用。

## 特色功能

- 📱 **行動優先設計**：針對 iPhone Safari 和 Android Chrome 優化，支援 LINE 內建瀏覽器
- 🇹🇼 **繁體中文介面**：清晰易讀的大字體，溫暖舒適的配色
- 💾 **本地儲存**：所有資料僅儲存在您的裝置上，完全私密
- 📊 **詳細記錄**：追蹤療程進度、睡眠品質、精神狀態、副作用等
- 📈 **視覺化報告**：自動生成圖表和統計數據，方便與醫師討論
- 💾 **備份還原**：可匯出 JSON 或 CSV 格式，方便備份或換機

## 功能說明

### 1. 設定
- 治療開始日期
- 預計療程次數（預設 20 次）
- 暱稱（選填）

### 2. 每日記錄
- 日期
- 是否進行 rTMS 療程及次數
- 睡眠時間（自動計算總時數）
- 入睡時間（分鐘）
- 夜間醒來次數
- 早晨精神狀態（1-10 分）
- 日間嗜睡程度（1-10 分）
- 午睡記錄
- 副作用（頭痛、頭皮不適、頭暈、其他）
- 備註

### 3. 歷史記錄
- 查看所有記錄
- 編輯或刪除記錄

### 4. 醫生報告
- 選擇日期範圍產生報告
- 平均數據統計
- 前後期比較（至少 14 天記錄）
- 睡眠時數、精神狀態、嗜睡程度趨勢圖
- 副作用統計
- 詳細記錄表
- 列印/儲存為 PDF
- 匯出 CSV

### 5. 備份
- 匯出所有資料為 JSON
- 從 JSON 匯入還原
- 清除所有資料

## 治療觀察重點

應用程式會根據療程進度自動提供建議：

- **第 1-5 次**：初期觀察階段，效果尚不明顯是正常的
- **第 10 次左右**：開始評估日間精神和睡眠品質的改善
- **第 20 次**：完整評估療效，與醫師討論後續規劃

## 部署到 GitHub Pages

### 方法一：透過 GitHub 網頁介面

1. 在 GitHub 建立新的 repository
2. 上傳 `index.html` 檔案到 repository 根目錄
3. 前往 repository 的 Settings → Pages
4. 在 "Source" 下選擇 "Deploy from a branch"
5. 選擇 `main` 分支和 `/ (root)` 目錄
6. 點選 "Save"
7. 幾分鐘後，您的網站就會在 `https://[username].github.io/[repository-name]/` 上線

### 方法二：透過 Git 指令

```bash
# 建立新的 repository 或 clone 現有的
git clone https://github.com/[username]/[repository-name].git
cd [repository-name]

# 將 index.html 複製到 repository
cp path/to/index.html .

# 提交並推送
git add index.html
git commit -m "Add rTMS treatment logging app"
git push origin main

# 前往 GitHub repository Settings → Pages 啟用 GitHub Pages
```

### 方法三：使用其他靜態網站託管服務

此應用程式是純靜態網頁，可以部署到任何支援靜態網站的平台：

- **Netlify**：拖曳 `index.html` 到 Netlify Drop
- **Vercel**：透過 GitHub 連結或 CLI 部署
- **Cloudflare Pages**：連結 GitHub repository
- **Firebase Hosting**：使用 Firebase CLI 部署

## 本地測試

如果您想在本地測試：

```bash
# 使用 Python 3 內建的 HTTP 伺服器
python3 -m http.server 8000

# 使用 Node.js 的 http-server (需先安裝: npm install -g http-server)
http-server -p 8000

# 或者直接用瀏覽器開啟
open index.html  # macOS
start index.html # Windows
xdg-open index.html # Linux
```

然後在瀏覽器開啟 `http://localhost:8000`

## 技術說明

- **純靜態**：僅 HTML、CSS、JavaScript，無需建置步驟
- **完全自給自足**：無任何外部相依或 CDN，使用內建 SVG 繪製圖表
- **localStorage**：資料儲存在瀏覽器的 localStorage，容量約 5-10MB
- **完整離線能力**：可在無網路環境下完全運作，適合 LINE 內建瀏覽器
- **響應式設計**：支援手機（最小 375px）到桌面各種螢幕
- **單一檔案**：整個應用程式僅一個 HTML 檔案，易於部署和分享

## 重要提醒

⚠️ **資料安全**
- 所有資料僅儲存在您的瀏覽器中
- 清除瀏覽器資料會刪除所有記錄
- 建議定期使用「備份」功能匯出資料
- 換手機或瀏覽器前請先匯出備份

⚠️ **醫療免責聲明**
- 此應用程式僅供個人記錄使用
- 不構成醫療建議
- 任何治療決策請諮詢您的醫師

## 授權

此專案採用 MIT 授權條款。您可以自由使用、修改和分發。

## 支援

如有問題或建議，歡迎提出 Issue 或 Pull Request。
