# Git & GitHub 入門

## 下一堂

- 遠端伺服器管理與操作
- 常見指令教學 (還原、查看歷史紀錄)

## 為什麼要學 Git ？

- Git 是程式碼版本控制軟體
- 用網頁版型介紹用了 Git 的差異

## 軟體與服務安裝

- [Git 軟體安裝](https://git-scm.com/) - 首頁 Download
- [Github 會員註冊](https://github.com/)
- [SourceTree 軟體安裝](https://www.sourcetreeapp.com/)

## 終端機

- Win：**Git Bash**

- - 開始 > 搜尋輸入 > Git Bash

- Mac：**終端機**

- - 輸入「control + 空白」，關鍵字輸入「終端機」

## 終端機指令學習

- 練習：前往到某資料夾，觀看內容

- 練習：嘗試用指令開一個新資料夾或檔案

  ![image-20211116005704534](https://tva1.sinaimg.cn/large/008i3skNgy1gwgbpdmxenj30vg0cyjss.jpg)

## 嘗試 Git 是否有安裝成功

- 在終端機裡面輸入：git --version

  ![](https://jljk.quip.com/-/blob/PLCAAAVcFfM/BdX0ZS7AOpVmQn8ht14DXg?s=pFUnA7u75HbL)

  

## 設定個人資料

- 輸入姓名：`git config --global user.name "gon"`
- 輸入個人的 email：`git config --global user.email "gonsakon@gmail.com"`
- 查詢 git 設定內容：`git config --list`





## 基本指令架構

![](https://jljk.quip.com/-/blob/PLCAAAVcFfM/9Da2tqR0MK_uYno9VB6FKQ?s=pFUnA7u75HbL)

## Git 常用指令

- 初始化數據庫： `git init`

- [開啟 .git 隱藏檔方案](https://helpx.adobe.com/tw/x-productkb/global/show-hidden-files-folders-extensions.html)

- - Mac command+shift+.

- 查詢當前狀態：`git status`

- - 要將檔案加入到指定資料夾

- 將檔案加入到索引：`git add .`

- 將索引檔案變成一個更新(commit)：`git commit -m "新增網頁環境"`

- 觀察 commit 歷史紀錄： `git log`

- 下載遠端數據庫： `git clone 數據庫網址`

- 更新遠端數據庫： `git push origin master`

  ![](https://jljk.quip.com/-/blob/PLCAAAVcFfM/_Q_xLJfhOUo0VDumEoUx3A?s=pFUnA7u75HbL)



1.這裡有幾個未被追蹤的檔案
2.有幾個未被加入索引
3.幾個已加入索引的檔案

![](https://jljk.quip.com/-/blob/PLCAAAVcFfM/hmRq1MdKspeAhbfdq4bHvg?s=pFUnA7u75HbL)

1.這裡有幾個未被追蹤的檔案
2.有幾個未被加入索引
3.幾個已加入索引的檔案

![](https://jljk.quip.com/-/blob/PLCAAAVcFfM/SU0fkObL6I9NwOXsz9fTIw?s=pFUnA7u75HbL)

