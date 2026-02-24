# 📈 Stock Diary

個人股票交易紀錄與視覺化儀表板

## 功能
- 買賣交易紀錄（日期、股票名稱、代號、買/賣、股數、成本、手續費）
- 持倉分佈圓餅圖
- 各股已實現損益長條圖
- 累積投入成本折線圖
- 手機友善輸入介面

## 快速設定（5分鐘完成）

### 1. Fork 或建立此 Repo

### 2. 啟用 GitHub Pages
進入 repo → **Settings** → **Pages**
- Source 選 **GitHub Actions**

### 3. 產生 GitHub Token
前往：https://github.com/settings/tokens?type=beta
- Repository access：選 `stock-diary`
- Permissions → Contents：**Read and write**
- 複製產生的 token（`ghp_xxx...`）

### 4. 開始使用
- 儀表板：`https://johnnyfan0875.github.io/stock-diary/`
- 輸入頁：`https://johnnyfan0875.github.io/stock-diary/input.html`

在 `input.html` 填入 Token 後就可以開始記錄交易。Token 只存在你的瀏覽器 localStorage，不會上傳。

## 更新機制

```
input.html 輸入交易
    ↓
GitHub Contents API 更新 data.json
    ↓ （即時）
圖表頁直接讀取 raw.githubusercontent.com（幾秒內反映）
    ↓ （同時觸發）
GitHub Actions 重新部署（約 1-2 分鐘）
```

## 檔案結構
```
stock-diary/
├── index.html          # 儀表板（圖表）
├── input.html          # 交易輸入介面
├── data.json           # 交易資料
└── .github/
    └── workflows/
        └── deploy.yml  # 自動部署
```
