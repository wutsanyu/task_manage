## 注意事項

- 遇到問題時，能夠適時以口頭或線上工具向助教求救

### 開發需求

本次練習的主要目的，是要開發一套「任務管理系統」。這個系統需要做到的事情有：

- 任務功能
	- 可新增的任務
	- 可設定任務的開始及結束時間
	- 可設定任務的優先順序（高、中、低）
	- 可設定任務目前的狀態（待處理、進行中、已完成）

### 瀏覽器支援

- 預設需要支援 Chrome 的最新版本

### 開發工具

請以下列程式語言、網站開發框架及資料庫系統的最新穩定版本進行開發：

- Ruby
- Ruby on Rails
- PostgreSQL

※ 本練習中對效能、資安沒有特別的要求，但仍需要有一定的品質。網站效能太差的話，會被要求改善。

## 參考資料

- Git: [https://gitbook.tw/](https://gitbook.tw/)
- Rails: [https://railsbook.tw/](https://railsbook.tw/)

## 必修課題

### 步驟1: 建立 Rails 的開發環境

#### 1-1: 安裝 Ruby

- 利用 [rbenv](https://github.com/rbenv/rbenv) 或 [RVM](https://rvm.io) 安裝最新版本的 Ruby
- 以 `ruby -v` 指令來確認 Ruby 的版本，至少需要 2.5 以上版本

#### 1-2: 安裝 Rails

- 以 gem 指令安裝 Rails
- 安裝最新版本的 Rails
- 以 `rails -v` 指令來確認 Rails 的版本，至少需要 5.2.3 以上版本

#### 1-3: 安裝資料庫（PostgreSQL）

- 在你使用的 OS 下安裝 PostgreSQL
	- macOS 的話，請以 `brew` 等工具安裝

### 步驟2: 建立 Rails 專案

- 以 `rails new` 指令，建立 Rails 應用程式最低限度的樣板和檔案
- 在 `rails new` 產生的專案目錄下，建立 `docs` 資料夾，並將本教程文件 commit 進去
	- 目的是為了方便之後開發時可以參考
- 將使用的 Ruby 版號寫進 `Gemfile`（也請確認 Rails 版號是否有標明）

### 步驟3: 想像網站成品會是什麼樣子

- 開始進行設計之前，先對最終成品的預想。建議在紙上畫 prototype
- 請參照網站需求，開始想需要怎樣的資料結構
	- 需要哪些 model (或資料表)？
	- 資料表會需要哪些欄位？
- 有想法之後，將 model 的關係圖手繪出來
	- 完成後將關係圖拍照存檔，放進 repo 裡
	- 把資料表的欄位記錄在 `README.md`（model 名稱、欄位名稱、資料形態）

※ 在這個階段，model 關係圖不需要是完全正確的。以現在所能預想的範圍來規劃就好（做到後面的步驟，發現需要修改時再來調整的概念）

### 步驟4: 資料庫連接等週邊設定

- 建立新的 topic 分支
	- 之後都在 topic 分支上開發並進行 commit
- 安裝 bundler
- 在 `Gemfile` 安裝 `pg`（PostgreSQL 的 adapter）
- 設定 `database.yml`
- 以 `rails db:create` 建立資料庫
- 以 `rails db` 確認有正確連接資料庫

### 步驟5: 建立任務 model

開始來做管理任務所需要的 CRUD。一開始先簡單做，只要能記錄任務的抬頭和任務內容即可。

- 以 `rails generate` 指令建立所需的 model 類別
- 撰寫 migration 並以此建立資料表
	- 非常重要：migration 要確定能安全回到上一步的狀態！請養成以 `redo` 確認的習慣
- 以 `rails c` 指令，透過 model 確認有正確連接資料庫
	- 順便試著在 console 裡建立資料

### 步驟6: 資料驗證

- 開始設定資料驗證
	- 請思考需要在哪個欄位上加入哪種驗證比較好

### 步驟7: 新增任務

- 製作任務的新增、列表以及檢視頁面
	- 以 `rails generate` 指令產生 controller
		- 除了 Rails 預設的 erb 樣版引擎之外，請詢問助教其它 template engine（ERB / Slim / Haml..etc）有什麼好處，並從上述挑選其中一款來使用
	- 實做 controller 和 view 必要的部分
	- 完成新增以及之後需要在畫面上顯示的 Flash 訊息
- 修改 `routes.rb`，讓 `http://localhost:3000/` 會顯示任務的列表頁面

### 步驟8: 加入設計

- 使用 Bootstrap 4，為目前的作品套入設計
- 【選項】自己寫 CSS 來設計
- 自由發揮

### 步驟9: 設定 Rails 的時區

- 將 Rails 的時區設為台灣（台北）


