## [V2.3] - 2026-11-28 (五种语言全补齐 & 稳定性升级 / Full 5-Language Parity & Stability Upgrade)

### 简体中文
**✦ 多语言补齐、引擎加固与架构优化**
- **五种语言全链路补齐（响应 @KieranW 反馈）**：第一时间响应海外创作者反馈，彻底补齐简体中文 / 繁体中文 / 英文 / 日文 / 韩文在全部二级弹窗（模型扩展包、外置视觉大模型配置、数据体检三件套、批量生成、角色/配方/词库弹窗）、批量打标进度条、抽查标题、音乐播放状态及全站 Toast 提示中的多语言覆盖；非简体中文界面自动隐藏国内专属网盘提示。
- **本地视觉大模型与批量稳定性提升**：将本地 GGUF 引擎上下文窗口由 `2048` 提升至 `4096`，并在批量自然语言反推中新增单图瞬时异常自动重试机制，显著降低大图叠加锚点批量打标时的失败率。
- **元数据、续传校验与预处理保护**：优化 WebP EXIF 偏移切片逻辑，修复部分 WebP 原图 UTF-16 提示词漏读问题；为大体积模型断点续传新增实际接收字节完整度校验；训练集配对重命名新增异常自动回滚机制，透明底铺白异常自动清理临时文件；解除单图与批量反推并发时的评级状态竞态。
- **纯内存前端封装与交互细节打磨**：前端静态资源经词法去注释后封入原生编译加密保险箱纯内存直供，安装目录零明文前端文件落地；锁定按钮行高与最小高度，彻底消除抓取状态切换时的输入框轻微位移。
- **无损覆盖升级**：直接运行 `hsMuse_V2.3_Setup.exe` 覆盖安装即可 100% 保留原有个人数据、自建角色、词库、音乐与外置 `models/` 目录（`hsMuse_V2.3.exe` 仅作绿色便携备用）。

