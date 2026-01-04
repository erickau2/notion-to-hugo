---
title: "使用 sing-box + Surfshark 作為vpn 分流（split tunneling）"
date: "2025-07-29T05:51:00.000Z"
lastmod: "2026-01-03T16:25:00.000Z"
draft: false
series: []
authors:
  - "ling chi uu"
tags:
  - "devOps"
  - "installation"
  - "vpn"
categories:
  - "documentation"
  - "技術文章"
NOTION_METADATA:
  object: "page"
  id: "23f78d6d-8b2f-8082-a464-f766999793ef"
  created_time: "2025-07-29T05:51:00.000Z"
  last_edited_time: "2026-01-03T16:25:00.000Z"
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
  is_locked: false
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
      people:
        - object: "user"
          id: "83eb8096-da42-4d2d-b65f-d6e75aeeb194"
          name: "ling chi uu"
          avatar_url: "https://lh5.googleusercontent.com/-AJIIDFvWQIw/AAAAAAAAAAI/AAAAAAA\
            AAAA/AMZuucl-g3H8juy2xf-KPapRSs6s-63T8g/photo.jpg"
          type: "person"
          person:
            email: "erickson122764@gmail.com"
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
        - id: "143f5c06-8cab-4718-b349-5b894d829983"
          name: "installation"
          color: "green"
        - id: "154ad32c-b017-4086-8482-7af63e8077e6"
          name: "vpn"
          color: "red"
    categories:
      id: "nbY%3F"
      type: "multi_select"
      multi_select:
        - id: "nrY:"
          name: "documentation"
          color: "red"
        - id: "d3301358-a439-41b8-a42b-b85e60e85d2f"
          name: "技術文章"
          color: "default"
    Last edited time:
      id: "vbGE"
      type: "last_edited_time"
      last_edited_time: "2026-01-03T16:25:00.000Z"
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
            content: "使用 sing-box + Surfshark 作為vpn 分流（split tunneling）"
            link: null
          annotations:
            bold: false
            italic: false
            strikethrough: false
            underline: false
            code: false
            color: "default"
          plain_text: "使用 sing-box + Surfshark 作為vpn 分流（split tunneling）"
          href: null
  url: "https://www.notion.so/sing-box-Surfshark-vpn-split-tunneling-23f78d6d8b2f\
    8082a464f766999793ef"
  public_url: null
MANAGED_BY_NOTION_HUGO: true

---


---


## 這種做法適合誰？


這套 **sing-box + Surfshark** 的設定，特別適合這幾種情境：

- 需要穩定使用 AI / 國外服務

	例如：ChatGPT、Gemini、Claude、Copilot、部分只在海外開放的工具或網站。

- 不希望整個系統都走 VPN

	你可能平常逛本地網站、打遊戲、看串流，都希望維持原本路線與延遲。

- 在意效能與可維護性

	不想每次服務 IP 或 domain 改變，就要自己改規則、重抓清單。

- 想要「設定好之後就很少需要動它」

	期待的是一套長期穩定、好除錯的方案，而不是每天折騰自己。


簡單說：如果你只是想「讓需要翻牆的服務穩定工作」，而不是「把整台電腦都變成國外」，這篇就是為你寫的。


---


## 一、懶人版實作流程（5–10 分鐘完成）


### 你最後會得到什麼效果？

