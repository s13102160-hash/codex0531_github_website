# 建立基礎 GitHub Pages 網站

## 1. 建立網站檔案

最小的靜態網站可以只包含：

- `index.html`
- `styles.css`

`index.html` 是 GitHub Pages 預設會尋找的首頁檔案。`styles.css` 負責控制畫面樣式。

## 2. 建立學習紀錄結構

本專案採用以下紀錄結構：

```text
docs/github-basic-website/
  00-index.md
  01-setup.md
  99-troubleshooting.md
logs/
  2026-05-31-github-basic-website.md
assets/screenshots/github-basic-website/
```

目前尚未加入截圖。如果之後操作 GitHub 網頁介面時有截圖，可以放在：

```text
assets/screenshots/github-basic-website/
```

再把圖片用相對路徑插入到每日紀錄中。

## 3. 發布到 GitHub Pages 的概念

GitHub Pages 是 GitHub 提供的靜態網站發布服務。依官方文件，GitHub Pages 可以從 repository 中的 HTML、CSS、JavaScript 檔案發布網站。

對這個初學專案，最簡單的發布來源是：

- Branch：`main`
- Folder：`/(root)`

也就是把 `index.html` 放在 repository 根目錄，GitHub Pages 就能把它當作首頁。

## 4. 下一步操作

完成本機檔案後，下一步會是：

1. 在 GitHub 建立 repository。
2. 把本機 Git 專案連到 GitHub remote。
3. 推送 `main` branch。
4. 到 GitHub repository 的 `Settings` -> `Pages` 設定發布來源。
5. 等待 GitHub Pages 顯示網站網址。
