---
name: video-script-creator
version: 3.0.0
description: >
  视频脚本创作工作台（深度集成星球研究所/桢公子方法论 + 5 种 fallback 风格）。
  支持完整 / 快速 / 评估 3 种调用模式，覆盖地理 / 人文 / 科技 / 工程类视频脚本创作。
tags: [video, script, science-communication, xingqiu, china, copywriting]
mode: agentic
---

# Video Script Creator v3

> **核心流程文档（≤300 行）**。详细规则见 [`PRINCIPLES.md`](./PRINCIPLES.md) 和 [`QUALITY.md`](./QUALITY.md)。

---

## 0.0 不适用场景（遇到请拒绝或换工具）

| 不适用 | 替代方案 |
|--------|---------|
| 纯娱乐 / 段子 / 鬼畜视频 | 用通用创作助手 |
| 直播带货 / 抖音种草脚本 | 用电商脚本 skill |
| 政企宣传片 / 主旋律纪录片 | 合规边界不同，本 skill 不保证通过审查 |
| 学术论文 / 期刊文章 | 用论文写作 skill |
| ≤2 分钟纯搞笑短片 | 星球所风格不匹配，建议纯文案 |
| 用户没给任何主题 | 拒绝并请用户提供 |

---

## 0.1 灵魂四问（启动必问 4 个）

| # | 问题 | 目的 |
|---|------|------|
| 1 | **主题是什么？** | 锁定选题 |
| 2 | **必须包含哪些元素？**（≥1 个，建议 2-3 个） | 锁定"三连接"输入 |
| 3 | **已有想法 / 风格倾向？** | 触发 fallback 或确认默认 |
| 4 | **视频时长 + 方案数？**（默认 10 分钟 + 3 套） | 锁定输出规格 |

> 💡 **不要问超过 4 个问题**。其余需求（受众 / 客户 / 风格）由撰稿人用 `0.2 内部反思检查表` 自行对齐。

---

## 0.2 内部反思检查表（撰稿人自查，**不要问用户**）

完成灵魂四问后，开始 Phase 1 之前，自己反思：

- [ ] **客户端**：这次是纯科普、商务合作、还是企业宣传？商务的话客户边界在哪？
- [ ] **受众端**：能用 1 句话说清"目标观众是谁 / 已知道什么 / 想看什么"吗？
- [ ] **整体故事**：脑中有"故事风格"方向了吗？（层层递进 / 反向设问 / 时间线 / 人物代际）
- [ ] **趣味要素**：列出 ≥3 个"可看性亮点"作为素材池。

任一项不清晰，回头补问用户；清晰了再进 Phase 1。

---

## 1. 三种调用模式

```
用户说"写一个关于 XXX 的视频脚本"   → 完整模式（默认）
用户说"给我 X 个钩子 / 方案 / 金句"  → 快速模式（→ references/mode-quick.md）
用户给方案说"帮我评估 / 优化"        → 评估模式（→ references/mode-evaluation.md）
```

不确定时，问用户："你想要完整脚本、快速创意、还是评估已有方案？"

---

## 2. 风格锚点选择（默认 vs Fallback）

| 模式 | 触发条件 | 锚点 | 详细 |
|------|---------|------|------|
| **默认** | 用户未指定风格 | 星球研究所 / 桢公子 | `references/style-xingqiu.md` |
| **Fallback 1** | 用户说"何同学 / 科技产品 / 工程师视角" | 何同学 | `references/style-fallback.md` |
| **Fallback 2** | 用户说"奇葩小国 / 硬核狠人 / 人物命运" | 小约翰可汗 | 同上 |
| **Fallback 3** | 用户说"段子 / 法理 / 价值观 / 张三" | 罗翔 | 同上 |
| **Fallback 4** | 用户说"工具评测 / 行业洞察 / 团队纪录片" | 影视飓风 Tim | 同上 |
| **Fallback 5** | 用户说"学者 / 严谨 / 亲身经历 / 课堂" | 汪品先 / 韩茂莉 | 同上 |

