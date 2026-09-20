# lohaaa Skills

lohaaa 的个人 Agent Skills 仓库。

## 软件需求交付工作流

`lohaaa-flows` 是四个独立 Agent Skills 的分组目录，不是一个统一技能。每个技能负责一个阶段，通过同一份需求文件衔接；需求文件中的每个最小可交付单元都附带自己的进度表。

### 阶段技能

| 技能 | 阶段 | 主要产出 |
|---|---|---|
| `lohaaa-plan` | 需求分析与方案设计 | 方案决策、模块边界、功能单元和需求文件 |
| `lohaaa-build` | 开发实施 | 已实现并实际验证、等待验收的功能单元 |
| `lohaaa-check` | 验收与质量检查 | 单元及模块验收结论、代码和页面质量结果 |
| `lohaaa-release` | 发布准备与人工交接 | 发布、迁移、人工生产验证和回滚清单；不执行生产操作 |

阶段顺序：

```text
lohaaa-plan → lohaaa-build → lohaaa-check → lohaaa-release
```

所有阶段只更新同一份需求文件，不建立独立进度表。验收失败时从 `lohaaa-check` 返回 `lohaaa-build` 修复，再重新验收。

`lohaaa-release` 不允许 AI 登录或操作生产环境，也不允许 AI 执行生产发布、迁移、回滚或生产验证。生产步骤必须由用户或授权操作人员执行，AI 只准备清单并记录人工提供的结果。

### 安装

列出仓库中的技能：

```bash
npx skills add lohaaa/skills --list
```

安装全部工作流技能：

```bash
npx skills add lohaaa/skills --skill lohaaa-plan --skill lohaaa-build --skill lohaaa-check --skill lohaaa-release
```

全局安装并跳过交互确认：

```bash
npx skills add lohaaa/skills --skill lohaaa-plan --skill lohaaa-build --skill lohaaa-check --skill lohaaa-release -g -y
```

也可以只安装或直接使用某个阶段：

```bash
npx skills add lohaaa/skills --skill lohaaa-plan
npx skills use lohaaa/skills@lohaaa-plan
```

## 仓库结构

```text
skills/
└─ lohaaa-flows/
   ├─ lohaaa-plan/
   │  ├─ SKILL.md
   │  └─ assets/
   │     └─ 需求文件模板.md
   ├─ lohaaa-build/
   │  └─ SKILL.md
   ├─ lohaaa-check/
   │  └─ SKILL.md
   └─ lohaaa-release/
      └─ SKILL.md
```

## 规范兼容

技能遵循 [Agent Skills 规范](https://agentskills.io/specification)，可通过 [Skills CLI](https://github.com/vercel-labs/skills) 从 GitHub 安装。

## 许可证

[MIT](LICENSE)
