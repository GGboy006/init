# 紫微斗数大师口播 Skill

这不是网站，也不是排盘软件。这是一份给 AI Agent 用的 **Skill**：对方丢来生辰或命盘图，按正经紫微斗数师傅的流程批，并给出**能直接语音念出的口语稿**。

格式遵循开放标准 [Agent Skills](https://agentskills.io/specification)（`SKILL.md`）。同一份内容可供 Cursor、Claude Code、Codex、Gemini CLI 等兼容工具读取。Claude.ai、ChatGPT 网页聊天没有这套 Skill 机制，不能自动加载。

## 它做什么

- 接生辰或命盘图片，材料不齐就反问
- 先核盘、定象，再讲四化、飞星、大限流年
- 命盘形成真格局会点出来，破格会说破
- 默认南派、《紫微斗数全书》四化；星曜定性、四化定量
- 不恐吓、不包办医疗法律投资

## 文件放在哪

正文只维护一份，在：

```text
.agents/skills/ziwei-doushu-master/
├── SKILL.md
└── references/
    ├── timing.md      # 核时、定盘、大限流年
    ├── palaces.md     # 十二宫、宫/位、六条线
    ├── stars.md       # 主星、双星、辅煞
    ├── sihua.md       # 四化、飞星
    └── patterns.md    # 格局
```

项目里另外两个入口指向同一份目录，方便各工具自动发现：

- Cursor：`.cursor/skills/ziwei-doushu-master/`
- Claude Code：`.claude/skills/ziwei-doushu-master/`

改 `SKILL.md` 或 `references/` 时，改 `.agents/skills/` 里那一份即可。

## 各工具怎么用

打开这个仓库后：

- **Cursor**：在 Agent 对话里丢生辰或盘图即可；也可输入 `/ziwei-doushu-master`。若希望整段对话都按师傅口吻，把该 Skill 开成 Custom Mode。
- **Claude Code**：打开同一仓库后，丢生辰或盘图，或用 `/ziwei-doushu-master`。
- **Codex / Gemini CLI**：兼容 Agent Skills 的客户端会读 `.agents/skills/`。

想装到自己所有项目，把整个 `ziwei-doushu-master` 文件夹复制到对应用户目录：

| 工具 | 用户级目录 |
| --- | --- |
| 通用 | `~/.agents/skills/` |
| Cursor | `~/.cursor/skills/` |
| Claude Code | `~/.claude/skills/` |

Windows 用户目录一般是 `C:\Users\你的用户名\`，把 `~` 换成它即可。

## 口径说明

批盘顺序、口播规矩、宫位和飞星句法，来自咱们整理的专业流程，并参考 [iztro 紫微研习社](https://iztro.com/) 的结构化教材（全书/南派口径）。Skill 里是改写过的规则，不是原文转载。其他门派四化表不同，遇到要先声明，不要混断。