**关键规则**：星球所风格是"克制的底色"，其他 UP 主是"主笔法"。**选 1-2 位 UP 主作为主参考，星球所风格作为克制的底色**（来自 [`creator-database.md`](./references/creator-database.md) 终极提示）。

---

## 3. 温度参数（按场景配置）

| 场景 | 推荐温度 | 原因 |
|------|---------|------|
| 星球所风格科普 | 0.7 | 允许隐喻 + 克制 |
| 商务项目（人文化包装） | 0.5 | 更克制，避免过度联想 |
| 反常识爆款 | 0.85 | 鼓励金句和强对比 |
| 学者派 / 严谨向 | 0.3 | 数据和事实为主 |
| 短平快短视频 | 0.85 | 节奏快、情绪烈 |

> 默认 0.7。商务项目 / 学者派 / 反常识场景必须显式调整。

---

## 4. 六阶段完整流程

```
   [灵魂四问 + 内部反思]
              ↓
Phase 1 · 创作者风格研究            [≥5 位 UP 主技法级洞察]
              ↓
Phase 2 · 事实深度研究              [≥15 事实元素 + 可追溯来源]
              ↓
Phase 3 · 风格-事实合成             [识别 3-5 个连接点 + 候选方向]
              ↓
Phase 4 · 多方案生成                [3 套方案 + 对比矩阵 + 个人推荐]
              ↓
Phase 5 · 深化选定方案              [五阶段情绪弧线 + 三连接 + 锚定句 + 生产指导]
              ↓
Phase 6 · 交付                      [Markdown → HTML / DOCX]
```

### Phase 1 · 创作者风格研究
- 必含：星球研究所 + 1-2 位 fallback 风格 UP 主 + 至少 1 位"反向参考"UP 主
- 输出：每位 UP 主的"定位 / 钩子 / 主线 / 金句 / 风险"5 维分析
- 详见 [`creator-database.md`](./references/creator-database.md)

### Phase 2 · 事实深度研究
- 必含：硬数据（≥10 个）+ 人物故事（≥3 个）+ 地理 / 语境 + 技术 / 领域
- 每个数字必须带可追溯来源（精确到文献 / 论文 / 报告 / 官方）
- 推荐用 Explore 子代理并行 3-5 个研究方向
- 详见 [`PRINCIPLES.md §事实优先`](./PRINCIPLES.md)

### Phase 3 · 风格-事实合成
- 识别"事实元素"×"UP 主笔法"的 3-5 个连接点
- 每个连接点要回答："用哪位 UP 主的笔法，讲哪个事实，能产生什么化学反应？"
- 输出：3 个候选方向（每方向 1-2 句话描述）

### Phase 4 · 多方案生成（核心交付物）
- 3 套方案，**必须彼此清晰可区分**（类型 / 钩子 / 主线 / 节奏都不同）
- 每套方案含 8 个部分：名称 / 类型命题 / 核心骨架 / 钩子段落 / 3 金句 / 文案大纲 / 画面建议 / 优劣分析
- 必出：对比矩阵（通用 + 商务专项 + 风格特色维度）+ 个人推荐
- 详见 [`proposal-template.md`](./references/proposal-template.md)

### Phase 5 · 深化选定方案
- 必含：
  - 层叠螺旋结构（5-6 层，每层有驱动问题 + 情感目标）
  - 五阶段情绪弧线（上扬 / 发展 / 下坠 / 回升 / 绵长）—— [`emotion-arc.md`](./references/emotion-arc.md)
  - 三连接规则（技术 / 物理 / 人物）—— [`three-connections.md`](./references/three-connections.md)
  - 锚定句（最后 30 秒，可截图转发）
  - 生产指导（拍摄 / 音乐 / 旁白 / 视觉）
  - 叙事模型图（Mermaid）
- 用 `assets/script-template.md` 模板填完整文案正文

