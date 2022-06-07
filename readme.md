海南大学本科生毕业论文latex模板——ctex版
-----

本仓库在[原仓库](https://github.com/zoltarsun/hainuthesis)基于使用 CJK 宏包编写的 $\LaTeX$ 模板基础上进行些许修改。
- 就海南大学现在的（2022年）本科生毕业论文格式要求进行了一些改动。
- 改用 ctex 并支持使用 XeLaTeX -> BibTeX -> XeLaTeX*2 的编译链进行编译（原仓库使用 LaTeX、BibTeX 和 dvipdfmx 或 pdfLaTeX 和 BibTeX 进行编译，效果完美，只是貌似无法使用overleaf）
- 进行了一些修改，使其变得更加易用
    - 增加if条件选择来方便地开启或关闭某功能或板块
    - 添加更多的注释
- 更改成了文科论文格式（文理切换在做了
- 内附文科论文格式要求word模板
### 进度
可以正常编译和……至少写我的经管类纯文字的水水论文没问题。还需增强对英文字体的支持。文科格式已大致参照海南大学2022年文科毕业论文（设计）格式修改完成。理科格式与原项目相同。封面仍维持原项目内容未作改动，因为学校会提供单独的封面文件。

#### TODO：
- 文理模板切换！！
- 正文中对 Times New Roman 英文字体的支持还不够好
- ①、②等符号无法正常显示
- 五级标题标号要求为 ① 这种格式，目前并不支持。
- 复杂公式的显示不完美，其中字体粗细变化不统一，怀疑同样还是字体调整问题
- 增加更为详尽的readme，更多人能够享受内容和排版分离的快乐
- 文理科论文模板的切换做的十分粗暴，毫不优雅。大概会改进……的吧。

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
#### 添加参考文献
在文献检索网站点击引用，选择bibtex格式，将复制的内容粘贴到`/reference/reference.bib`文件中去，文献会自动在参考文献一页生成。形式大概是这样
```bib
@article{article_example,
  author      = {作者},
  title       = {题目},
  journal     = {刊名（全称）},
  year        = {年},
  number      = {卷},
  volume      = {期},
  pages       = {页码},
}
```
引用时，在引用处（文中）添加`\cite{article_example}`(article_example的位置对照上面给出的bibtex的格式。可以自定，一个文献一个名字就行)。添加网页参考同理，.bib文件中有模板。

### 高级
#### 自定义格式
文章的各种格式定义（包括封面、目录、正文……等等等等）在`setup\format.tex`中，所有的宏包都在`setup\package.tex`文件中。

如要修改参考文献的输出格式，可以修改`./HNUThesis.bst`。
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