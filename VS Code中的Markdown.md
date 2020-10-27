# 在VS Code中使用Markdown插件

本文介绍了一些VS Code中的Markdown的插件。

- [1. Markdown 插件](#1-markdown-插件)
- [2. 其他通用编辑器插件](#2-其他通用编辑器插件)
- [3. 快捷键](#3-快捷键)

## 1. Markdown 插件
[VSCode Doc: Markdown](https://code.visualstudio.com/docs/languages/markdown) 介绍了在VSCode中使用Markdown的基本方法。VSC本身支持Markdown（具体来说是其一种方言[CommonMark](https://commonmark.org/)），但是使用插件可以获得更好的体验。

VSC中的Markdown插件主要分为两类：编辑类和渲染类。

**编辑类：**

- [`Markdown All in One`](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)  
  包含大部分功能，日常使用已经足够。
- [`Markdown Shortcuts`](https://marketplace.visualstudio.com/items?itemName=mdickin.markdown-shortcuts)  
  高效的快捷键。少部分可能与`Markdown All in One`冲突，实测以该插件为高优先级，也可以自行修改快捷键。
- [`markdownlint`](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)  
  提供代码lint。

**渲染类：**

- [`Github Markdown Preview`](https://marketplace.visualstudio.com/items?itemName=bierner.github-markdown-preview)  
  该插件集合可以修改 Preview 时的风格为 GitHub，但是代码块风格不能修改。包含插件如下:

  - `Markdown Preview Github Styling`: CSS that makes the preview match Github's markdown style.
  - `Markdown Emoji`: Adds `:emoji:` support to the markdown preview.（不支持GFM自定义的一些，如`:octocat:`.）
  - `Markdown Checkboxes`: Adds `- [ ]` tasklist support to the markdown preview.
  - `Markdown yaml Preamble`: Adds support for rendering the yaml frontmatter as a table. Be sure to set `"markdown.previewFrontMatter": "show"`.

⚠ 使用`Github Markdown Preview`不等于渲染效果等同于GFM。GFM的某些特性可能不能显示。实际上GFM的渲染效果并不是特别多，比如不支持LaTeX。

- [`Markdown Preview VS Code Highlighting`](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-shiki)  
  该插件可以修改代码风格。
- [`Markdown+Math`](https://marketplace.visualstudio.com/items?itemName=goessner.mdmath)  
  更好的数学渲染工具（`Markdown All in One`文档里自己说的，虽然都是使用KaTeX引擎），使用时将`Markdown All in One`的`math.enabled`取消掉。

- [~~`Markdown Preview Enhanced`~~](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)  
  MPE支持的渲染效果最多，不需要安装上面这么多插件。不过MPE不支持从预览窗口反向定位代码位置（虽然可以同步滑动）。因为有时我们还是需要上传到GitHub，但是有些效果GitHub不支持，所以*可能不太适合需要分享给别人的文件*。我个人最终放弃了MPE。  
  [这篇文章](https://zhuanlan.zhihu.com/p/56699805)介绍了一些使用MPE的经验。

- [~~`Markdown PDF`~~](https://marketplace.visualstudio.com/items?itemName=yzane.markdown-pdf)  
  严格来说这个是用来导出PDF的，但其实过程也是在渲染。不推荐使用这个插件，因为首先不支持LaTeX（可以自行修改配置使用MathJax或KaTex），而且会下载一个Chrome，而且导出效果并不好，感觉没有必要使用这个插件。`Markdown All in One`和`Markdown+Math`都可以实现导出HTML，再使用浏览器打印一下，效果反而更好。

## 2. 其他通用编辑器插件

这些插件也可以在编辑别的代码时使用，由于对于Markdown比较有用，故在此列出。

- [`Bracket Pair Colorizer 2`](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2)  
  注意把`Markdown`加入排除列表，但是代码块内的其他语言可以高亮。
- [`Whitespace+`](https://marketplace.visualstudio.com/items?itemName=davidhouchin.whitespace-plus)  
  可以显示行尾空格，因为 Markdown 行尾两个空格相当于回车`<br>`。
- [`Prettier`](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)  
  使用这个Formatter比`Markdown All in One`的效果更好一些。

- [`Emoji Snippets`](https://marketplace.visualstudio.com/items?itemName=devzstudio.emoji-snippets)  
  使用`:`触发补全Emoji，注意补全之后输入的是Emoji字符（图形），而不是`:emoji:`代码。
## 3. 快捷键

带`*`的快捷键被我修改过。

:bulb: 在VSC中点击“设置”按钮，选择“键盘快捷方式”进入快捷键编辑页面。

`Markdown All in One`中的快捷键：

|           Key           |           Command            |
| :---------------------: | :--------------------------: |
|      Ctrl/Cmd + B       |         Toggle bold          |
|      Ctrl/Cmd + I       |        Toggle italic         |
|  Ctrl/Cmd + Shift + ]   |   Toggle heading (uplevel)   |
|  Ctrl/Cmd + Shift + [   |  Toggle heading (downlevel)  |
|     Ctrl/Cmd + M M      |  Toggle math environment\*   |
|         Alt + C         | Check/Uncheck task list item |
|  Ctrl/Cmd + Shift + V   |        Toggle preview        |
|     Ctrl/Cmd + K V      |    Toggle preview to side    |
| Ctrl/Cmd + M Ctrl/Cmd G |          添加目录\*          |
| Ctrl/Cmd + M Ctrl/Cmd N |   Section 添加/更新编号\*    |
| Ctrl/Cmd + M Ctrl/Cmd - |        Toggle list\*         |

`Markdown Shortcuts`中的快捷键：

|              Name               |                   Description                    | Default key binding |
| :-----------------------------: | :----------------------------------------------: | :-----------------: |
| md-shortcut.showCommandPalette  |               Display all commands               |    ctrl+M ctrl+M    |
|     md-shortcut.toggleBold      |                  Make **bold**                   |       ctrl+B        |
|    md-shortcut.toggleItalic     |                  Make _italic_                   |       ctrl+I        |
| md-shortcut.toggleStrikethrough |              Make ~~strikethrough~~              |                     |
|     md-shortcut.toggleLink      |       Make [a hyperlink](www.example.org)        |       ctrl+L        |
|     md-shortcut.toggleImage     |         Make an image ![](image_url.png)         |    ctrl+shift+L     |
|   md-shortcut.toggleCodeBlock   |               Make `a code block`                |    ctrl+M ctrl+C    |
|  md-shortcut.toggleInlineCode   |                Make `inline code`                |    ctrl+M ctrl+I    |
|    md-shortcut.toggleBullets    |              Make \* bullet point\*              |    ctrl+M ctrl+8    |
|    md-shortcut.toggleNumbers    |              Make 1. numbered list               |    ctrl+M ctrl+1    |
|  md-shortcut.toggleCheckboxes   | Make - [ ] check list (Github flavored markdown) |    ctrl+M ctrl+X    |
|    md-shortcut.toggleTitleH1    |                Toggle # H1 title                 |                     |
|    md-shortcut.toggleTitleH2    |                Toggle ## H2 title                |                     |
|    md-shortcut.toggleTitleH3    |               Toggle ### H3 title                |                     |
|    md-shortcut.toggleTitleH4    |               Toggle #### H4 title               |                     |
|    md-shortcut.toggleTitleH5    |              Toggle ##### H5 title               |                     |
|    md-shortcut.toggleTitleH6    |              Toggle ###### H6 title              |                     |
|      md-shortcut.addTable       |                Add Tabular values                |                     |
| md-shortcut.addTableWithHeader  |         Add Tabular values with header\*         |    ctrl+M ctrl+T    |
