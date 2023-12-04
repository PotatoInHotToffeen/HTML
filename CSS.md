# CSS

盒子模型：**外边距（margin）+ border（边框） + 内边距（padding）+ content（内容）** ，可以把每一个容器，比如div，都看做是一个盒子模型：

如果给DIV设置长宽为500px，这样设置只是设置content，如果再设置padding为10px，border为1px，那么整个DIV的宽高就变成544（500+40+4）

![](C:\Users\yangyxy\AppData\Roaming\marktext\images\2023-11-06-15-33-10-image.png)

如果使用了box-sizing: border-box，**padding和border的值就不会在影响元素的宽高，相当于把padding和border的值都算在content里，盒子模型会自动根据padding和border的值来调整content的值，就不需要手动调整**

flex是一种自适应的布局方式，对父元素下的子元素生效，孙级元素不包含，子元素默认排列方式是横着排，如果要修改排列方式为竖着，则flex-direction:

```html
display: flex;
```

- **background-size设置背景图片大小。****
  
  [`cover`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-size#cover)
  
  缩放背景图片以完全覆盖背景区，可能背景图片部分看不见。
  
  [`contain`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-size#contain)
  
  缩放背景图片以完全装入背景区，可能背景区部分空白。

- **background-position** CSS 属性为每一个背景图片设置初始位置。

- **background-repeat**  CSS属性定义背景图像的重复方式。

- **color**  CSS属性设置元素的文本以及文本装饰的前景色颜色值

- **justify-content：定义了项目在主轴(main axis)的对齐方式。** 
  
  ```css
  .container {
      justify-content: flex-start | flex-end | center | space-between | space-around;
  }
  ```

- **建立在主轴为水平方向时测试，即 flex-direction: row**
  
  默认值: flex-start 左对齐
  
  ![](https://pic1.zhimg.com/80/v2-1bafab80044a7ab2a6198d5937172eb0_720w.webp)
  
  flex-end：右对齐
  
  ![](https://pic3.zhimg.com/80/v2-8b163809a4c944486a127a7c22eee7b2_720w.webp)
  
  center：居中
  
  ![](https://pic4.zhimg.com/80/v2-dea82c75d35f532d35a52d1f9c1c762b_720w.webp)
  
  space-between：两端对齐，项目之间的间隔相等，即剩余空间等分成间隙。
  
  ![](https://pic1.zhimg.com/80/v2-ea4061e0f64dd8d7a1fcb5b0ad6f96a8_720w.webp)
  
  space-around：每个项目两侧的间隔相等，所以项目之间的间隔比项目与边缘的间隔大一倍。

**align-items: 定义了项目在交叉轴(cross axis)上的对齐方式**

- ```css
  .container {
      align-items: flex-start | flex-end | center | baseline | stretch;
  }
  ```
  
  **建立在主轴为水平方向时测试，即 flex-direction: row**
  
  默认值为 stretch 即如果项目未设置高度或者设为 auto，将占满整个容器的高度。
  
  ![](https://pic2.zhimg.com/80/v2-0cced8789b0d73edf0844aaa3a08926d_720w.webp)
  
  假设容器高度设置为 100px，而项目都没有设置高度的情况下，则项目的高度也为 100px。
  
  flex-start：交叉轴的起点对齐
  
  ![](https://pic3.zhimg.com/80/v2-26d9e85039beedd78e412459bd436e8a_720w.webp)
  
  假设容器高度设置为 100px，而项目分别为 20px, 40px, 60px, 80px, 100px, 则如上图显示。
  
  flex-end：交叉轴的终点对齐
  
  ![](https://pic4.zhimg.com/80/v2-8b65ee47605a48ad2947b9ef4e4b01b3_720w.webp)
  
  center：交叉轴的中点对齐
  
  ![](https://pic3.zhimg.com/80/v2-7bb9d8385273d8ad469605480f40f8f2_720w.webp)
  
  baseline: 项目的第一行文字的基线对齐
  
  ![](https://pic3.zhimg.com/80/v2-abf7ac4776302ad078986f7cd0dddaee_720w.webp)
  
  以文字的底部为主，仔细看图可以理解。
