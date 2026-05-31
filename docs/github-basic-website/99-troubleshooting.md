# 問題排查紀錄

## 2026-05-31：資料夾還不是 Git 專案

問題：
執行 Git 狀態檢查時，系統顯示目前資料夾不是 Git repository。

觀察到的訊息：

```text
fatal: not a git repository (or any of the parent directories): .git
```

原因：
這個學習資料夾尚未執行過 Git 初始化，因此還沒有 `.git` 版本控制資料。

解法：

1. 建立網站與學習紀錄檔案。
2. 執行 Git 初始化。
3. 確認 Git 可以看到新增的檔案。

狀態：
已完成。執行 Git 初始化後，資料夾已成為 Git repository，並使用 `main` 作為初始分支。

## 2026-05-31：Git 尚未設定提交身分

問題：
準備建立第一個 commit 前，檢查到目前專案與全域 Git 都沒有設定 `user.name` 和 `user.email`。

觀察到的狀態：

```text
git config user.name
git config user.email
git config --global user.name
git config --global user.email
```

以上檢查都沒有回傳姓名或 email。

原因：
Git 需要提交者姓名與 email 才能建立 commit。

解法：
在本專案設定本機 Git 身分，例如：

```text
git config user.name "你的名稱"
git config user.email "你的 email"
```

狀態：
已完成。本專案已設定 `user.name` 和 `user.email`。

補充：
第一次同時設定姓名與 email 時，姓名設定遇到暫時鎖定：

```text
error: could not lock config file .git/config: File exists
```

檢查後 `.git/config.lock` 已不存在，代表鎖定已釋放。重新設定 `user.name` 後成功。

## 2026-05-31：電腦上沒有 GitHub CLI

問題：
準備檢查是否能直接用指令建立 GitHub repository 時，系統顯示找不到 `gh`。

觀察到的訊息：

```text
gh : 無法辨識 'gh' 詞彙是否為 Cmdlet、函數、指令檔或可執行程式的名稱。
```

原因：
目前電腦沒有安裝 GitHub CLI，或它不在系統 PATH 中。

解法：
可以改用 GitHub 網頁介面建立 repository，之後再把 repository URL 設定成 Git remote。

狀態：
改採 GitHub 網頁建立 repository 的流程。

## 2026-05-31：Windows 換行提示

問題：
把檔案加入 Git 暫存區時，Git 顯示 LF 之後可能會被轉成 CRLF。

觀察到的訊息：

```text
warning: in the working copy of 'README.md', LF will be replaced by CRLF the next time Git touches it
```

原因：
Windows 版 Git 常會依照換行設定處理文字檔。這是換行格式提示，不是提交失敗。

解法：
本次先接受預設行為，繼續完成 commit。若之後專案需要固定換行規則，可以新增 `.gitattributes`。

狀態：
已了解，未阻止 commit。

## 2026-05-31：推送時遇到 Git dubious ownership

問題：
推送到 GitHub 時，Git 偵測到 repository 擁有者與目前執行推送的 Windows 使用者不同，因此阻擋操作。

觀察到的訊息：

```text
fatal: detected dubious ownership in repository at 'D:/你哥/codex0531_github_website'
```

原因：
這個 repository 是在 Codex 沙盒使用者下初始化的，但推送時使用的是 Windows 使用者 `Hong`。Git 會用這個保護機制避免操作不信任的資料夾。

解法：
把目前專案資料夾加入 Git 的全域 safe.directory 清單：

```text
git config --global --add safe.directory 'D:/你哥/codex0531_github_website'
```

狀態：
等待授權後執行。
