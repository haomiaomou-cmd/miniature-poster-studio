# Prompt 模板与配方库

## 六维风格分析框架

对每张参考海报按以下维度分析，结论直接填入 prompt 模板变量：

1. **标题字体与占比**：超大字/中字？圆润粗体/衬线/空心描线？占画面宽度比例？位于何处？
2. **图文层次关系**：主体与标题谁前谁后？文字是否被主体遮挡/叠压？
3. **点缀元素**：丝带标签、圆形徽章、手写体、印章、竖排小字、英文小标等
4. **配色方案**：背景色（纯色/环境）与主体色的关系（同色系/互补撞色），总色数
5. **版式结构**：四角信息块的位置与内容（品牌名、徽章、slogan、注脚）
6. **整体气质**：微缩趣味商业广告 / 瑞士极简 / 杂志编辑 / 复古等

## 首次生成模板（微缩创意摄影风格）

```
Miniature scale creative advertising photography poster, in the style of
Tatsuya Tanaka miniature calendar dioramas.
Keep the [主体描述，必须具体，如 a cake shaped like a torn-open coffee sack
filled with glossy chocolate coffee-bean candies] from image1 exactly as the
hero subject, placed on [背景描述：主体自身环境如 a fine cocoa-powder ground /
或纯色 studio backdrop].
Transform the scene into a playful miniature world: tiny 1:87 scale human
figurines interact with the subject - [动作1，如 one tiny worker climbing a
small wooden ladder against the pouch], [动作2，如 two tiny figures pushing
a miniature wheelbarrow loaded with a giant coffee bean], [动作3，可选，如
one tiny worker shoveling cocoa powder in the foreground].
Background: [纯色/环境背景描述], monochrome, minimal, no texture, generous
negative space at the top.
Design-forward large Chinese title "[标题词，2~6字]" in the upper area above
the subject, using the staggered mixed typography recipe (see below),
followed by a thin letter-spaced English caption "[英文小标]" underneath
(follow the overall typography layout style of the reference poster image2).
[点缀元素，如 A small red ribbon-shaped label reading "[点缀词]" near the
title.]
Top-left corner: small brand text block "[品牌词]".
Top-right corner: [右上元素，见四角信息配方].
Bottom-left corner: one short slogan line "[中文slogan]" in small white
text, exactly this short text and nothing else, spelled correctly.
Bottom-right corner: a small clean white English typography note
"[英文注脚]" on a single line, very small and subtle, spelled correctly.
Absolutely NO color swatch square, NO solid square accent, NO date or time
anywhere on the poster.
Only [N] colors total: [色1], [色2], [主体色], [点缀色].
Realistic studio photography lighting, soft shadows, high detail, vertical
poster format.
```

## 设计感标题配方（Design-forward Title Recipes）

标题默认选用以下一种或两种组合，在 prompt 中具体描述排版细节：

1. **错落混排**：四字标题拆成两行错位排布（如"豆趣"上、"时光"右下沉落），字号字重混搭（大字实心 + 略小字）
2. **空心描边字**：标题中 1 个字改为 hollow outline style，其余实心，形成对比
3. **英文小标**：标题正下方加一行字距拉开的 letter-spaced 小写英文 caption（如 "COFFEE TIME"），细体
4. **竖排印章风**：单列竖排 + 仿印章点缀（适合国风/节日主题）
5. **手写感斜向流动**（实战验证通过）：四字沿左上→右下的斜向流动排布，各字高低参差，统一使用半行书毛笔手写体（consistent semi-cursive brush style, visible ink-stroke texture, consistent stroke weight）——注意：同一标题内不要混用圆润实心字、空心字与手写体（用户实测反馈不统一），字体风格必须统一；设计感靠错落高低、大小节奏与丝带印章实现；丝带标签微倾贴于标题侧下方似印章钤印；英文小标末端加手绘下划线笔触。适合标题区留白较大、需要与居中主体形成呼应的构图

Prompt 表述示例（实战验证通过）：
> arrange the four characters along a gentle diagonal flow from upper-left to lower-right, "花" largest in solid rounded heavy style, "漾" medium size in hollow outline style, "时光" in an elegant semi-cursive handwritten brush style with visible ink-stroke texture and slightly varying character sizes, each character naturally offset at different heights instead of a rigid baseline; place the red ribbon label tilted slightly, attached to the lower right like a stamping seal

6. **场景几何呼应式**（实战验证通过）：先观察主体场景的空间几何特征（棋盘格对角线、圆形餐盘弧线、垂直堆叠线等），让标题字沿同一几何线排布。如棋盘格场景 → 四字沿对角线"阶梯式下落"（each character stepping down along the same diagonal line as the checkerboard squares, like steps descending a staircase，一字最高、视觉锚字最大居中、末字最低），丝带印章移至末字下方作"收官钤印"，英文小标水平置于对角线起点侧。让排版成为场景叙事的延伸

Prompt 表述示例（实战验证通过）：
> the four unified handwritten brush calligraphy characters now step down along the SAME diagonal line as the checkerboard paper squares on the ground, like steps descending a staircase, each character sitting clearly at a different height with generous spacing, echoing the diagonal rhythm of the checkerboard; the red ribbon label moves to sit directly beneath the last character like a final stamp

