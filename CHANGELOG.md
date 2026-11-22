# Changelog / 更新日志

## [V1.49] - 2026-11-22 (首个正式公开发行版 / First Public Release)

### 简体中文

**✦ 核心功能与产品亮点**
- **可成长的动态角色库（最高支持 500 位角色）**：开箱内置 51 位人气角色与原创预设；支持自由新建与定制个人 OC、写入 LoRA 触发词及多套专属服设、内置 AI 一键提取角色外貌指令，联网直采时更能自动识别、去重并收录新角色入库。支持中英文与外貌词实时秒搜、原版服设一键锁定，以及单/双人左右空间隔离。
- **可自定义模块化美学词库 / 记忆库（最高支持 40 套 · 单栏 500 词条）**：采用便携独立的 JSON 架构，首发内置 9 套高密度美学词库 + 动态【灵感潮汐】池；支持 10 格可视化编辑、自定义排序、AI 一键造库导入及文件拖拽共享，所有自建词库均自动参与全库智能混搭，打造越用越懂你的专属离线提示词记忆库。
- **四大世界观隔离引擎（Era Lock）与双格式批量生成**：严格隔离「现代时尚 / 东方仙侠 / 物哀哥特 / 自然水畔汤泉」四大生态，原子级绑定人物、穿搭、动作、神态、场景与光影，一键同步输出「8 级规范排序 Tag」与「电影级自然语言长句」；支持 `{A|B}` 随机通配符，单次最高支持 100 条批量去重生成与导出。
- **多源并发灵感直采 & 批量清洗工作台**：支持按 SFW / 纯欲 / R18 分级多线程并发抓取高分创意，关闭自动收录角色时依然完整保留外貌词并持续反哺本地灵感池；清洗工作台支持单次最高 200 行批量处理，按需剥离 LoRA、权重括号、废词、人物外貌或基础服装（精准保留景别与神态词），一键转安全预览 / NSFW 并合成流畅自然语言。
- **桌面端 + 本地 WebUI 实时同步 & 全套周边生态**：推荐优先点击顶栏【网页版】体验更流畅的大屏排版与实时词数统计；内置 1K~8K DPI 自适应、5 国语言（简/繁/英/日/韩）、4 款极简高定皮肤 + 12 套灵感色卡、四引擎翻译（Youdao / MyMemory / Google / 自定义 AI 大模型）、GitHub Private Gist 私有云跨机同步、本地离线备份/恢复、轻量本地 BGM 播放器，以及完整保留个人数据的软件内一键在线更新。

---

### English

**✦ Core Highlights**
- **Self-Growing Character Archive (Up to 500 Profiles)**: Ships ready out of the box with 51 curated anime, game & original starter presets. Create custom OCs with LoRA triggers and multi-outfit closets, use the built-in AI trait-extraction prompt, or let Live Fetch automatically discover, deduplicate, and archive new characters. Includes instant live search, canonical-outfit locking, and spatially separated Solo/Dual framing.
- **Customizable Modular Knowledge Bases (Up to 40 Packs · 500 Entries per Slot)**: Built on portable JSON packs, shipping with 9 high-density aesthetic packs + the dynamic *Muse Tide* pool. Visually edit across 10 structured slots, reorder packs, import AI-generated themes in seconds, share via drag-and-drop, and mix all custom packs seamlessly in All-KB Smart Mix.
- **4-Era Worldview Isolation (Era Lock) & Batch Production**: Separates *Modern*, *Eastern Fantasy (Xianxia)*, *Wabi-Sabi/Gothic*, and *Nature/Onsen* worlds to eliminate era clashes. Simultaneously outputs **8-level sorted Tag sequences** and **cinematic natural language prose**, with `{A|B}` wildcard syntax and up to 100 unique batch prompts per run.
- **Concurrent Live Inspiration Fetch & Batch Prompt Cleaner**: Races top-rated visual sources by rating (SFW / Sensual / R18) to feed curated tags into your offline pool. The Cleaner handles up to 200 lines per batch—stripping LoRAs, weights, quality filler, character traits, or base outfits (while preserving framing and expressions), converting between SFW/NSFW, and generating natural prose.
- **Desktop & Local WebUI Parity + Ecosystem Tools**: Click **[WebUI]** in the top bar for the smoothest widescreen workflow and live counters. Features 1K–8K DPI scaling, 5-language UI switching, 4 minimalist themes + 12 palettes, 4-engine translation (including custom OpenAI-compatible AI LLMs), zero-server GitHub Private Gist cloud sync, offline backup/restore, local BGM player, and in-app updates that preserve 100% of your local data.