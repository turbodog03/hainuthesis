海南大学本科生毕业论文latex模板——ctex版
-----

本仓库在[原仓库](https://github.com/zoltarsun/hainuthesis)基于使用 CJK 宏包编写的 $\LaTeX$ 模板基础上进行些许修改。
- 就海南大学现在的（2022年）本科生毕业论文格式要求进行了一些改动。
- 改用 ctex 并支持使用 XeLaTeX -> BibTeX -> XeLaTeX*2 的编译链进行编译（原仓库使用 LaTeX、BibTeX 和 dvipdfmx 或 pdfLaTeX 和 BibTeX 进行编译，效果完美，只是貌似无法使用overleaf）
- 进行了一些修改，使其变得更加易用（如增加if条件选择来方便地开启或关闭某功能或板块
### 进度
可以正常编译和……至少写我的经管类纯文字的水水论文没问题。还需增强对英文字体的支持。

#### TODO：
- 正文中对 Times New Roman 英文字体的支持还不够好
- ①、②等符号无法正常显示
- 复杂公式的显示不完美，其中字体粗细变化不统一，怀疑同样还是字体调整问题
- 增加更为详尽的readme，更多人能够享受内容和排版分离的快乐

## 食用指南
> 持续完善中
### 概述

### 初级（只增删内容，不更改任何格式）
#### 你需要知道的
- 在语句前添加%即为注释掉
- 大括号内的文字即为要修改的内容
- 文件夹内的pdf文件即是这份tex文档生成的。可以进行比照学习，一个有用的方法是在tex文件中搜索pdf文件中的字符串。
#### 更改封面及摘要的信息
在`/preface/cover.tex`中。按其中的注释操作即可。
#### 关于目录
不用担心，目录会被自动生成。后文将提到这点。
#### 更改和编写内容
在主文件`hainumain.tex`中，找到如下代码段：
```tex
\include{body/figures}
\include{body/tables}
\include{body/equations}
\include{body/others}
\include{body/conclusion}
\include{appendix/acknowledgements}    
```
`\include`意为把之后大括号内的文件复制到这个地方。正文内容均在这几个文件中，可对照来看。
#### 编译
编辑完成后，在overleaf左上角的menu栏中，setting项选择：
- compiler xelatex
- tex live version 2021
- main document hainumain.tex
> 上面三项是重点，后面其实没啥所谓
- Spell check Off
- Auto-complete On
- Auto-close Brackets On
- Code check On
- Editor theme textmate
- Overall theme Default
- Keybindings None
- Font Size 12px
- Font Family Lucida / Source Code Pro
- Line Height Normal

*****
供自用，感谢前辈们的付出。