### English
**✦ Localization Parity, Core Stability & Hardened Runtime**
- **Complete 5-Language Parity (Responding to @KieranW's Feedback)**: Promptly resolved all remaining untranslated strings across Model Pack cards, External Vision LLM Setup, the Dataset Audit & Preprocessing Toolkit, Batch Generator, Character/Recipe/KB dialogs, live batch progress bars, review titles, music statuses, and toast notifications across Simplified/Traditional Chinese, English, Japanese, and Korean.
- **Vision LLM Context & Batch Reliability**: Expanded local GGUF inference server context window from `2048` to `4096` and added automatic single-image retry in batch captioning mode.
- **Metadata, Download & Dataset Safeguards**: Improved WebP EXIF UTF-16 offset slicing to prevent missed prompts; added byte-length integrity checks for resumable large model downloads; added automatic rollback protection for dataset pair renaming, temp-file cleanup for alpha flattening, and resolved a tagger rating concurrency race condition.
- **Memory-Sealed Frontend & UI Polish**: Sealed stripped web assets inside the native compiled cryptographic vault for pure in-memory serving (zero plaintext HTML/CSS/JS left on disk); locked button line-height and min-height to eliminate subtle layout shifts during live fetch states.
- **Seamless Upgrade**: Run `hsMuse_V2.3_Setup.exe` over any existing installation to preserve 100% of your local data, custom presets, music, and external `models/` (`hsMuse_V2.3.exe` is for portable single-file use only).

---
# Changelog / 更新日志
## [V2.2] - 2026-11-28 (重大跨代重构版 / Major Generational Overhaul)

### 简体中文

**✦ 重大跨代升级与全面重构**
- **「一核双端」现代画廊界面与 1K~8K 全分辨率适配**：底层彻底重构为现代 WebView 桌面端 + 本地 HTTP WebUI 一体化同源架构，支持严格唯一窗口互斥（浏览器活跃时桌面端自动静音隐藏，右键托盘可一键切回桌面并无感续播）及网页端地址栏锚点同步；全新 4 套常驻皮肤（`暗夜` / `留白` / `落樱` / `沧澜`）0ms 乐观瞬切 + 12 套灵感配色 + 自定义主题色，配备全站物理弹簧滑动胶囊、`暗夜 ↔ 留白` 顶栏羽化昼夜掠影、识图顶栏「双核就绪」发光 LED 胶囊及 `Alt+1~4` 极速切页。
- **全新主打：双核离线识图反推（零内置模型轻量化架构）**：支持拖入、点选或 `Ctrl+V` 粘贴 PNG / WebP / JPEG 图像，**0ms 秒读**主流生图工具内嵌正负面提示词与采样参数（深度兼容复杂连线拼接节点、归零条件截断与工作流兜底解析）；外置 `models/tagger/` 支持 **本地 ONNX 标签词条反推**（自动嗅探 GPU 加速并零显存兜底 CPU，配备 4 档评级分布、可单击剔除/恢复的条形置信度排行、一键提取角色档案、送入清洗台及 2~5 张参考图提炼共性画风配方）；可选 **自然语言视觉大模型反推**（软件内支持 HuggingFace 官方源 / 国内 HF-Mirror 断点续传一键下载或夸克网盘获取，无独显亦可直连本地推理服务或云端视觉 API，支持 4 种描写风格、5 档篇幅、固定前后缀与标签锚点联合反推，卸载瞬间 **100% 清空显存**）。
- **全新主打：AI 训练集批量打标 & 数据体检工作台**：支持文件夹递归扫描、独立输出路径、4 种冲突模式（断点续跑跳过 / 覆盖 / 追加 / 前置）、触发词前置、角色 LoRA 外貌词剥离、颜文字豁免下划线转换、括号转义、参数自动记忆与完成后自动卸载模型，同步支持 **标准标签序列 `.txt`** 与 **英文自然语言 `.txt`** 双轨落盘；内置 **全库词频体检**（点击 `🔍` 反查对应图片、一键筛未标图、`Shift` 多选子集改标、图文逐张微调 `Ctrl+S` + 一键双语翻译核对）以及零依赖 **数据体检三件套**（坏图/低清/透明通道体检、透明底一键铺白/浅灰底、两阶段原子配对重命名）。
- **HTML5 原生流式背景音乐引擎**：彻底移除旧版系统接口与 30MB 体积限制，零后台线程流畅播放 `.mp3 / .wav / .flac / .m4a / .aac / .ogg / .opus` 及大体积无损音轨，支持四态切换（`🔁 / 🔀 / 🔂 / 🔇`）、长按 0.5 秒切歌、损坏自动跳过与双端防重音。
- **81 位双轨角色库、三大语法方言与数据中心扩容**：内置角色扩充至 **81 位双轨角色**（含原创角色「林听雪」，完整无损继承旧版存档），支持「词条文本 ↔ 权重编排」双向切换、6 套纯净美学基调、3 种通用输出语法方言（`标准标签` / `NovelAI` / `自然语言`）、独立 4 引擎双语对照翻译弹窗（Youdao / MyMemory / Google / 自定义 AI）、200 行批量清洗与权重剥离、对称双栏「云同步与数据中心」（GitHub Private Gist 漫游扩容至 **2,000 角色 / 80 词库 / 2,000 收藏 / 200 配方**）及 **5 种界面语言** 双端全同步。
- **无损覆盖升级与外置模型说明**：直接运行 `hsMuse_V2.2_Setup.exe`（`--onedir` 低误报目录架构）覆盖安装即可 **100% 保留原有个人数据、自建角色、词库与外置 `models/` 目录**（`hsMuse_V2.2.exe` 仅作绿色便携备用）；可选视觉模型包可前往 HuggingFace 仓库（`hshiKoi/hsMuse-models`）或国内夸克网盘获取。

---

### English

**✦ Major Generational Overhaul & New Features**
- **Unified "One-Core, Dual-Client" Gallery UI & 1K–8K Responsive Layout**: Rebuilt from the ground up into a unified WebView desktop + local HTTP WebUI architecture with strict single-window exclusivity (auto-muting and hiding the desktop client while the browser tab is active, with seamless tray-click restoration) and URL hash sync. Added 4 resident themes (*Night* / *Pure* / *Sakura* / *Cobalt*) with 0ms optimistic switching + 12 inspiration palettes + custom accent colors, spring-sliding pill tracks, a Day/Night feathered topbar sweep, a glowing "Dual-Core Ready" LED pill, and `Alt+1–4` instant tab switching.
- **Flagship Dual-Core Offline Image Tagger (Zero-Bloat External Architecture)**: Drag, select, or `Ctrl+V` PNG / WebP / JPEG images for **0ms full-chain metadata extraction** (supporting SD WebUI, NovelAI, and complex linked ComfyUI node graphs with workflow fallbacks). External `models/tagger/` powers **Local ONNX Tag Extraction** (auto GPU acceleration with zero-VRAM CPU fallback, 4-tier rating bars, clickable confidence filtering, 1-click Character Profile extraction, and multi-image Style Recipe distillation). Optional **Vision LLM Natural Captioning** supports in-app resumable downloads from HuggingFace (`hshiKoi/hsMuse-models`) or zero-VRAM connections to local/cloud OpenAI-compatible Vision APIs, offering 4 styles, 5 length presets, prefix/suffix wrapping, tag-anchor guidance, and **100% VRAM release on unload**.
- **Flagship AI Dataset Batch Captioning & Audit Workbench**: Supports recursive folder scanning, custom output paths, 4 conflict modes (Skip/Resume, Overwrite, Append, Prepend), trigger word prepending, character-LoRA appearance stripping, kaomoji-safe underscore handling, bracket escaping, persistent preferences, auto-unload on completion, and dual `.txt` export (**Standard Tags** + **English Natural Language**). Includes **Dataset Tag Frequency Audit** (`🔍` reverse image lookup, untagged filter, `Shift` multi-select batch editing, side-by-side image review with `Ctrl+S` + bilingual translation check) and a **Dataset Toolkit** (corrupt/low-res/alpha inspection, 1-click PNG background flattening, and 2-phase atomic pair renaming).
- **Native HTML5 Lossless Streaming BGM Engine**: Replaced legacy system audio APIs and removed the 30MB file size cap; streams `.mp3 / .wav / .flac / .m4a / .aac / .ogg / .opus` and large lossless tracks with zero background threads, 4-state cycling (`🔁 / 🔀 / 🔂 / 🔇`), hold-0.5s track skipping, corrupt-file auto-skip, and dual-client anti-overlap.
- **81 Dual-Track Characters, 3 Universal Syntax Dialects & Expanded Data Center**: Expanded built-in presets to **81 dual-track character profiles** (including OC *Lin Tingxue*, preserving all legacy saves) with `Tag Editor ↔ Weight Board` switching, 6 Pure Aesthetic Tones, 3 universal syntax dialects (`Standard Tags` / `NovelAI` / `Natural Language`), a standalone 4-engine bilingual translation popup (Youdao / MyMemory / Google / Custom AI), 200-line batch prompt cleaner & weight stripping, an expanded symmetrical Sync & Data Center (GitHub Private Gist sync up to **2,000 characters / 80 KBs / 2,000 favorites / 200 recipes**), and full 5-language dual-client parity.
- **Seamless Overwrite Upgrade & External Model Packaging**: Run `hsMuse_V2.2_Setup.exe` (`--onedir` low-false-positive installer) over any existing installation to preserve **100% of your local data, custom characters, knowledge bases, and external `models/`** (`hsMuse_V2.2.exe` is provided for portable single-file use only).

---

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
- **桌面端 + 本地 WebUI 实时同步 & 全套周边生态**：推荐优先点击顶栏【网页版】体验更流畅的大屏排版与实时词数统计；内置 1K~8K DPI 自适应、5 种界面语言（简/繁/英/日/韩）、4 款极简高定皮肤 + 12 套灵感色卡、四引擎翻译（Youdao / MyMemory / Google / 自定义 AI 大模型）、GitHub Private Gist 私有云跨机同步、本地离线备份/恢复、轻量本地 BGM 播放器，以及完整保留个人数据的软件内一键在线更新。

---

### English

**✦ Core Highlights**
- **Self-Growing Character Archive (Up to 500 Profiles)**: Ships ready out of the box with 51 curated anime, game & original starter presets. Create custom OCs with LoRA triggers and multi-outfit closets, use the built-in AI trait-extraction prompt, or let Live Fetch automatically discover, deduplicate, and archive new characters. Includes instant live search, canonical-outfit locking, and spatially separated Solo/Dual framing.
- **Customizable Modular Knowledge Bases (Up to 40 Packs · 500 Entries per Slot)**: Built on portable JSON packs, shipping with 9 high-density aesthetic packs + the dynamic *Muse Tide* pool. Visually edit across 10 structured slots, reorder packs, import AI-generated themes in seconds, share via drag-and-drop, and mix all custom packs seamlessly in All-KB Smart Mix.
- **4-Era Worldview Isolation (Era Lock) & Batch Production**: Separates *Modern*, *Eastern Fantasy (Xianxia)*, *Wabi-Sabi/Gothic*, and *Nature/Onsen* worlds to eliminate era clashes. Simultaneously outputs **8-level sorted Tag sequences** and **cinematic natural language prose**, with `{A|B}` wildcard syntax and up to 100 unique batch prompts per run.
- **Concurrent Live Inspiration Fetch & Batch Prompt Cleaner**: Races top-rated visual sources by rating (SFW / Sensual / R18) to feed curated tags into your offline pool. The Cleaner handles up to 200 lines per batch—stripping LoRAs, weights, quality filler, character traits, or base outfits (while preserving framing and expressions), converting between SFW/NSFW, and generating natural prose.
- **Desktop & Local WebUI Parity + Ecosystem Tools**: Click **[WebUI]** in the top bar for the smoothest widescreen workflow and live counters. Features 1K–8K DPI scaling, 5-language UI switching, 4 minimalist themes + 12 palettes, 4-engine translation (including custom OpenAI-compatible AI LLMs), zero-server GitHub Private Gist cloud sync, offline backup/restore, local BGM player, and in-app updates that preserve 100% of your local data.
