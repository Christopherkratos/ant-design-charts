

title: 仪表盘

## order: 22

### 图表容器

#### width

<description>**optional** _number_ _default:_ `400`</description>

设置图表宽度。

#### height

<description>**optional** _number_ _default:_ `400`</description>

设置图表高度。

#### autoFit

<description>**optional** _boolean_ _default:_ `true`</description>

图表是否自适应容器宽高。当 `autoFit` 设置为 true 时，`width` 和 `height` 的设置将失效。

#### padding

<description>**optional** _number\[] | number | 'auto'_</description>

画布的 `padding` 值，或者开启 `auto`。

#### appendPadding

<description>**optional** _number\[] | number_</description>

额外增加的 `appendPadding` 值。

#### renderer

<description>**optional** _string_ _default:_ `canvas`</description>

设置图表渲染方式为 `canvas` 或 `svg`。

#### pixelRatio

<description>**optional** _number_ _default:_ `window.devicePixelRatio`</description>

设置图表渲染的像素比。


### 数据映射

#### percent

<description>**required** _number_</description>

指标比例。

#### radius

<description>**optional** _number_ _default:_ `0.95`</description>

圆盘的外半径，0 ~ 1。 

#### innerRadius

<description>**optional** _number_ _default:_ `0.9`</description>

圆盘的内半径，0 ~ 1。

#### startAngle

<description>**optional** _number_ _default:_ `(-7 / 6) * Math.PI`</description>

圆盘的起始角度。

#### endAngle

<description>**optional** _number_ _default:_ `(1 / 6) * Math.PI`</description>

圆盘的终止角度。

### 图形样式

#### range

<description>**optional** _object_</description>

仪表盘辅助圆弧的样式。

| 配置项   | 类型        | 描述                 |
| ----- | --------- | ------------------ |
| ticks | number\[] | 辅助圆弧显示数字数组         |
| color | string\[] | 辅助圆弧的颜色色板，按照色板顺序取值 |

#### indicator

<description>**optional** _object_</description>

仪表盘指示器样式配置。按照组件分成为：

-   `pointer`：指示器中的指针样式配置
-   `pin`：指示器中的圆盘样式配置

| 配置项   | 类型     | 描述     |
| ----- | ------ | ------ |
| style | object | 组件样式配置 |

#### statistic

<description>**optional** _object_</description>

指标文本组件。

| 配置项     | 类型                     | 描述   |
| ------- | ---------------------- | ---- |
| title   | false \| StatisticText | 标题   |
| content | false \| StatisticText | 主体内容 |

StatisticText

| 配置项       | 类型       | 描述         |
| --------- | -------- | ---------- |
| style     | object   | 统计文本的样式    |
| formatter | Function | 主体文本的格式化内容 |
| rotate    | number   | 旋转角度       |
| offsetX   | number   | X 偏移值      |
| offsetY   | number   | Y 偏移值      |


#### axis

<description>**optional** _object_</description>

指标辅助轴样式。

##### nice

<description>**optional** _boolean_ _default:_ `true`</description>

是否美化。

##### min

<description>**optional** _number_ _default:_ `0`</description>

坐标轴最小值。

##### max

<description>**optional** _number_</description>

坐标轴最大值。

##### minLimit

<description>**optional** _number_</description>

最小值限定。

##### maxLimit

<description>**optional** _number_</description>

最大值限定。

##### tickCount

<description>**optional** _number_</description>

期望的坐标轴刻度数量，非最终结果。

##### tickInterval

<description>**optional** _number_</description>

坐标轴刻度间隔。

##### tickMethod

<description>**optional** _string | Function_ _default:_ `false`</description>

指定 tick 计算方法，或自定义计算 tick 的方法，内置 tick 计算方法包括 `cat`、`time-cat`、 `wilkinson-extended`、`r-pretty`、`time`、`time-pretty`、`log`、`pow`、`quantile`、`d3-linear`。

##### position

<description>**optional** _`top` \| `bottom` \| `left` \| `right`_</description>

适用于直角坐标系，设置坐标轴的位置。

##### line

<description>**optional** _object_</description>

坐标轴线的配置项，null 表示不展示。

<!--线条样式-->

| 属性名           | 类型              | 介绍                                                         |
| ------------- | --------------- | ---------------------------------------------------------- |
| stroke        | string          | 线的颜色                                                       |
| lineWidth     | number          | 线宽                                                         |
| lineDash      | [number,number] | 虚线配置，第一个值为虚线每个分段的长度，第二个值为分段间隔的距离。lineDash 设为[0,0]的效果为没有描边。 |
| opacity       | number          | 透明度                                                        |
| shadowColor   | string          | 阴影颜色                                                       |
| shadowBlur    | number          | 高斯模糊系数                                                     |
| shadowOffsetX | number          | 设置阴影距图形的水平距离                                               |
| shadowOffsetY | number          | 设置阴影距图形的垂直距离                                               |
| cursor        | string          | 鼠标样式。同 css 的鼠标样式,默认 'default'。                             |

示例代码：

