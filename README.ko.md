# 人话 renhua · AI가 중국어를 사람처럼 쓰게 하기

[English](README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | 한국어 | [Tiếng Việt](README.vi.md) | [हिन्दी](README.hi.md)

<p align="center"><img src="docs/share.png" alt="renhua: AI-written vs human-written Chinese" width="100%"></p>
<p align="center"><sub><a href="https://github.com/jack-reson8/copy-that"><b>Copy That</b></a> 시리즈 · 한 줄로 전체 설치</sub></p>

**실제 사람의 말투로 샤오홍슈(Xiaohongshu), X, 일기, 제품 소개, 댓글 답글을 쓰는 Claude skill입니다. AI 티를 지우고, 약간의 인터넷 감성과 유머를 더합니다.**

참고: 이 skill이 쓰는 것은 **중국어** 콘텐츠입니다(人话 = "평범한 사람의 말"). 중국어로 글을 발행하는 분들을 위한 도구이며, 이 README는 그 외의 분들을 위한 번역입니다.

AI가 쓴 중국어는 금방 티가 납니다. 이모지 체크리스트, 삼단 나열, 구호 같은 마무리, "不是……而是……"(X가 아니라 Y) 구문, 단골 마무리 질문. 이 skill은 한 인디 개발자가 실제로 입력한 407개의 말(리듬, 자주 쓰는 단어, 평가하는 방식)에서 추출했습니다. 자신의 말투로 바꿔 쓸 수도 있습니다(아래 참고). 참고 파일 3개도 함께 들어 있습니다.

| 파일 | 내용 |
|---|---|
| `plugins/renhua/skills/renhua/SKILL.md` | 원본 개발자의 말투, 지워야 할 AI 티 8종, 5단계 작성 흐름, 플랫폼별 차이, AI 말투 vs 사람 말투 비교 |
| `…/references/examples.md` | 샤오홍슈에서 실제로 터진 제목을 구조별로 분류(반전+자조 / 신분+도전+기한 / "X를 만들어 테스트했다" / 한 줄 밈). 대학생 말투 vs 테크 크리에이터 말투 |
| `…/references/insight.md` | 핵심 통찰과 명대사 쓰는 법: 첫 문장 주제를 끝에서 다시 받기, 결과 먼저, 문단 끝 명대사의 6가지 모양, 데이터로 받친 통찰 문단(승인받은 승진 심사 발표문을 분해한 것) |
| `…/references/humor.md` | 인터넷 감성 기법 17가지: 量子位, 差评, CZ, 孙宇晨, 曾颖, 邵艾伦, levelsio, Marc Lou, 半佛仙人, 王登科, 和菜头의 문장 패턴. 각각 직접 쓴 예문 포함 |

## 설치

**Claude Code 플러그인(권장)**

```bash
claude plugin marketplace add jack-reson8/renhua
claude plugin install renhua@renhua
```

**일반 skill 폴더**

```bash
git clone https://github.com/jack-reson8/renhua
cp -R renhua/plugins/renhua/skills/renhua ~/.claude/skills/
```

**Codex**(CLI 또는 ChatGPT 데스크톱 앱):

```bash
codex plugin marketplace add jack-reson8/renhua
codex plugin add renhua@renhua
```

`plugins/renhua/skills/renhua`를 `~/.codex/skills/`에 복사해도 됩니다.

**다른 에이전트**(Cursor, Gemini CLI, GitHub Copilot 등 skills CLI를 지원하는 에이전트에서 사용 가능):

```bash
npx skills add jack-reson8/renhua
```

이 skill은 개방형 [Agent Skills](https://agentskills.io) 표준을 따르므로 Claude Code, Codex, SKILL.md를 읽을 수 있는 모든 에이전트에서 쓸 수 있습니다.

## 내 말투로 바꾸기
`SKILL.md`의 「他实际怎么说话」(그가 실제로 말하는 방식) 부분을 내 패턴으로 바꾸세요. AI와의 대화 기록을 내보내 내가 직접 입력한 문장만 남기고, 자주 쓰는 단어, 문장 길이, 문장부호 습관, 평가하는 방식을 집계합니다. 나머지(AI 티 제거, 단계, 예시 모음, 유머 기법)는 그대로 쓸 수 있습니다.

## 함께 쓰는 skill
이미지는 [post-skill](https://github.com/jack-reson8/post-skill), 모션 영상은 [pro-motion](https://github.com/jack-reson8/pro-motion), skill 작성은 [skill-skill](https://github.com/jack-reson8/skill-skill).

MIT License
