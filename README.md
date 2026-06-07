# 🎤 soil-english-deck — SOIL 英文教學簡報技能（英文科專用、零金鑰）

> 給定英文教材或主題，依李俊儀教授 **SOIL 六引擎** 工作流，產出一份有教學力的 **`.pptx`** 簡報。
> 專為**英文老師**設計，**不需要任何 API 金鑰**。

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## 這是什麼

改編自數學科版的 `soil-teaching-deck`，調整為**英文科專用**並**移除所有需要金鑰的功能**：

| | 數學科版（原版） | 英文科版（本 repo） |
|---|---|---|
| 學科版型 | 幾何圖形（三角形 / 函數 / 三角形的心…）| **英文教學版型**（時態對照、例句結構卡、對話、單字表、寫作前後對照、閱讀標注）|
| 插圖 | `draw`（gpt-image / OpenAI，**需金鑰**）| ❌ 移除 → **PptxGenJS 原生視覺 + emoji**（零金鑰）|
| 產出 | `.pptx` | `.pptx`（相同）|
| SOIL 六引擎 | ✅ | ✅（完整保留）|

---

## SOIL 六引擎

1. **概念定位** — 這堂英文課要學生帶走什麼（總概念 / 子概念 / 常見誤解）
2. **脈絡定位** — 引起動機 → 維持注意 → 喚起行動的理解節奏
3. **頁面架構** — 每頁一個任務，挑選英文教學版型
4. **認知編修** — 六個認知詞把每頁修成真正的教學頁
5. **風格建構** — 把風格固定成規則（含 S/V/O 分色慣例）
6. **簡報總導演** — 用 PptxGenJS 生成 `.pptx`

---

## 八種英文教學視覺版型（全部零金鑰、PptxGenJS 原生）

| 版型 | 用途 |
|------|------|
| `tense_table` | 時態 / 用法對照（過去式 vs 完成式）|
| `sentence_card` | 例句結構卡（主詞/動詞/受詞分色）|
| `dialogue` | 對話雙欄（口說 / 聽力）|
| `vocab_list` | 單字表（單字 / 詞性 / 音標 / 例句）|
| `writing_diff` | 寫作前後對照（原句 vs 修改）|
| `reading_callout` | 閱讀文本 + 重點標注 |
| `word_family` | 字根 / 字族 / 搭配詞放射圖 |
| `icon_grid` | emoji 圖示要點網格 |

---

## 🔧 安裝

```bash
git clone https://github.com/mathruffian-dot/soil-english-deck.git
cd soil-english-deck
python install.py
```

安裝腳本會偵測你的 Agent 技能資料夾（Claude Code / OpenCode / Codex）並把 skill 複製過去。

> 需要的元件：Python 3.8+、Node.js（PptxGenJS 生成 .pptx 用）。**不需要 OpenAI / 任何 API 金鑰。**

---

## 🚀 使用方式

對你的 Agent 說：

```
幫我把這課課文做成英文教學簡報
```
或
```
用 SOIL 做一份「現在完成式」的教學投影片
```

Agent 會依六引擎逐步進行，每顆引擎跑完都會**停下來等你確認**，最後產出 `.pptx`。

---

## 📁 結構

```
soil-english-deck/
├── README.md
├── install.py            # 安裝腳本（多家 Agent 通用）
├── LICENSE
└── skill/
    └── SKILL.md          # 主要指令（Agent 讀取，六引擎 + 八版型，自足無外部依賴）
```

---

## 📄 授權

MIT License。改編自 `soil-teaching-deck`（李俊儀教授 SOIL 教學心法）。
