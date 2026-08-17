# 小说 → 漫剧短视频 流水线 Skill（novel-to-manju）

把一个小说（或一个题材想法）做成抖音竖屏漫剧/短视频的**全流程提示词 skill**。自包含，无需其它文件，拿到就能用。

## 它是什么

一句话：**喂一篇小说，产出「爆款改文 → 漫剧剧本 → 人物/场景/三视图提示词 → 分镜脚本 → MiniMax H3 视频提示词」**的完整流水线。

内置：
- 全流程 8 步 + 工具分工（文字用 DeepSeek/豆包，图用即梦/MJ/SD 当参考图，视频用 MiniMax H3）
- 合规敏感词过滤（血腥/裸露/色情/封建的替代规则）
- 一致性锁定（人物/场景跨镜头不变）
- MiniMax H3 官方 **Ref2VA 六段式**输出模板（subject_definitions → retention_analysis → detailed_description → overall_soundscape → non_diegetic_music）
- 打斗/技能特效、人物五官库、场景公式、三视图等全套规则

## 快速上手

### 用法 A：装进 Claude Code / Codex（按 `/` 调用）

**1. 安装 skill（自动触发）**
- Claude Code：把整个文件夹复制到项目或用户目录的 `.claude/skills/novel-to-manju/`
  - 项目级：`你的项目/.claude/skills/novel-to-manju/SKILL.md`
  - 用户级：`~/.claude/skills/novel-to-manju/SKILL.md`
- Codex：复制到 `.codex/skills/novel-to-manju/`

**2. 安装斜杠命令（手动 `/manju` 触发）**
- Claude Code：把 `commands/manju.md` 复制到 `.claude/commands/`（或 `~/.claude/commands/`）
- Codex：把 `commands/manju.md` 复制到 `.codex/prompts/`

**3. 使用**
- 直接说："帮我把这段小说做成漫剧"（skill 自动触发）
- 或输入 `/manju`，再粘贴小说

### 用法 B：直接粘给豆包 / DeepSeek

把 `SKILL.md` 全文复制，粘给豆包 / DeepSeek / ChatGPT，附上小说原文，它会按 8 步产出。

### 用法 C：只做某一环

说"生成男主三视图""把这段打斗写成分镜""生成 H3 视频提示词"，skill 只跑对应环节。

## 目录结构

```
novel-to-manju/
├── SKILL.md            ← 主 skill（自包含，核心）
├── README.md           ← 本文件
├── LICENSE             ← CC0 1.0
├── commands/
│   └── manju.md        ← 斜杠命令（/manju）
└── docs/               ← （可选）原始提示词资料库
    └── 生成视频提示词格式和示例.txt  ← H3 Ref2VA 官方格式+原创示例
```

## 触发词

"做漫剧 / 小说转视频 / 漫剧剧本 / 爆款改文 / 原创小说 / 人物提示词 / 场景提示词 / 三视图 / 分镜 / 镜头提示词 / 打斗特效 / MiniMax H3 视频提示词 / 封面" 等，都会触发本 skill。

## 许可证

[CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) — 公有领域，可自由使用、修改、商用、再分发，无需署名。
