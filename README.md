# lohaaa Skills

lohaaa 的个人 Agent Skills 仓库。

## 软件需求交付工作流

`lohaaa-flow` 是一个覆盖需求分析、开发实施、验收和发布的多阶段技能。需求文件中的每个最小可交付单元都附带进度表，避免维护独立且容易失去同步的进度记录。

### 安装

列出仓库中的技能：

```bash
npx skills add lohaaa/skills --list
```

安装到当前项目：

```bash
npx skills add lohaaa/skills --skill lohaaa-flow
```

全局安装并跳过交互确认：

```bash
npx skills add lohaaa/skills --skill lohaaa-flow -g -y
```

也可以直接使用而不安装：

```bash
npx skills use lohaaa/skills@lohaaa-flow
```

## 能力范围

- 用通俗语言澄清需求本质、范围和完成标准
- 调研并比较常用方案与现代化方案
- 从最大需求集逐层拆分到页面或 API 单元
- 判断现有模块、新模块或独立项目边界
- 按官方规范、项目约定和 Clean Code 实施
- 执行页面、API 客户端或后端 API 的纵向交付
- 进行单元验收、模块验收及代码和页面质量检查
- 检查数据库、配置、基础设施、发布后操作和回滚路径

## 仓库结构

```text
skills/
└─ lohaaa-flow/
   ├─ SKILL.md
   ├─ references/
   │  ├─ 01-需求分析与方案设计.md
   │  ├─ 02-开发实施规范.md
   │  ├─ 03-验收与质量检查.md
   │  └─ 04-发布准备与上线.md
   └─ assets/
      └─ 需求文件模板.md
```

## 规范兼容

技能遵循 [Agent Skills 规范](https://agentskills.io/specification)，可通过 [Skills CLI](https://github.com/vercel-labs/skills) 从 GitHub 安装。

## 许可证

[MIT](LICENSE)
