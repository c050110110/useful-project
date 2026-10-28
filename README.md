# useful-project

个人维护的实用 Agent Skills 集合。

## Skills

### plan-reviewer

对已经形成的技术、机器人与硬件、科研、管理或业务方案进行多视角审查，同时输出证据化审查报告和完整修订建议版。

它仅在明确调用 `$plan-reviewer`、点名 `plan-reviewer`，或明确要求“审查/评审方案”时使用，不会因普通的计划制定或讨论自动触发。

安装到 Codex：

```bash
mkdir -p ~/.codex/skills
cp -R skills/plan-reviewer ~/.codex/skills/
```

建议在安装后开启一个新对话，以确保 Skill 被重新发现。
