---
read_when:
  - 你需要定时任务和唤醒功能
  - 你正在调试定时任务的执行和日志
summary: "`openclaw cron` 的 CLI 参考（调度和运行后台任务）"
title: cron
x-i18n:
  generated_at: "2026-02-01T19:58:49Z"
  model: claude-opus-4-5
  provider: pi
  source_hash: bc9317c824f3b6339df657cc269961d9b5f121da65ec2b23a07d454e6d611135
  source_path: cli/cron.md
  workflow: 14
---

# `openclaw cron`

管理 Gateway网关调度器的定时任务。

相关内容：

- 定时任务：[定时任务](/automation/cron-jobs)

提示：运行 `openclaw cron --help` 查看完整的命令列表。

说明：隔离式 `cron add` 任务默认使用 `--announce` 投递摘要。使用 `--no-deliver` 仅内部运行。
`--deliver` 仍作为 `--announce` 的弃用别名保留。

说明：一次性（`--at`）任务成功后默认删除。使用 `--keep-after-run` 保留。

## 常见编辑

更新投递设置而不更改消息内容：

```bash
openclaw cron edit <job-id> --announce --channel telegram --to "123456789"
```

为隔离任务禁用投递：

```bash
openclaw cron edit <job-id> --no-deliver
```
