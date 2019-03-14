## Fourty Seconds CV

### Description

Just another CV class for LaTeX - but this time highly customizable!

This project can be regarded as a major rewrite of the original twentysecondscv
class. It does not aim to provide a new CV style that you can't find anywhere
else, but rather takes a very well established one and adds a straightforward
user interface to almost all layout elements and thus creates a highly 
customizable framework-class: FortySecondCV.

Just try it yourself starting from `template.tex`!

When you should use twentysecondcv or altacv or any other LaTeX CV class:

* You are happy with the layout elements offered by the existing CV class styles
* You don't need to change paper sizes / formats at all
* You don't want to customize your CV further

When you should use the FortySecondCV class:

* You want to highly customize your CV while keeping the sidebar layout
* You don't want to modify any definition in the class file
* You prefer an easy to use user interface to almost all style elements
* You need a cleanly written class file in case you decide to change low-level
  class definitions


### Attributions

* This LaTeX CV class is based on the style ideas of the 
  [twentysecondscv class](https://github.com/spagnuolocarmine/TwentySecondsCurriculumVitae-LaTex)
  by Carmine Spagnuolo 
* Language icons in the template are taken from [gosquared's repository](https://github.com/gosquared/flags)


### Requirements

* You need to compile your document with XeLaTeX in order to have the latest
  Font Awesome icons (`fontawesome5`). If you still want to compile with
  pdfLaTeX for whatever reason, FortySecondsCV will fall back to the older icon
  package (`fontawesome`), where some icons look different and some others are
  not even included.

### Example

![](pics/template-0.jpg)
![](pics/template-1.jpg)
