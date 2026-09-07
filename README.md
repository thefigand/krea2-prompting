# Krea 2 Prompting Skill

将中文灵感、画面 brief 或艺术描述转换为可直接粘贴的 Krea 2 英文文生图提示词。

它偏向 Krea 2 的长篇自然语言叙述：用连贯的场景、光线、主体动作、空间层次、镜头构图和风格描述来表达画面意图，而不是堆砌 Stable Diffusion 风格的逗号标签。

> 非 Krea 官方项目。本技能基于 Krea 2 提示词实践整理而成。

## 适用场景

- 从一句中文创意扩写为 Krea 2 英文提示词
- 需要明确主体在画面中的占比、镜头、视角或景深
- 想让环境、光影、色彩和画风更一致
- 需要处理 Krea 2 的文字渲染、Turbo 分辨率或负面提示词问题

不适用于 Stable Diffusion 标签式提示词或 negative prompt 工作流。

## 安装

将本仓库克隆或复制到 Codex 的个人技能目录：

```text
~/.codex/skills/krea2-prompting/
├── SKILL.md
├── agents/openai.yaml
└── references/
    └── krea2-prompt-patterns.md
```

例如：

```bash
git clone https://github.com/thefigand/krea2-prompting.git ~/.codex/skills/krea2-prompting
```

重启 Codex 或开启新对话后，技能即可被自动发现。

## 使用

直接用自然语言说明画面。例如：

```text
用 Krea 2 生成提示词：傍晚的未来上海街头，一位穿红色风衣的女侦探站在雨中的霓虹灯下，电影感，人物占画面三分之一。
```

或显式调用：

```text
$krea2-prompting
一只白狐在雪山上的古老神社前回头，空灵、冷色、广角镜头。
```

默认输出为一段可直接粘贴到 Krea 2 的英文 Prompt。

## 生成逻辑

技能会按实际需要组织以下信息：

1. 场景与基调
2. 时间、天气和光线
3. 主体的动作、外观、服装与互动
4. 前景、中景、背景或远景
5. 镜头、视角、构图与主体画面占比
6. 画风、色彩、光影与质感

它会保留用户明确指定的主体、动作、颜色和空间关系，并避免无根据地加入关键物件、IP、文字或相互冲突的镜头指令。

## Krea 2 注意事项

- 画面中的可读文字应使用英文引号，例如：`a neon sign that says "OPEN 24H"`
- Krea 2 不使用 negative prompt；如需控制生成自由度，请使用 CFG scale。
- Krea Turbo 的分辨率应不超过 2K，且宽高为 16 的倍数。
- 若构图很重要，建议说明镜头和主体占比，例如 `occupying only one-fifth (20%) of the frame` 或 `taking up nearly half of the foreground frame`。

## 文件说明

- [`SKILL.md`](SKILL.md)：核心提示词规则与输出格式
- [`references/krea2-prompt-patterns.md`](references/krea2-prompt-patterns.md)：常用措辞、结构模板和完整示例
- [`agents/openai.yaml`](agents/openai.yaml)：Codex 界面元数据

## License

[MIT](LICENSE)