7. **左缘竖排呼应塔形**（实战验证通过）：主体为垂直塔状（叠放食物、堆叠物）且居中/偏右时，标题沿海报左缘竖排成单列，与塔的垂直轮廓呼应；"首字最大在上，其余渐小下延"，丝带印章贴于竖列末端下方，英文小标横排于竖列底部。此布局同时为右侧主体让出完整空间

Prompt 表述示例（实战验证通过）：
> rendered VERTICALLY as a single top-to-bottom column along the left edge of the poster, echoing the vertical silhouette of the muffin tower on the right, "麦" at the top as the largest character, the others slightly smaller descending below it with subtle size rhythm; the red ribbon label attached right below the column like a stamping seal

**品牌名串词规避（实战验证）**：版式参照图中的品牌词（如"咖啡工坊"）是四角中最顽固的串词源，即使 prompt 显式声明也可能首轮保留。对策：① 主体与参照图品类差异大时，优先选品类相近的参照图；② 或首轮生成不带品牌文案，品牌留到单独一轮迭代加入；③ 右上角英文注脚同理，首轮后逐一核对。

Prompt 表述示例（实战验证通过）：
> arrange the four characters in a staggered two-line layout with mixed sizes and mixed weights ("豆趣" larger bold solid, "时光" slightly smaller), make the character "趣" a hollow outline-style character while others stay solid, add a thin elegant English caption "COFFEE TIME" in letter-spaced small caps right under the title

## 四角信息配方（Four-Corner Information）

四角默认全配齐，右上角不得空缺。右上角元素可选：

- **双行小字**：two short lines of tiny letter-spaced white English text（如 "MINIATURE COFFEE DIORAMA"）aligned to the right edge, very small and subtle —— 实战验证通过
- **圆形徽章**：A small round badge reading "[徽章词，如 源自新疆 / SINCE 2012]"
- **竖排小字**：侧边竖排英文或中文小字（适合留白多的极简构图）

Prompt 表述示例（实战验证通过）：
> add a small text element in the top-right corner: two short lines of tiny letter-spaced white English text "MINIATURE COFFEE DIORAMA" aligned to the right edge, very small and subtle, exactly this text and nothing else, spelled correctly

## 迭代修改模板

```
Keep this poster exactly as it is: [逐一复述要保留的元素——主体、小人、
标题、点缀标签、各角落文案]. ONLY ONE CHANGE: [仅描述本次改动].
Everything else stays identical.
```

两个相关布局改动合并时，将 "ONLY ONE CHANGE" 改为 "ONLY TWO CHANGES:" 并逐条列出；超过两个改动拆成多轮。删除元素用 "remove X entirely, leave the area empty"。文字被挤掉没渲染时，把位置描述改得更具体（如 "slightly above the very bottom edge, to the right of [某个具体小人]"）后重试一次；连续两次失败则建议该处留白。

**已知失败模式（实战两次验证）**：使用旧成品/参照海报作 image2 时，四角文案极易串用参照图的文字（即使 prompt 已显式声明新文案，首次生成仍可能串词）。对策：首轮生成后立即按迭代模板用 "ONLY CORRECT THE FOUR CORNER TEXT BLOCKS:" 一轮修正（实测一轮成功）；或将四角文案留给第二轮迭代再加，首轮专注主体与标题。

**已知失败模式 2（实战验证）**：手写/毛笔字体渲染笔画复杂的汉字（如"流""蜜"）时容易写成错字，且重试仍可能失败。对策：slogan 选笔画简单的词（如"一口酥香 满口酥脆"），或左下 slogan 声明用印刷体小字而非手写体；某段小字连续两轮渲染失败后放弃重试，改词或留白。

## 标题词选择规则

优先用主体英文词或核心卖点词的中文对应（咖啡豆→"豆趣时光"、瓜子→"嗑点时光"），2~6 字；英文场景直接用主体词（COFFEE / NUTS / FRESH），3~8 字母为佳。

## 右下角注脚参考库

| 主体类型 | 注脚示例 |
|---------|---------|
| 咖啡/咖啡豆 | 100% ARABICA / FRESHLY ROASTED |
| 坚果/零食 | 100% NATURAL / CRUNCHY & FRESH |
| 水果/农产品 | ORCHARD FRESH / SINGLE ORIGIN |
| 烘焙/点心 | HANDMADE DAILY / SINCE 2012 |
| 巧克力 | 70% COCOA / BEAN TO BAR |

若主体在右下角附近活动的小人较多、空间不足，删除注脚描述，改为 "leave the bottom-right corner empty"。

## 微缩小人动作库

按主体类型选择呼应的叙事动作：

| 主体类型 | 动作示例 |
|---------|---------|
| 食物/零食 | 爬梯攀爬、推独轮车运"巨型食材"、铲挖粉末、搬运糖粒 |
| 饮品 | 乘小船漂浮于液面、垂钓、沿杯壁攀岩 |
| 乐器/物品 | 演奏、滑板/赛车于物品表面、悬挂旗帜 |
| 农产品 | 收割、装卸麻袋、驾驶微型卡车 |
