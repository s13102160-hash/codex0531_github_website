# 2026-05-31 GitHub 基礎網站學習紀錄

## 學習主題

透過 Codex 建立第一個最基礎的 GitHub Pages 靜態網站，並使用學習過程紀錄 Skill 保存操作過程。

## 學習目標

- 建立可以直接發布的 `index.html`
- 加入簡單但可讀的 `styles.css`
- 建立學習索引、設定筆記、問題排查紀錄
- 將資料夾初始化為 Git 專案
- 準備後續推送到 GitHub 並開啟 GitHub Pages

## 當前環境

- 日期：2026-05-31
- 工作資料夾：`D:\你哥\codex0531_github_website`
- 專案初始狀態：資料夾為空
- Git 初始狀態：尚未初始化

## 操作紀錄

### 1. 確認專案狀態

Codex 指引：
先檢查資料夾內容與 Git 狀態，避免覆蓋既有檔案或使用錯誤的專案結構。

使用者操作：
提出要透過 Codex 學習如何在 GitHub 上架設最基礎網站，並使用學習過程紀錄 Skill。

觀察結果：
資料夾目前沒有檔案。Git 狀態檢查顯示這裡還不是 Git repository。

問題：
尚未建立 `.git` 版本控制資料。

原因：
這是一個新的學習資料夾。

解法：
先建立網站與學習紀錄檔案，再初始化 Git。

狀態：
已確認。

### 2. 建立最小靜態網站

Codex 指引：
第一次練習 GitHub Pages 時，不需要 React、Vite、Next.js 或任何建置工具。先用純 HTML/CSS，可以把 GitHub Pages 的核心流程學清楚。

使用者操作：
由 Codex 在專案根目錄建立網站檔案。

觀察結果：
新增：

- `index.html`
- `styles.css`
- `README.md`

問題：
無。

原因：
不適用。

解法：
不適用。

狀態：
已建立，待驗證。

### 4. 初始化 Git repository

Codex 指引：
建立 Git repository 後，才能把檔案加入版本控制，後續也才能連到 GitHub remote 並推送。

使用者操作：
由 Codex 在目前資料夾初始化 Git repository，並設定初始分支為 `main`。

觀察結果：
Git 顯示已在目前資料夾建立新的 repository。

問題：
無。

原因：
不適用。

解法：
不適用。

狀態：
已完成，待檢查 Git 是否偵測到新增檔案。

### 5. 驗證檔案與 Git 狀態

Codex 指引：
建立檔案後要確認兩件事：網站首頁有連到樣式檔，Git 也有偵測到新增檔案。

使用者操作：
由 Codex 檢查 `index.html` 是否引用 `styles.css`，並檢查 Git 狀態。

觀察結果：

- `index.html` 包含 `styles.css` 連結。
- `styles.css` 檔案存在。
- Git 目前在 `main` 分支，尚未有 commit。
- Git 偵測到新增的 `README.md`、`assets/`、`docs/`、`index.html`、`logs/`、`styles.css`。

問題：
尚未建立第一個 commit，也尚未連到 GitHub remote。

原因：
這一輪先完成本機網站與學習紀錄，尚未進行 GitHub 帳號與遠端 repository 操作。

解法：
下一步可以建立第一個 commit，接著在 GitHub 建立 repository 並推送。

狀態：
本機檔案驗證完成。

### 6. 檢查 commit 前置條件

Codex 指引：
建立第一個 commit 前，需要確認 Git 有提交用的姓名與 email。若要由 Codex 直接建立 GitHub repository，也需要確認是否有 GitHub CLI。

使用者操作：
由 Codex 檢查 Git 身分設定與 GitHub CLI 是否可用。

觀察結果：

- 專案層級沒有 `user.name`。
- 專案層級沒有 `user.email`。
- 全域層級沒有 `user.name`。
- 全域層級沒有 `user.email`。
- 系統找不到 `gh` 指令，因此目前不能直接用 GitHub CLI 建立 repository。

問題：
目前還不能建立 commit，因為 Git 提交身分尚未設定。

原因：
Git commit 需要提交者姓名與 email。

