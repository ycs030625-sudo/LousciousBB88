# 双雪涛 写作风格 Skill 蒸馏项目

> 把双雪涛的创作风格和写作方法论蒸馏成可执行的 AI Skills

## 📖 项目概述

这是一个开源项目，采用 **RIA-TV++ 蒸馏方法论**，将当代著名作家双雪涛的创作特征、写作技法、灵感方法等，结构化地提取为 **12 个核心 AI Skill**。

### 为什么做这个项目？

- 📚 **知识留存**: 将作家的隐性知识显式化，让读者真正学会而不只是"读过"
- 🤖 **AI 赋能**: 让 Claude、ChatGPT 等 AI 工具能精准调用双雪涛的写作风格
- ✍️ **写作学习**: 帮助写作者理解和运用其冷峻、荒诞、寓言式的叙事技巧
- 🔄 **可复用**: 每个 Skill 独立、可组合、支持自动进化（接入 darwin-skill）

---

## 🎯 蒸馏成果

### 12 个核心 Skill

| # | Skill 名称 | 分类 | 描述 |
|---|-----------|------|------|
| 01 | 冷峻叙事 | 叙事技法 | 克制、精准、不煽情的叙述手法 |
| 02 | 荒诞现实主义 | 创意方法 | 将现实荒诞性与魔幻元素结合 |
| 03 | 象征与隐喻 | 修辞手法 | 精准、陌生化的比喻与象征运用 |
| 04 | 东北方言融入 | 语言特色 | 将地方口语融入现代文学 |
| 05 | 多线交织结构 | 结构设计 | 案件线 + 心理线的并行叙事 |
| 06 | 心理细致刻画 | 人物塑造 | 通过细节与沉默展现内心世界 |
| 07 | 小人物原型 | 人物塑造 | 底层人物的坚韧、孤独、尊严 |
| 08 | 时间结构创新 | 结构设计 | 倒叙、插叙、并行的时间处理 |
| 09 | 细节与伏笔 | 叙事技巧 | 早期细节在后期产生爆发意义 |
| 10 | 灵感观察法 | 创意方法 | 从日常观察中发现故事与人物 |
| 11 | 冷幽默运用 | 语气与风格 | 沉重中的黑色幽默、荒诞感 |
| 12 | 东北城市书写 | 地域特色 | 工业衰落城市的意象与隐喻 |

---

## 📁 项目结构

```
shuang-xuetao-skill/
├── README.md                          ← 你在这里
├── WRITER_OVERVIEW.md                 ← 阶段 0: 作家整体理解
├── SKILL.md                           ← 元 skill 定义与执行规范
├── methodology/                       ← 6 阶段执行方法论
│   ├── 00-overview.md
│   ├── 01-stage0-analysis.md
│   ├── 02-stage1-extract.md
│   ├── 03-stage1.5-verify.md
│   ├── 04-stage2-ria.md
│   ├── 05-stage3-link.md
│   └── 06-stage4-test.md
├── extractors/                        ← 5 个并行提取器 prompt
│   ├── style-extractor.md
│   ├── theme-extractor.md
│   ├── narrative-extractor.md
│   ├── character-extractor.md
│   └── creative-method-extractor.md
├── templates/                         ← 生成文件的模板
│   ├── SKILL.md.template
│   ├── INDEX.md.template
│   └── test-prompts.json.template
├── candidates/                        ← 阶段 1: 候选单元池
│   ├── styles.md
│   ├── themes.md
│   ├── narrative-techniques.md
│   ├── characters.md
│   └── creative-methods.md
├── rejected/                          ← 阶段 1.5: 被淘汰的候选 + 原因
│   └── rejected-candidates.md
├── skills/                            ← 阶段 2-4: 最终 Skills
│   ├── 01-cold-narrative/
│   │   ├── SKILL.md
│   │   └── test-prompts.json
│   ├── 02-absurd-realism/
│   │   ├── SKILL.md
│   │   └── test-prompts.json
│   ├── ... (其他 10 个 skills)
│   └── 12-northeast-writing/
│       ├── SKILL.md
│       └── test-prompts.json
├── INDEX.md                           ← 阶段 3: Skill 导航与引用图
└── LICENSE                            ← MIT License
```

---

## 🚀 如何使用这些 Skills？

### 方式 1：在 Claude Code 中使用

