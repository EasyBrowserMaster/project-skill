# Project Memory Skill

面向 Claude、Codex、Cursor、Gemini 等 AI Agent 的项目长期记忆 Skill。

本仓库根目录即 Skill 本体，克隆到 AI 工具的 skills 目录即可使用。

## 核心能力

* 建立项目级长期记忆目录 `.ai/`
* 记录项目规则、技术发现、决策、交接状态和失败方案
* 支持多个 AI Agent 在同一项目中共享上下文
* 避免重复分析已解决问题、重复尝试已失败方案
* 为长周期项目提供稳定的任务交接机制

## 快速使用

### 方式一：AI 对话框直接安装（推荐）

在你的 AI 编码工具（Cursor / Claude Code / Codex 等）的对话框中输入：

```
帮我安装下这个 skill：project-memory-skill
项目地址：https://github.com/EasyBrowserMaster/project-memory-skill
```

AI 会自动完成下载、配置，并在后续涉及项目记忆的任务中自动调用该 Skill。

### 方式二：手动安装

将本仓库克隆到对应 AI 工具的 skills 目录下。

> Windows 用户请用 PowerShell 命令；`~` 写法仅在 Git Bash / WSL / macOS / Linux 下能正确展开，在 PowerShell / cmd.exe 中会创建出名为 `~` 的目录。

**Cursor：**

macOS / Linux / Git Bash：
```bash
git clone https://github.com/EasyBrowserMaster/project-memory-skill.git ~/.cursor/skills/project-memory-skill
```

Windows（PowerShell）：
```powershell
git clone https://github.com/EasyBrowserMaster/project-memory-skill.git "$HOME\.cursor\skills\project-memory-skill"
```

**Claude Code（Codex CLI）：**

macOS / Linux / Git Bash：
```bash
git clone https://github.com/EasyBrowserMaster/project-memory-skill.git ~/.codex/skills/project-memory-skill
```

Windows（PowerShell）：
```powershell
git clone https://github.com/EasyBrowserMaster/project-memory-skill.git "$HOME\.codex\skills\project-memory-skill"
```

**VSCode（Copilot / Cline 等插件）：**

macOS / Linux / Git Bash：
```bash
git clone https://github.com/EasyBrowserMaster/project-memory-skill.git ~/.vscode/skills/project-memory-skill
```

Windows（PowerShell）：
```powershell
git clone https://github.com/EasyBrowserMaster/project-memory-skill.git "$HOME\.vscode\skills\project-memory-skill"
```

> 安装完成后，AI Agent 会自动读取 `SKILL.md` 获取项目记忆能力。当你需要为项目建立长期记忆、跨 Agent 共享上下文或交接任务时，Skill 会自动激活：先检查 `.ai/` 记忆文件，再开始分析或修改项目。

## 项目结构

```text
project-memory-skill/
├── SKILL.md
├── README.md
├── cases/
├── examples/
├── references/
├── scripts/
└── templates/
    └── ai-memory/
```

关键文件：

* `SKILL.md`：Skill 入口文件
* `references/project-memory-skill.md`：完整规则说明
* `templates/ai-memory/`：项目 `.ai/` 记忆目录模板
* `examples/basic-project-memory.md`：基础使用示例

## 适用场景

* 长周期研发项目
* 多 Agent 协作
* Claude、Codex、Cursor、Gemini 间切换
* 逆向工程、浏览器开发、MCP 项目等上下文密集型任务

## 版本记录

* 1.0.0：整理为可导入 Skill 包结构，增加模板、示例和安装说明。