### Phase 6 · 交付
- 必含：
  - 完整 Markdown 文档
  - 所有来源带可点击链接引用
  - 走 `html-report` 生成精美 HTML 版
  - 可选：走 `docx` 生成 Word 版

---

## 5. 模型选择指引

| 任务阶段 | 推荐模型 | 原因 |
|---------|---------|------|
| 灵魂四问 | lite 模型 | 简单问答 |
| Phase 1 创作者研究 | sonnet/opus | 需要大量先验知识 |
| Phase 2 事实研究 | sonnet | 需要细致搜索 + 交叉验证 |
| Phase 3-4 方案生成 | opus（按 §3 调温度） | 创意核心环节 |
| Phase 5 深化 | opus | 保持风格一致性 |
| Phase 6 交付排版 | sonnet | 模板填充为主 |

---

## 6. references 索引

| 文件 | 用途 | 调用时机 |
|------|------|---------|
| [`style-xingqiu.md`](./references/style-xingqiu.md) | 星球所 / 桢公子风格库（默认） | Phase 1 |
| [`style-fallback.md`](./references/style-fallback.md) | 5 种 fallback 风格体系 | Phase 1（fallback 触发时） |
| [`hook-formulas.md`](./references/hook-formulas.md) | 30 个钩子开头公式 | Phase 3-4 |
| [`emotion-arc.md`](./references/emotion-arc.md) | 五阶段情绪弧线 | Phase 5 |
| [`three-connections.md`](./references/three-connections.md) | 三连接规则 | Phase 4-5 |
| [`proposal-template.md`](./references/proposal-template.md) | 3 套方案 + 对比矩阵模板 | Phase 4 |
| [`creator-database.md`](./references/creator-database.md) | 10 位头部 UP 主笔法速查 | Phase 1 |
| [`quality-checklist.md`](./references/quality-checklist.md) | 三道审校关清单 | Phase 4-6 |
| [`mode-quick.md`](./references/mode-quick.md) | 快速模式使用说明 | 触发快速模式时 |
| [`mode-evaluation.md`](./references/mode-evaluation.md) | 评估模式使用说明 | 触发评估模式时 |
| [`errors-handling.md`](./references/errors-handling.md) | 异常处理文档 | 任何阶段 |
| [`case-template.md`](./references/case-template.md) | 案例模板（解耦） | 实战参考 |
| [`case-fujian-microgrid.md`](./references/case-fujian-microgrid.md) | 福建微电网完整案例 | 实战参考 |

**配套文档**：
- [`PRINCIPLES.md`](./PRINCIPLES.md) —— Show Don't Tell / 三连接 / 一句话 / 四字原则等创意原则
- [`QUALITY.md`](./QUALITY.md) —— 质量门 + 一票否决项 + 量化指标

**可复用资产**：
- [`assets/proposal-template.md`](./assets/proposal-template.md) —— 3 套方案模板（直接复制）
- [`assets/script-template.md`](./assets/script-template.md) —— 脚本正文模板（直接复制）

---

## 7. 星球研究所风格的"长期主义"标准

> 魏桢原话："我们创作的核心原则是解答基本问题，提出经典理念。让内容能够经得住时间的考验。"

**终极自检**：三年后、五年后、十年后再看这期视频，它还会让人想看第二遍吗？
- 是 → 通过
- 需更新数据 → 通过
- 热点过了就没意义 → 重做

详见 [`QUALITY.md §长期主义标准`](./QUALITY.md)。

---

## 8. 商务项目伦理底线

商务项目可以用"人文化包装"把产品融入故事，但必须遵守：

1. **产品是"自然发现的"**，不是"被推销的"（不要让观众感觉被广告）
2. **事实优先**，产品信息必须可验证
3. **客户边界优先于创作自由度**（合规模块用完一句话标注）

违反任一条 → 必须修改。

---

_v3.0.0 · 2026-06-17 · 主理人：GhostShadowTan_