- macOS/iphone (linux/window/andriod也可以啦） **全系統透明代理**（不用逐一設定每個 App）。
- **只有指定網站會走 Surfshark VPN**。
- 其他網站維持原本速度與路線。

---


### Step 1｜從 App Store 下載 sing-box VT


打開 **Mac App Store**，搜尋：


> sing-box VT


![](https://www.roov.org/.gitbook/assets/2024-10-05_20-21-43.png)


這是 sing-box 的 GUI 版本，適合日常使用與設定管理。


下載後直接打開即可。


---


### Step 2｜在 Surfshark 後台建立 WireGuard 金鑰（重點）


使用 SurfShark 時，**不需要自己產生 WireGuard key**。


Surfshark 已經提供完整的 WireGuard 金鑰產生功能，直接用官方後台即可。


### Step 2-1｜前往 Surfshark 手動設定頁面

1. 登入 Surfshark 官網。
1. 前往：

	> VPN → 手動設定 → 任何一個安裝方法 → WireGuard


	![](https://notion.tech-bro.top/api?block_id=2dd78d6d-8b2f-808f-8e8b-ef72c8a6cb53)


	![](https://notion.tech-bro.top/api?block_id=2dd78d6d-8b2f-80c8-825b-e35b22f91529)


### Step 2-2｜建立 WireGuard 設定


在 WireGuard 頁面中：

1. 點選「我沒有金鑰組」。

	![](https://notion.tech-bro.top/api?block_id=2dd78d6d-8b2f-8080-8b1d-d2332284c744)

1. 輸入任意好記的名稱，點「產生新金鑰組」。

	![](https://notion.tech-bro.top/api?block_id=2dd78d6d-8b2f-8038-b3fb-dd37fdcdb317)


Surfshark 會自動產生一組 WireGuard 設定。


複製頁面上顯示的 **私鑰（Private key）**：


![](https://notion.tech-bro.top/api?block_id=2dd78d6d-8b2f-80e3-86db-d03addb657d5)


### Step 2-3｜記下以下資訊（稍後會用到）


請保存以下欄位：


![](https://notion.tech-bro.top/api?block_id=2dd78d6d-8b2f-8066-8285-ff43f76a5611)

- **Server hostname = 伺服器位址**

	例如：[`tw-tai.prod.surfshark.com`](http://tw-tai.prod.surfshark.com/)

- **Server port**

	例如：`51820`

- **Private key**

	👉 貼上剛才複製的私鑰。

- **Peer public key**

	👉 Surfshark 伺服器端的 public key。

- **IP address / Allowed IPs**

	例如：`10.14.0.2/16`


到這裡，你已經拿到 sing-box 所需的全部 WireGuard 資料。


→這裡有模板直接改需要的地方就好 


```json
{
  "experimental": {
    "cache_file": {
      "enabled": true,
      "path": "cache.db"
    }
  },
  "log": {
    "level": "info",
    "timestamp": true
  },
  "dns": {
    "servers": [
      {
        "tag": "surfshark-dns",
        "address": "162.252.172.57",
        "detour": "surfshark_out"
      },
      {
        "tag": "local-dns",
        "address": "1.1.1.1",
        "detour": "direct"
      }
    ],
    "rules": [
      {
        "rule_set": [
          "chatgpt_site",
          "tiktok_set",
          "gemini_set",
          "anthropic_set"
        ],
        "server": "surfshark-dns"
      }
    ],
    "final": "local-dns",
    "strategy": "ipv4_only"
  },
  "inbounds": [
    {
      "type": "tun",
      "tag": "tun-in",
      "interface_name": "singtun0",
      "address": ["172.19.0.1/30"],
      "mtu": 1280,
      "auto_route": true,
      "strict_route": true,
      "stack": "gvisor",
      "sniff": true
    }
  ],
  "outbounds": [
    {
      "type": "wireguard",
      "tag": "surfshark_out",
      "server": "填入 Surfshark提供的伺服器位址",
      "server_port": 51820,
      "local_address": ["10.14.0.2/16"],
      "peer_public_key": "填入 Surfshark 提供的 Peer Public Key",
      "private_key": "填入 Surfshark 提供的 Private Key",
      "mtu": 1280
    },
    {
      "type": "direct",
      "tag": "direct"
    },
    {
      "type": "dns",
      "tag": "dns-out"
    }
  ],
  "route": {
    "rules": [
      {
        "protocol": "dns",
        "outbound": "dns-out"
      },
      {
        "rule_set": [
          "chatgpt_site",
          "tiktok_set",
          "gemini_set",
          "anthropic_set"
        ],
        "outbound": "surfshark_out"
      }
    ],
    "rule_set": [
      {
        "tag": "chatgpt_site",
        "type": "remote",
        "format": "binary",
        "url": "https://raw.githubusercontent.com/MetaCubeX/meta-rules-dat/sing/geo-lite/geosite/openai.srs"
      },
      {
        "tag": "gemini_set",
        "type": "remote",
        "format": "binary",
        "url": "https://raw.githubusercontent.com/MetaCubeX/meta-rules-dat/sing/geo/geosite/google-gemini.srs"
      },
      {
        "tag": "tiktok_set",
        "type": "remote",
        "format": "binary",
        "url": "https://github.com/MetaCubeX/meta-rules-dat/raw/refs/heads/sing/geo-lite/geosite/tiktok.srs"
      },
      {
        "tag": "anthropic_set",
        "type": "remote",
        "format": "binary",
        "url": "https://github.com/MetaCubeX/meta-rules-dat/raw/refs/heads/sing/geo/geosite/anthropic.srs"
      }
    ],
    "final": "direct",
    "auto_detect_interface": true
  }
}

```


---


### Step 3｜在 sing-box VT 建立 Profile 並啟用（iphone 步驟也一樣）

1. 打開 **sing-box VT**。
1. 進入 **Profiles**。

![](https://notion.tech-bro.top/api?block_id=2dd78d6d-8b2f-80fc-8d55-d6729200572d)

1. 建立新的 Profile，然後進入 Edit Profile。

![](https://notion.tech-bro.top/api?block_id=2dd78d6d-8b2f-80fa-935a-d3d53a039889)

1. 貼上你的設定檔，就是剛才的模板，記得填server hostname/private key 和public key（技術段落會解釋其設計）。
1. 儲存並啟用。

第一次啟用時，macOS 會詢問 VPN / Network Extension 權限，請全部允許。


---


### Step 4｜確認是否成功


完成後，你可以用以下方式檢查：

- 開啟 ChatGPT / Gemini / Claude → 應該可以正常使用。
- 開啟本地或台灣網站 → 速度與未開 VPN 時相近。
- 在 sing-box Dashboard 中，可以看到流量與連線狀態。

到這裡，**懶人版已經完成，可以直接開始用**。


---


## 二、技術說明：為什麼要這樣設計？


如果你是工程師，或希望知道背後原理，這一段會比較有幫助。


### 2-1 核心原則：只讓「需要 VPN 的網站」走 VPN


整體概念可以用一句話總結：


> 只讓「需要 VPN 的網站」走 VPN，其餘流量全部直連。


實際流程長這樣：


```text
[TUN 全系統接管]
        ↓
[Routing Rules 判斷]
  ├─ 指定服務 → Surfshark (WireGuard)
  └─ 其他流量 → Direct
        ↓
[DNS 與流量出口保持一致]
```


---


### 2-2 為什麼使用 TUN 模式？

- 不需要替每個 App 設 Proxy。
- 瀏覽器、原生 App 都適用。
- 系統層級接管，穩定性高。

這也是 sing-box 在 macOS 上最實用的模式。


---


### 2-3 為什麼 DNS 一定要分流？


多數 AI 服務會同時檢查：

- 連線 IP。
- DNS 解析來源。

如果出現以下不一致的情況：

- DNS 使用本地。
- 實際流量卻走 VPN。

就很容易被判定為異常地區，導致服務不穩定或觸發額外驗證。


因此設定中會：

- 指定網站 → 使用 Surfshark DNS，並經 VPN 出口。
- 其他網站 → 使用本地 DNS，直接走原本路線。

---


### 2-4 為什麼選擇 WireGuard？

- 延遲低。
- 封包結構簡單。
- 效能好、資源消耗低。
- 與 sing-box 整合成熟。

對於「部分流量走 VPN」這類需要長期穩定工作的場景，WireGuard 是非常合適的協議。


---


### 2-5 為什麼使用遠端 rule set（`.srs`）？

- 二進位格式，效能佳。
- 有社群長期維護。
- 不需要自己追蹤 domain 變動。

比起手動維護一長串 domain 清單，穩定又省心。


---

