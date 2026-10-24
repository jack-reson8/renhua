# 人话 renhua · AI से चीनी भाषा इंसान की तरह लिखवाएँ

[English](README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Tiếng Việt](README.vi.md) | हिन्दी

<p align="center"><img src="docs/share.png" alt="renhua: AI-written vs human-written Chinese" width="100%"></p>
<p align="center"><sub><a href="https://github.com/jack-reson8/copy-that"><b>Copy That</b></a> सीरीज़ का हिस्सा · एक लाइन में पूरा सेट इंस्टॉल करें</sub></p>
<p align="center"><a href="https://jack-reson8.github.io/skill-skill/check/"><img src="https://img.shields.io/badge/skill%20health-100%2F100-brightgreen" alt="skill health 100/100"></a></p>

**एक Claude skill जो असली इंसान के लहजे में Xiaohongshu पोस्ट, X पोस्ट, डायरी, प्रोडक्ट कॉपी और कमेंट के जवाब लिखता है: AI वाली छाप हटाता है और थोड़ा इंटरनेट वाला अंदाज़ व हल्का हास्य जोड़ता है।**

ध्यान दें: यह skill **चीनी** भाषा का कंटेंट लिखता है (人话 यानी "आम इंसान की बोली")। यह उन लोगों के काम का है जो चीनी में प्रकाशित करते हैं; यह README बाकी पाठकों के लिए अनुवादित है।

AI की लिखी चीनी आसानी से पकड़ में आ जाती है: emoji की चेकलिस्ट, तीन-तीन की तुकबंदी वाली सूचियाँ, नारे जैसे उपसंहार, "不是……而是……" ("X नहीं, बल्कि Y") ढाँचा और हर बार वही अंतिम सवाल। यह skill एक इंडी डेवलपर के खुद टाइप किए 407 असली वाक्यों (लय, पसंदीदा शब्द, चीज़ों को परखने का तरीका) से निकाला गया है। आप इसे अपने लहजे से बदल सकते हैं (नीचे देखें)। साथ में तीन संदर्भ फ़ाइलें भी हैं।

| फ़ाइल | विषय-सामग्री |
|---|---|
| `plugins/renhua/skills/renhua/SKILL.md` | मूल डेवलपर कैसे बोलता है, हटाने लायक AI वाली 8 छापें, लिखने की 5-चरणीय प्रक्रिया, प्लेटफ़ॉर्म के अंतर, AI वाला लहजा बनाम इंसानी लहजा |
| `…/references/examples.md` | Xiaohongshu के असली वायरल शीर्षक, ढाँचे के अनुसार वर्गीकृत (विरोधाभास + आत्म-व्यंग्य / पहचान + चुनौती + समय-सीमा / "X बनाया और परखा" / एक पंक्ति का मीम), कॉलेज छात्र बनाम टेक क्रिएटर का लहजा |
| `…/references/insight.md` | मुख्य अंतर्दृष्टि और धारदार अंतिम पंक्ति कैसे लिखें: शुरुआती विषय-वाक्य का अंत में दोहराव, नतीजा पहले, अनुच्छेद के अंत की पंक्ति के छह रूप, आँकड़ों से समर्थित अंतर्दृष्टि वाले अनुच्छेद (एक स्वीकृत पदोन्नति-प्रस्तुति के मसौदे से निकाले गए) |
| `…/references/humor.md` | इंटरनेट वाले अंदाज़ की 17 तकनीकें: 量子位, 差评, CZ, 孙宇晨, 曾颖, 邵艾伦, levelsio, Marc Lou, 半佛仙人, 王登科 और 和菜头 के वाक्य-ढाँचे, हर एक के साथ अपना लिखा उदाहरण |

## इंस्टॉल

**Claude Code प्लगइन (अनुशंसित)**

```bash
claude plugin marketplace add jack-reson8/renhua
claude plugin install renhua@renhua
```

**सामान्य skill फ़ोल्डर**

```bash
git clone https://github.com/jack-reson8/renhua
cp -R renhua/plugins/renhua/skills/renhua ~/.claude/skills/
```

**Codex** (CLI या ChatGPT डेस्कटॉप ऐप):

```bash
codex plugin marketplace add jack-reson8/renhua
codex plugin add renhua@renhua
```

आप `plugins/renhua/skills/renhua` को `~/.codex/skills/` में कॉपी भी कर सकते हैं।

**अन्य एजेंट** (Cursor, Gemini CLI, GitHub Copilot और skills CLI द्वारा समर्थित अन्य एजेंट के साथ काम करता है):

```bash
npx skills add jack-reson8/renhua
```

यह skill खुले [Agent Skills](https://agentskills.io) मानक का पालन करता है, इसलिए Claude Code, Codex और SKILL.md पढ़ सकने वाला कोई भी एजेंट इसे इस्तेमाल कर सकता है।

## अपना लहजा इस्तेमाल करें
`SKILL.md` में 「他实际怎么说话」 ("वह असल में कैसे बोलता है") वाले हिस्से को अपने पैटर्न से बदलें: AI के साथ अपनी चैट एक्सपोर्ट करें, सिर्फ़ अपने टाइप किए वाक्य रखें, और अपने आम शब्द, वाक्य की लंबाई, विराम-चिह्नों की आदतें और चीज़ों को परखने का तरीका गिनें। बाकी हिस्से (AI छाप हटाना, चरण, उदाहरण-संग्रह, हास्य तकनीकें) जस के तस इस्तेमाल हो सकते हैं।

## संबंधित skills
इमेज के लिए [post-skill](https://github.com/jack-reson8/post-skill), मोशन वीडियो के लिए [pro-motion](https://github.com/jack-reson8/pro-motion), skill लिखने के लिए [skill-skill](https://github.com/jack-reson8/skill-skill)।

MIT License
