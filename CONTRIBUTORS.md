# CONTRIBUTORS · 协作者名册与签名约定

> 本文件是协作者身份与提交签名的**唯一权威**（2026-10-13 立）。[AGENTS.md](AGENTS.md) 只保留指向本文件的链接，不重复维护内容，避免两处漂移。
> **新协作者（含 AI）第一件事：读本文件，按名册设置身份，再开始提交。**

## 为什么有这份文件

多个 AI 协作者共用同一个 Git 凭证（`gethlx`）与同一个 GitHub 账号，**默认无法从提交或 issue 判断是谁干的**。2026-10-13 实测：main 最近 12 笔提交作者全为 `gethlx`；PR #3 作者名为"老邪"（设了），PR #7 为默认 `gethlx`（没设）；GitHub issue／PR 侧信为零。后果：复核时认错干活的 bot、出错时找不到该复盘的人、功劳与责任都落不下。

## 名册

| 协作者 | 底层／位置 | Git `user.name` | Git `user.email` | 提交 trailer | Issue／PR 签名行 |
|---|---|---|---|---|---|
| 军师 | WorkBuddy，本机 Mac | `WorkBuddy 军师` | `workbuddy-junshi@users.noreply.github.com` | `Agent: workbuddy-junshi` | `> 提交者：军师（WorkBuddy，本机）` |
| 老邪 | Grok bot，云端 | `老邪 (Grok)` | `laoxie-grok@users.noreply.github.com` | `Agent: grok-laoxie` | `> 提交者：老邪（Grok bot，云端）` |
| GPT | Codex，云端 | `GPT (Codex)` | `gpt-codex@users.noreply.github.com` | `Agent: gpt-codex` | `> 提交者：GPT（Codex，云端）` |
| 晶晶 | 人，本机 Mac | `gethlx` | （保持现有设置） | `Agent: human-jingjing` | `> 提交者：晶晶` |

邮箱使用 `@users.noreply.github.com` 仅作**标签**，不指向真实账号、不会关联 GitHub 个人页；若你已有惯用邮箱，可换用，但必须与名册一致且不与 `gethlx` 混淆。

## 三层信号（齐用，双写兜底）

**1. Git 身份**（决定提交作者）。在自己工作副本执行一次：

```bash
git config user.name "<名册中的 user.name>"
git config user.email "<名册中的 user.email>"
```

**2. 提交 trailer**（写在提交信息末尾的独立行，机器可读）：

```
Agent: workbuddy-junshi
```

全库查询：

```bash
git log --format='%h | %an | %(trailers:key=Agent,valueonly) | %s'
```

**忘设 git 身份时，trailer 仍可追溯；反之亦然**——所以两层都要写，互为兜底。

**3. Issue／PR 签名行**（正文首行或末行，固定格式）：

```
> 提交者：老邪（Grok bot，云端）
```

GitHub 网页直接可见，`gh api` 可抓取；这是 GitHub 侧唯一的来源信号。

## 请老邪与 GPT 立即执行（2026-10-13）

- [ ] 按上方名册在自己的工作副本执行两条 `git config`
- [ ] 之后每次提交信息末尾加自己的 trailer
- [ ] 之后每个 issue／PR 正文加自己的签名行
- [ ] PR 分支沿用各自前缀（`laoxie/`、`gpt/`），便于第二重识别

军师（WorkBuddy）侧已由 [AUTOMATION.md](AUTOMATION.md) 第7步强制带身份与 trailer；每周定时任务的提交无需人工干预。**复核时军师将按 trailer 抽查，未登记者提交会在复核报告中点名。**

## 旧提交归属追溯（2026-10-13 由主公确认）

| 批次 | 实际协作者 |
|---|---|
| 2026-10-13 上午：issue #4–#14、PR #3／#7、分支 `laoxie/*` | **老邪（Grok bot）** |
| 2026-10-01 审核轮、issue #1／#2、`reports/2026-10-01-审核与纠正报告.md` 与 `reports/2026-10-05-research-周更新复核.md` | **GPT（Codex）** |
| main 其余提交（含全部 `weekly-market:`／`weekly-research:` 与修复批次） | **军师（WorkBuddy）或每周定时任务** |
| 2026-10-01 之前的提交 | 无法区分，不再追溯 |

## 新增协作者

先在名册登记——名称、底层模型、运行位置、Git 身份、trailer、签名行、允许写入范围——再开始提交。**未登记者不得提交。**

## 相关

- 协作流程与分支规则：见 PR #3 拟新增的 `CONTRIBUTING.md`（合并后应链接本文件，不重复名册）。
- 每周任务写入边界与提交要求：[AUTOMATION.md](AUTOMATION.md)。
- 证据判定规则：[VETTING.md](VETTING.md)。
