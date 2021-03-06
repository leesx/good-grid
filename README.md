### grid网格布局使用指南

[在线demo](https://lishangxi.cn/grid/)

#### 网格布局父元素的属性使用

> grid-template-rows 定义网格布局的行;

- 将高度(注意:要设置height)平分三份

```
.container{
    grid-template-rows:1fr 1fr 1fr; //
}
```

- 将高度设置为固定值

```
.container{
    grid-template-rows:100px 100px 100px; //或者写为 repeate(100px)
}
```
- 给每个行起个名字

```
.container {
  grid-template-columns: [first] 40px [line2] 50px [line3] auto [col4-start] 50px [five] 40px [end];
  grid-template-rows: [row1-start] 25% [row1-end] 100px [third-line] auto [last-line];
}
```
![demo](https://segmentfault.com/img/remote/1460000012889805?w=514&h=365)

> grid-tempe-columns 定义网格布局的列

用法可以参考grid-template-rows

> grid-gap 复合属性,定义网格布局中行列之间的间隔大小。

.container{
    grid-gap:10px 10px; // [行间隔 列间隔]
}

> justify-items 定义网格布局中的子元素的水平布局,可取值 [start | end | center | stretch]

> align-items 定义网格布局中的子元素的垂直方向的布局,可取值 [start | end | center | stretch]


#### 实现1px边框

grid还没轻松设置元素边框的属性，希望以后有相关的属性，现在只能通过近似hack的方式做到。下面介绍一个

给父级元素设置`background-color: rgb(198,164,154);grid-gap:1px;border: 1px solid rgb(198,164,154);`;
给子元素设置 背景色 `background-color: #fff;`

```
.grid {
  display: grid;
  grid-template-columns: repeat(3,100px);
  width: 304px;
  grid-template-rows: repeat(3, 100px);
  background-color: rgb(198,164,154);
  grid-gap:1px;
  border: 1px solid rgb(198,164,154);
}

.grid > * {
  background-color: #fff;
  padding: 20px;
}
```

或者给子元素直接设置边框，通过margin负值间接实现。


> demo1 图文混排

![demo21](./images/demo1.png)

> demo2 百度热词

![demo2](./images/demo2.png)

> demo3 百度新闻

![demo3](./images/demo3.png)

> demo4 淘宝精选

![demo4](./images/demo4.png)

> demo5 品质生活家

![demo5](./images/demo5.png)

> demo1 九宫格

![demo6](./images/demo6.png)

> demo7 魔盒演示

![demo7](./images/demo7.png)

