# Changelog / 更新日志
## [V1.51] - 2026-11-24

### 简体中文

**✦ 维护修复**
- **修复更新与意见反馈弹窗底部按钮被裁切**：重构 `ui/dialogs.py` 弹窗布局，将底部操作按钮区、进度条与复选框改为优先锚定（`side="bottom"`）并限制日志/输入框默认行数，彻底解决 Windows 高 DPI 缩放或长更新日志下按钮被挤出窗口外的问题。
- **修复启动双弹窗重叠**：优化版本检测与公告调度逻辑，当检测到新版本并弹出更新窗时不再叠加弹出公告窗。

---

### English

**✦ Maintenance Fixes**
- **Fixed Clipped Dialog Buttons under High-DPI**: Refactored Update and Feedback dialogs (`ui/dialogs.py`) to anchor bottom action bars and checkboxes first (`side="bottom"`) with constrained text-box heights, preventing buttons from being pushed off-screen on high-DPI displays or long changelogs.
- **Prevented Overlapping Startup Popups**: Refined startup update/announcement scheduling so announcements no longer overlap when a new version update dialog is shown.

---

## [V1.50] - 2026-11-24

### 简体中文

**✦ 重点优化与更新内容**
- **高 DPI 全分辨率适配与窗口交互升级**：新增视口自适应缩放、关键栏位锚定与左侧溢出智能滚动，全面修复 Windows 125%/150%+ 缩放及小屏下的裁切与挤压问题；新增 8 向边角自由缩放、全界面空白区拖拽、退出自动记忆窗口尺寸与位置（多屏防出屏纠偏），以及双击空白区或右键托盘一键恢复默认尺寸。
- **记忆库审美重构、空间锁与水系硬隔离**：新增室内/室外空间锁与道具兼容校验，严格隔离非水系与水畔/汤泉生态；重构四大世界观剧本与词库权重，明亮通透比例提升至约 **6:4**；推出全新高通透花庭库 **「晴风花庭」** 替代旧库「霓虹机能」；全面清除塑料油光反光词、蜡烛杂物与外貌污染词，并引入滑动防重复队列打通 9 大内置库全量混搭。
- **16 套自适应电影机位与 51 位角色重构**：镜头语言升级为 16 套姿态/空间自适应电影机位，强化荷叶/白百合/窗纱前景虚化与奶油浅景深；内置 51 位角色全员重构为「纯净外貌 + 独立原版服设」三元组结构，消除歧义与表情冲突，支持多套官服自动轮换、换装保护标志性特征及老存档升级自动补齐官服。
- **翻译加速、快捷键、音乐单曲循环与多端细节修复**：Youdao 翻译升级为 **320 字符并发分段 + 本地缓存 + 快速超时切换**，长句秒出译文；回退快捷键由 `Alt+Z` 调整为智能 **`Ctrl+Z`**（避开 NVIDIA 浮层冲突且输入框内保留原生文字撤销，桌面与 WebUI 同步）；本地 BGM 新增单曲循环（`🔁 / 🔀 / 🔂 / 🔇`）；修复 WebUI 角色搜索框五语同步、外文弹窗标题拼接及 GitHub Gist 云同步仅上传增量角色过滤。
- **低误报目录式安装向导（`--onedir`）**：正式安装版 `hsMuse_V1.50_Setup.exe` 切换为 `--onedir` 目录式架构，冷启动更快、显著降低安全软件误报；覆盖升级自动清理旧运行时并 100% 保留个人数据。

---

### English

**✦ Key Improvements & Fixes**
- **High-DPI Adaptation & Desktop Window Ergonomics**: Added viewport auto-fit scaling, anchored core controls, and smart left-panel auto-scroll to eliminate UI clipping on Windows 125%/150%+ scaling and compact screens. Added 8-direction resizing, blank-area dragging, persistent window size/position memory (with multi-monitor off-screen recovery), and one-click reset via blank-area double-click or tray menu.
- **Knowledge Base Overhaul, Space Lock & Water Isolation**: Added Indoor/Outdoor Space Lock, prop-compatibility checks, and strict water isolation so non-water themes stay 100% dry. Rebalanced bright-to-moody lighting to **~6:4**, introduced the airy **Sunlit Garden** pack replacing *Neon Techwear*, removed glossy/candle/trait-contaminating tags, and added a thread-safe anti-repeat queue across all 9 built-in packs.
- **16 Adaptive Cinematic Angles & 51 Character Profiles**: Upgraded to 16 pose- and space-adaptive camera angles with foreground botanical/curtain bokeh and creamy depth of field. Refactored all 51 built-in characters into pure appearance traits + independent canonical outfits with multi-outfit rotation, signature-trait protection during outfit swaps, and automatic outfit backfill for legacy saves.
- **Faster Translation, Smart Shortcuts, Repeat One & Sync Fixes**: Upgraded Youdao translation with **320-char concurrent chunking, local caching, and fast fallback**; switched Undo Roll from `Alt+Z` to smart **`Ctrl+Z`** (avoiding NVIDIA overlay clash while preserving native text undo in input fields across Desktop & WebUI); added **Repeat One (`🔂`)** to the BGM player; fixed WebUI search placeholder localization, dialog title i18n, and incremental Gist character sync.
- **Low-False-Positive `--onedir` Installer**: Migrated `hsMuse_V1.50_Setup.exe` to a `--onedir` directory layout for faster cold starts and fewer antivirus false positives, preserving 100% of local data on upgrade.

---

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
