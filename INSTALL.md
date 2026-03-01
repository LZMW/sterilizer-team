# Sterilizer Team (净化战队) - 安装指南

**版本**：v3.0
**安装类型**：本机安装（无备份）
**配置包位置**：`N:\编程备份\3.0团队\sterilizer-team`

---

## 📋 安装概述

本指南将帮助您完成 Sterilizer 团队的本机安装，无旧版本备份。

**安装内容**：
- 1个协调器Skill（sterilizer-coordinator）
- 6个专家Agent（Alpha, Scrub, Probe, Pulse, Canvas, Beacon）

**目标路径**：
- Skill: `C:\Users\Mr.Chen\.claude\skills\sterilizer-coordinator\`
- Agents: `C:\Users\Mr.Chen\.claude\agents\sterilizer-*.md`

---

## 🚀 快速安装（一键脚本）

### Windows (Git Bash / WSL)

```bash
# 设置变量
TEAM_DIR="N:/编程备份/3.0团队/sterilizer-team"
SKILL_DEST="$HOME/.claude/skills/sterilizer-coordinator"
AGENT_DEST="$HOME/.claude/agents"

# 安装协调器Skill
echo "安装 sterilizer-coordinator Skill..."
mkdir -p "$SKILL_DEST"
cp "$TEAM_DIR/skills/sterilizer-coordinator/skill.md" "$SKILL_DEST/"

# 安装专家成员
echo "安装专家成员..."
cp "$TEAM_DIR/agents/sterilizer-alpha.md" "$AGENT_DEST/"
cp "$TEAM_DIR/agents/sterilizer-scrub.md" "$AGENT_DEST/"
cp "$TEAM_DIR/agents/sterilizer-probe.md" "$AGENT_DEST/"
cp "$TEAM_DIR/agents/sterilizer-pulse.md" "$AGENT_DEST/"
cp "$TEAM_DIR/agents/sterilizer-canvas.md" "$AGENT_DEST/"
cp "$TEAM_DIR/agents/sterilizer-beacon.md" "$AGENT_DEST/"

# 验证安装
echo ""
echo "=== 安装验证 ==="
echo "Skill:"
ls -la "$SKILL_DEST/skill.md"
echo ""
echo "Agents:"
ls -la "$AGENT_DEST"/sterilizer-*.md
echo ""
echo "✅ 安装完成！"
```

---

## 📝 详细安装步骤

### 步骤1：安装协调器Skill

```bash
# 创建目录
mkdir -p "$HOME/.claude/skills/sterilizer-coordinator"

# 复制配置文件
cp "N:/编程备份/3.0团队/sterilizer-team/skills/sterilizer-coordinator/skill.md" \
   "$HOME/.claude/skills/sterilizer-coordinator/"

# 验证
ls -la "$HOME/.claude/skills/sterilizer-coordinator/skill.md"
```

**预期输出**：
```
-rw-r--r-- 1 Mr.Chen 197121 [大小] [日期] skill.md
```

### 步骤2：安装专家成员

```bash
# 复制所有成员配置
cp "N:/编程备份/3.0团队/sterilizer-team/agents/sterilizer-alpha.md" \
   "$HOME/.claude/agents/"
cp "N:/编程备份/3.0团队/sterilizer-team/agents/sterilizer-scrub.md" \
   "$HOME/.claude/agents/"
cp "N:/编程备份/3.0团队/sterilizer-team/agents/sterilizer-probe.md" \
   "$HOME/.claude/agents/"
cp "N:/编程备份/3.0团队/sterilizer-team/agents/sterilizer-pulse.md" \
   "$HOME/.claude/agents/"
cp "N:/编程备份/3.0团队/sterilizer-team/agents/sterilizer-canvas.md" \
   "$HOME/.claude/agents/"
cp "N:/编程备份/3.0团队/sterilizer-team/agents/sterilizer-beacon.md" \
   "$HOME/.claude/agents/"

