---
title: "打造你的智能財經助理：使用n8n自動化市場分析"
date: "2025-05-25T10:07:00.000Z"
lastmod: "2025-05-29T07:41:00.000Z"
draft: false
series: []
tags:
  - "devOps"
  - "n8n"
  - "self-host"
categories: []
authors:
  - "ling chi uu"
NOTION_METADATA:
  object: "page"
  id: "1fe78d6d-8b2f-81c3-a5a5-fd639c4dbab3"
  created_time: "2025-05-25T10:07:00.000Z"
  last_edited_time: "2025-05-29T07:41:00.000Z"
  created_by:
    object: "user"
    id: "83eb8096-da42-4d2d-b65f-d6e75aeeb194"
  last_edited_by:
    object: "user"
    id: "83eb8096-da42-4d2d-b65f-d6e75aeeb194"
  cover: null
  icon:
    type: "emoji"
    emoji: "🥊"
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
      checkbox: false
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
        - id: "9149a066-555c-466f-91e3-cc23ad48bdd7"
          name: "n8n"
          color: "yellow"
        - id: "5bc30978-2320-468d-aa94-cd3814914cd5"
          name: "self-host"
          color: "purple"
    categories:
      id: "nbY%3F"
      type: "multi_select"
      multi_select: []
    Last edited time:
      id: "vbGE"
      type: "last_edited_time"
      last_edited_time: "2025-05-29T07:41:00.000Z"
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
            content: "打造你的智能財經助理：使用n8n自動化市場分析"
            link: null
          annotations:
            bold: false
            italic: false
            strikethrough: false
            underline: false
            code: false
            color: "default"
          plain_text: "打造你的智能財經助理：使用n8n自動化市場分析"
          href: null
  url: "https://www.notion.so/n8n-1fe78d6d8b2f81c3a5a5fd639c4dbab3"
  public_url: null
MANAGED_BY_NOTION_HUGO: true

---


## 🤖 為什麼需要財經分析助理？


在瞬息萬變的金融市場中，即時資訊就是力量。想像一下，每天早上打開信箱，就能收到一份由AI精心分析的市場動態報告，是不是很棒？今天就讓我們一起打造這個智能助理！


## 🛠️ 準備工具


> 我們需要以下神器：  
>   
> - n8n - 你的自動化工作流平台  
>   
> - Finhub API - 提供最新市場資訊  
>   
> - Google Gemini API - 你的AI分析專家  
>   
> - Gmail API - 負責傳遞分析報告


## 🎯 工作原理


整個流程非常優雅：

1. 從Finhub獲取最新10條市場新聞
1. 交給Gemini AI進行深度分析
1. 自動整理成一份精美的email報告
1. 準時發送到你的信箱

## 🚀 實戰教學


### 1️⃣ Finhub API設置


	首先訪問 Finnhub.io：

	- 註冊一個免費帳號
	- 獲取你的API金鑰
	- 找到Markets News API接口

### 2️⃣ n8n工作流配置


	打開n8n儀表板：

	- 創建新的工作流
	- 添加HTTP Request節點來獲取新聞
	- 設置時間排序和數量限制

### 3️⃣ Google Gemini設置


	準備AI分析引擎：

	- 註冊Google Cloud帳戶
	- 開通Gemini API
	- 獲取API密鑰

### 4️⃣ Gmail配置


	設置郵件發送：

	- 開啟雙重認證
	- 生成應用專用密碼
	- 設置SMTP帳戶

## 💡 進階技巧


> **安全提示：**建議創建專門的Gmail帳戶來處理自動化郵件，這樣可以更好地管理和保護你的主要郵箱。


## 🎉 成果展示


完成設置後，你將擁有：

- 每日自動更新的市場分析報告
- AI驅動的智能見解
- 省時省力的自動化流程
- 個性化的市場動態追蹤

現在，你已經擁有了自己的智能財經助理！它會24/7為你監控市場，提供及時、專業的分析報告。讓科技為你的投資決策助力吧！


## 重要連結

- Finnhub API: [https://finnhub.io/](https://finnhub.io/)
- Google Gemini API文件: [https://docs.n8n.io/integrations/builtin/credentials/googleai/](https://docs.n8n.io/integrations/builtin/credentials/googleai/)
- Gmail設定文件: [https://docs.n8n.io/integrations/builtin/credentials/sendemail/gmail/](https://docs.n8n.io/integrations/builtin/credentials/sendemail/gmail/)
- n8n部署平台: [https://run.claw.cloud/](https://run.claw.cloud/)

## API端點


```javascript
Finnhub Market News API:
https://finnhub.io/api/v1/news?category=general&token=YOUR_API_KEY

```


## 重要提醒


> Gmail安全設定：建議創建專門的Gmail帳戶處理自動化郵件，以更好地管理和保護主要郵箱。


## n8n部署設定

- 推薦版本：n8nio/n8n:1.92.0
- 必要環境變數：N8N_RUNNERS_ENABLED=true

本設定可用於自動化：

- 整合API資料分析
- 發送自動化郵件報告
- 建立AI分析工作流
- 自動整理財經報表

[daily_financial_news.json](https://notion.tech-bro.top/api?block_id=1fe78d6d-8b2f-81a1-b787-d162a9869b4b)

