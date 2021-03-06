# 纯纯写作 Markdown 使用指南

## 何谓 Markdown？

Markdown 是一种用纯文本表达富文本内容的标记语言。它简单易学，纯纯写作支持 Markdown(MD)，您可以点击 `快捷输入栏` 顶部的 `M↓` 勾选启用。

纯纯写作提供了许多 Markdown 快捷输入项，你可以点击 `快捷输入栏` 右侧的 `⌨️` 使用它们。

### 注意事项

1. **空格**在 Markdown 中是重要的组成成分，不可缺失。

2. Markdown 所使用的标记多为**半角**，请勿与全角混淆。

3. Markdown 下**无法使用缩进**，有需要缩进的段落请手动插入缩进。

4. Markdown 并无完全统一的规范，纯纯写作遵循并实现了 CommonMark 的 Markdown 标准，某些第三方的 Markdown 在纯纯写作中**可能无法使用**（如`==高亮文本==`）。

5. 标题、列表、引用文本、表格、选择框、分割线等部件**无法在行内使用**，必须在**行首**才可以使用并渲染。

6. 一个你不一定发现的纯纯写作小知识：选中一些文本后，使用纯纯写作内部的快捷输入项或快捷 Markdown 标记，当快捷输入的内容光标位置在插入项中的时候（如插入括号并设定插入后光标在括号中），将会直接插入在选中文字的前后，而非替换掉这段文字。

7. 默认情况下 Markdown 规定，两段之间必须**空一行**或者在**段尾部空两格**，才能真正在渲染时换行，比如：

```md
第一行

第二行
```

如果在纯纯写作设置页面开启 `GFM Line Breaks` 则只需要一个换行即可获得渲染时换行。因为`GFM Line Breaks`是默认打开的，因此本教程默认是依据打开 GFM Line Breaks 开关书写的。

在本指南中，除表格部份外，均使用竖形制表符`|`代指光标落点。

## 正文部分

### 目录

Markdown 的目录可以输入`[TOC]`生成，纯纯写作暂不支持目录自动生成。~~目前已在计划中，近期很有可能会提供支持~~。

### 标题

Markdown 的标题是用井号`#`加空格来表示的，而`#`的多少就代表着标题的层级，从少到多一共有六个层级。

标题的文字内容填充在空格后面。举例如：

```md
# 一级标题

## 二级标题

### 三级标题

#### 四级标题

##### 五级标题

###### 六级标题
```

标题实际上应该在前后都插入相同数量的井号`#`（如：`## 二级标题 ##`），纯纯写作中无需这样做。

另一种标题样式是由至少三个等于号`=`组成一级标题或至少三个短连接线/减号`-`组成二级标题，此样式应当插入在对应标题文本下方的一行。

需要注意的是，在文本与短连接线之间不可以有空行，否则会被识别为分割线。

### 加粗/斜体/粗斜体

这三个东西放在一起说，主要是因为它们所主要使用的标记符号是一样的，都是星号`*`或者下划线`_`，区别只在于符号的多少。

斜体是由前一后一两个星号或下划线组成的：`*斜体文本*`、`_斜体文本_`

加粗通常是由前二后二四个星号或下划线组成的：`**加粗文本**`、`__加粗文本__`

而粗斜体以此类推，是由前三后三六个星号或下划线组成的：`***粗斜体文本***`、`___粗斜体___`

纯纯写作中未提供下划线式的快捷输入项，因此建议使用星号来加粗或斜体。

### 删除线/下划线

删除线与下划线都是文字加线，就放在一起说了。

删除线是由前二后二四个波浪线组成的：`~~删除线文本~~`

而在 Markdown 中是无法直接插入下划线的，因此就需要使用行内的 html 标记`<u>|</u>`来插入下划线。

将文字插入在`<u>|</u>`标记中即可实现下划线的效果，示例：`<u>下划线文本</u>`

### 有序列表

有序列表的标记方式较为简单，数字加句点加空格即可：`1. 第一点`

换行即可自动补全下一行的数据。

### 无序列表

无序列表有三种可以使用的方式，纯纯写作提供了其中常见的两种并对其提供了自动填充。

第一种是短连接线/减号`-`加空格：`- 减号列表`

第二种是星号`*`加空格：`* 星号列表`

除此之外，纯纯写作未提供但是支持渲染的标记方式是加号`+`加空格：`+ 加号列表`

三者在实际使用上并没有什么区别。

值得注意的一点是，当在渲染连续的无序列表时，由同种标记组成的列表会距离较近，而不同标记组成的列表会距离较远，这一点在某些情况下会很实用。

有序列表和无序列表是可以互相嵌套的，可以通过在列表前加入至少两个空格来完成列表的嵌套。

### 引用

当需要引用一段话的时候，不妨试试引用标记，它是由大于号`>`加空格组成的：`> 被引用文本`

### 脚注