解法：
先在本專案設定 Git 提交姓名與 email，再建立第一個 commit。GitHub repository 則改由 GitHub 網頁建立，之後再設定 remote。

狀態：
已收到使用者提供的姓名與 email，並完成本專案 Git 身分設定。

### 7. 設定本專案 Git 提交身分

Codex 指引：
為了避免影響其他專案，這次只設定目前專案的 Git 身分，不修改全域設定。

使用者操作：
提供 commit 用姓名與 email。

觀察結果：

- `user.name` 設為 `s13102160-hash`
- `user.email` 設為 `s13102160@stu.edu.tw`

問題：
第一次設定姓名時出現暫時鎖定：

```text
error: could not lock config file .git/config: File exists
```

原因：
姓名與 email 同時寫入 Git 設定時，Git 設定檔短暫被鎖定。

解法：
確認 `.git/config.lock` 不存在後，重新設定 `user.name`。

狀態：
已完成。

### 9. 設定 GitHub remote 並嘗試推送

Codex 指引：
GitHub repository 建立完成後，需要把遠端 URL 設為 `origin`，再推送 `main` 分支。

使用者操作：
提供 GitHub repository URL：

```text
https://github.com/s13102160-hash/codex0531_github_website.git
```

觀察結果：

- 已設定 `origin` remote。
- 第一次推送時，執行環境無法連線到 GitHub。
- 改用授權連線後，Git 顯示 `dubious ownership` 安全阻擋。

問題：
目前 repository 的擁有者與推送使用者不同，Git 要求把資料夾加入 safe directory。

原因：
repository 是在 Codex 沙盒中初始化，但推送時使用 Windows 使用者 `Hong`。

解法：
將目前專案資料夾加入 Git 全域 safe.directory 清單後，再重新推送。

狀態：
等待安全目錄設定後重試推送。

### 8. 建立第一個 commit

Codex 指引：
完成網站與學習紀錄後，先建立第一個本機版本。這樣後續推送到 GitHub 時，就有一個清楚的初始狀態。

使用者操作：
由 Codex 將網站檔案與學習紀錄加入 Git 暫存區，並建立 commit。

觀察結果：

- commit 訊息：`Initial GitHub Pages website`
- commit 編號開頭：`7690c90`
- Git 記錄 8 個檔案被建立。

問題：
加入暫存區時，Git 顯示 Windows 換行提示。

原因：
Windows 版 Git 可能會把 LF 換行轉成 CRLF。這是提示，不是錯誤。

解法：
本次接受預設行為，繼續完成 commit。若之後需要固定換行規則，再建立 `.gitattributes`。

狀態：
已完成。

### 3. 建立學習紀錄

Codex 指引：
依照 learning-process-log Skill，將穩定筆記放在 `docs/<topic>/`，每日操作紀錄放在 `logs/`。

使用者操作：
由 Codex 建立筆記結構。

觀察結果：
新增：

- `docs/github-basic-website/00-index.md`
- `docs/github-basic-website/01-setup.md`
- `docs/github-basic-website/99-troubleshooting.md`
- `logs/2026-05-31-github-basic-website.md`

問題：
目前沒有截圖檔案可整理。

原因：
這一輪尚未在 GitHub 網頁介面操作或提供截圖。

解法：
之後若有截圖，放入 `assets/screenshots/github-basic-website/`，再補進紀錄。

狀態：
已建立，待驗證。

## 本次重要觀念

GitHub Pages 適合發布靜態網站。官方文件說明，它可以從 GitHub repository 中的 HTML、CSS、JavaScript 檔案發布網站。

本專案採用最簡單的發布方式：

- 首頁檔案：`index.html`
- 發布 branch：`main`
- 發布資料夾：`/(root)`

## 待辦事項

- 初始化 Git repository：已完成
- 檢查檔案是否都被 Git 偵測到：已完成
- 設定 Git 提交身分：已完成
- 建立第一個 commit：已完成
- 在 GitHub 建立遠端 repository
- 設定 remote：已完成
- 推送到 GitHub
- 到 `Settings` -> `Pages` 開啟 GitHub Pages
- 記錄 GitHub Pages 網址與操作截圖