```ts
{
  xAxis: {
    grid: {
      line: {
        style: {
          stroke: 'black',
          lineWidth: 2,
          lineDash: [4, 5],
          strokeOpacity: 0.7,
          shadowColor: 'black',
          shadowBlur: 10,
          shadowOffsetX: 5,
          shadowOffsetY: 5,
          cursor: 'pointer'
        }
      }
    }
  }
}
```


##### tickLine

<description>**optional** _object_</description>

坐标轴刻度线线的配置项，null 表示不展示。

<!--线条样式-->

| 属性名           | 类型              | 介绍                                                         |
| ------------- | --------------- | ---------------------------------------------------------- |
| stroke        | string          | 线的颜色                                                       |
| lineWidth     | number          | 线宽                                                         |
| lineDash      | [number,number] | 虚线配置，第一个值为虚线每个分段的长度，第二个值为分段间隔的距离。lineDash 设为[0,0]的效果为没有描边。 |
| opacity       | number          | 透明度                                                        |
| shadowColor   | string          | 阴影颜色                                                       |
| shadowBlur    | number          | 高斯模糊系数                                                     |
| shadowOffsetX | number          | 设置阴影距图形的水平距离                                               |
| shadowOffsetY | number          | 设置阴影距图形的垂直距离                                               |
| cursor        | string          | 鼠标样式。同 css 的鼠标样式,默认 'default'。                             |

示例代码：

```ts
{
  xAxis: {
    grid: {
      line: {
        style: {
          stroke: 'black',
          lineWidth: 2,
          lineDash: [4, 5],
          strokeOpacity: 0.7,
          shadowColor: 'black',
          shadowBlur: 10,
          shadowOffsetX: 5,
          shadowOffsetY: 5,
          cursor: 'pointer'
        }
      }
    }
  }
}
```


##### subTickLine

<description>**optional** _object_</description>

坐标轴子刻度线的配置项，null 表示不展示。

<!--线条样式-->

| 属性名           | 类型              | 介绍                                                         |
| ------------- | --------------- | ---------------------------------------------------------- |
| stroke        | string          | 线的颜色                                                       |
| lineWidth     | number          | 线宽                                                         |
| lineDash      | [number,number] | 虚线配置，第一个值为虚线每个分段的长度，第二个值为分段间隔的距离。lineDash 设为[0,0]的效果为没有描边。 |
| opacity       | number          | 透明度                                                        |
| shadowColor   | string          | 阴影颜色                                                       |
| shadowBlur    | number          | 高斯模糊系数                                                     |
| shadowOffsetX | number          | 设置阴影距图形的水平距离                                               |
| shadowOffsetY | number          | 设置阴影距图形的垂直距离                                               |
| cursor        | string          | 鼠标样式。同 css 的鼠标样式,默认 'default'。                             |

示例代码：

```ts
{
  xAxis: {
    grid: {
      line: {
        style: {
          stroke: 'black',
          lineWidth: 2,
          lineDash: [4, 5],
          strokeOpacity: 0.7,
          shadowColor: 'black',
          shadowBlur: 10,
          shadowOffsetX: 5,
          shadowOffsetY: 5,
          cursor: 'pointer'
        }
      }
    }
  }
}
```


##### title

<description>**optional** _object_</description>

标题的配置项，null 表示不展示。

| 细分配置项名称    | 类型           | 功能描述         |
| ---------- | ------------ | ------------ |
| offset     | _number_     | 标题距离坐标轴的距离   |
| spacing    | _lineStyle_  | 标题距离坐标轴文本的距离 |
| style      | _shapeStyle_ | 标题文本配置项      |
| autoRotate | _boolean_    | 是否自动旋转       |

**_shapeStyle_**

<!--图形样式-->

| 属性名           | 类型              | 介绍                                                            |
| ------------- | --------------- | ------------------------------------------------------------- |
| fill          | string          | 图形的填充色                                                        |
| fillOpacity   | number          | 图形的填充透明度                                                      |
| stroke        | string          | 图形的描边                                                         |
| lineWidth     | number          | 图形描边的宽度                                                       |
| lineDash      | [number,number] | 描边的虚线配置，第一个值为虚线每个分段的长度，第二个值为分段间隔的距离。lineDash 设为[0,0]的效果为没有描边。 |
| lineOpacity   | number          | 描边透明度                                                         |
| opacity       | number          | 图形的整体透明度                                                      |
| shadowColor   | string          | 图形阴影颜色                                                        |
| strokeOpacity | number          | 图形边框透明度                                                       |
| shadowBlur    | number          | 图形阴影的高斯模糊系数                                                   |
| shadowOffsetX | number          | 设置阴影距图形的水平距离                                                  |
| shadowOffsetY | number          | 设置阴影距图形的垂直距离                                                  |
| cursor        | string          | 鼠标样式。同 css 的鼠标样式，默认 'default'。                                |

示例代码：

```ts
{
  style: {
    fill: 'red',
    fillOpacity: 0.5,
    stroke: 'black',
    lineWidth: 1,
    lineDash: [4, 5],
    strokeOpacity: 0.7,
    shadowColor: 'black',
    shadowBlur: 10,
    shadowOffsetX: 5,
    shadowOffsetY: 5,
    cursor: 'pointer'
  }
}
```


