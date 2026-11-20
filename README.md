# Matt Pocock 做完一個兩萬一千行的功能：他在哪裡出手，在哪裡放手

Matt Pocock 的 YouTube 影片〈Watch me ship a 21,000-line feature with mattpocock/skills〉（1:09:30，2026-11-18 上傳）的深度導讀。他用自己的 skills，把一個「讓 diagram 直接畫在縮圖裡他的臉旁邊」的功能，從模糊想法做到上線。導讀涵蓋：選 skill 的決策、grilling 與術語表／ADR／情境測試、三版原型、smart zone 與 dumb zone、spec 與 ticket、compact 與 AFK 實作、把 21,000 行 PR 拆成一串堆疊 PR（口述七個、畫面標示九個） 並人工審查、retro 與註解稽核，以及講者自述最有價值的兩個時間點；講者說法與官方 repo 現況的差異集中對照。

## 製作聲明

本導讀的分析、撰稿、翻譯、查證與插圖由 AI 模型完成，不是人類分析，也沒有經過人工逐句校稿。依 YouTube 機器字幕（en-orig）整理；第二版另用 agy（gemini-3.8-flash-high）直接看影片：對 22 個存疑字幕窗口（含 4 個數字句）各做兩次獨立聽寫（兩次一致才採用，共改 4 句中文字幕）、掃描全片畫面，並由 AI 主控取 720p 影格逐張檢視核對畫面數字與作者的圖（非人工核對；agy 沒有參與事實查證），未全片對照原音逐句校對。模型分工：主控為 Claude Sonnet 5.5（Claude Code）；逐句翻譯為 agy（gemini-3.8-flash-medium），再由 Sonnet 逐章修詞、Opus 統一審查；撰稿、審稿 A（事實）與 B（編輯）、合併修稿、終審、總編輯潤稿與篇幅精簡皆由 Opus subagent 負責；查證由 Sonnet subagent 進行，並經主控以 `gh` 與一手來源核對，沒有另請其他模型交叉查證；資訊型示意圖由 Sonnet subagent 以程式繪成 SVG，封面與比喻插畫由 Codex 的圖像生成工具（imagegen）製作；作者在影片裡秀出的決策樹、smart zone 方塊圖、PR 對照表與 Spec／Tickets 投影片另譯成繁體中文重繪（標示出處，版權屬原作者）。分工與採計原則見導讀文末〈製作說明〉。

## 檔案

| 檔案 | 說明 |
|---|---|
| `index.html` | 導讀長文，單檔網頁，可直接用瀏覽器開啟 |
| `matt-pocock-ship-feature.md` | 正式 Markdown |
| `player.html` | 雙語字幕同步播放器（影片嵌入自 YouTube） |
| `translation-zh.html` | 影片全文繁體中文譯文（非官方） |
| `share_post.md` | 純文字社群分享文 |
| `images/` | 封面 `hero-16x9.png`／`hero-9x16.png`、分享圖 `og-hero.jpg`、籬笆與原型插畫、Spec／Tickets 投影片繁中版（`spec-tickets-*.png`）、示意圖 SVG（決策樹、smart zone、PR 堆疊、流程、retro、註解稽核、人的價值；各有桌面與手機版） |
| `qa/`、`research/` | 驗收截圖、查證帳本、審稿紀錄與建置腳本，僅留本機 |

## 原始資料

- 類型：影片
- 名稱：Watch me ship a 21,000-line feature with mattpocock/skills（頻道 Matt Pocock，1:09:30）
- 網址：https://www.youtube.com/watch?v=jVBlkOF8sHk
- 逐字稿位置：專案 `transcription/Watch_me_ship_a_21,000-line_feature_with_mattpocockskills_jVBlkOF8sHk.srt`（YouTube 自動字幕 `en-orig`，機器產生，無說話者標記）；本目錄 `research/raw.srt` 為複本，整理後的逐句雙語定稿為 `research/cues_final.json`（1,013 句、19 章）

## 重要來源

- 第一手：[影片與說明欄](https://www.youtube.com/watch?v=jVBlkOF8sHk)、[mattpocock/skills 官方 repo](https://github.com/mattpocock/skills)（2026-11-20 讀取，最新 release v1.3.2）
- 補充：[Dex Horthy〈No Vibes Allowed〉講座](https://www.youtube.com/watch?v=rmvDxxNubIg)（AI Engineer，2025-12-02）、[Lauren Tan〈All Code Is Slop (Except Mine)〉演講](https://www.youtube.com/watch?v=O_zcc6Xl12g)（AI Engineer，2026-11-14）、G. K. Chesterton《The Thing》（1930 年版，[Internet Archive 掃描全文](https://archive.org/download/thingwhyiamcatho0000ches/thingwhyiamcatho0000ches_djvu.txt)）

## 狀態

已發布（2026-11-20）：
- 網頁：https://lushinshang.github.io/matt-pocock-ship-feature/
- 雙語播放器：https://lushinshang.github.io/matt-pocock-ship-feature/player.html
- 全文譯文：https://lushinshang.github.io/matt-pocock-ship-feature/translation-zh.html
- GitHub Repo：`lushinshang/matt-pocock-ship-feature`（公開內容不含 `research/` 與 `qa/`）
