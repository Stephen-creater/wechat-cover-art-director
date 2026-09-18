---
name: wechat-cover-art-director
description: "为中文微信公众号文章策划并生成多套风格不同的 16:9 封面，并按用户的采用/淘汰反馈维护个人封面案例库。用于用户给出公众号标题或正文要封面、头图、题图，或对已生成的封面候选给出采用、淘汰、打分等反馈时。不用于 ds 微信发布流程内的封面、归藏风格卡片、小红书 3:4 图文或 PPT。"
---

# 微信公众号封面艺术指导

像艺术指导一样，先找到文章最值得视觉化的矛盾、例子或隐喻，再生成多套真正不同的封面。吸引力来自概念、构图、配色和字体，不来自堆砌元素。本 Skill 独立工作，只使用自己的资产库。

## 读取路由

1. 必读 [preferences.md](references/preferences.md)（证据等级与审美结论）和 [rejections.md](references/rejections.md)（失败模式）。
2. 读 [router.md](references/router.md)，按标题容量、构图骨架、明暗和媒介选模板；题材只用于替换隐喻。
3. 只打开命中的 1-2 个 [cases/](references/cases/) 案例，不要全量加载。
4. 探索新模板时读 [template-space.md](references/template-space.md) 与 [creative-system.md](references/creative-system.md)，只从未覆盖的空间出题。
5. 写 prompt 时套用 [prompt-builder.md](references/prompt-builder.md)；与具体反例撞车时查 [rejected-index.md](references/rejected-index.md)。
6. 生成后按 [quality-gate.md](references/quality-gate.md) 逐张验收。

追溯某个案例或批次的来龙去脉时才读 [feedback/](references/feedback/)。

## 输入

- 从消息或附件识别标题和正文。标题逐字保留，包括大小写、数字和全半角标点。
- 标题不明确时只追问标题；标题和正文足够时直接执行，不让用户预选风格。
- 用户指定数量或比例时照做。未指定时默认 5 张：最多 2 张复用组（R，1 张直接适配 + 1 张借一维），其余为探索组（E）。

## 创意分流

先提炼：核心判断、最有张力的对比或因果、能承载它的具体物体或行为、读者第一感受。正文里有能一眼解释论点的例子或实体时，优先用它。

每个方向在背景配色、版式与标题位置、媒介、核心隐喻四项中至少三项不同。同批不能只是同模板换色，也不能全是蓝紫科技风。

## 硬性规则

- 默认亮色、浅色或有空气感的彩色背景。一批最多 1 张深色，需由内容证明；用户不要深色时一张不做。
- 一个强主体、清晰轮廓、漂亮留白、设计过的标题；无法解释文章的图标、方块、线路、粒子和装饰全部删除。
- 默认不用黑板、粉笔、卡通、黏土玩具、廉价赛博面板、通用机器人、发光大脑。
- 参考图只从 `assets/approved-covers/` 取，每张最多 2 个案例（一个控结构，一个控材质或配色）；弱正向只借一个维度；反例和未采用图不得作正向参考。
- 已通过模板不为凑样本重复生成；已淘汰方向不换色重跑。
- 只渲染用户标题，不加副标题、栏目名、译文、作者名、Logo、水印或二维码。
- 长标题拆成 `小引题 / 大主判断 / 小解释层`，只放大主判断，总行数可到 4 行；按语义短语断行。

## 生成

- 用当前环境的图片生成工具（Codex 中为内置 `image_gen`），每个方向独立调用、独立 prompt，默认 16:9 PNG。
- prompt 写明具体构图、颜色、主体、标题区和禁用项，不堆空泛形容词。

## 交付

- 候选存到 `outputs/YYYY-MM-DD-<slug>/`：`NN-E01.png` / `NN-R01.png`，以及 `prompts.json`、`manifest.json`（编号、名称、分组、参考案例、prompt）、`README.md`（方向表与质量门结果）和拼版 `preview.jpg`。
- 过程稿、脚本和 `checkpoint.md` 放 `work/YYYY-MM-DD-<slug>/`（git 忽略），中断后据此续跑。
- 展示全部方向，各用一句话说明隐喻和视觉语言；不替用户选最佳，除非被问。
- 用户筛选前，候选只留本地，不提交。
- 用户不喜欢时先找审美原因、调整创意系统，不在失败模板上小修小补。

## 异常与降级

- 没有图片生成工具：交付 `prompts.json` 与方向说明，明确告知未出图。
- 标题出错（错字、多字、标点变形、额外可读文字）：针对问题重生成，最多 2 次；仍不达标就照常交付，在 README 逐张注明，由用户决定。不做像素层贴字修补。
- 只有标题没有正文：可以生成，但说明隐喻只基于标题。
- 路由无合适案例：直接原创。

## 已验证的易错点

- 全角标点常被渲染成半角，如 `（Ontology）` 变 `(Ontology)`，验收时逐字核对。
- 量具、书页、活字等道具容易长出可读数字或文字；prompt 里写明表面无字，验收时专门检查。
- 长标题容易被压成等字号文字墙，或在语义短语中间断行。
- “科技文章”容易被默认做成黑底蓝紫霓虹；生成前核对整批明暗分布。
- WorkBuddy 等环境的生图工具会在右下角加“AI生成”水印；验收时检查角落，在 README 注明，交付时提醒用户。

## 资产闭环

只有用户明确说“采用、通过、实际使用、收录”时才进正向库；证据等级按 [preferences.md](references/preferences.md) 判定，同批名次要写进案例和路由。

新增正向案例：

1. 图片复制到 `assets/approved-covers/Axx-<slug>.png`。
2. 最终 prompt、证据等级、可复用与不复用项写入 `references/cases/Axx-<slug>.md`。
3. 更新 [approved-index.md](references/approved-index.md)、[router.md](references/router.md) 和 [template-space.md](references/template-space.md)。
4. 用户说明了原因时，把可执行结论提炼进 preferences 或 rejections，逐轮原话记入 `references/feedback/`。

新增淘汰：图片可得时复制到 `assets/rejected-covers/<round>/`，prompt 存 `references/rejected-prompts/<round>/`，更新 rejected-index。无逐张原因时只记批次事实，不编造原因。

## GitHub 同步

远程仓库 `https://github.com/Stephen-creater/wechat-cover-art-director`，分支 `main`。任何 Skill 文件变更都要在同一任务内完成：核对文件、引用与敏感信息 → 精确暂存本次文件 → commit → push `origin/main` → 读回远端提交确认。未推送前不得声称更新完成；用户要求只做本地草稿时除外。