1. 打开 [Claude Code](https://code.claude.com/)
2. 上传 `skills/` 文件夹中的任意 SKILL.md
3. 告诉 Claude："使用这个写作 skill，帮我改进我的小说开头"
4. Claude 会激活该 skill，应用相应的写作技法

### 方式 2：在 Cursor 编辑器中集成

1. 将 `skills/` 文件夹复制到项目根目录
2. 在 `.cursor-rules` 中引用相关 SKILL.md
3. 开始写作时，Cursor 会自动应用双雪涛风格的建议

### 方式 3：学习参考

1. 按推荐顺序（见 INDEX.md）逐个阅读 SKILL.md
2. 每个 skill 包含原文引用、方法论、可执行步骤
3. 根据 A2（触发场景）判断何时应用该技法

### 方式 4：自动进化

1. 使用 [darwin-skill](https://github.com/alchaincyf/darwin-skill)
2. 所有 skill 都配备 `test-prompts.json`（darwin 兼容格式）
3. darwin 会自动优化每个 skill 的触发精准度

---

## 📖 蒸馏方法论：RIA-TV++

### 6 个执行阶段

```
阶段 0: 整体理解 (Adler 分析)
   ↓ WRITER_OVERVIEW.md
阶段 1: 5 维度并行提取
   ↓ candidates/ (5 个文件)
阶段 1.5: 三重验证筛选
   ↓ skills/ (12 个通过的单元)
阶段 2: RIA++ 构造 Skill
   ↓ SKILL.md (6 段结构)
阶段 3: Zettelkasten 链接
   ↓ INDEX.md + 引用图
阶段 4: 压力测试
   ↓ test-prompts.json (包含诱饵)
```

### RIA++ 的含义

- **RIA** = Reading / Interpretation / Appropriation (赵周的便签拆书法)
- **TV** = Triple Verification (三重验证)
- **++** = E (Execution) + B (Boundary)

### 三重验证标准

✅ **V1 跨域验证**: 在双雪涛多部作品中都出现过吗？  
✅ **V2 预测力测试**: 能预测其未来作品风格吗？  
✅ **V3 独特性检验**: 这是他独有的特征吗？  

---

## 💡 核心 Skill 的 6 段结构

每个 SKILL.md 包含：

```markdown
# R — 原文 (Reading)
从双雪涛作品中直接引用 ≤150 字

# I — 方法论骨架 (Interpretation)
用自己的话重写，5-15 行

# A1 — 书中应用 (Past Application)
在《平原上的摩西》《飞行家》《猎人》中的具体表现

# A2 — 触发场景 ★ (Future Trigger)
何时应该运用这个 skill？包含语言信号

# E — 可执行步骤 (Execution)
1-2-3 步骤，每步有完成标准

# B — 边界与局限 (Boundary)
什么时候不适用？作者的盲点是什么？
```

---

## 📚 参考作品

本项目主要分析以下双雪涛代表作：

- **《平原上的摩西》** — 中篇，已改编电影（周冬雨主演）
- **《飞行家》** — 短篇集，含《刺杀小说家》原著
- **《猎人》** — 短篇集，11 篇作品
- **《翅鬼》** — 长篇，早期代表作
- **《聋哑时代》** — 成长小说
- **《天吾手记》** — 长篇，虚实交织

---

## 🔗 生态关系

本项目是更大 Skill 生态的一部分：

- [nuwa-skill](https://github.com/alchaincyf/nuwa-skill) — 蒸馏人（思维方式、表达 DNA）
- **shuang-xuetao-skill**（本项目）— 蒸馏作家的写作风格和方法论
- [darwin-skill](https://github.com/alchaincyf/darwin-skill) — 进化任意 skill

三者咬合：nuwa 蒸馏人，cangjie/shuang 蒸馏书籍与作家，darwin 让它们持续进化。

---

## ✅ 质量标准

所有 skill 必须通过：

- ✅ 三重验证（V1+V2+V3）
- ✅ 完整的 R/I/A1/A2/E/B 六段
- ✅ 原文引用 ≤150 字/段
- ✅ 完整的 test-prompts.json（包含诱饵测试）
- ✅ 明确的 trigger 条件（不能"一个关于 X 的 skill"）

不通过的候选进入 `rejected/` 文件夹，保留审计轨迹。

---

## 🎓 学习路径

### 新手入门
1. 读 `WRITER_OVERVIEW.md` — 理解双雪涛的整体风格
2. 阅读 `INDEX.md` — 了解 12 个 skill 的关系
3. 从推荐顺序开始，逐个学习 skill

### 进阶研究
1. 查看 `candidates/` — 了解哪些内容被提取、如何筛选
2. 查看 `rejected/` — 理解为什么某些候选被淘汰
3. 研究 `methodology/` — 学习 RIA-TV++ 的完整方法论

### 实战应用
1. 选择对应的 SKILL.md
2. 按照 A2（触发场景）识别何时应用
3. 按照 E（执行步骤）进行创作
4. 检查 B（边界）确保不滥用

---

## 📝 贡献指南

欢迎改进和扩展！

- 发现新的写作特征？提交 Issue
- 有更好的案例说明？提交 PR
- 发现 test-prompt 不准？反馈问题

---

## 📄 License

MIT License — 自由使用、修改、分发，注明出处即可

---

## 📞 联系与反馈

- GitHub Issues — 提问、反馈、建议
- Discussions — 讨论如何运用这些 skills

---

**最后更新**: 2026-06-25  
**版本**: 0.1.0（初版）  
**状态**: 完成阶段 0-4 蒸馏，所有 12 个 skill 已产出

---

## 🙌 致谢

感谢：
- 双雪涛的精彩创作为这个项目提供了素材
- [cangjie-skill](https://github.com/kangarooking/cangjie-skill) 提供的 RIA-TV++ 方法论
- 所有参与评审、测试的贡献者

