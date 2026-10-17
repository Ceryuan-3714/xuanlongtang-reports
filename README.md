# 玄龙堂研究报告

[在线查看52条日线报告](https://ceryuan-3714.github.io/xuanlongtang-reports/)

大火苗B → 蓝柱C → 小火苗A → 触发蓝柱S → 后续10根日线。

信号筛选范围：2026-09-03—2026-10-03；使用2026-10-03归档，行情截至2026-09-30。
52条信号、39个合约；29条完整后10根、23条不足。数据未更新至当前日期。

- `index.html`：独立交互报告，包含52张K线及成交量图。
- `results.json`：逐条证据和后续K线，原始内部日线时间为交易日期次日零点；网页已还原交易日期。
- `summary.json`：聚合统计。

仅用于历史行情研究，不构成投资建议或收益承诺。不包含手续费、滑点和期权价值变化；相关合约和重叠信号不是独立样本。

## 最新 V3 全蓝间隔报告

[在线查看64个符合点](https://ceryuan-3714.github.io/xuanlongtang-reports/v3-blue-candles/report.html)

十品种2026年4—8月五周期及沥青2026年9月60/15分钟，共52组归档。原生周期61点，合成240分钟参考3点；另2点因历史价格差异单独保存。大小火苗之间全部蓝K；红区起止允许±2根偏移，B红面积>A，A AA峰值>B。只展示符合点，默认实际确认点前后各50根，末尾不足注明实际数量。

背离点标在小火苗后第一根蓝K，可跳过十字星；先出现新红K则原配对不算。算法匹配确认时间单独记录，图表及CSV均以背离点为定位。2026年10月11日更新。

## V3 v9 完整红区与5根双向唯一对应

[新规则报告](https://ceryuan-3714.github.io/xuanlongtang-reports/v3-blue-candles/report.html) · [保留的v8旧规则报告](https://ceryuan-3714.github.io/xuanlongtang-reports/v3-blue-candles-v8/report.html)

2026年10月17日按新规则重算52组原归档。完整红区两侧均有蓝区；区间最近距离≤5根；红区和火苗双向一一对应；取消峰值高低比较。1355段完整红区，1349段因对应多个火苗排除，6段单向唯一，3段双向唯一，最终0个合格配对。98项测试及独立批处理全量复核通过。没有抓取截至今日的新行情，生产后端未部署。

## V3 v10 完整区间偏移对应及相邻区块

[最新报告](https://ceryuan-3714.github.io/xuanlongtang-reports/v3-blue-candles/report.html?version=v10) · [v9存档](https://ceryuan-3714.github.io/xuanlongtang-reports/v3-blue-candles-v9/report.html) · [v8存档](https://ceryuan-3714.github.io/xuanlongtang-reports/v3-blue-candles-v8/report.html)

完整红区与完整火苗首尾偏移分别≤5根，双方唯一最优互选后形成区块，只比较相邻区块。保留先大后小、价格创新高、红区面积减小及中间全蓝K，无峰值门槛。52组原归档120874根K线独立复核，7个符合点，展示第一蓝K前后各50根。106项测试通过。未更新行情到今天；生产后端未部署。

## V3 v11 火苗60%动态偏移

[最新报告](https://ceryuan-3714.github.io/xuanlongtang-reports/v3-blue-candles/report.html?version=v11) · [v10存档](https://ceryuan-3714.github.io/xuanlongtang-reports/v3-blue-candles-v10/report.html)

每个完整火苗允许偏移=ceil(火苗K线数量×60%)，首尾分别检查，大小火苗独立计算；5根火苗允许3根偏移。其余完整红区、双向唯一最优互选、相邻区块比较、价格面积及中间全蓝K规则保持。52组原归档120874根K线独立复核，6个符合点，前后各50根；108项测试通过。生产后端未部署。

## V3 v12 新增小火苗全蓝窗口路径

[最新报告](https://ceryuan-3714.github.io/xuanlongtang-reports/v3-blue-candles/report.html?version=v12) · [v11存档](https://ceryuan-3714.github.io/xuanlongtang-reports/v3-blue-candles-v11/report.html)

保留完整大小红区面积缩小路径，新增：前面大火苗已对应完整大红区，后面小火苗按自身R=ceil(K线根数×60%)向前后各扩展R根，整个窗口S10103严格全蓝，也满足指标条件。大小、价格新高、中间全蓝K和第一蓝K背离点条件仍检查。未知数据、中性和红区不算全蓝；不伪造A红区。52组归档独立复核，5144个全蓝窗口候选最终新增0个，原6点保留。112项测试通过；各点前后50根K线。生产后端未部署。
