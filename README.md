# 反思型文章写作助手（reflective-article-writer）

反思型文章写作助手技能：通过引导式对话帮助用户写深度反思类文章（周记、读后感、研究型文章、观点随笔），而非直接代写。写作前先确认优先目的（反思第一、吸引用户第二），再按周记/读后感/其他三类场景引导成文。

## 技能结构

```
reflective-article-writer/
└── SKILL.md          # 技能唯一必需文件（含 YAML frontmatter 元数据与完整指令）
```

## 一、安装到其他 Agent

技能的本质是一个包含 `SKILL.md` 的文件夹，几乎所有主流 Agent 都采用「复制文件夹到指定技能目录」的方式安装。以下按平台给出步骤。

### 1. 豆包（Doubao）桌面端

1. 左上角从「对话」切换到「工作」模式
2. 左侧栏点「技能 · 连接器 · 伙伴」
3. 打开「我的技能」，点右上角「+ 新建」→「上传技能」
4. 把 `reflective-article-writer.zip`（或解压后的技能文件夹）拖入即可
5. 回到对话框输入 `/`，从技能列表中选择「反思型文章写作助手」启用

> 另一种方式：直接在豆包对话框说「帮我安装 reflective-article-writer 技能」，豆包会从开源社区自动拉取安装。

### 2. Claude Code

```bash
# 全局安装（所有项目可用）
mkdir -p ~/.claude/skills/reflective-article-writer
# 将 SKILL.md 复制到上述目录

# 或项目级安装
mkdir -p .claude/skills/reflective-article-writer
cp SKILL.md .claude/skills/reflective-article-writer/
```

### 3. Cline

```bash
# Windows 全局：C:\Users\<用户名>\.cline\skills\reflective-article-writer\
# macOS/Linux 全局：~/.cline/skills/reflective-article-writer\
# 项目级：<项目>\.cline\skills\reflective-article-writer\
# 复制 SKILL.md 到对应目录即可，Cline 会自动发现
```

### 4. Cursor

```
<项目>\.cursor\skills\reflective-article-writer\SKILL.md
```

### 5. 其他兼容 Agent（Windsurf / Codex 等）

参照各自文档，把技能文件夹放入其 skills 扫描目录（常见为 `~/.agents/skills/`、`.windsurf/skills/`、`.codex/skills/` 等），或在支持 `npx skills add` 的环境下直接执行：

```bash
npx skills add reflective-article-writer   # 前提：已发布到 GitHub 仓库
```

## 二、发布到网上（平台与方式）

### A. 代码托管平台（发布主阵地，推荐）

| 平台 | 说明 | 建议 |
|---|---|---|
| GitHub | 全球技能生态中心，所有技能市场/收录列表都从这里抓取 | 首选，建一个仓库放技能文件夹 + README |
| Gitee 码云 | 国内访问快，无需翻墙 | 同步一份，方便国内用户 |
| GitLab | 企业/自托管场景 | 可选 |

**GitHub 发布步骤**：
1. 注册/登录 GitHub → New repository（如 `reflective-article-writer`）
2. 上传技能文件夹 + 本说明文档（改名为 README.md）
3. 选择开源协议（如 MIT）
4. 在仓库 Description 里写清功能与触发场景，便于被检索收录

### B. 技能市场 / 收录列表（扩大曝光，免费）

| 市场/列表 | 提交方式 |
|---|---|
| Anthropic 官方 skills 仓库（github.com/anthropics/skills） | 提交 Pull Request |
| awesome-claude-skills（ComposioHQ，26k+ star） | Fork 后提交 PR |
| skills.sh | 无需提交，GitHub 公开仓库自动索引 |
| superpowers（github.com/obra/superpowers） | 提交 PR 收录 |

### C. 国内内容平台（教程 + 引流，适合中文用户）

| 平台 | 内容形式 | 说明 |
|---|---|---|
| CSDN 博客 | 图文教程 | 可发布「安装+使用」文章并附 zip |
| 掘金 | 图文教程 | 技术社区，质量较高 |
| 知乎 | 问答/文章 | 回答「如何分享豆包技能」类问题 |
| 微信公众号 | 图文 | 反思型写作定位与公众号场景天然契合 |
| 抖音 / B站 | 短视频教程 | 豆包 Skill 教程流量大，录 1 分钟安装演示 |
| 博客园 | 图文 | 老牌技术社区，可同步 CSDN 内容 |

### D. 分发注意事项

1. **附上使用说明**：在 README 里写清「触发词」和「使用示例」（如：帮我写一篇《活着》的读后感）
2. **版本管理**：GitHub 打 tag/release，用户可追踪更新
3. **隐私检查**：发布前确认 SKILL.md 内不含个人隐私、账号信息或内部资料（本技能已确认干净）
4. **授权声明**：如引用了他人的方法论，注明出处；MIT 协议下允许他人自由使用和修改
5. **改名记录**：本技能由 wechat-official-account-writer（公众号助手）更名而来，发布新版本时建议在 README 中说明，方便老用户迁移

## 三、快速使用示例

```
用户：帮我写这周的周记
助手：先问优先目的（确认反思第一）→ 提醒查看上周相册唤起素材 → 选取瞬间 → 成稿
```

```
用户：帮我写一篇《活着》的读后感
助手：先问优先目的 → 提醒回看全书笔记 → 提炼核心感悟 → 搭建框架 → 成稿
```

```
用户：帮我写一篇「人的智力是否一样」的研究型文章
助手：先问优先目的 → 明确研究问题 → 推荐权威文献 → 梳理论点 → 成稿
```