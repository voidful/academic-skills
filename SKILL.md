---
name: academic-research
description: "Complete academic research skill suite covering the full pipeline: paper reading (read/explain papers with storytelling), idea generation (brainstorm research directions), experiment design (plan experiments, ablation, baselines), proof writing (mathematical proofs, LaTeX theorems), paper writing (draft to camera-ready for top venues like NeurIPS/ICLR/ACL), paper review (structured 4-step review with scoring), and professor fit analysis (evaluate advisors, cold emails, interview strategy). Trigger keywords: read paper, brainstorm, experiment design, prove, write paper, review, professor fit, advisor, cold email, LaTeX, research, NeurIPS, ICLR, ACL, arXiv, 讀論文, 寫論文, 審稿, 實驗設計, 數學證明, 研究方向, 教授分析, 選指導教授."
license: MIT
compatibility: Works with Claude Code, ChatGPT/Codex CLI, and Gemini CLI.
metadata:
  author: research-skills
  version: "1.0.0"
---

# Academic Research Skills Suite

一套完整的學術研究 Skill 套件，涵蓋從論文閱讀到撰寫、審稿的完整研究流程。支援 Claude Code、ChatGPT/Codex CLI、Gemini CLI。

---

## Skill 路由表

根據使用者的意圖，載入對應的子 Skill：

| 觸發條件 | 子 Skill | 路徑 | 說明 |
|----------|---------|------|------|
| 讀論文、解釋論文、paper reading、看不懂這篇 | Paper Reading | [paper-reading/SKILL.md](paper-reading/SKILL.md) | 太奶角色論文導讀（繁中） |
| 想 idea、brainstorm、研究方向、下一步做什麼 | Idea Generation | [idea-generation/SKILL.md](idea-generation/SKILL.md) | 發散→搜索→收斂三階段構思 |
| 實驗設計、ablation、baseline、跑什麼實驗 | Experiment Design | [experiment-design/SKILL.md](experiment-design/SKILL.md) | 實驗設計與規劃 |
| 數學證明、prove、theorem、推導 | Proof Writer | [proof-writer/SKILL.md](proof-writer/SKILL.md) | 理論推導與數學證明 |
| 寫論文、paper writing、improve my paper、LaTeX | Paper Writing | [paper-writing/SKILL.md](paper-writing/SKILL.md) | 論文撰寫（頂會標準） |
| review、審稿、reviewer 會怎麼說、這篇能上嗎 | Paper Review | [paper-review/SKILL.md](paper-review/SKILL.md) | 4 步驟學術審稿 |
| 教授分析、professor fit、選指導教授、cold email、申請策略 | Professor Fit Analyser | [professor-fit-analyser/SKILL.md](professor-fit-analyser/SKILL.md) | 教授適配度分析與申請策略 |

**指引**：當使用者的請求匹配上方觸發條件時，請讀取對應路徑的 `SKILL.md` 並依照其指示執行。如果使用者的需求橫跨多個 Skill，請依照下方 Pipeline 順序依序處理。

---

## Skill Pipeline

```
professor-fit-analyser ─┐
                        ↓
paper-reading ──→ idea-generation ──→ experiment-design
      │                                       │
      ↓                                       ↓
paper-review ←── paper-writing ←──── proof-writer
      │                 ↑
      └─────────────────┘  (revision cycle)
```

---

## 語言慣例

- **預設語言**: 繁體中文（分析、解釋、討論）
- **英文場景**: LaTeX 生成、正式審稿輸出、數學符號與定理名稱
- **學術詞彙**: 參考 [shared/chinese-academic-glossary.md](shared/chinese-academic-glossary.md) 確保一致性

---

## 共享資源

- [shared/chinese-academic-glossary.md](shared/chinese-academic-glossary.md) — 中英學術詞彙對照
- [shared/conference-standards.md](shared/conference-standards.md) — 各頂會格式標準
- [shared/researcher-philosophies.md](shared/researcher-philosophies.md) — 研究者哲學與寫作風格

---

## 跨平台安裝

本套件符合 [Agent Skills 開放標準](https://agentskills.io/specification)，可在以下平台使用：

### Claude Code
```bash
# 方法一：Clone 到 skills 目錄
git clone <repo-url> ~/.claude/skills/academic-research

# 方法二：在專案中使用
git clone <repo-url> .claude/skills/academic-research
```

### ChatGPT / Codex CLI
```bash
git clone <repo-url> ~/.codex/skills/academic-research
# 或在專案中
git clone <repo-url> .codex/skills/academic-research
```

### Gemini CLI
```bash
git clone <repo-url> ~/.gemini/skills/academic-research
# 或在專案中
git clone <repo-url> .gemini/skills/academic-research
```

### 通用方式
將本倉庫目錄複製到你的 AI agent 的 skills 目錄即可。根目錄 `SKILL.md` 作為入口，agent 會透過 `*/SKILL.md` 模式自動發現所有子 skills。
