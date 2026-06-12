# AR Vision Link

## 專案簡介

AR Vision Link 是一套結合 WebAR 人臉辨識、即時多人線上測驗、WebRTC 視訊串流與 AR Overlay 顯示技術的智慧互動學習平台。

本系統以瀏覽器為主要執行環境，使用者無需安裝額外軟體即可完成：

* 使用者註冊
* 人臉登入
* 個人資料管理
* 測驗建立與管理
* 房間建立與加入
* 多人同步作答
* 即時計分與排行榜
* WebRTC 即時視訊串流
* AR Overlay 顯示

系統主要目標為打造一個兼具互動性、即時性與沉浸感的線上測驗平台，使傳統線上測驗結合 AR 技術與人臉辨識功能，提高使用者參與度與學習體驗。

---

# 專案技術架構

## 前端技術

* React
* Vite
* React Router
* MediaPipe FaceMesh
* face-api.js
* Socket.IO Client
* WebRTC
* HTML5
* CSS3
* JavaScript

## 後端技術

* Node.js
* Express.js
* Socket.IO Server

## 資料庫

* Supabase PostgreSQL

## 雲端部署

* GitHub
* Render
* Supabase Cloud

---

# 系統功能

## 帳號與個人資料管理

### T01 使用者註冊

提供新使用者建立個人帳號與基本資料。

### T02 人臉登入

透過攝影機取得臉部特徵向量，與資料庫中的人臉資料進行比對後登入系統。

### T03 個人資料管理

提供修改：

* 姓名
* 暱稱
* 自我介紹

以及重新註冊人臉資料功能。

---

## 測驗內容管理

### T04 建立測驗

主持人可建立測驗與新增題目內容。

功能包含：

* 題目建立
* 選項設定
* 正確答案設定
* 作答時間限制設定

### T05 編輯測驗

主持人可：

* 修改題目
* 新增題目
* 刪除題目
* 刪除測驗

---

## 房間與遊戲管理

### T06 建立房間

主持人選擇測驗後建立房間並取得房號。

### T07 加入房間

玩家透過房號加入指定測驗房間。

### T08 開始遊戲

主持人控制測驗開始與題目切換流程。

---

## 玩家作答與排行榜

### T09 玩家作答

玩家於指定時間內完成作答。

### T10 計算分數

系統自動計算：

* 單題得分
* 總分
* 答對題數

### T11 排行榜

依據總分排序產生排行榜。

---

## WebRTC 與 AR 功能

### T12 WebRTC 視訊串流

主持人可即時觀看玩家鏡頭畫面。

### T13 AR Overlay 顯示

透過 MediaPipe 臉部追蹤技術，在玩家頭頂顯示：

* 暱稱
* 分數
* 其他遊戲資訊

並隨臉部移動同步更新位置。

---

# 系統資料庫

本系統主要使用六個資料表：

## users

儲存使用者資料與臉部特徵向量。

## quizzes

儲存測驗主檔資料。

## questions

儲存測驗題目資料。

## game_sessions

儲存房間與遊戲狀態資料。

## player_answers

儲存玩家每題作答紀錄。

## player_records

儲存玩家總成績與排行榜資料。

---

# 專案目錄結構

```text
AR-Vision-Link/
│
├── Activity Diagram/
│   ├── 
│   └── 活動圖.docx
│
├── Class Diagram/
│   └── 類別圖.docx
│
├── Glossary/
│   └── 詞彙表.docx
│
├── Use Case Diagram/
│   ├── AR顯示.jpg
│   ├── 作答積分與排行榜.jpg
│   ├── 房間的加入與開始.jpg
│   ├── 帳號與個人資料管理.jpg
│   └── 測驗題目管理.jpg
│
├── Use Case Scenarios/
│   └── 使用案例描述.docx
│
└── README.md
```

---

# 文件說明

本專案依照軟體工程分析與設計流程，建立完整系統文件。

以下說明各資料夾內容與用途。

---

## Activity Diagram

活動圖（Activity Diagram）描述系統各功能的執行流程與操作步驟。

包含：

### 使用者註冊活動圖

描述：