**_label_**

<description>**optional** _object_</description>

文本标签的配置项，null 表示不展示。

<!--label样式-->

| 属性名          | 类型                                                         | 介绍                                                      |
| ------------ | ---------------------------------------------------------- | ------------------------------------------------------- |
| type         | string                                                     | 当用户使用了自定义的 label 类型，需要声明具体的 type 类型，否则会使用默认的 label 类型渲染 |
| offset       | number                                                     | label 的偏移量                                              |
| offsetX      | number                                                     | label 相对于数据点在 X 方向的偏移距离                                 |
| offsetY      | number                                                     | label 相对于数据点在 Y 方向的偏移距离                                 |
| content      | string \| IGroup \| IShape \| GeometryLabelContentCallback | 展示的文本内容，如果不声明则按照参与映射的第一字段的值进行显示                         |
| style        | object                                                     | label 文本图形属性样式                                          |
| autoRotate   | string                                                     | 是否自动旋转，默认 true                                          |
| rotate       | number                                                     | 文本旋转角度                                                  |
| labelLine    | null \| boolean \|object                                   | 用于设置文本连接线的样式属性，null 表示不展示。                              |
| labelEmit    | boolean                                                    | 只对极坐标下的文本生效，表示文本是否按照角度进行放射状显示，true 表示开启，false 表示关闭      |
| layout       | 'overlap' \| 'fixedOverlap' \| 'limitInShape'              | 文本布局类型，支持多种布局函数组合使用。                                    |
| position     | 'top' \| 'bottom' \| 'middle' \| 'left' \| 'right'         | 指定当前 label 与当前图形的相对位置                                   |
| animate      | boolean \| AnimateOption                                   | 动画配置。                                                   |
| formatter    | Function                                                   | 格式化函数                                                   |
| autoHide     | boolean                                                    | 是否自动隐藏，默认 false                                         |
| autoEllipsis | boolean                                                    | 是否自动省略，默认 false                                         |

示例代码：

```ts
{
  label: {
    style: {
      fill: 'red',
      opacity: 0.6,
      fontSize: 24
    },
    rotate: true
  }
}
```


##### grid

<description>**optional** _object_</description>

坐标轴网格线的配置项，null 表示不展示。

| 细分配置项名称        | 类型                  | 功能描述                            |
| -------------- | ------------------- | ------------------------------- |
| line           | _lineStyle_         | 线的样式                            |
| alternateColor | _string\|string\[]_ | 两个栅格线间的填充色                      |
| closed         | _boolean_           | 对于 circle 是否关闭 grid             |
| alignTick      | _boolean_           | 是否同刻度线对齐，如果值为 false，则会显示在两个刻度中间 |

**_lineStyle_**

<!--线条样式-->

| 属性名           | 类型              | 介绍                                                         |
| ------------- | --------------- | ---------------------------------------------------------- |
| stroke        | string          | 线的颜色                                                       |
| lineWidth     | number          | 线宽                                                         |
| lineDash      | [number,number] | 虚线配置，第一个值为虚线每个分段的长度，第二个值为分段间隔的距离。lineDash 设为[0,0]的效果为没有描边。 |
| opacity       | number          | 透明度                                                        |
| shadowColor   | string          | 阴影颜色                                                       |
| shadowBlur    | number          | 高斯模糊系数                                                     |
| shadowOffsetX | number          | 设置阴影距图形的水平距离                                               |
| shadowOffsetY | number          | 设置阴影距图形的垂直距离                                               |
| cursor        | string          | 鼠标样式。同 css 的鼠标样式,默认 'default'。                             |

示例代码：

```ts
{
  xAxis: {
    grid: {
      line: {
        style: {
          stroke: 'black',
          lineWidth: 2,
          lineDash: [4, 5],
          strokeOpacity: 0.7,
          shadowColor: 'black',
          shadowBlur: 10,
          shadowOffsetX: 5,
          shadowOffsetY: 5,
          cursor: 'pointer'
        }
      }
    }
  }
}
```


##### animate

<description>**optional** _boolean_ _default:_ `true`</description>

动画开关，默认开启。

##### animateOption

<description>**optional** _object_</description>

动画参数配置。

```ts
interface ComponentAnimateCfg {
  /** 动画执行时间 */
  readonly duration?: number;
  /** 动画缓动函数 */
  readonly easing?: string;
  /** 动画延迟时间 */
  readonly delay?: number;
}
// 配置参考
{
  animateOption: {
    appear: ComponentAnimateCfg;
    update: ComponentAnimateCfg;
    enter: ComponentAnimateCfg;
    leave: ComponentAnimateCfg;
  }
}
```

##### verticalFactor

<description>**optional** _number_</description>

标记坐标轴 label 的方向，左侧为 1，右侧为 -1。

##### verticalLimitLength

<description>**optional** _number_</description>

配置坐标轴垂直方向的最大限制长度，对文本自适应有很大影响。
