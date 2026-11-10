# lecture-breakdown · 课件知识点拆分

上传一讲课件（PDF、PPT 或截图），AI 会把它拆成按重要度和依赖顺序排列的知识点，再一个一个讲透，每讲完一个点出一道自测题，帮你在复习时真正理解课件。

A skill for Claude and Codex that breaks a lecture deck into ranked, dependency-ordered knowledge points and walks you through them one by one with self-check questions. Explanations are in Chinese; key terms stay in English.

## 适合什么时候用

复习可以分三步走：

1. **理解重要知识点** ← 这个 skill 负责这一步
2. 做一遍样卷，弄清楚考试考什么
3. 针对弱点做专项练习

它不会帮你出整套题或押题，只在每个知识点后面给一句「考法预判」，留到做样卷的时候再去核对。

## 它会做什么

1. **知识地图**：把一讲拆成 6–15 个知识点，每个点标出重要度（核心 / 重要 / 了解）、判断依据、前置依赖和页码。
2. **逐个讲透**：每个点按固定结构讲：一句话定义、解决什么问题、怎么运作、最小例子、易错点、考法预判，最后附一道自测题。
3. **卡点处理**：答错了只补卡住的那一环，最多追问两轮。还不通就直接讲清楚，记进卡点记录，不会一直追问下去。
4. **收尾**：整理出已掌握的点、卡点记录和考法预判清单。开卷考试会附 A4 笔记候选条目，闭卷考试会附必背清单。

## 安装

**Claude（网页版 / 桌面版）**

1. 下载本仓库里的 [`lecture-breakdown.zip`](lecture-breakdown.zip)。
2. 在 Claude 里打开 **Customize > Skills**，点 **+**，选 **Create skill > Upload a skill**，上传这个 zip。
3. 在列表里把它打开。

想自己打包也可以，但 zip 里必须有一层 `lecture-breakdown/` 文件夹，不能把 `SKILL.md` 直接放在 zip 的根目录。

**Claude Code**

在 Claude 账号里启用这个 skill 后，用同一个账号登录 Claude Code，它会自动同步过去。

**Codex**

在 Codex 里输入：

```
$skill-installer install https://github.com/CatDisgust/lecture-breakdown/tree/main/lecture-breakdown
```

也可以手动安装：把 `lecture-breakdown/` 文件夹复制到 `~/.codex/skills/` 下面。

装好后重启 Codex。如果之前装过旧版本，先删掉 `~/.codex/skills/lecture-breakdown/` 再装。

在 Codex 里，课件文件要放在当前工作目录下，用的时候告诉它文件名就行。

## 用法

上传一讲的课件（在 Codex 里就是说出文件名），然后说一句：

> 用 lecture-breakdown 拆一下这讲，考试是闭卷

最好告诉它考试是闭卷、开卷还是限制开卷，收尾时给你的清单会不一样。不说的话它会先问你。

常用指令：
- 「从第 3 个点开始」：跳到指定的知识点
- 「快速过」：不做自测，直接讲完所有核心点，最后统一出 3–5 道题
- 「停」：马上收尾，输出卡点记录和清单

## 说明

- 讲解只以课件为准。课件外补充的内容会单独标出来。
- 如果环境里装了 [Aha](https://github.com/CatDisgust/aha-skill)，遇到卡点时会调用它。
