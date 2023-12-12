# CSS

### 盒子模型

**外边距（margin）+ border（边框） + 内边距（padding）+ content（内容）** ，可以把每一个容器，比如div，都看做是一个盒子模型：

如果给DIV设置长宽为500px，这样设置只是设置content，如果再设置padding为10px，border为1px，那么整个DIV的宽高就变成544（500+40+4）

![CSS box-model](https://www.runoob.com/images/box-model.gif)

如果使用了box-sizing: border-box，**padding和border的值就不会在影响元素的宽高，相当于把padding和border的值都算在content里，盒子模型会自动根据padding和border的值来调整content的值，就不需要手动调整**

### flex

采用 Flex 布局的元素，称为 Flex 容器（flex container），简称"容器"。它的所有子元素自动成为容器成员，称为 Flex 项目（flex item），简称"项目"。

```html
display: flex;
```

![](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071004.png)

容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做`main start`，结束位置叫做`main end`；交叉轴的开始位置叫做`cross start`，结束位置叫做`cross end`。

项目默认沿主轴排列。单个项目占据的主轴空间叫做`main size`，占据的交叉轴空间叫做`cross size`。

flex是一种自适应的布局方式，对父元素下的子元素生效，孙级元素不包含，子元素默认排列方式是横着排。

#### 容器的6个属性

1. ###### flex-direction: 决定主轴的方向(即项目的排列方向)
   
   row | row-reverse | column | column-reverse
   
   ```css
   .container {
       flex-direction: row | row-reverse | column | column-reverse;
   }
   ```
   
   默认值：row，主轴为水平方向，起点在左端。![](https://pic2.zhimg.com/80/v2-ae8828b8b022dc6f1b28d5b4f7082e91_720w.jpg)
   
   row-reverse：主轴为水平方向，起点在右端![](https://pic3.zhimg.com/80/v2-215c8626ac95e97834eddb552cfa148a_720w.jpg)
   
   column：主轴为垂直方向，起点在上沿![](https://pic1.zhimg.com/80/v2-33efe75d166a47588e0174d0830eb020_720w.jpg)
   
   column-reverse：主轴为垂直方向，起点在下沿![](https://pic2.zhimg.com/80/v2-344757e0fb7eee11e75b127b8485e679_720w.jpg)

2. ###### flex-wrap: 决定容器内项目是否可换行默认情况下，项目都排在主轴线上，使用 flex-wrap 可实现项目的换行
   
   nowrap | wrap | wrap-reverse;
   
   ```css
   .container {
       flex-wrap: nowrap | wrap | wrap-reverse;
   }
   ```
   
   默认值：nowrap 不换行，即当主轴尺寸固定时，当空间不足时，项目尺寸会随之调整而并不会挤到下一行。
   
   ![](https://pic4.zhimg.com/80/v2-a590927ad6d83de8840d52a0cf2f0df3_720w.jpg)
   
   wrap：项目主轴总尺寸超出容器时换行，第一行在上方
   
   ![](https://pic2.zhimg.com/80/v2-426949b061e8179aab00cacda8168651_720w.jpg)
   
   wrap-reverse：换行，第一行在下方
   
   ![](https://pic2.zhimg.com/80/v2-91c53ebf744814e1ab60267643866439_720w.jpg)

3. ###### flex-flow: flex-direction 和 flex-wrap 的简写形式
   
   ```css
   .container {
       flex-flow: <flex-direction> || <flex-wrap>;
   }
   ```
   
   默认值为: row nowrap，感觉没什么卵用，老老实实分开写就好了。这样就不用记住这个属性了。

4. ###### justify-content：定义了项目在主轴的对齐方式
   
   flex-start | flex-end | center | space-between | space-around
   
   ```css
   .container {
       justify-content: flex-start | flex-end | center | space-between | space-around;
   }
   ```
   
   建立在主轴为水平方向时测试，即 flex-direction: row
   
   默认值: flex-start 左对齐
   
   ![](https://pic1.zhimg.com/80/v2-1bafab80044a7ab2a6198d5937172eb0_720w.jpg)
   
   flex-end：右对齐![](https://pic3.zhimg.com/80/v2-8b163809a4c944486a127a7c22eee7b2_720w.jpg)
   
   center：居中![](https://pic4.zhimg.com/80/v2-dea82c75d35f532d35a52d1f9c1c762b_720w.jpg)
   
   space-between：两端对齐，项目之间的间隔相等，即剩余空间等分成间隙。![](https://pic1.zhimg.com/80/v2-ea4061e0f64dd8d7a1fcb5b0ad6f96a8_720w.jpg)
   
   space-around：每个项目两侧的间隔相等，所以项目之间的间隔比项目与边缘的间隔大一倍。![](https://pic1.zhimg.com/80/v2-42a358111a221ff52768bdd55238eb0c_720w.jpg)

5. ###### align-items: 定义了项目在交叉轴上的对齐方式
   
   flex-start | flex-end | center | baseline | stretch
   
   ```css
   .container {
       align-items: flex-start | flex-end | center | baseline | stretch;
   }
   ```
   
   建立在主轴为水平方向时测试，即 flex-direction: row
   
   默认值为 stretch 即如果项目未设置高度或者设为 auto，将占满整个容器的高度。
   
   ![](https://pic2.zhimg.com/80/v2-0cced8789b0d73edf0844aaa3a08926d_720w.jpg)
   
   假设容器高度设置为 100px，而项目都没有设置高度的情况下，则项目的高度也为 100px。flex-start：交叉轴的起点对齐
   
   ![](https://pic3.zhimg.com/80/v2-26d9e85039beedd78e412459bd436e8a_720w.jpg)
   
   假设容器高度设置为 100px，而项目分别为 20px, 40px, 60px, 80px, 100px, 则如上图显示。
   
   flex-end：交叉轴的终点对齐
   
   ![](https://pic4.zhimg.com/80/v2-8b65ee47605a48ad2947b9ef4e4b01b3_720w.jpg)
   
   center：交叉轴的中点对齐
   
   ![](https://pic3.zhimg.com/80/v2-7bb9d8385273d8ad469605480f40f8f2_720w.jpg)
   
   baseline: 项目的第一行文字的基线对齐![](https://pic3.zhimg.com/80/v2-abf7ac4776302ad078986f7cd0dddaee_720w.jpg)
   
   以文字的底部为主，仔细看图可以理解。

6. ###### align-content: 定义了多根轴线的对齐方式，如果项目只有一根轴线，那么该属性将不起作用
   
   flex-start | flex-end | center | space-between | space-around | stretch;
   
   ```css
   .container {
       align-content: flex-start | flex-end | center | space-between | space-around | stretch;
   }
   ```
   
   这个这样理解：
   
   当你 flex-wrap 设置为 nowrap 的时候，容器仅存在一根轴线，因为项目不会换行，就不会产生多条轴线。
   
   当你 flex-wrap 设置为 wrap 的时候，容器可能会出现多条轴线，这时候你就需要去设置多条轴线之间的对齐方式了。
   
   建立在主轴为水平方向时测试，即 flex-direction: row, flex-wrap: wrap
   
   默认值为 stretch，看下面的图就很好理解了
   
   ![](https://pic2.zhimg.com/80/v2-c284017b4b8b731bc213cd1caab514e5_720w.jpg)
   
   从图可以看出又三条轴线(因为容器宽度有限)，当值为 stretch 时会三条轴线平分容器的垂直方向上的空间。
   
   值得注意的是，虽然在每条轴线上项目的默认值也为 stretch，但是由于我每个项目我都设置了高度，所以它并没有撑开整个容器。如果项目不设置高度的话就会变成下面这样：
   
   ![](https://pic3.zhimg.com/80/v2-2d5feceece695fb84fd650fc49164bd6_720w.jpg)
   
   这个我在前面也有提到(align-items)，这里重点还是理解三条轴线会平分垂直轴上的空间。
   
   flex-start：轴线全部在交叉轴上的起点对齐
   
   ![](https://pic2.zhimg.com/80/v2-61d92d7dc68e3d7d415a16830050fd11_720w.jpg)
   
   flex-end：轴线全部在交叉轴上的终点对齐![](https://pic2.zhimg.com/80/v2-0a0a7f10c50596aade787ae11b7b0a75_720w.jpg)
   
   center：轴线全部在交叉轴上的中间对齐
   
   ![](https://pic1.zhimg.com/80/v2-dcf53fce8dbcde7da9c677dd1a033860_720w.jpg)
   
   space-between：轴线两端对齐，之间的间隔相等，即剩余空间等分成间隙。![](https://pic2.zhimg.com/80/v2-d80940f71e1e08d45d3d6df4c5401d0d_720w.jpg)
   
   space-around：每个轴线两侧的间隔相等，所以轴线之间的间隔比轴线与边缘的间隔大一倍。![](https://pic2.zhimg.com/80/v2-7c4d5c01f3851a3cec7f8487c6edb21d_720w.jpg)

7. 