在需要添加脚注的文字后加上脚注名：`[^脚注名]`。 然后在文本的任意位置另起一行(一般在最后)添加脚注：`[^脚注名]:脚注内容`，即可插入脚注。

注意：在脚注的冒号`:`后不应加入空格。

### 文字居左/居中/居右

Markdown 无法直接实现文字居中，因此使用了 html 代码`<p align="">|</p>`，纯纯写作默认提供的是`<p align="center">|</p>`居中，但是通过修改相应的位置代码就可以做到左中右都支持，左中右分别是 left, center, right。

文字位置的格式是：`<p align="位置">需要修改位置的文字</p>`

纯纯写作**无法**使用`<center>|<\center>`方式居中。

### 插入图片

插入图片是一个相对重要的功能，它的格式是：`![]()`。

前面的方括号填写的是图片名称，而后面括号填写的是图片位置。当你使用网络图片时应该填写它的网络位置，当你使用本地图片时应该用图片选择器选中或填写它的本地位置。

需要注意的是，在使用网络图床时，要注意保护个人隐私，选择值得信任的图床；在使用本地图片时，该图片不可以被移动或删除，否则将无法正常显示，同时该图片也无法随着 Markdown 文档一同分享出去。

### 插入链接

与插入图片类似，其格式为：`[]()`。

在前面的方括号中输入链接描述，在后面的圆括号中输入链接即可，如：`[POPO 原創市集](https://www.popo.tw/index.html)`

### 插入表格

纯纯写作提供了快捷插入三列四行表格的快捷输入项。

在 Markdown 下的表格并没有 excel 那样非常多的格式，只有简单的几列几行的表格。

表格的基本构成部件是竖形制表符`|`、空格、冒号`:`和短连接线/减号`-`四个部件，制表符分隔表格的每一栏，空格确定表格内的文本内容，冒号确定表格中文本的位置，短连接线则负责标记表头与辅助确定表格中文本的位置。不多解释，直接上实例：

```md
| 左对齐 |  居中  | 右对齐 |
| :----- | :----: | -----: |
| left   | center |  right |
| left   | center |  right |
| left   | center |  right |
```

需要注意的地方：

1. 插入表格时，表格的上一行必须为空行，否则表格不会被成功渲染。
2. `:---` 代表内容和标题栏左对齐、`:--:` 代表内容和标题栏居中、`---:` 代表内容和标题栏右对齐。
3. `|`与`-`之间的多余空格会被忽略，不影响布局。
4. 内容和`|`之间的多余空格会被忽略，因此为了美观可以使用空格来对齐不同行的单元格，表头处`-`的数量至少要有一个。
5. 每行第一个`|`和最后一个`|`可以省略，因此在输入表格后的内容时最好多空一行，以防止下一行被认为是表格中的内容。

### 选择框

Markdown 的选择框是由短连接线/减号`-`与方括号`[]`组成的，通过在方括号中输入空格或字母`x`来确定是否选中该选择框。选择框的顺序是短连接线、空格、前方括号、空格或字母`x`、后方括号、空格加需要选择的文本，这些内容缺一不可，纯纯写作的 Markdown 快捷输入项中已经提供了相应选择框的快捷输入方式，可以有效避免输入错误。

举例：`- [ ]` 未选中、`- [x]` 选中

### 分割线

分割线是由至少三个的短连接线/减号`-`构成的，占单独一行。

需要注意的是，在文本与其下方的分割线之间应该加入一个空行，否则分割线上的文本会被识别为标题。

### 改变字符颜色

纯纯写作可以通过 html 的`<font color="">|</font>`来改变字符的颜色，格式为`<font color="颜色色号或常见颜色的英语单词">需要改变颜色的文本</font>`。

举例：`<font color="black">黑色文字</font>`、`<font color="#000000">黑色文字</font>`

注意：改变字体颜色与字符居中暂时**无法嵌套**；改变字体颜色在许多地方可能造成冲突而**无法显示**（如表格），**请谨慎使用**。

### 输入标记字符

如果你需要输入标记字符的本体，那你就需要看一下这一条了，Markdown 通过反斜线\来输入标记字符。

举例说明：`*斜体*`在 Markdown 中将会显示为*斜体*，加入`\`即可输出`\*斜体\*`。

### 代码块

写作的时候一般用不上的东西，技术大佬应该不屑于看我这入门教程，就在最后简单说一下，Markdown 通过使用` ```|``` `来包含多行代码，使用`` `|` ``来包含行内代码。

纯纯写作支持代码高亮，在开头的` ``` `后输入语言名字即可。

举例：

````md
```js
windows.addEventListener('load', function(){
console.log('windows loaded');
```

```python
def myfun(x):
​ return(x\*\*2)
```
````

更多更全的 Markdown 使用指南可以参考[Markdown 编辑器语法指南](https://segmentfault.com/markdown)
