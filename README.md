# MBTI 自我探索 Skill

一個讓 Claude 陪你認識自己的 [Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)（繁體中文）。

整個流程**只做一份網頁測驗**，其餘都透過多輪訪談完成：先找出真正貼切的 MBTI 類型，再把對自己的理解延伸到生活的各個面向。

## 為什麼做這個

網路上的「MBTI 測驗」大多不是正版，例如 16Personalities 自己就說明它和 MBTI 不能互換。正版 MBTI 的數據也顯示，15 週內重測，四個字母完全相同的人只有約 51%。

所以正版流程本來就包含一個步驟：**最適類型確認**，由本人在理解理論之後，對照自己的生活經驗來決定。這個 Skill 讓 Claude 扮演那位會追問的訪談者。

## 流程

| 模組 | 內容 |
|---|---|
| A 理論 | 正版 MBTI 的三層理論（榮格原著 → Myers-Briggs → 網路後加的說法），以及網路測驗哪裡不準 |
| B 網頁測驗 | 先寫下自己猜的類型，再做免費的開放量表 [OEJTS](https://openpsychometrics.org/tests/OJTS/)，約 48 題 |
| C 類型確認 | 用具體的生活例子、認知功能區分題、壓力下的劣勢功能題來區分候選類型，最後由本人決定 |
| D 生活維度 | 工作、人際、感情、家庭、金錢、運動、創作等面向的偏好與地雷，每一項都標註依據和確定度 |
| E 人生方向 | 從你最有成就感的經驗出發，一路走到下週就能做的第一步 |
| F 情感需求 | 透過關係史訪談，整理出核心需求、需求的來源，以及表達上的落差 |

每個模組都可以單獨做，也可以隨時停下來，下次接著繼續。每一步都會存成 Markdown 紀錄檔。

## 安裝

### Claude Code

```bash
git clone https://github.com/chunhua0710/mbti-self-discovery.git
cp -R mbti-self-discovery/mbti-self-discovery ~/.claude/skills/
```

裝好後，開一個新的工作階段就能使用。

### Claude.ai 網頁版或桌面 App

到 [Releases](https://github.com/chunhua0710/mbti-self-discovery/releases) 下載 `mbti-self-discovery.skill`，再到設定裡的 Skills（技能）上傳。介面名稱可能略有不同。

## 怎麼開始

直接跟 Claude 說，例如：
- 「我想做 MBTI，訪問我確認類型」
- 「我測出 INFJ 和 INFP 都有，到底是哪個？」
- 「幫我整理我在工作和感情上的地雷」
- 「我對人生方向很徬徨，可以引導我嗎？」

建議在一個專用的資料夾裡開始，紀錄檔都會存在那裡。

## 檔案結構

```
mbti-self-discovery/
├── SKILL.md                     # 流程、訪談原則、敏感話題處理
└── references/
    ├── theory.md                # 正版 MBTI 理論、官方測驗格式、信效度數據、來源
    ├── type-interview.md        # OEJTS 判讀、16 型功能表、題庫、劣勢功能、紀錄範本
    ├── life-dimensions.md       # 生活維度的偏好與地雷
    ├── life-direction.md        # 人生方向五步驟
    ├── emotional-needs.md       # 情感需求訪談
    ├── sources.md               # 出處對照表：每個數字的出處、頁碼、備份連結
    └── jung-1923/               # 榮格《心理類型》1923 英譯本原文（公有領域）
        ├── ch10-general-description-of-the-types.md   # 第十章 類型總述，p. 412–517
        └── ch11-definitions.md                        # 第十一章 名詞定義，p. 518–617
```

## 隱私

- 訪談紀錄只存在你自己的電腦上
- OEJTS 是外部網站，它會匿名保存作答資料，用於研究
- 只有在你主動提供並同意時，Claude 才會讀你的私人資料，例如聊天紀錄

## 限制

- OEJTS 不是官方 MBTI，訪談也不是正式施測。想要官方結果，可以做 MBTIonline，或找認證的施測師
- 這是自我了解的工具，**不是心理診斷**。遇到困擾時，請尋求專業協助
- 不適用於評估或篩選別人，例如招募、替同事判定類型

## 資料來源與查證

**主要數字和說法都附出處。** [`references/sources.md`](mbti-self-discovery/references/sources.md) 列出每一個主張的出處和頁碼，例如「15 週重測，四字母全部相同只有 51%」→ 官方 Global 美國版增補手冊，PDF 第 8 頁，Table 12。每個連結也盡量附上 Wayback Machine 的備份，原網址失效時可以用。

**收錄了哪些原文**
| 資料 | 收錄方式 | 原因 |
|---|---|---|
| 榮格《心理類型》1923 Baynes 英譯本，第十章〈類型總述〉、第十一章〈定義〉 | 全文收在 [`references/jung-1923/`](mbti-self-discovery/references/jung-1923/)，附原書頁碼 | 公有領域，見下方說明 |
| The Myers-Briggs Company 的官方技術文件 | 只附連結和頁碼 | 有版權。官方提供下載，不代表允許轉載 |
| 期刊論文（Pittenger、Randall、McCrae & Costa、Arnau 等） | 只附連結、DOI 和頁碼 | 有版權 |
| Lee & Kim (2024) | 只附 DOI | CC BY 開放取用，從期刊網站就能直接讀 |

**榮格原文的權利說明**：Baynes 英譯本 1923 年出版，在美國已是公有領域。在台灣，作者（1961 年過世）和譯者（1943 年過世）都已超過著作財產權的保護期間。歐盟等「作者過世後 70 年」的地區，保護期要到 2031 年底才結束，請依所在地的法律使用。原文由 archive.org 的掃描檔 OCR 轉出，可能有錯字，逐字引用前請用頁碼對照[掃描檔](https://archive.org/details/psychologicaltyp00jung_1)。

## 聲明

- 這個專案沒有收錄任何官方 MBTI 題目
- OEJTS 由 [Open-Source Psychometrics Project](https://openpsychometrics.org/) 提供，題目以 CC BY-NC-SA 4.0 授權。本專案只提供連結，沒有收錄它的題目
- MBTI®、Myers-Briggs® 是 The Myers-Briggs Company 的商標。本專案與該公司沒有任何關聯

## 授權

本專案採用 [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) 授權，全文見 [LICENSE](LICENSE)。歡迎自由使用、修改和分享，但需標註出處，且**不得用於商業用途**。

例外：`references/jung-1923/` 裡的榮格原文是公有領域，不受本專案授權限制。
