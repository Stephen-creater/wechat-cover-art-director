# 淘汰资产与提示词索引

## 资产规模

- 可用淘汰图片：42 张
- 已保存淘汰提示词：36 个文件，覆盖 69 个方向
- 淘汰图片：`../assets/rejected-covers/`
- 淘汰提示词：`rejected-prompts/`

## 证据等级

- `明确原因`：用户直接说明为什么不喜欢，可形成高置信规则。
- `批次淘汰`：知道没有通过，但没有逐张理由，只能阻止直接复用。
- `对照观察`：通过与淘汰案例之间的可见差异，作为中置信假设继续验证。

## Round 1

### 有图反例

- `R1-OAI-01-chip-cutaway`：批次淘汰；芯片环形剖面、浅灰背景。
- `R1-OAI-02-blueprint-fold`：批次淘汰；纸张蓝图、折叠分流。
- `R1-OAI-03-memory-relay`：原版淘汰；文字位置和背景分离不足，最终由 A06-v3 修正后通过。
- `R1-OAI-03-v2-centered`：明确原因；仅水平居中、整体偏下。
- `R1-OAI-04-prefix-robot-arm`：批次淘汰；机械臂复制前缀。
- `R1-OAI-05-cache-echo-type`：批次淘汰；银紫字体回声。

对应图片位于 `assets/rejected-covers/round1/`，提示词位于 `references/rejected-prompts/round1/`。

### 无图提示词

NB-01 至 NB-10 全部批次淘汰。已保存半透明芯片、双层高架、磁带、抽屉、折纸、红蓝编辑、双时间光轨、共享根系、服务器产品、回声波纹等提示词。

## Round 2

### 有图反例

- `R2-IG2-02-violet-cyan-split`：批次淘汰；静态紫青架构分屏。
- `R2-IG2-03-enterprise-console`：批次淘汰；企业悬浮控制台。
- `R2-IG2-04-silver-sculpture`：批次淘汰；银色抽象雕塑。
- `R2-IG2-06-teal-xray`：批次淘汰；青绿 X-ray 模块。
- `R2-IG2-07-glass-ribbon`：批次淘汰；玻璃丝带、高亮穿越文字区风险。
- `R2-IG2-08-cache-portals`：批次淘汰；双层缓存门户。
- `R2-IG2-09-minimal-stage`：批次淘汰；极简舞台、主体关系偏弱。
- `R2-IG2-10-scifi-landscape`：批次淘汰；科幻地景。

对应图片位于 `assets/rejected-covers/round2/`，提示词位于 `references/rejected-prompts/round2/`。

### 无图提示词

NB2-02、03、04、05、06、08、09、10 全部批次淘汰。已保存芯片微距、指挥中心、液态玻璃、杂志分栏、模块空间、数据峡谷、金属字体、服务器阵列等提示词。

## 生成前使用方法

1. 从新 prompt 中提取主体、背景、版式和材质词。
2. 在 `rejected-prompts/` 中用 `rg` 搜索相同关键词。
3. 若命中批次淘汰提示词，不直接复用；必须在主体关系、构图或媒介中至少改变两项。
4. 若命中明确原因的反例，必须消除对应问题后才能生成。

## Round 3

- 有图反例 6 张：IG3-01、IG3-02、IG3-05、IG3-06、IG3-08、IG3-09。
- 无图淘汰方向 9 个：NB3-01、NB3-02、NB3-03、NB3-04、NB3-05、NB3-06、NB3-07、NB3-09、NB3-10。
- 图片位置：`assets/rejected-covers/round3/`
- 提示词位置：`references/rejected-prompts/round3/R3-rejected-prompts.md`

## Round 4 ImageGen

- 有图反例 7 张：IG4-02、IG4-03、IG4-05、IG4-06、IG4-07、IG4-09、IG4-10。
- 图片位置：`assets/rejected-covers/round4/`。
- 提示词摘要：`references/rejected-prompts/round4/R4-imagegen-rejected-prompts.md`。
- 证据：批次淘汰；禁止直接复刻，但不推断整类艺术风格永久不可用。

## Round 5 ImageGen

- 有图反例 8 张：IG5-02、IG5-03、IG5-04、IG5-05、IG5-06、IG5-07、IG5-08、IG5-09。
- 图片位置：`assets/rejected-covers/round5/`。
- 提示词摘要：`references/rejected-prompts/round5/R5-imagegen-rejected-prompts.md`。
- IG5-01 与 IG5-10 为弱正向，不属于反例；其余为批次淘汰，不推断逐张失败原因。

## Round 6 智能涌现文章

- 有图反例 7 张：R01、R02、R03、E02、E03、E04、E05。
- 图片位置：`assets/rejected-covers/round6/`。
- 提示词摘要：`references/rejected-prompts/round6/R6-ai-emergence-rejected-prompts.md`。
- E01、R04、R05 分别为强正向、正常通过、弱正向，不属于反例。
