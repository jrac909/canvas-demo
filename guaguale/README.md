## description
一个简单的刮刮乐刮奖效果。

## 分析
我们可以用两层结构，让 canvas 画布覆盖在奖品信息上，鼠标拖过的地方就清空画布内容，显示出画布下方的奖品信息。

## 要点
1. 要用到的三个事件：mousedown(鼠标按下), mousemove(鼠标移动), mouseup(鼠标放开)，通过标识 isDrag 来控制只有鼠标按下的时候移动，才清空对应区域。
2. 怎么清空画布内容，在 canvas 中提供的清空方式只有 clearRect，我们如何清除自定义形状的区域呢。转换思路，canvas 提供了一种混合属性，globalCompositeOperation，这里我们只讲 'destination-out', 这个值表示新绘制的区域如果和之前绘制的部分有重叠，则清空当前绘制的区域，这样就刚好实现了想要的效果。
3. 利用 css user-select: none; 属性禁用用户拖动鼠标选中文字。