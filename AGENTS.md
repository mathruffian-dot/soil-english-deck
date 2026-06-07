# AGENTS.md — 給 AI Agent 的安裝與使用指引

> 你是 AI agent。當你讀到這個 repo（或使用者說「安裝 soil-english-deck」「裝這個英文簡報技能」）時，依下列步驟把技能安裝好，之後即可在對話中觸發。

---

## 這是什麼

`soil-english-deck` 是一個 **SOIL 英文教學簡報技能**：給定英文教材或主題，依李俊儀教授 SOIL 六引擎，產出有教學力的 **`.pptx`** 簡報。**零金鑰**（不需 OpenAI / Firebase / 任何 API key）。

---

## 安裝步驟

### 方式 A：用安裝腳本（推薦）
```bash
git clone https://github.com/mathruffian-dot/soil-english-deck.git
cd soil-english-deck
python install.py
```
`install.py` 會偵測你的技能資料夾（Claude Code `~/.claude/skills`、OpenCode `~/.config/opencode/skills`、Codex `~/.agents/skills`）並把 `skill/` 複製為 `soil-english-deck`。

### 方式 B：手動複製
把本 repo 的 `skill/` 目錄複製到你的技能資料夾並改名為 `soil-english-deck`，例如：
```bash
cp -r skill/ ~/.claude/skills/soil-english-deck/
```

安裝後**重新啟動 / 重新整理**你的 agent 以掛載技能。

---

## 執行需求

- **Python 3.8+**、**Node.js**（用 PptxGenJS 生成 `.pptx`）。
- **源石黑體**（粗圓字型）：技能內含 **F-0 自動下載安裝流程**，生成 `.pptx` 前若偵測缺字會自動從 ButTaiwan/genseki-font 下載安裝（免金鑰）。
- 讀取 PptxGenJS 技術文件：你的環境中的 `pptx` 技能 `pptxgenjs.md`。
- **不需要**任何 API 金鑰、不呼叫 `draw` 生圖。

---

## 安裝後怎麼用

對使用者說的話若符合以下，就觸發本技能（細節見 `skill/SKILL.md`）：
- 「幫我把這課課文做成英文教學簡報」
- 「用 SOIL 做一份〈現在完成式〉的教學投影片」
- 「幫我設計文法 / 單字 / 閱讀 / 寫作的教學簡報」
- 「這份英文簡報哪裡可以改」

技能會依 SOIL 六引擎逐步進行，每顆引擎跑完都停下來等使用者確認，最後用 PptxGenJS 產出 `.pptx`。

---

## 內容結構
```
soil-english-deck/
├── README.md          # 人類入口
├── AGENTS.md          # 本檔（agent 入口）
├── install.py         # 安裝腳本（多家 agent 通用）
├── LICENSE
└── skill/
    └── SKILL.md       # 技能主體：SOIL 六引擎 + 8 種英文教學版型 + F-0 字型流程
```
