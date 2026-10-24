# 人話 renhua · AI に中国語を「人の言葉」で書かせる

[English](README.md) | [简体中文](README.zh-CN.md) | 日本語 | [한국어](README.ko.md) | [Tiếng Việt](README.vi.md) | [हिन्दी](README.hi.md)

<p align="center"><img src="docs/share.png" alt="renhua: AI-written vs human-written Chinese" width="100%"></p>
<p align="center"><sub><a href="https://github.com/jack-reson8/copy-that"><b>Copy That</b></a> シリーズの一つ · 1 行で全部インストール</sub></p>
<p align="center"><a href="https://jack-reson8.github.io/skill-skill/check/"><img src="https://img.shields.io/badge/skill%20health-100%2F100-brightgreen" alt="skill health 100/100"></a></p>

**実在の人の話し方で、小紅書（Xiaohongshu）・X・日記・プロダクト紹介・コメント返信を書く Claude skill。AI っぽさを消し、ネットらしいノリと少しのユーモアを足します。**

注意：この skill が書くのは**中国語**のコンテンツです（人話＝「ふつうの人の言葉」）。中国語で発信する人向けのツールで、この README はそれ以外の方のための翻訳です。

AI が書いた中国語はすぐ見抜かれます。絵文字のチェックリスト、三つ並べの対句、スローガン調の締め、「不是……而是……」（Xではなく Y）構文、お決まりの問いかけエンディング。この skill は、ある個人開発者が実際に打った 407 件の発言（リズム、よく使う言葉、物事の評価の仕方）から抽出したものです。自分の口調に差し替えることもできます（下記参照）。参考ファイルも 3 つ付いています。

| ファイル | 内容 |
|---|---|
| `plugins/renhua/skills/renhua/SKILL.md` | 元になった開発者の話し方、消すべき AI っぽさ 8 種、5 ステップの執筆フロー、プラットフォームごとの違い、AI 調と人話の比較 |
| `…/references/examples.md` | 小紅書でバズった実際のタイトルを構造別に分類（ギャップ＋自虐／立場＋挑戦＋期限／「X を作って試した」／一言ネタ）。大学生トーンとテック系発信者トーンの違い |
| `…/references/insight.md` | 核心の洞察と決め台詞の書き方：冒頭の主題文を末尾で回収、結果を先に、段落末の決め台詞の 6 パターン、データで裏付けた洞察段落（承認された昇進審査の発表原稿を分解したもの） |
| `…/references/humor.md` | ネットらしさを出す 17 の手法：量子位、差评、CZ、孙宇晨、曾颖、邵艾伦、levelsio、Marc Lou、半佛仙人、王登科、和菜头の文型。それぞれオリジナルの例文つき |

## インストール

**Claude Code プラグイン（推奨）**

```bash
claude plugin marketplace add jack-reson8/renhua
claude plugin install renhua@renhua
```

**通常の skill フォルダ**

```bash
git clone https://github.com/jack-reson8/renhua
cp -R renhua/plugins/renhua/skills/renhua ~/.claude/skills/
```

**Codex**（CLI または ChatGPT デスクトップ版）：

```bash
codex plugin marketplace add jack-reson8/renhua
codex plugin add renhua@renhua
```

`plugins/renhua/skills/renhua` を `~/.codex/skills/` にコピーしても使えます。

**その他のエージェント**（Cursor、Gemini CLI、GitHub Copilot など、skills CLI 対応のエージェントで使えます）：

```bash
npx skills add jack-reson8/renhua
```

この skill はオープンな [Agent Skills](https://agentskills.io) 標準に沿っているので、Claude Code、Codex、SKILL.md を読めるエージェントなら使えます。

## 自分の口調に差し替える
`SKILL.md` の「他实际怎么说话」（彼が実際どう話すか）の節を、自分のパターンに書き換えてください。AI とのチャット履歴をエクスポートし、自分が打った文だけを残して、よく使う言葉、文の長さ、句読点の癖、物事の評価の仕方を集計します。残りの部分（AI っぽさの除去、手順、例文集、ユーモアの手法）はそのまま使えます。

## 関連 skill
画像は [post-skill](https://github.com/jack-reson8/post-skill)、モーション動画は [pro-motion](https://github.com/jack-reson8/pro-motion)、skill の書き方は [skill-skill](https://github.com/jack-reson8/skill-skill)。

MIT License
