四十秒简历 Forty Seconds CV
================

[English](Readme.md)

## 简介 Description

只是另一个 LaTeX 简历模板——但是这一次高度可定制！

这个项目可以被视为对原始的 twentysecondcv 类的改写。它的目标不在于提供全新的简历样式，而是基于一个已发布的优秀模板，添加直接的用户界面，并使其高度可定制的框架类: FortySecondsCV.

从 `template.tex` 开始自己尝试一下吧！

什么情况下您应该使用 twentysecondcv 或 altacv 或任何其他 LaTeX 类文件模板：

* 您对现有简历类样式提供的布局元素感到满意
* 您不需要改变纸张大小或格式
* 您不想进一步定制您的简历

什么情况下您应该使用 FortySecondsCV：

* 您想构建一个2页的简历，包括侧边栏
* 您想使用多种颜色和布局元素来高度自定义简历
* 您不想修改类文件中的任何定义
* 您更喜欢易于使用的用户界面，包括所有样式元素
* 您需要一个编写清晰的类文件，以防您决定更改低级文件类定义

## Attributions

* 此 LaTeX 简历的风格创意基于 Carmine Spagnuolo 的 [twentysecondscv class](https://github.com/spagnuolocarmine/TwentySecondsCurriculumVitae-LaTex)
* 模板中的语言图标取自 [gosquared's repository](https://github.com/gosquared/flags)

## 要求 Requirements

您需要使用 XeLaTeX 或 LuaLaTeX 编译文档，以便具有最新的 Font Awesome 图标（`fontawesome5`）和 Academicons。 如果您出于任何原因仍然想要使用 pdfLaTeX 进行编译，~~FortySecondsCV 将会回到较旧的图标包（`fontawesome`），其中一些图标看起来不同，甚至不包括一些其他图标~~ 学术论文将会不可用。

## 许可证 License

Forty Seconds CV 根据 BSD 3-Clause license 许可发行。详见 LICENSE 文件。

## 用户界面 User Interface

### 类选项 Class options

能够传递给 FortySecondsCV 的可用选项包括：

* 标准文章类别的所有有效选项，例如 `a4paper` 或 `11pt`。
* `sidesectionsize` 设置侧边栏部分标题的字体大小。使用设置 `large`，`huge`将其设置为 `\large`，`\huge` 等（即不带斜杠 `\`）
* `showframes `显示侧边栏和正文文本的边框，用以帮助调整边距。注意，这将轻微移动表中的内容，因为表格线也占据一定空间。
* `vline = <length> `在 x=`<length>` 位置绘制一条红色垂直线以帮助调整侧边栏内容。
* `maincolor = <color> `设置用于整个侧边栏的主题颜色，包括标题，图标和图表。许多颜色都源于此。
* `sidecolor = <color>` 设置侧边栏的背景色。
* `sidetextcolor = <color>` 设置位于侧边栏中的文本的颜色。
* `sectioncolor = <color>` 设置正文中各节（section）标题的颜色。
* `subsectioncolor = <color>` 小节（subsection）的颜色，与节的颜色相同。
* `itemtextcolor = <color>` 设置 cvitem 的颜色。
* `sidebarwidth = <length>` 设置侧边栏的总宽度，即可见边栏颜色的宽度。
* `topbottommargin = <length>` 设置侧边栏和主体的上下页边距。
* `leftrightmargin = <length>` 设置侧边栏和主体的左右页边距以及两列之间的距离。
* `profilepicsize = <length>` 设置个人资料图片的宽度。
* `profilepicborderwidth = <length>` 设置个人资料图片边框的宽度。
* `profilepicstyle = profilecircle` 将个人资料图片剪切为和原始 `twentysecondcv`  一样的圆圈形状
* `profilepiczoom = <float>` 设置个人资料图片的缩放系数。
  结合下面的两个选项，您可以直接使用自己喜欢的个人资料图片，无需修改和裁剪。 
* `profilepicxshift = <length>`  设置个人资料图片的左右偏移（xshift）。
* `profilepicyshift = <length>`  设置个人资料图片的上下偏移（yshift）。
* `profilepicrounding = <length>`  设置默认个人资料图片样式的圆角半径。
* `sidebarplacement = right` 将侧边栏置于主体的右侧，而非左侧。

注意：

* 长度可以以任何绝对长度单位指定，例如用 `em` 表示宽度，用 `ex` 表示高度或相对高度，也可以使用 `0.5\paperheight` 或 `0.3\linewidth`。
* 颜色可以从 `xcolor` 软件包的 `dvipsnames`，`svgnames` 和 `x11names` 供的完整目录中进行选择。前往 [xcolor package documentation](http://mirrors.ctan.org/macros/latex/contrib/xcolor/xcolor.pdf) 查看详细信息和颜色表。
* 颜色也可以使用以下方式在文档正文中重新定义，例如使用 `\definecolor{sidecolor}{HTML}{000000}`。

### 侧边栏 Sidebar

简历正面和背面的侧边栏可以在 LaTeX 代码的  `document`  部分中使用 `\ makefrontsidebar` 和 `\ makebacksidebar` 命令生成。建议在 `\ makebacksidebar` 紧邻的前一行使用 `\newpage`。

可以使用以下方法添加前侧边栏和后侧栏中的布局元素
```latex
\addtofrontsidebar{}
\addtobacksidebar{}
```
其中，一些元素（如个人资料图片，姓名和职务）有预定义，您可以使用下面的命令来重新定义它们
```latex
\renewcommand{\makefrontsidebar}{%
  \begin{sidebar}
    <your code>
  \end{sidebar}
}
```
您可以使用所有先前定义的宏，例如 `\cvname` 和 `\cvjobtitle` 或其他元素，例如 [此处](#个人信息-personal-information) 绍的符号表。更详细的示例请参见 [#22][i22]。

[i22]: https://github.com/PandaScience/FortySecondsCV/issues/22

`sidebar` 环境可以确保至少所有文本都将正确放置在每个页面的左列（侧边栏）内。如果您需要更严格的限制，例如为了防止在使用多个图表标签时发生溢出，可以将侧边栏内容的一部分包含在 `sidebarminipage` 中：
```latex
\begin{sidebarminipage}
  \chartlabel{Bubble Diagram}
  \chartlabel{with}
  \chartlabel{proper}
  \chartlabel{overflow}
  \chartlabel{protection}
  \chartlabel{for}
  \chartlabel{labels}
\end{sidebarminipage}
```
使用 `sidebar` 环境时，您还可以轻松地为其添加更多侧边栏定义。如果希望边栏显示在主体的右侧而不是左侧，请使用类选项 `sidebarplacement=right`。

如果要在单个页面上完全删除侧边栏，不调用任何侧边栏构造函数即可。然后，您可以使用以下命令设置您喜好的页边距：
```latex
\newpage
% no \makebacksidebar etc.
\newgeometry{
  top=<length>,
  bottom=<length>,
  left=<length>,
  right=<length>
}
```
默认的页边距参数为 `\leftrightmargin` 和 `\topbottommargin`。如果您想在随后的页面回到默认页面布局，只需在下一个 `\newpage` 之后使用 `\restoregeometry`。

侧边栏元素的文本颜色可以通过 `sidetextcolor` 选项进行调整。如果想要更深层的样式更改，您可以重新定义 `\sidetext` 命令，例如：
```latex
  \renewcommand{\sidetext}[1]{\textcolor{red}{\texttt{#1}}}
```

### 个人信息 Personal Information

通过便捷命令设置个人信息
```latex
  % logo picture - logo图片
  \cvlogopic[0.8\linewidth]{pics/logo.png}
  % profile picture - 个人资料图片
  \cvprofilepic{pics/profile.png}
  % your name - 您的姓名
  \cvname{Panda Bear}
  % job title/career - 职位/职业
  \cvjobtitle{Panda Scientist,\\[0.2em] Panda of the Year}
  % date of birth - 出生日期
  \cvbirthday{Mar 7, 2019}
  % short address/location, use \newline if more than 1 line is required - 短地址，如果不止一行请使用\newline
  \cvaddress{Park Ave.~1, 555 555 B-Woods}
  % phone number - 电话
  \cvphone{+86 555 555 555}
  % personal website - 个人网站
  \cvsite{https://pandascience.net}
  % email address - 电子邮箱
  \cvmail{panda@bamboo.cn}
  % pgp key
  \cvkey{4096R/FF00FF00}{0xAABBCCDDFF00FF00}
  % any other custom entry - 其他任意条目
  \cvcustomdata{\faFlag}{Chinese}
```
* 只有 `\cvname` 和 `\cvjobtitle` 是必填的。
* 如果您不希望任何（可选）条目出现在您的简历中，不填写它们即可。如果您不使用任何以上便捷命令，那么整个个人信息表将不会出现。
* 电子邮件地址将自动添加 `mailto:email`。
* 您的网站也将被添加超链接
* For the pgp key, the first argument defines the displayed text which is linked to a keyserver searching for the ID in the second argument.
Note: For safety, you should use your key's long ID or its fingerprint in the second argument.
* `\cvcustom{<icon>}{<text>}` 巨集（macro） 显示了如何使用图标作为第一个参数以及一些文本作为第二个参数来定义新行。在这个场景背后，该命令实际上用于定义以上示例中的其他便捷命令。

如果您不喜欢“个人信息表”的默认样式，则可以通过以下方式定义自己的样式：
```latex
\begin{icontable}[<arraystretch=1>]{<width 1st column>}{<space between columns>}
  \personal{<icon>}{<text>}
  \social{<icon>}{<url>}{<text>}
\end{icontable}
```
其中第一列的宽度也将确定此列中所有图标的大小，因为图标已缩放到其单元格的最大宽度。出于视觉目的，您可以使用第二个必填参数微调图标和相应文本之间的间距。可选参数确定表格行之间的间距，这仅对于较小的图标高度（即较小的第一列）很重要。

* `\personal` 需要一个图标和一个文本。 该图标将传递到`\circleicon{<icon>}`，该命令在图标符号周围绘制一个填充有颜色为`maincolor`的圆圈。符号本身显示为白色。

* `\social` 需要一个图标和 url +文本。`Text` 将被超链接到 `url`。如果 `url` 为空，您的 LaTeX 编译器将发出关于“禁止目标为空的链接”的无害警告，并且文本不会超链接。图标本身会传递到 `\socialicon{<icon>}`，后者会调整图标符号的大小并以颜色 `maincolor` 绘制它。此版本是社交网络图标的首选版本（请参见示例）。

默认的“个人信息表”使用
```latex
\begin{icontable}[1.6]{1.7em}{0.4em}
  \personal{<icon>}{<text>}
\end{icontable}
```


### 其他侧边栏样式元素 Further Sidebar Style Elements

* 节标题（Section heading）
  ```latex
  \profilesection{<section title>}
  ```

* 简单技能（Skill），仅包含一个图标和一些文本，并带有可选的缩进
  ```latex
  \skill[<indent>]{<icon>}{<text>}
  ```

* 点状技能（Pointskill）由图标、文本、分数和可选的最大可能数组成（默认值：5）。一些例子：
  ```latex
  \pointskill{<icon>}{<text>}{<points>}
  ```
  使用 Font Awesome 或 Academicons 图标创建技能，参数为文本、以及 5 分以内的 `<points>`。
  ```latex
  \pointskill{<icon>}{<text>}{<points>}[<maxnum>]
  ```
  使用 Font Awesome 或 Academicons 图标创建技能，参数为文本、以及最大值为 `<maxnum>`以内的 `<points>`。
  ```latex
  \pointskill{\flag{DE.png}}{German}{5}
  ```
  使用国旗图标来创建语言技能，必须使用 `\flag` 命令来指示该语言技能，这样才能告知类不应使用 `\maincolor` 为图标着色。

* 条形技能（Barskill） 由图标、文本和技能条应填充的百分比组成
  ```latex
  \barskill{<icon>}{<text>}{<percentage>}
  ```
* “关于我”（About me）由多行文本组成
  ```latex
  \aboutme{<text spanning multiple lines>}
  ```

* 圆形彩色标签，例如图表和其他图形
  ```latex
  \chartlabel{<text>}
  ```

* 轮图/饼图/扇形图
  ```latex
  \wheelchart{<outer radius>}{<inner radius>}{%
    <percentage>/<spacing>/<color>/<text>,
    <percentage>/<spacing>/<color>/<text>
  }
  ```
  * 百分比总计应为 100

* 会员资格
  ```latex
  \begin{memberships}[<separation>=1em]
    \membership[<iconwidth>=4em]{<logo>}{<text>}
    \membership[<iconwidth>=4em]{<logo>}{<text>}
    \membership[<iconwidth>=4em]{<logo>}{<text>}
  \end{memberships}
  ```
  * 包含图标的第一列的宽度等于最大图标的宽度，以使第二列中的所有文本条目对齐。

* 社交网络
  ```latex
  \begin{socialnetwork}[<separation>=1em]
    \social{<icon>}{<url>}{<text>}
    \social{<icon>}{<url>}{<text>}
    \social{<icon>}{<url>}{<text>}
  \end{socialnetwork}
  ```
  * 另一种图标样式，可以用于例如来自 Academicons 的社交网络图标，但也适用于 FontAwesome 图标。
  * `text` 会被超链接至 `url`。
  * `text` 可以像往常一样通过以下方式格式化，例如 `\texttt{}` 等。

### 主体 Body
简历的右栏包含一些内容的表格，例如“工作经验”必须在文档环境中定义。

* 节（Section） and 小节（subsection）标题
  ```latex
  \cvsection
  \cvsubsection
  ```

* 简历条目应该被 `cvtable` 括起来， 不论它们是哪一种条目:
  ```latex
  \begin{cvtable}[<arraystretch>=1]
    \cvitem{<dates>}{<title>}{<location>}{<description>}
    \cvitem{<dates>}{<title>}{<location>}{}
    \cvitemshort{<key>}{<description>}
    \cvpubitem{<title>}{<author>}{<journal>}{<year>}
  \end{cvtable}
  ```
  * 包含描述的 `cvitem` 会使标题加粗，日期左对齐，并将描述放在下一行。 描述本身将使用在 [类选项](#类选项-class-options) 中定义的 `itemtextcolor` 作为自己的颜色
  * 缺少描述的 `cvitem` 将添加与前一行相同样式的单行项目，但标题为“普通”而不是粗体。
  * `cvitemshort` 将 `<key>` 左对齐，后跟其描述。
  * `cvpubitem` 添加了一个条目，该条目具有左对齐的年份/日期，同一行上的粗体标题，然后是斜体作者和普通文本各占一行。
  * `<arraystretch>` 修改 `cvtable` 各项之间的间距。对于 `cvitem` 表，应至少使用 1.5，对于 `cvitemshort`和无描述的
`cvitem`，默认值已足够使用。

* `cvsection`， `cvsubsection` 和描述文本的颜色可以按照 [类选项](#类选项-class-options) 中的说明定义。

* 名称和职称组合，并具有适当的间距，字体和颜色
  ```late
  \nameandjob
  ```

* 以地点、日期和签名来确定简历是惯例，例如在德国，通过以下方法
  Germany is done via
  ```latex
  \cvsignature
  ```

### 字体配置 Font Configuration

* 通过加载相应的软件包来更改默认字体，例如对于Google Noto
  ```latex
  \usepackage[sfdefault]{noto} % use noto google font
  ```
  或使用 XeLaTeX 的选项直接通过 fontspec 加载本地字体
  ```latex
  \usepackage[quiet]{fontspec}
  \newfontfamily\headingfont[Path = fonts/]{segoeuib.ttf}
  ```

* 在处理多语言文档时，强烈建议不要使用 pdfLaTeX。由于我对 LuaLaTeX 的经验很少（但可能很快会切换到后者），因此我现在只能提供有关 XeLaTeX 的说明。您首先需要加载 polyglossia 软件包并分别为每种语言设置字体。对于基于拉丁语的文档，然后使用一些，例如阿拉伯文字片段
  ```latex
  \usepackage{polyglossia}
  \newfontfamily\arabicfont[Script=Arabic]{Amiri}
  \setdefaultlanguage{english}
  \setotherlanguage{arabic}
  % typeset arabic snippets in body text with either of
  \textarabic{...}
  \begin{Arabic}...\end{Arabic}
  ```
  而对于非拉丁文档，您可以使用类似这样的方法
  ```latex
  \usepackage{polyglossia}
  \setmainfont{Amiri}
  \newfontfamily\englishfont{Clear Sans}
  \setdefaultlanguage{arabic}
  \setotherlanguage{english}
  % typeset english snippets in body text with either of
  \textenglish{...}
  \begin{english}...\end{english}
  ```
  对于波斯语（farsi），根据 [此回答](https://tex.stackexchange.com/a/238245) 以下方法应该起作用：
  ```latex
  \newfontfamily\farsifont[Script=Arabic,Scale=10,Contextuals=Swash]{IranNastaliq}
  ```

  根据您的默认字体样式，您需要使用 `\arabicfontfs`
  (sans serif) 或 `\arabicfonttt` (monospace) 来代替 `\arabicfont`。

  注意：将 RTL 字体设置为主字体也会自动翻转简历的其他部分。就我所知，尽管对于大多数部分来说这似乎没有问题（我一点也不习惯 RTL），但它确实破坏了一些技能命令，尤其是 `\pointskill` 和 `\membership` 并导致了一些间距问题。 无论如何，对于 RTL，您可能依然希望使用 `sidebarplacement=right` 功能。
  
* TODO: LuaLaTeX + babel settings

* 通过 fontspec 加载时，需要手动安装 Amiri 和 Clear Sans 之类的字体。对于单语言文档，这不是必需的，您可以直接使用相应的 LaTeX 包来像第一个示例中所示那样简单地切换字体。

* 如果要查找特定图标，例如 inkedIn，则应首先在 [FontAwesome gallery](https://fontawesome.com/icons?d=gallery) 中搜索其名称，例如，`linkedin-in` 然后在 [fontawesome5 package](https://ftp.gwdg.de/pub/ctan/fonts/fontawesome5/doc/fontawesome5.pdf) 中找到相应的 LaTeX 代码，在本例中为 `\faLinkedinIn`。

* 如果要全局增加行距，请使用
  ```latex
  \usepackage{setspace}
  \setstretch{1.1}
  ```
  而不是 `arraystretch` 修饰符。请注意，这也会影响边栏的内容。

* 如果要更改基本字体大小，请对所有正文元素和侧边栏中的段落使用 `article` 类选项，例如 `12pt`。侧栏的标题可以通过 [类选项](#类选项-class-options) 中的 `sidesectionsize` 进行更改。对于名称和职称字体大小，您必须按照 [此处](#侧边栏-sidebar) 的说明重新定义相应的命令。


## 范例 Example

![](pics/template-0.jpg)
![](pics/template-1.jpg)
