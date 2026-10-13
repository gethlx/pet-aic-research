# 项目协作规范

- 每批项目文件或本项目定时任务配置的变更，必须在同批更新根目录 `导航账本.md`，记录对象、原因、实际验证和未完成事项；只读检查无需记账。
- 先读 `导航账本.md` 定位；执行定时任务以 `AUTOMATION.md` 为方法权威，证据判定以 `VETTING.md` 为准。账本用于导航与记录，不替代原始证据。
- 保留未知和来源自报属性。维护研究结论时明确区分论文报告、独立验证、产品可用性与商业表现。
- 定时任务的改动范围、共享目录写入保护及 Git 收尾边界统一见 `AUTOMATION.md`；普通维护按用户本轮授权执行，不自行提交、推送或触发定时任务。

## 协作者身份与签名约定（2026-10-13 立，主公确认）

多个 AI 协作者共用同一 Git 凭证（gethlx），**默认身份无法区分来源**（实测 2026-10-13：老邪在 PR #3 设了作者名"老邪"，PR #7 未设；军师与定时任务提交全部显示为 gethlx）。所有协作者提交时必须带可识别身份，三层信号建议齐用：

| 协作者 | 底层／位置 | Git `user.name` | 提交 trailer | Issue／PR 签名行 |
|---|---|---|---|---|
| 军师 | WorkBuddy，本机 Mac | `WorkBuddy 军师` | `Agent: workbuddy-junshi` | `> 提交者：军师（WorkBuddy，本机）` |
| 老邪 | Grok bot，云端 | `老邪 (Grok)` | `Agent: grok-laoxie` | `> 提交者：老邪（Grok bot，云端）` |
| GPT | Codex，云端 | `GPT (Codex)` | `Agent: gpt-codex` | `> 提交者：GPT（Codex，云端）` |
| 晶晶 | 人，本机 Mac | `gethlx` | `Agent: human-jingjing` | `> 提交者：晶晶` |

- Git 身份：各协作者在自己工作副本设 `git config user.name` 与 `user.email`（邮箱用 `<名>@users.noreply.github.com`，仅作标签，不指向真实账号）。
- Trailer：写在提交信息末尾独立行；机器可读查询 `git log --format='%h %(trailers:key=Agent,valueonly)'`。**忘设 git 身份时 trailer 仍可追溯**，反之亦然，故双写。
- Issue／PR：正文首行或末行固定签名行，网页与 `gh` 均可读。
- 追溯归属（2026-10-13 主公确认）：2026-10-13 上午的 issue #4–#14 与 PR #3／#7 为**老邪（Grok bot）**；2026-10-01 审核轮、issue #1／#2 及两份复核报告为 **GPT（Codex）**；main 其余提交为军师（WorkBuddy）或每周定时任务。更早提交无法区分，不再追溯。
- 新增协作者先在本表登记（名称、底层模型、位置、身份、trailer、允许写入范围）再开始提交。
