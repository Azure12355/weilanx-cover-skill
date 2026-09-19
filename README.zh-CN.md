<h1 align="center">weilanx 封面 Skill</h1>

<p align="center">
  <img src="./docs/assets/project-icon.svg" width="128" height="128" alt="weilanx 封面 Skill 图标">
</p>

<p align="center"><strong>一个用于生成多种比例、高冲击力中文内容封面的通用图片生成 Skill。</strong></p>
<p align="center">根据用户提供的人物图、准确标题和真实主题，生成具有清晰层级的信息拼贴封面提示词，并严格约束人物一致性。</p>

<p align="center">
  <a href="./README.md">English</a> · <strong>简体中文</strong>
</p>

## 项目简介

本仓库包含一个自包含的 Agent Skill，用于生成或修改 weilanx 风格的教程、知识分享和经验复盘封面。它重点解决中文标题可读性、视觉层级、主题信息拼贴，以及用户人物图的身份保真。

仓库使用 weilanx 项目名称，并包含已授权展示的生成示例。私人人像、原始参考图、本机绝对路径和账号标识均不包含在仓库内。

## 功能

- 默认使用 3:4，并支持 4:3、16:9、2.35:1 等用户指定比例的原生构图。
- 保持中文标题准确，并明确控制断句。
- 对人物身份和自然摄影纹理施加强约束。
- 明确前景、中景和背景的层次关系。
- 使用与主题有关的信息卡、贴纸、路径和辅助图形。
- 支持修改已有封面和生成多套变体。

## 安装

将本仓库复制到 Agent 的 Skills 目录，并保持 `SKILL.md`、`references/` 和 `agents/` 的相对结构不变。不同宿主应用的 Skills 目录并不相同，请以对应产品当前的安装文档为准。

## 使用方法

请提供：

1. 一张你有权使用的人物图。
2. 必须准确呈现的中文标题。
3. 真实主题或使用场景。
4. 可选：一张你有权使用的风格参考图。

示例请求：

```text
使用 $weilanx-cover-skill 生成一张 3:4 教程封面。
标题：“3 步整理研究笔记”
人物放在右侧，采用路径流程构图。
只使用真实标签，不要虚构互动数据。
```

宿主需要提供支持参考图片的图像生成工具。中文文字和人物一致性的最终效果仍取决于所选模型，发布前请人工检查每一张结果。

## 多比例效果示例

<table>
  <tr>
    <th>3:4 竖版</th>
    <th>4:3 横版</th>
  </tr>
  <tr>
    <td><img src="./docs/examples/ai-cover-3-steps.png" alt="3:4 中文教程封面示例"></td>
    <td><img src="./docs/examples/cover-4x3.png" alt="4:3 中文信息卡封面示例"></td>
  </tr>
  <tr>
    <th>16:9 视频横版</th>
    <th>2.35:1 超宽海报</th>
  </tr>
  <tr>
    <td><img src="./docs/examples/cover-16x9.png" alt="16:9 中文视频封面示例"></td>
    <td><img src="./docs/examples/cover-235x100.png" alt="2.35:1 中文超宽海报示例"></td>
  </tr>
</table>

这组示例使用同一个已授权卡通角色和同一套视觉语言，但每种画布都重新构图，并非简单裁切。它们展示了准确中文标题、信息卡和针对不同比例的视觉层级。出于隐私和人物权益考虑，原始参考图不会放入仓库。

## 隐私与素材处理

本仓库不附带人物照片或风格参考图，所有输入都应在运行时提供。本地实验素材可放在 `local-assets/`，该目录已被 Git 忽略。未经明确同意和授权，不要提交人脸照片、截图或第三方作品。

## 项目结构

| 路径 | 用途 |
|---|---|
| `SKILL.md` | 触发条件、工作流与完整生成提示词 |
| `references/visual-style.md` | 通用视觉默认值与禁用风格 |
| `agents/openai.yaml` | 可选的界面元数据 |
| `docs/assets/project-icon.svg` | 仓库自有的中性图标 |
| `docs/examples/` | 使用已授权角色参考生成的多比例封面示例 |

## Agent 快速上手

### 目标

基于用户自有输入生成或修改封面。本仓库是提示词工作流，不是图片编辑器、模型或参考图片合集。

### 事实来源

- 工作流与提示词：`SKILL.md`
- 视觉默认值：`references/visual-style.md`
- 界面元数据：`agents/openai.yaml`

### 安全工作流

1. 完整阅读 `SKILL.md` 和 `references/visual-style.md`。
2. 确认用户提供了有权使用的人物图和准确标题。
3. 风格参考只用于启发，不复制其中的人物、文字、Logo 或版式。
4. 使用宿主的图片生成工具生成，检查标题和人物一致性后交付。
5. 私有输入和生成结果应保存在仓库外，或放入已忽略的本地目录。

### 验证命令

```shell
rg -n 'file://|BEGIN (RSA |EC |OPENSSH )?PRIVATE KEY' .
git diff --check
```

### 边界

- 不提交私人人像、用户生成内容、凭据或本机绝对路径。
- 不为封面虚构数据或宣传结论。
- 保持用户标题和人物参考准确。
- 向仓库添加任何第三方视觉素材前先确认授权。

## 贡献

参见 [CONTRIBUTING.md](./CONTRIBUTING.md)。所有改动都应保持 Skill 的通用性、隐私安全，并且不依赖任何特定创作者身份或文件结构。

## 许可证

本项目采用 [MIT 许可证](./LICENSE) 开源。
