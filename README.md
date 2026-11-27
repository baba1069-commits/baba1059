# AI 编程 Skills / 项目清单

按视频出现顺序整理。链接为官方仓库；标注「待确认」的条目同名项目较多，请对照视频核对。

| # | 名称 | 仓库 | 一句话说明 |
|---|------|------|-----------|
| 1 | VoiceStudio | [debpalash/VoiceStudio](https://github.com/debpalash/VoiceStudio) | 本地优先的开源语音工作室（ElevenLabs 替代）：声音克隆、视频配音、听写、有声书 |
| 2 | security-audit | [cloudflare/security-audit-skill](https://github.com/cloudflare/security-audit-skill)（待确认） | 多 Agent 的仓库安全审计 skill，六阶段流程 + 独立复核 |
| 3 | Matt Pocock Skills | [mattpocock/skills](https://github.com/mattpocock/skills) | Matt Pocock 的 skill 合集，核心是 `grill-me` |
| 4 | Orca | [stablyai/orca](https://github.com/stablyai/orca) | 多 Agent 桌面 IDE，每个 Agent 在独立 git worktree 中并行工作 |
| 5 | T3 Code | [pingdotgg/t3code](https://github.com/pingdotgg/t3code) | Theo 团队出品的 Agent 控制台：桌面 / Web / 手机统一管理本机的 Claude Code、Codex 等 |
| 6 | Impeccable | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | 前端设计 skill，`/impeccable` 下有 audit、polish、critique 等子命令 |
| 7 | Hallmark | [Nutlope/hallmark](https://github.com/Nutlope/hallmark) | 反 AI 味（anti-slop）设计 skill，支持 audit / redesign / study |
| 8 | agent-desktop | [vercel-labs/agent-desktop](https://github.com/vercel-labs/agent-desktop)（待确认） | 让 Agent 通过系统无障碍树操控桌面应用的 CLI，无需截图 |
| 9 | HyperFrames | [heygen-com/hyperframes](https://github.com/heygen-com/hyperframes) | HeyGen 开源框架：用 HTML/CSS/动画渲染出确定性的 MP4 视频，专为 Agent 设计 |
| 10 | taste-skill | [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) | 反 AI 味前端设计 skill，可调 VARIANCE / MOTION / DENSITY 三个参数 |

## 安装与要点

### 1. VoiceStudio
- 提供 macOS / Windows / Linux / Docker 版本，见仓库 Releases；也可用 Bun 从源码运行。
- 默认引擎 OmniVoice，支持 600+ 语言；仓库自带 `voicestudio` skill，可通过 REST API 或 MCP 调用（需先启动 VoiceStudio 后端）。
- 许可证 AGPL-3.0。前身叫 OmniVoice Studio。注意 PyPI 上的 `voicestudio` 包是另一个无关项目。

### 2. security-audit
- 同名项目很多。最常被推荐的是 Cloudflare 的版本，其他选择：
  - [trailofbits/skills](https://github.com/trailofbits/skills)：Semgrep 规则、变体分析等专项
  - [zm2231/z-audit](https://github.com/zm2231/z-audit)：七阶段（密钥、API 鉴权、IDOR、基础设施…）
  - [McGo/claude-code-security-audit](https://github.com/McGo/claude-code-security-audit)：按类别审计，可出 PDF 报告
- Claude Code 自带 `/security-review` 命令，可审查当前分支的改动。
- 第三方安全 skill 安装前务必先读一遍 SKILL.md，部分变体被扫描器标为高风险。

### 3. Matt Pocock Skills（grill-me）
```bash
npx skills add https://github.com/mattpocock/skills --skill grill-me
```
- Claude Code 中也可装整个插件：`mattpocock-skills@claude-plugins-official`。
- `grill-me`：在动手前对你的计划 / 设计进行"拷问式"追问，沿决策树逐个分支问到底，直到双方理解一致。
- `grill-with-docs`：同上，额外产出文档。

### 4. Orca
- 并排运行 Claude Code、Codex、OpenCode，每个 Agent 各占一个 worktree，互不冲突，diff 清晰。
- 内置源码管理、GitHub PR / Actions 关联、SSH 远程、内嵌浏览器（Design Mode）、CLI、手机通知。
- 支持 macOS / Windows / Linux，可用 Homebrew 或 AUR 安装。MIT 许可。

### 5. T3 Code
```bash
npx t3@latest
```
- 桌面版可从 GitHub Releases、winget、Homebrew、AUR 获取。
- 可驱动 Codex、Claude Code、Cursor、Grok、OpenCode。README 自称"非常早期，预期会有 bug"。

### 6. Impeccable
```bash
npx skills add https://github.com/pbakaus/impeccable --skill impeccable
# 或在 Claude Code 中：
/plugin marketplace add pbakaus/impeccable
```
- 基于 Anthropic 的 frontend-design skill 扩展，含间距、网格、层级、动效、响应式等参考指南。Apache-2.0。

### 7. Hallmark
```bash
npx skills add https://github.com/nutlope/hallmark --skill hallmark
```
- 默认：新建 UI，选定宏观结构并跑"slop 测试"
- `hallmark audit <目标>`：按反模式打分，只给问题清单不改代码
- `hallmark redesign <目标>`：保留文案、信息架构和品牌，重做结构
- `hallmark study <截图|URL>`：从参考设计中提取风格

### 8. agent-desktop
```bash
npm install -g agent-desktop      # 或 brew install agent-desktop
agent-desktop permissions --guide
agent-desktop snapshot --app Finder -i
```
- 读取系统无障碍树，给元素分配稳定引用（`@e1`、`@e2`…），比截图点击更确定。
- 支持 macOS 13+、Windows 10 1809+、Ubuntu 24.04+。macOS 需授予"辅助功能"权限。
- 另有同名项目 [lahfir/agent-desktop](https://github.com/lahfir/agent-desktop)（Rust，思路相同），请按视频确认是哪个。

### 9. HyperFrames
```bash
npx skills add heygen-com/hyperframes --full-depth --yes
npx hyperframes preview my-video.html
npx hyperframes render my-video.html --output my-video.mp4
```
- skill 教会 Agent 完整流程：规划 → 写 HTML → 接入可 seek 的动画 → 加素材 → lint → 预览 → 渲染。Apache-2.0。

### 10. taste-skill
```bash
npx skills add https://github.com/Leonxlnx/taste-skill --skill "design-taste-frontend"
```
- 默认 v2（实验版）会先读需求、推断设计语言再调三个参数；需要旧行为用 `design-taste-frontend-v1`。
- 还有面向 GPT/Codex 的 `gpt-taste`、面向 Google Stitch 的 `stitch-design-taste` 等变体。

---

> 星标数、版本号变化很快，以上以各仓库 README 为准。
