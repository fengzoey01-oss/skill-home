# skill-home

一个给 Codex Skills 用的“技能首页”。

`skill-home` 解决的不是“没有 skill 可用”，而是“skill 一多，人就不知道该用哪个”。

它的目标很简单：

- 让用户不用记 skill 名
- 让用户不用理解内部路由
- 让用户只要说人话，就能先得到推荐，再决定要不要继续

---

## 它是什么

当你装了越来越多 skills 之后，最常见的问题往往不是能力不够，而是入口太复杂。

比如这些需求，其实很多人第一反应都不是“我该用哪个 skill”，而是“我现在该怎么开始”：

- 我想研究一下 Cursor
- 帮我看看这个商业模式
- 审一下这个 AI 产品需求
- 我想写一篇公众号长文
- 整理一下这个项目文档

`skill-home` 做的事情，就是先把这些自然语言需求接住，然后：

1. 自动判断最适合的已安装 skill
2. 用一句人话解释为什么推荐它
3. 在真正调用前先征求确认

它不会静默替用户做决定。

它会先说：

```text
我建议用 $hv-analysis，因为你这是深度研究，不是普通聊天。要我现在用它继续吗？
```

---

## 为什么做这个

很多 AI 工具最后不好用，不是因为能力不强，而是因为把复杂度原封不动地留给了用户。

当 skill 还是 2 个、3 个的时候，手动记一下还行。  
当 skill 变成 10 个、20 个、50 个之后，问题就开始出现了：

- 名字记不住
- 边界分不清
- 每次开始前都要先犹豫一下
- 能力越多，系统反而越难上手

所以 `skill-home` 不是一个“更强的 skill”。

它更像是一个翻译层，一个入口层，一个给技能系统降复杂度的首页。

---

## 适合谁

- 装了很多 Codex skills，但不想记名字的人
- 想把 skill 系统交给团队成员或朋友使用的人
- 想让 skill 使用方式更像“说人话”而不是“背命令”的人
- 会持续安装新 skills，希望入口能跟着演化的人

---

## 最短用法

几乎只需要记住这一句：

```text
用 $skill-home 帮我选
```

也可以直接套这些：

```text
用 $skill-home 看看这件事该用哪个 skill
用 $skill-home 我不知道该用什么
用 $skill-home 先推荐，再问我确认
用 $skill-home 看看我现在装了哪些 skill
用 $skill-home 找找有没有适合这个需求的 skill
```

---

## Usage 示例

### 1. 做商业判断

```text
用 $skill-home 帮我看看这个 AI 产品经理求职辅导方向值不值得做
```

可能得到的推荐：

```text
我建议用 $dbs，因为你现在是在判断方向，不是直接写方案。要我现在用它继续吗？
```

### 2. 做深度研究

```text
用 $skill-home 我想研究一下 Cursor 和 Windsurf 的差别
```

可能得到的推荐：

```text
我建议用 $hv-analysis，因为你这是深度研究和横向比较。要我现在用它继续吗？
```

### 3. 审 AI 产品需求

```text
用 $skill-home 审一下这个 AI Agent 需求文档
```

可能得到的推荐：

```text
我建议用 $ai-product-requirement-review，因为你这是 AI 产品需求评审，不是普通文档整理。要我现在用它继续吗？
```

### 4. 写长文

```text
用 $skill-home 我想把这份素材写成公众号文章
```

可能得到的推荐：

```text
我建议用 $khazix-writer，因为你是想把素材写成长文。要我现在用它继续吗？
```

### 5. 整理项目文档

```text
用 $skill-home 整理一下这个项目文档
```

可能得到的推荐：

```text
我建议用 $neat-freak，因为你现在是在做项目收尾和文档同步。要我现在用它继续吗？
```

---

## 核心能力

- 推荐最匹配的已安装 skill
- 先推荐、再确认，不静默调用
- 支持浏览当前已安装的 skills
- 提供傻瓜版技能使用卡，方便复制粘贴
- 支持动态扫描本地 skill 目录，适配后续新增 skills

---

## 仓库结构

```text
.
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
├── references/
│   └── foolproof-skill-card.md
└── scripts/
    └── refresh_installed_skills.py
```

说明：

- `references/foolproof-skill-card.md`
  傻瓜版技能使用卡，适合直接照抄

- `scripts/refresh_installed_skills.py`
  扫描本地 skill 目录并生成当前技能索引

- `references/installed-skills.md`
  这是运行时生成文件，不提交到仓库，避免带上本机路径

---

## 安装方式

把这个目录复制到你的 Codex skills 目录：

```text
~/.codex/skills/skill-home
```

然后重启 Codex。

---

## 设计原则

这个 skill 背后其实只有三条原则：

1. 不要求用户记 skill 名
2. 不要求用户先理解系统结构
3. 不偷偷替用户做决定

所以它不是把“复杂能力”藏起来，而是把“复杂选择”先接住。

---

## 一句话总结

`skill-home` 不是一个更强的 skill。

它是一个让技能系统真正变得可用的入口。
