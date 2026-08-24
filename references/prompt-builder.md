# 提示词构建骨架

生成新案例时使用以下结构。不要把方括号原样发送给模型。

```text
Use case: ads-marketing
Asset type: 16:9 Chinese WeChat Official Account cover

Exact title: “[用户标题]”

Article-specific idea: [一句话说明文章的核心判断或冲突]
Reference strategy: [Axx 强适配 / Axx 只借用配色或构图 / 完全原创]
Core visual metaphor: [只能属于这篇文章的主体、行为和关系]
Composition: [标题位置、主体位置、留白、空间关系]
Medium and material: [摄影、3D、纸艺、图解、建筑等]
Palette: [主背景、主体色、强调色，解释各自作用]
Typography: render only the exact title in [1-3] natural lines; [字体、字重、颜色、对齐]
Constraints: no extra readable text, logos, watermark, QR code; every element must serve the article idea
Avoid: [从 rejections.md 和本次主题中选取 5-8 个具体禁用项]
```

## 提示词质量要求

- 至少有一句明确说明每个核心元素代表什么。
- 写具体光线、材质、尺度和构图，不堆 `premium`、`epic`、`futuristic` 等空泛形容词。
- 参考案例时说明“复用什么、不复用什么”。
- 标题必须逐字保留，禁止模型添加副标题或小标签。
