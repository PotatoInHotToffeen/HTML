# HTML

VSCode里打三个!!!可以自动生成以下代码，是HTML文档类型声明，是每个HTML或XHTML文档中需要的第一行代码。DOCTYPE声明是给Web浏览器的一个指令，说明网页是用什么版本的HTML写的。这可以确保不同的网络浏览器对网页的解析方式是相同的。

### 示例

##### HTML5及以后的doctype语法

```html
<!DOCTYPE html>
```

#### 严格型 HTML 4.01 的 doctype 语法：

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
```

VSCode里对HTML文件输入doc或输入!可以自动生成基本标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

</body>
</html>
```

1. lang: 语言，告诉搜索引擎站点是中文站还是英文站，或其他语言站；

2. head: 元素是所有头部元素的容器，元素<mark>必须包含文档的标题（title）</mark>，可以包含脚本、样式、meta 信息 以及其他更多的信息。
   
   1. meta是数据的数据信息：
   
   | 属性                                                                 | 值                                                                    | 描述                              |
   | ------------------------------------------------------------------ | -------------------------------------------------------------------- | ------------------------------- |
   | [charset](https://www.runoob.com/tags/att-meta-charset.html)       | *character_set*                                                      | 定义文档的字符编码。                      |
   | [content](https://www.runoob.com/tags/att-meta-content.html)       | *text*                                                               | 定义与 http-equiv 或 name 属性相关的元信息。 |
   | [http-equiv](https://www.runoob.com/tags/att-meta-http-equiv.html) | content-type<br>default-style<br>refresh                             | 把 content 属性关联到 HTTP 头部。        |
   | [name](https://www.runoob.com/tags/att-meta-name.html)             | application-name<br>author<br>description<br>generator*<br>*keywords | 把 content 属性关联到一个名称。            |
   
   2. name = viewport是专门为移动设备下显示所设计的：
   
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```
   
   * <mark>`width`</mark>
   
   控制视口的大小。这可以设置为特定像素数（如'width=600'），也可以设置为特殊值`device-width`，即 [100vw](https://developer.mozilla.org/zh-CN/docs/Web/CSS/length#%E8%A7%86%E5%8F%A3_viewport_%E6%AF%94%E4%BE%8B%E7%9A%84%E9%95%BF%E5%BA%A6)，100% 的视口宽度。最小值为 `1`。最大值为 `10000`。负值会被忽略。
   
   * <mark>`height`</mark>
   
   控制视口的大小。这可以设置为特定像素数（如 `width=600`），也可以设置为特殊值 `device-height`，即 [100vh](https://developer.mozilla.org/zh-CN/docs/Web/CSS/length#%E8%A7%86%E5%8F%A3_viewport_%E6%AF%94%E4%BE%8B%E7%9A%84%E9%95%BF%E5%BA%A6)，100% 的视口高度。最小值为 `1`。最大值为 `10000`。负值会被忽略。
   
   * <mark>`initial-scale`</mark>
   
   控制页面首次加载时显示的缩放倍数。最小值是 `0.1`。最大值是 `10`。默认值为 `1`。负值会被忽略。
   
   * <mark>`minimum-scale`</mark>
   
   控制页面允许缩小的倍数。最小值是 `0.1`。最大值是 `10`。默认值为 `1`。负值会被忽略。
   
   * <mark>`maximum-scale`</mark>
   
   控制页面允许放大的倍数。设置一个低于 `3` 的值将不具备无障碍访问性。最小值是 `0.1`。最大值是 `10`。默认值为 `1`。负值会被忽略。
   
   * <mark>`user-scalable`</mark>
   
   控制是否允许页面上的放大和缩小操作。有效值为 `0`、`1`、`yes` 或 `no`。默认值为 `1`，与 `yes` 相同。将值设置为 `0`（即与 `no` 相同）将违反 Web 内容无障碍指南（WCAG）。
   
   * <mark>`interactive-widget`</mark>
   
   指定交互式 UI 组件（如虚拟键盘）对页面视口的影响。有效值：`resizes-visual`、`resizes-content` 或 `overlays-content`。默认值：`resizes-visual`。
   
   3. title元素是一项元数据，用于表示整个 HTML 文档的标题

3. 一般还需要链接css样式：“rel=stylesheet”，rel是关联的意思，关联的是一个样式表(stylesheet) 文档，它表示这个link在文档初始化时将被使用，href是URL。
   
   ```html
   <link rel ="stylesheet" href="style.css">
   ```

#### 注释方法：

```html
<!-- 注释此处 -->
```