* 註冊資料填寫
* 人臉照片上傳
* 註冊成功或失敗流程

### 臉部登入活動圖

描述：

* 開啟攝影機
* 臉部辨識
* 登入成功或失敗流程

### 個人資料管理活動圖

描述：

* 個人資料修改
* 臉部重新註冊
* 登出流程

### 主持遊戲活動圖

描述：

* 建立房間
* 等待玩家
* 開始遊戲
* 切換題目
* 顯示排行榜

### 加入遊戲與作答活動圖

描述：

* 輸入房號
* 加入房間
* 作答流程
* 更新分數

### AR 人臉辨識活動圖

描述：

* 人臉偵測
* 身分辨識
* AR Overlay 顯示

### 排行榜活動圖

描述：

* 排名計算
* 成績顯示

### 系統總活動圖

描述整個系統由登入到遊戲結束的完整流程。

---

## Class Diagram

類別圖（Class Diagram）描述系統的靜態架構。

內容包含：

* 系統主要類別
* 類別屬性
* 類別方法
* 類別間關聯關係

透過類別圖可以了解：

* 系統模組分工
* 資料流向
* 元件依賴關係

作為系統設計的重要依據。

---

## Use Case Diagram

使用案例圖（Use Case Diagram）描述系統角色與功能間的互動關係。

內容包含：

### 帳號與個人資料管理

* 使用者註冊
* 人臉登入
* 個人資料管理

### 測驗內容管理

* 建立測驗
* 編輯測驗

### 房間建立與加入

* 建立房間
* 加入房間
* 開始遊戲

### 玩家作答與排行榜

* 玩家作答
* 計算分數
* 排行榜更新

### WebRTC 與 AR 顯示

* WebRTC 視訊串流
* AR Overlay 顯示

同時包含各功能的例外情況（Exception Flow）。

---

## Use Case Scenarios

使用案例描述（Use Case Scenarios）詳細記錄每個功能的需求與執行流程。

共包含十三個核心使用案例：

| 編號    | 功能            |
| ------ | -------------   |
| UC-T01 | 使用者註冊       |
| UC-T02 | 人臉登入         |
| UC-T03 | 個人資料管理     |
| UC-T04 | 建立測驗         |
| UC-T05 | 編輯測驗         |
| UC-T06 | 建立房間         |
| UC-T07 | 加入房間         |
| UC-T08 | 開始遊戲         |
| UC-T09 | 玩家作答         |
| UC-T10 | 計算分數         |
| UC-T11 | 更新排行榜       |
| UC-T12 | WebRTC 視訊串流  |
| UC-T13 | AR Overlay 顯示 |

每份案例皆包含：

* 前置條件
* 後置條件
* 正常流程
* 例外流程

作為系統需求分析的重要文件。

---

## Glossary

詞彙表（Glossary）統一定義專案中所有重要名詞。

內容包含：

### 系統名詞

* AR Vision Link
* WebAR
* 多人即時測驗

### 使用者角色

* Host（主持人）
* User（玩家）

### 系統功能

* 人臉登入
* 建立測驗
* 建立房間
* 玩家作答
* 排行榜

### 技術名詞

* WebRTC
* MediaPipe
* Face Embedding
* AR Overlay

### 資料表名詞

* users
* quizzes
* questions
* game_sessions
* player_answers
* player_records

提供團隊開發與文件閱讀時的一致性定義。

---

# 執行方式

## Frontend

```bash
cd frontend

npm install

npm run dev
```

---

## Backend

```bash
cd backend

npm install

node server.js
```

---


# 專案成果

本專案成功整合：

* WebAR 人臉辨識
* 人臉登入系統
* React 前端架構
* Supabase 雲端資料庫
* Socket.IO 即時同步
* WebRTC 視訊串流
* 多人即時測驗
* 即時計分與排行榜
* AR Overlay 顯示

建立一套兼具教育互動性與 AR 體驗的智慧測驗平台。

---

# 作者

長庚大學 資訊工程系

AR Vision Link 專題開發團隊

B1229006 陳語嫻
B1229021 黃星昊
B1229031 黃柏瑞
B1229049 陳泓均

---

# License

For Academic Use Only
