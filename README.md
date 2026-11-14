# lecture-breakdown · 课件知识点拆分

上传一讲课件（PDF、PPT 或截图），AI 会把它拆成按重要度和依赖顺序排列的知识点，再一个一个讲透，每讲完一个点出一道自测题，帮你在复习时真正理解课件。

A skill for Claude and Codex that breaks a lecture deck into ranked, dependency-ordered knowledge points and walks you through them one by one with self-check questions. Explanations are in Chinese; key terms stay in English.

## 适合什么时候用

复习可以分三步走：

1. **用这个 skill 把每节课快速过一遍，理解重要知识点** ← 这个 skill 负责这一步
2. 做一遍样卷，弄清楚考试考什么
3. 根据样卷做专项练习

它不会帮你出整套题或押题，只在每个知识点后面给一句「考法预判」，留到做样卷的时候再去核对。

## 它会做什么

1. **知识地图**：把一讲拆成 6–15 个知识点，每个点标出重要度（核心 / 重要 / 了解）、判断依据、前置依赖和页码。
2. **逐个讲透**：每个点按固定结构讲：一句话定义、解决什么问题、怎么运作、例子、易错点、考法预判，最后附一道自测题。讲法参考 [Aha](https://github.com/CatDisgust/aha-skill)：从你已经懂的地方接上，先讲场景再给公式符号，用例子走完每一步，流程和对比会主动画图。
3. **卡点处理**：答错了只补卡住的那一环，第二次换个例子或者画图讲。最多追问两轮，还不通就直接讲清楚，记进卡点记录，不会一直追问下去。一个点没讲通，不会跳到下一个。
4. **收尾**：整理出已掌握的点、卡点记录和考法预判清单。开卷考试会附 A4 笔记候选条目，闭卷考试会附必背清单。最后直接整理成一份笔记。

## 安装

这个 skill 只包含指令文件，不需要额外的 API 密钥或服务。同一个平台只装一份。

**claude.ai（网页版 / 桌面版）**

1. 下载本仓库里的 [`lecture-breakdown.zip`](lecture-breakdown.zip)，不用解压。
2. 在 Claude 里打开 **Customize > Skills**，点 **+**，选 **Create skill > Upload a skill**，上传这个 zip。
3. 在列表里把它打开。

想自己打包也可以，但 zip 里必须有一层 `lecture-breakdown/` 文件夹，不能把 `SKILL.md` 直接放在 zip 的根目录。

**Claude Code**

把 `lecture-breakdown` 文件夹放进 `~/.claude/skills/`，确认指令文件位于 `~/.claude/skills/lecture-breakdown/SKILL.md`。如果已经在 claude.ai 账号里启用了这个 skill，用同一个账号登录 Claude Code 也会自动同步过去，不用再装一次。

**Codex**

把下面这段话发给 Codex：

```text
请使用 $skill-installer 安装 lecture-breakdown：
https://github.com/CatDisgust/lecture-breakdown/tree/main/lecture-breakdown
```

也可以手动安装：把 `lecture-breakdown` 文件夹放进 `~/.agents/skills/`，确认指令文件位于 `~/.agents/skills/lecture-breakdown/SKILL.md`。装好后如果 Codex 没识别到，重新打开 Codex 再试。

在 Codex 里，把课件放进 Codex 当前打开的文件夹，用的时候告诉它文件名就行。

`~` 代表你的用户主目录。

## 用法

上传一讲的课件（在 Codex 里就是说出文件名），然后说一句：

> 用 lecture-breakdown 拆一下这讲，考试是闭卷

最好告诉它考试是闭卷、开卷还是限制开卷，收尾时给你的清单会不一样。不说的话它会先问你。

想明确指定用这个 skill，在 Codex 里写 `$lecture-breakdown`，在 Claude Code 里写 `/lecture-breakdown`。

常用指令：
- 「从第 3 个点开始」：跳到指定的知识点
- 「只讲理解」：从这里开始不出自测，每个点照常讲完整
- 「快速过」：只讲核心点，不做自测，最后统一出 3–5 道题
- 「画图讲解」：把当前这个点用图再讲一遍
- 「停」：马上收尾，输出卡点记录和清单

## 说明

- 讲解只以课件为准。课件外补充的内容会单独标出来。
- 如果环境里装了 [Aha](https://github.com/CatDisgust/aha-skill)，讲解时会直接按它的说明来。
- 提一句你的背景（比如学过哪些课、会什么编程语言），它会从你熟悉的东西讲起。

## 许可证

[MIT License](LICENSE) © 2026 CatDisgust
