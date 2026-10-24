# 人话 renhua · 让 AI 写中文时说人话

**一个 Claude skill：用一个真人的说话方式写小红书、X、日记、产品介绍、评论回复，去掉 AI 味，再加一点网感和小幽默。**

AI 写的中文一眼就能认出来：emoji 清单、排比、金句升华、"不是……而是……"、万能结尾提问。这个 skill 是从一位独立开发者自己打的 407 句原话里提炼出来的（节奏、常用词、评价方式），再加上两份参考：

| 文件 | 内容 |
|---|---|
| `plugins/renhua/skills/renhua/SKILL.md` | 他怎么说话、必须删掉的 8 类 AI 味、5 步写作流程、平台差异、AI 味 vs 人话对照 |
| `…/references/examples.md` | 小红书真实爆款标题按结构分类（反差自嘲 / 身份+挑战+期限 / 做了个X实测 / 一句话梗），大学生口吻 vs 科技自媒体口吻 |
| `…/references/insight.md` | 核心洞察和金句的写法：主题句首尾呼应、结果先行、段尾金句的六种形状、有数据撑着的洞察段（从一份被认可的转正答辩稿里拆出来） |
| `…/references/humor.md` | 17 个网感手法：量子位、差评、CZ、孙宇晨、曾颖、邵艾伦、levelsio、Marc Lou、半佛仙人、王登科、和菜头的句式，每个附一个我们自己写的例子 |

## 安装

**Claude Code 插件（推荐）**

```bash
claude plugin marketplace add jack-reson8/renhua
claude plugin install renhua@renhua
```

**普通 skill**

```bash
git clone https://github.com/jack-reson8/renhua
cp -R renhua/plugins/renhua/skills/renhua ~/.claude/skills/
```

**Codex**（CLI 或 ChatGPT 桌面版）：

```bash
codex plugin marketplace add jack-reson8/renhua
codex plugin add renhua@renhua
```

也可以把 `plugins/renhua/skills/renhua` 复制到 `~/.codex/skills/`。Skill 遵循 [Agent Skills](https://agentskills.io) 开放标准，Claude Code、Codex 以及任何能读取 SKILL.md 的 agent 都能用。

## 想换成你自己的口吻
把 `SKILL.md` 里「他实际怎么说话」那一节换成你自己的规律：导出你和 AI 的聊天记录，只留你自己打的字，统计常用词、句长、标点习惯、评价方式。其余部分（删 AI 味、步骤、示例库、幽默手法）可以直接用。

## 配套
出图用 [post-skill](https://github.com/jack-reson8/post-skill)，动效视频用 [pro-motion](https://github.com/jack-reson8/pro-motion)，写 skill 用 [skill-skill](https://github.com/jack-reson8/skill-skill)。

MIT License
