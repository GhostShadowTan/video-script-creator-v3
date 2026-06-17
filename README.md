# Video Script Creator

> **创意脚本导演工作台** —— 一个专业的视频脚本 / 短视频文案创作 skill。
> 以星球研究所（含桢公子监制作品）方法论为锚点，覆盖完整 6 阶段专业工作流。

![version](https://img.shields.io/badge/version-3.0.0-blue.svg)
![mode](https://img.shields.io/badge/mode-agentic-green.svg)
![license](https://img.shields.io/badge/license-MIT-lightgrey.svg)

---

## 这是什么

`video-script-creator` 是一个面向 **AI Agent / LLM 工作流** 的视频脚本创作 skill。它把"星球研究所"团队（创始人耿华军、监制魏桢/桢公子）多年沉淀的撰稿方法论拆解为可执行的工作流，让模型能够：

- 研究 ≥5 位头部创作者的笔法，提炼技法级洞察
- 做事实深度研究（硬数据 / 人物故事 / 地理语境 / 技术领域）
- 合成"风格-事实"配对，生成 ≥3 套差异化方案
- 用三连接规则、五阶段情绪弧线、一票否决项做质量把控
- 输出生产就绪的脚本（含拍摄 / 音乐 / 旁白 / 视觉指导）

适用场景：地理 / 人文 / 科技 / 工程类科普视频脚本、商务项目人文化包装、纪录片文案。

---

## 快速开始

### 3 种调用模式

| 模式 | 触发语 | 适合场景 |
|------|--------|---------|
| **完整模式** | "写一个关于 XXX 的视频脚本" | 新选题，从 0 到 1 |
| **快速模式** | "给我 X 个钩子 / 方案 / 金句" | 局部创意产出 |
| **评估模式** | "这是我的方案，帮我评估" | 已有方案，要打分 / 优化 |

默认进入**完整模式**。

### 最小调用示例

```
请按 video-script-creator skill 的完整模式，为我创作一个关于
"福建微电网"的视频脚本。
```

模型会自动走完 6 阶段：灵魂四问 → 创作者研究 → 事实研究 → 风格-事实合成 → 3 套方案 + 对比矩阵 → 深化选定方案。

---

## 安装

### 作为 WorkBuddy Skill

把 `video-script-creator-v3/` 整个目录放到你的 skills 目录下：

```bash
# WorkBuddy 默认 skills 路径
cp -r video-script-creator-v3 ~/.workbuddy/skills/video-script-creator
```

### 作为 GitHub 仓库

```bash
git clone https://github.com/<your-org>/video-script-creator.git
cd video-script-creator
```

### 作为 zip 包分发

直接解压 `video-script-creator-v3.zip` 即可，无外部依赖。

---

## 目录结构

```
video-script-creator-v3/
├── SKILL.md                       # 核心流程（≤300 行，调用入口）
├── PRINCIPLES.md                  # 创意原则（Show Don't Tell / 三连接等）
├── QUALITY.md                     # 质量门 + 一票否决项
├── README.md                      # 本文件
├── CHANGELOG.md                   # 版本变更日志
├── LICENSE                        # MIT 许可
├── references/                    # 12 个主题化参考文件（语义命名）
│   ├── style-xingqiu.md           # 星球研究所 / 桢公子风格库
│   ├── style-fallback.md          # 备选风格体系（何同学/小约翰/罗翔等）
│   ├── hook-formulas.md           # 30 个钩子开头公式
│   ├── emotion-arc.md             # 五阶段情绪弧线
│   ├── three-connections.md       # 三连接规则
│   ├── proposal-template.md       # 3 套方案 + 对比矩阵模板
│   ├── creator-database.md        # 10 位头部 UP 主笔法速查
│   ├── quality-checklist.md       # 三道审校关清单
│   ├── mode-quick.md              # 快速模式使用说明
│   ├── mode-evaluation.md         # 评估模式使用说明
│   ├── errors-handling.md         # 异常处理文档
│   ├── case-template.md           # 案例模板（解耦）
│   └── case-fujian-microgrid.md   # 福建微电网完整案例
└── assets/                        # 可直接复制的模板
    ├── proposal-template.md
    └── script-template.md
```

---

## 6 阶段完整流程

```
0. 灵魂四问（启动摸底）              [4 个必问 + 1 个内部检查表]
       ↓
1. 创作者风格研究                    [≥5 位 UP 主，技法级洞察]
       ↓
2. 事实深度研究                      [≥15 个事实元素，可追溯来源]
       ↓
3. 风格-事实合成                     [识别连接点 + 候选方向]
       ↓
4. 多方案生成                        [3 套方案 + 对比矩阵 + 个人推荐]
       ↓
5. 深化选定方案                      [五阶段情绪弧线 + 三连接 + 锚定句 + 生产指导]
       ↓
6. 交付                              [Markdown → HTML / DOCX]
```

详细见 [`SKILL.md`](./SKILL.md)。

---

## 设计原则

1. **方法论先行**：每支脚本必须先做创作者研究和事实研究，**禁止凭空创作**
2. **多方案而非一稿**：永远先给 ≥3 套方案对比，再深化选定
3. **风格可切换**：星球所是默认锚点，但支持 fallback 到何同学 / 小约翰 / 罗翔等
4. **可分发的工程化**：版本号、CHANGELOG、LICENSE、README 齐全
5. **模型友好**：核心流程 ≤300 行，关键决策路径前置

---

## 引用来源

- **星球研究所 / 桢公子方法论**：创始人耿华军、监制魏桢（桢公子）公开访谈
- **头部 UP 主笔法库**：B 站 2024/2025 百大 UP 主榜单 + 火烧云数据
- **经典作品参考**：《中国从哪里来？》《什么是成都》《什么是武汉》《100年，重塑山河》《为14亿人治理江河》《三江并流有多神奇？》

---

## 版本

当前版本：**v3.0.0**（2026-06-17）

历史版本：
- v2.0.0 — 增量更新（实质内容与 v1 相同）
- v1.0.0 — 初始版本（星球所 / 桢公子方法论 6 阶段工作流）

详见 [`CHANGELOG.md`](./CHANGELOG.md)。

---

## 贡献

欢迎通过 PR 提交：

- 新的创作者笔法分析
- 新的钩子公式
- 新的方案模板
- 新的案例（用 `case-template.md` 格式）
- 错误处理规则补充

---

## 许可

MIT License — 详见 [`LICENSE`](./LICENSE)。

---

## 维护者

- 作者：GhostShadowTan
- 联系：通过 GitHub Issues

---

_最后更新：2026-06-17_
