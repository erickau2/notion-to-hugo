---
title: "🚀 用 Claw Cloud Run 免費部署 n8n！完整圖文教學（2025）"
date: "2025-05-25T10:07:00.000Z"
lastmod: "2025-05-25T10:09:00.000Z"
draft: true
series: []
tags:
  - "devOps"
  - "免費"
categories: []
authors:
  - "ling chi uu"
NOTION_METADATA:
  object: "page"
  id: "1fe78d6d-8b2f-819b-a9e4-fe8f69f3bedc"
  created_time: "2025-05-25T10:07:00.000Z"
  last_edited_time: "2025-05-25T10:09:00.000Z"
  created_by:
    object: "user"
    id: "83eb8096-da42-4d2d-b65f-d6e75aeeb194"
  last_edited_by:
    object: "user"
    id: "83eb8096-da42-4d2d-b65f-d6e75aeeb194"
  cover: null
  icon: null
  parent:
    type: "database_id"
    database_id: "1fe78d6d-8b2f-8161-9087-c4177b9b0b7f"
  archived: false
  in_trash: false
  properties:
    series:
      id: "B%3C%3FS"
      type: "multi_select"
      multi_select: []
    draft:
      id: "JiWU"
      type: "checkbox"
      checkbox: true
    authors:
      id: "bK%3B%5B"
      type: "people"
      people: []
    custom-front-matter:
      id: "c~kA"
      type: "rich_text"
      rich_text: []
    tags:
      id: "jw%7CC"
      type: "multi_select"
      multi_select:
        - id: "e610c277-eedb-4f12-97cb-42b19f1a94c9"
          name: "devOps"
          color: "default"
        - id: "c878dfdf-6caf-4f3e-86ca-4a7647247368"
          name: "免費"
          color: "pink"
    categories:
      id: "nbY%3F"
      type: "multi_select"
      multi_select: []
    Last edited time:
      id: "vbGE"
      type: "last_edited_time"
      last_edited_time: "2025-05-25T10:09:00.000Z"
    summary:
      id: "x%3AlD"
      type: "rich_text"
      rich_text: []
    Name:
      id: "title"
      type: "title"
      title:
        - type: "text"
          text:
            content: "🚀 用 Claw Cloud Run 免費部署 n8n！完整圖文教學（2025）"
            link: null
          annotations:
            bold: false
            italic: false
            strikethrough: false
            underline: false
            code: false
            color: "default"
          plain_text: "🚀 用 Claw Cloud Run 免費部署 n8n！完整圖文教學（2025）"
          href: null
  url: "https://www.notion.so/Claw-Cloud-Run-n8n-2025-1fe78d6d8b2f819ba9e4fe8f69f\
    3bedc"
  public_url: null
MANAGED_BY_NOTION_HUGO: true

---


# ✅ 你需要準備的東西：

1. 一個註冊超過 **180 天** 的 GitHub 帳號（有額外額度）
1. 一雙手 🖐️（真的不誇張，超簡單）

---


## 🥇 第一步：前往 Claw Cloud Run 官網註冊帳號


👉 官方網站：


[https://run.claw.cloud/](https://run.claw.cloud/)


👉 如果你覺得這篇教學對你有幫助，也歡迎使用我的推薦註冊連結：


[https://console.run.claw.cloud/signin?link=6049PE85GU5V](https://console.run.claw.cloud/signin?link=6049PE85GU5V)


> （使用此連結我會獲得一點點額度支持，真的非常感謝你。不使用也完全沒問題～）


---


## 🥈 第二步：使用 GitHub 登入


[圖片待貼上]

- 官方建議使用 GitHub 登入，**註冊超過 180 天的帳號** 每月會獲得 **$5 美金免費額度**
- 沒滿 180 天也沒關係，**仍然有一個月的免費試用**
- 沒有 GitHub 的話也可以用 Google 登入，但我還是建議註冊一個 GitHub 帳號。畢竟都 2025 年了，入門開源世界不嫌晚！

---


## 🥉 第三步：快速認識 Claw Cloud Run 介面


成功登入後會看到 Claw Cloud Run（以下簡稱 CCR）介面：


[圖片待貼上]


我們今天只會用到 **App Store** 和 **App Launchpad**，其他功能可以之後再探索！


---


## 🛠️ 第四步：部署 n8n


[圖片待貼上]

1. 點選左邊選單的 `App Store`
1. 找到 `n8n` 並點進去
1. 按下 `Deploy App` → `Confirm`

稍等幾分鐘，App 就會自動部署起來！


（有時平台偶爾會塞車，耐心等待一下即可）


---


## 🔧 第五步：修改 n8n 設定（這步很重要！）


部署完成後，請依以下步驟進行設定：

1. 回到 `App Launchpad`
1. 點進剛剛部署的 `n8n` App，然後按 `Update`
1. 修改以下兩個設定：

### ✅ 1. 更新 n8n 版本


將 `Image Name` 改成：


`n8nio/n8n:1.92.0`


> Claw 預設的 n8n 版本較舊，建議手動切換到 1.92.0，目前為社群推薦穩定版本。


---


### ✅ 2. 加入環境變數（Environment Variable）


在 `Environment` 區塊新增以下變數：


`N8N_RUNNERS_ENABLED=true`


這樣可以啟用新的工作排程引擎，提高穩定性。


---


### 💡 小技巧：節省資源費用（可選）


你可以考慮將 CPU 或記憶體調低一些來節省額度，不過會影響執行效率。**如果不確定自己在做什麼，建議保留預設值**，確保流程能順利跑起來。


---


## 🌐 第六步：啟用網址，開始使用 n8n！


部署大約 10~15 分鐘後，Claw 會提供你一個免費網址。


[圖片待貼上]


打開後會看到登入頁面，系統會請你設定：

- **Email**
- **密碼**（請務必設一組強密碼，因為只要知道你網址的人都能開啟這個頁面）

輸入完畢後，你的 n8n 就完成部署啦 🎉！


---


## 🎉 恭喜你，正式踏上自動化之旅！


你現在擁有屬於自己的免費 n8n 雲端平台，可以用來：

- 整合 API 資料
- 發送自動化郵件
- 建立 ChatGPT 工作流
- 串接表單、自動整理報表

未來還有更多可能，歡迎你持續探索！


---


### 🙏 最後


如果這篇教學對你有幫助，歡迎幫我分享給朋友，或是使用我的 [推薦連結](https://console.run.claw.cloud/signin?link=6049PE85GU5V) 支持一下小弟～


有任何問題也歡迎留言或私訊我討論！

