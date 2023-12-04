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
      
      name = viewport是专门为移动设备下显示所设计的：
      
      ```html
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      ```
   
   2. title元素是一项元数据，用于表示整个 HTML 文档的标题
      
      ![](C:\Users\yangyxy\AppData\Roaming\marktext\images\2023-11-06-11-19-56-image.png)
   
   3. 一般还需要链接css样式：“rel=stylesheet”，**rel是关联**的意思，关联的是一个**样式表(stylesheet)** 文档，它表示这个link在文档初始化时将被使用，href是URL。
      
      ```html
      <link rel ="stylesheet" href="style.css">
      ```
   
   4. 

注释方法：

```html
<!-- 注释此处 -->
```
