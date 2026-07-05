# AGENT.md

## 回复语言

- 始终使用中文回复用户。

## 项目定位

本仓库是从 `Ian Xiaohei Illustrations` 改造而来的 Codex 中文正文配图 Skill。

它的目标是帮助 AI Agent 为中文文章、帖子、博客、Notion 文档、方法论内容和工作流内容生成 16:9 横版正文配图。核心不是做通用插画或 PPT 信息图，而是把文章里的关键判断、流程、结构、状态或隐喻，转成一张纯白、手绘、怪诞但清爽的解释图。

默认视觉 IP 是“小猫”：一只圆脸、蓝灰短毛、琥珀眼、戴红色小龙虾钳子毛绒发箍的母蓝猫。小猫必须承担画面的核心动作，不能只是装饰。

## 目录说明

- `README.md`：面向使用者的项目介绍、安装方式、示例和注意事项。
- `NOTICE.md`：作者、归属和示例图片说明。
- `LICENSE`：MIT 许可证。
- `examples/`：对外展示的 prompt 和示例图片。
- `assets/`：根目录文档用资产，例如二维码。
- `ian-xiaohei-illustrations/`：真正需要复制到 Codex skills 目录的 Skill 包。
- `ian-xiaohei-illustrations/SKILL.md`：Skill 入口和主工作流。
- `ian-xiaohei-illustrations/agents/openai.yaml`：Skill 的展示名、描述和默认 prompt。
- `ian-xiaohei-illustrations/references/`：风格 DNA、小猫 IP、构图模式、prompt 模板和 QA checklist。

## 维护原则

- 保持这个仓库是 Skill 包，而不是应用项目；不要引入不必要的构建系统、前端框架或运行时依赖。
- 修改 Skill 行为时，优先更新 `ian-xiaohei-illustrations/SKILL.md` 和对应 `references/` 文件。
- 修改用户文档时，同步检查 `README.md`、`examples/prompts.md` 和 `NOTICE.md` 是否仍一致。
- 示例图片只用于风格校准；不要把旧案例写成必须复刻的模板。
- 所有说明应避免把风格讲成“商业插画”“PPT 信息图”“可爱卡通”。

## 风格规则

维护或扩展本 Skill 时，必须保留这些核心约束：

- 16:9 横版正文配图。
- 纯白背景，不要纸纹、米色、阴影、渐变或复杂背景。
- 黑色手绘线稿为主，少量红色、橙色、蓝色中文手写批注。
- 大量留白，主体通常占画面约 40%-60%。
- 一张图只表达一个核心动作、结构、状态或隐喻。
- 小猫必须参与核心动作。
- 不要正式流程图、复杂架构图、课程课件、商业 KV 或幼稚可爱风。
- 不要在图里写“Workflow / 流程图 / 系统架构图 / 常见坑 / 路线图”等类型标题。

## 生成资产约定

当用户要求实际生成图片时：

- 先根据文章或主题提炼认知锚点，再决定 shot list。
- 默认生成 4-8 张；短内容 1-3 张，长文也不要轻易超过 9 张。
- 每张图单独生成，不要拼成一张合集。
- 每张图只讲一个结构或隐喻。
- 生成后按 `ian-xiaohei-illustrations/references/qa-checklist.md` 检查。
- 工作区内的最终图片保存到 `assets/<article-slug>-illustrations/`。
- 命名使用有序、可读的英文短名，例如 `01-trust-bridge.png`。
- 不要覆盖已有资产，除非用户明确要求替换。

## 验证建议

这个仓库没有常规应用测试。改动后应至少检查：

- `README.md` 的安装和使用说明是否仍准确。
- `SKILL.md` 的触发描述和工作流是否清晰。
- `references/` 中的风格、prompt 和 QA 规则是否互相一致。
- 示例 prompt 是否仍能引导出“小猫怪诞正文配图”，而不是 PPT 或商业插画。

## 提交注意

- 保持文档文字简洁，避免过度解释。
- 不要删除作者署名、项目名和示例图片 attribution。
- 不要无关改动示例图片或二进制资产。
- 如果只是补充 Agent 说明，不需要改动 Skill 行为文件。
