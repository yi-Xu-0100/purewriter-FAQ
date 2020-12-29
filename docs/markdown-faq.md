# 纯纯写作 Markdown 使用常见问题

## 关于纯纯写作 Markdown 的使用规范与兼容性测试

纯纯写作的 Markdown 遵循 CommonMark 的 0.29 版本，参考链接：[CommonMark Spec](https://spec.commonmark.org/0.29/)

关于纯纯写作的 Markdown 可以使用该测试器进行测试：[CommonMark Markdown 标准测试器](https://spec.commonmark.org/dingus/)

## Markdown 的文本高亮（或其他一些代码）为何无法使用？

文本高亮的常见代码==|==并非 Markdown 原生的代码，而是其他第三方应用加入的代码，纯纯写作不支持这些非原生的代码。如果有需要可以尝试使用行内代码块（其代码为：`行内代码块`，纯纯写作中提供了快捷输入）代替，需要注意的是，行内代码块里不会渲染加粗、斜体、删除线、下划线等代码。

## Markdown 的居中为何无法使用 center 代码？

纯纯写作的居中与左右对齐只能使用 <p align="center/left/right">|</p> 代码来完成。因为 <center>|</center> 代码会出现无法正确渲染换行等 bug，所以纯纯写作取消了对此代码的支持。

## Markdown 导出图片或预览时有些地方未能正常显示？

新版的 Markdown 渲染器仍然有很多的小问题需要修复，还请理解开发者。如果介意的话可以在预览页面点击右上角的三个点切换旧版渲染器，此时，第三方字体将不能在预览与汇出图片中显示。