# 验证
ls -la "$HOME/.claude/agents"/sterilizer-*.md
```

**预期输出**：
```
-rw-r--r-- 1 Mr.Chen 197121 [大小] [日期] sterilizer-alpha.md
-rw-r--r-- 1 Mr.Chen 197121 [大小] [日期] sterilizer-beacon.md
-rw-r--r-- 1 Mr.Chen 197121 [大小] [日期] sterilizer-canvas.md
-rw-r--r-- 1 Mr.Chen 197121 [大小] [日期] sterilizer-probe.md
-rw-r--r-- 1 Mr.Chen 197121 [大小] [日期] sterilizer-pulse.md
-rw-r--r-- 1 Mr.Chen 197121 [大小] [日期] sterilizer-scrub.md
```

---

## ✅ 安装验证

### 方法1：检查文件存在

```bash
# 检查Skill
echo "=== Skill 验证 ==="
[ -f "$HOME/.claude/skills/sterilizer-coordinator/skill.md" ] && echo "✅ Skill 已安装" || echo "❌ Skill 未安装"

# 检查Agents
echo ""
echo "=== Agents 验证 ==="
for agent in alpha scrub probe pulse canvas beacon; do
    file="$HOME/.claude/agents/sterilizer-$agent.md"
    if [ -f "$file" ]; then
        echo "✅ sterilizer-$agent"
    else
        echo "❌ sterilizer-$agent"
    fi
done
```

**预期输出**：
```
=== Skill 验证 ===
✅ Skill 已安装

=== Agents 验证 ===
✅ sterilizer-alpha
✅ sterilizer-scrub
✅ sterilizer-probe
✅ sterilizer-pulse
✅ sterilizer-canvas
✅ sterilizer-beacon
```

### 方法2：使用Glob工具验证

在 Claude Code 中执行：

```bash
# 列出Skill
Glob pattern: C:/Users/Mr.Chen/.claude/skills/sterilizer-coordinator/*

# 列出Agents
Glob pattern: C:/Users/Mr.Chen/.claude/agents/sterilizer-*.md
```

---

## 🔄 卸载（如需要）

如果需要卸载 Sterilizer 团队：

```bash
# 卸载Skill
rm -rf "$HOME/.claude/skills/sterilizer-coordinator"

# 卸载Agents
rm -f "$HOME/.claude/agents/sterilizer-alpha.md"
rm -f "$HOME/.claude/agents/sterilizer-scrub.md"
rm -f "$HOME/.claude/agents/sterilizer-probe.md"
rm -f "$HOME/.claude/agents/sterilizer-pulse.md"
rm -f "$HOME/.claude/agents/sterilizer-canvas.md"
rm -f "$HOME/.claude/agents/sterilizer-beacon.md"

echo "✅ 卸载完成"
```

---

## 🎯 首次使用测试

安装完成后，可以使用以下测试命令验证团队是否正常工作：

```
测试命令：帮我评估一下这个项目的规模
预期行为：协调器调用 sterilizer-alpha 执行项目扫描评估
```

---

## 📋 文件清单

安装后的文件结构：

```
C:\Users\Mr.Chen\.claude\
├── skills\
│   └── sterilizer-coordinator\
│       └── skill.md
└── agents\
    ├── sterilizer-alpha.md
    ├── sterilizer-scrub.md
    ├── sterilizer-probe.md
    ├── sterilizer-pulse.md
    ├── sterilizer-canvas.md
    └── sterilizer-beacon.md
```

---

## 🔍 故障排查

### 问题1：Skill 未生效

**症状**：触发协调器时无响应

**解决方案**：
1. 检查文件路径是否正确
2. 确认 skill.md 文件内容完整
3. 重启 Claude Code

### 问题2：Agent 未找到

**症状**：提示 "找不到 sterilizer-* agent"

**解决方案**：
1. 检查 agents 目录下是否有对应文件
2. 确认文件名格式正确（全小写，连字符分隔）
3. 检查文件 YAML frontmatter 是否正确

### 问题3：配置冲突

**症状**：与其他配置冲突

**解决方案**：
1. 检查是否有旧版本残留
2. 确认名称唯一性
3. 使用 Glob 工具列出所有 sterilizer 相关文件

---

## 📞 支持

如遇到问题，请检查：
1. 安装路径是否正确
2. 文件权限是否正确
3. YAML 格式是否正确
4. 配置包是否完整

---

**安装版本**：v3.0
**最后更新**：2026-03-01
**配置包位置**：`N:\编程备份\3.0团队\sterilizer-team`
