# 实现

---

### HTML 部分：

    <canvas> 元素用于创建绘图区域。

### CSS 部分：

    html, body 的样式设置了页面的边距和滚动行为，使其在页面中占据整个空间且没有滚动条。

### JavaScript 部分：

* 首先，通过 `document.querySelector` 获取 `<canvas>` 元素的引用，并使用 `getContext('2d')` 获取绘图上下文对象。

* `mouseMoved` 变量用于跟踪鼠标是否移动过。
* `pointer` 对象表示画笔的当前位置，初始位置为窗口中心。
* `params` 对象包含了一些参数，用于控制画笔的行为，比如点的数量、宽度因子、弹性和摩擦力。
* `trail` 数组用于存储画笔轨迹的点的信息。
* 通过监听鼠标事件和触摸事件，更新画笔位置。
* `setupCanvas` 函数用于设置画布的大小，使其与窗口大小保持一致。
* `update`
  函数是动画的主要逻辑。它首先根据鼠标是否移动过来更新画笔位置，然后清空画布。接下来，对于每个点，根据前一个点的位置和参数中的弹性和摩擦力来更新点的位置。然后，使用 `ctx.quadraticCurveTo`
  方法绘制曲线，以创建平滑的笔迹效果。最后，使用 `ctx.stroke` 方法绘制路径。`requestAnimationFrame`
  方法用于循环调用 `update` 函数，以实现动画效果。
* 在页面加载完成后，调用 `setupCanvas` 函数进行初始化，并调用 `update` 函数开始动画。

* 通过修改参数 `pointsNumber`、`widthFactor`、`spring` 和 `friction` 的值，你可以调整画笔的行为和笔迹效果。试着修改这些参数的值，然后观察画布上的动画效果如何变化。
