# Sterilizer 团队安装指南

## 前置条件

- Claude Code 已安装并正常运行
- 确认 `~/.claude/` 目录结构存在

## 安装步骤

### 步骤 1: 复制 Agent 配置

将 `agents/` 目录下的所有 `.md` 文件复制到 Claude Code 的 agents 目录：

```bash
# Windows (Git Bash)
cp -r sterilizer-team/agents/*.md ~/.claude/agents/

# macOS / Linux
cp -r sterilizer-team/agents/*.md ~/.claude/agents/
```

### 步骤 2: 复制 Skill 配置

将 `skills/sterilizer-coordinator/` 目录复制到 Claude Code 的 skills 目录：

```bash
# Windows (Git Bash)
cp -r sterilizer-team/skills/sterilizer-coordinator ~/.claude/skills/

# macOS / Linux
cp -r sterilizer-team/skills/sterilizer-coordinator ~/.claude/skills/
```

### 步骤 3: 验证安装

确认文件结构如下：

```
~/.claude/
├── agents/
│   ├── sterilizer-alpha.md
│   ├── sterilizer-scrub.md
│   ├── sterilizer-probe.md
│   ├── sterilizer-canvas.md
│   ├── sterilizer-pulse.md
│   └── sterilizer-beacon.md
└── skills/
    └── sterilizer-coordinator/
        └── skill.md
```

### 步骤 4: 重启 Claude Code

重启 Claude Code 以加载新的团队配置。

### 步骤 5: 测试触发

在 Claude Code 中输入以下命令测试：

```
/sterilizer-coordinator

# 或者直接描述任务
帮我对这个项目进行一次彻底的整理和审计
```

## 触发关键词

### 协调器触发

| 关键词 | 说明 |
|--------|------|
| `/sterilizer-coordinator` | 显式调用协调器 |
| 项目整理 | 项目环境整理流程 |
| 项目审计 | 代码审计流程 |
| 净化战队 | 触发团队 |
| SPARI | 触发SPARI工作流 |

### 各专家触发

| 专家 | 触发关键词 |
|------|------------|
| Alpha | 项目评估、规模判断、整理策略 |
| Scrub | 环境清理、文件归档、目录整理、零删除 |
| Probe | 代码审计、真伪验证、源码分析 |
| Canvas | 知识重构、文档体系、架构图 |
| Pulse | 进度追踪、TODO汇总、完成度 |
| Beacon | 导航构建、索引生成、说明文档 |

## 使用示例

### 1. 启动完整项目净化

```
用户: 我的项目很乱，文档也不全，帮我整理一下
协调器: 启动 Sterilizer 净化战队，开始SPARI全流程...
```

### 2. 单阶段调用

```
用户: 帮我清理一下项目根目录
协调器: 使用 sterilizer-scrub 专家执行环境净化...

用户: 帮我审计一下代码和文档的一致性
协调器: 使用 sterilizer-probe 专家进行代码审计...
```

### 3. 并行任务

```
用户: 同时帮我审计代码和追踪进度
协调器: 并行启动 sterilizer-probe 和 sterilizer-pulse...
```

## 故障排除

### 问题: 专家没有被触发

**解决方案**:
1. 确认 `.md` 文件在正确目录
2. 确认文件格式正确（frontmatter + 内容）
3. 重启 Claude Code

### 问题: 协调器技能未出现

**解决方案**:
1. 确认 `skill.md` 在 `~/.claude/skills/sterilizer-coordinator/` 目录
2. 确认 skill.md 的 frontmatter 格式正确
3. 检查 Claude Code 的 skills 日志

### 问题: 工具权限错误

**解决方案**:
1. 检查各专家的 `tools` 配置
2. 确认 MCP 服务器已正确配置

## 卸载

如需卸载，删除以下文件：

```bash
# 删除 agents
rm ~/.claude/agents/sterilizer-*.md

# 删除 skill
rm -rf ~/.claude/skills/sterilizer-coordinator
```

## 更新

更新时，重新执行安装步骤即可覆盖旧文件。
