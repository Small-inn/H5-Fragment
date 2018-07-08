## 基本概念: 
    使用flex布局首先设置父容器的display:flex,使用justify-content:center 实现水平居中，然后设置align-item:center实现垂直居中。
    flex的核心概念就是容器和轴。容器包括外层容器和子容器、轴包括主轴和交叉轴。
    flex布局涉及12个css属性，父、子容器各6各，常用的只有4个
### 容器:
    特点: 父容器可以统一设置子容器的排列方式，子容器也可以单独的设置自身的排序方式，
    如果两者同时设置，以子容器的设置为准。

#### 父容器:
    1.设置子容器沿主轴排序:
    justify-content(属性用于定义如何沿着主轴方向排列子容器)
    属性值:
    flex-start 起始端对其,
    flex-end:末端对齐，
    center:居中对齐，
    space-around:子容器沿主轴均匀分布，位于首尾端的子容器到父容器的距离是子容器的一半
    space-between: 子容器沿主轴均匀分布，位于首尾两端的子容器与父容器相切
    2.设置子容器如何沿交叉轴排序：
      align-items(属性用于定义如何沿着交叉轴方向分配子容器的间距)
    * 位置排序
        flex-start:起始端对齐
        flex-end:末端对齐
        center:居中对齐
    * 基线排序
        baseline:基线对齐(默认是首行文字)
    * 拉伸排序
        stretch:子容器沿交叉轴方向的尺寸拉伸至父容器一致
#### 子容器:
    > 子容器是具有弹性的，它会自动填充剩余的空间，子容器的伸缩比例是由flex属性定义的。
    flex的值是多个属性的缩写，允许1-3个值连用，通常的一个值就可以满足需求
    * 一个值：
        带单位的 例如:flex-basis:10rem
        不带单位的 例如:flex-grow:1
    * 两个值:
        flex-grow|flex-basis: 1 30px
        flex-grow|flex-shink: 1 2
    * 三个值:
        flex-grow|flex-shink|flex-basis: 1 1 10%

    > 单独设置子容器如何沿交叉轴排序:align-self,这里呢，因为每个子容器
    也可以单独设置定义沿交叉轴排列的方式，因此当该属性的属性值与父容器align-items属性完全一致，
    如果两者同时设置则以子容器的align-self的属性为准
    * 属性值与父容器的align-items属性值相同


### 轴
    > 轴包括主轴和交叉轴，justify-content属性决定子容器沿主轴的排列方式，
    align-items属性决定子容器沿着交叉轴的排列方式。
    在布局中，flex-direction 属性决定主轴方向，交叉轴的方向由主轴确定。
    flex-direction:row(向右)|column(向下)|row-reverse(向左)|column-reverse(向上)


## flex的进阶知识
    1.父容器
        * 设置换行方式: flex-wrap 决定子容器是否可以换行排列。
        属性值：nowrap(不换行)|wrap(换行)|wrap-reverse(方向换行)
        * 轴向与换行组合设置:flex-flow flow即流向，也就是子容器往哪个方向流动，流动到终点是否容许换行
        flex-flow是一个复合属性，相当于flex-direction与flex-wrap的组合，例如：flex-flow: row wrap。
        * 多行沿交叉轴对齐:align-content 当子容器多行排列是，设置行与行之间的对齐方式
    2.子容器
        * 设置基准大小：flex-basis：120px 表示在不伸缩的情况下子容器的原始尺寸。主轴为横向时代表宽度，主轴为纵向时为高度
        * 设置扩展比例：flex-grow：1  表示子容器弹性伸缩的比例
        * 设置收缩比例：flex-shrink: 1 表示子容器弹性收缩的比例