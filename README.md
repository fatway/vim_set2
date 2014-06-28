# Vim插件及配置

启动配置与插件安装记录，目前插件主要针对python开发使用
基于`gVim Portable` [(offical_site)](http://portableapps.com/apps/development/gvim_portable) 软件进行相关配置

项目所有文件位于`../gVimPortable/Data/settings`目录下

使用Pathgen进行插件的统一管理, 结合Github, 很好很强大

version: 2, based on the first conf: [vim-set](https://github.com/fatway/vim_set)

refer: http://lostjs.com/2012/02/04/use-pathogen-and-git-to-manage-vimfiles/

--- 

## Pathogen

	Easy manipulation of 'runtimepath', 'path', 'tags', etc
	http://www.vim.org/scripts/script.php?script_id=2332
	统一管理插件 (插件的插件)

该插件动态加载bundle下的所有插件, 这样就方便各个插件的独立更新, 互不干扰

### 安装插件:

	$ git submodule add 插件的Git仓库地址 vimfiles/bundle/插件名字

由于加载的需要, 将pathogen.vim 手动置于autoload目录下, 以方便其动态加载其它插件

### 升级插件

  * 单独升级插件，只要先进入插件目录，然后执行：

	$ git checkout master; git pull

  * 通过git submodule foreach来可以一次性升级全部插件：

	$ git submodule foreach 'git checkout master && git pull'

	确保在master分支下的话, 使用下面进行更新
	$ git submodule foreach 'git stash && git pull && git stash clear'

### 删除插件

	$ rm -rf bundle/插件名
	$ git rm -r bundle/插件名



## trinity

	Trinity : the Trinity of taglist, NERDtree and SrcExpl: an IDE works like "Source Insight"
	http://www.vim.org/scripts/script.php?script_id=2347
	一站式开发集成插件，调用taglist,tree,srcexpl三个插件进行函数列表、文件目录
	2014年1月13日 14:21:32

根据在vimrc文件中的设置来开关相应的功能窗口

	nmap <F8>   :TrinityToggleAll<CR>             " 切换三个插件显示
	nmap <F9>   :TrinityToggleSourceExplorer<CR>  " 切换源码提示插件
	nmap <F10>  :TrinityToggleTagList<CR>         " 切换函数列表插件
	nmap <F11>  :TrinityToggleNERDTree<CR>        " 切换文件目录插件


三个独立插件如下（不需要再独立进行相关配置设定）

	－
	 |-- taglist.vim
	 |     http://www.vim.org/scripts/script.php?script_id=273
	 |     需要分析源代码的工具Ctags(http://ctags.sourceforge.net/)，
	 |     解压缩后拷贝ctags.exe到app下的vim安装位置，或者放于system32
	 |     快捷键:
	 |		`<CR>`         跳到光标下tag所定义的位置，用鼠标双击此tag功能也一样
	 |		`o`             在一个新打开的窗口中显示光标下tag
	 |		`<Space>`       显示光标下tag的原型定义
	 |		`u`             更新taglist窗口中的tag
	 |		`s`             更改排序方式，在按名字排序和按出现顺序排序间切换
	 |		`x`             taglist窗口放大和缩小，方便查看较长的tag
	 |		`+`             打开一个折叠，同zo
	 |		`-`             将tag折叠起来，同zc
	 |		`*`             打开所有的折叠，同zR
	 |		`=`             将所有tag折叠起来，同zM
	 |		`[[`            跳到前一个文件
	 |		`]]`            跳到后一个文件
	 |		`q`             关闭taglist窗口
	 |		`<F1>`          显示帮助
	 |
	 |-- SrcExpl
	 |     http://www.vim.org/scripts/script.php?script_id=2179
	 |     可以在定义跳转设定
	 |-- The NERD tree
	 |     http://www.vim.org/scripts/script.php?script_id=1658
	 |     目录树插件, 快捷键:
	 |		`o`	展开左侧某个目录，再按一下就是合并目录 
	 |		`t`	在新 Tab 中打开选中文件/书签，并跳到新 Tab
	 |		`T`	在新 Tab 中打开选中文件/书签，但不跳到新 Tab
	 |		`P`	跳到根结点
	 |		`p`	跳到父结点
	 |		`q`	关闭 NerdTree 窗口



## NERD_commenter

	http://www.vim.org/scripts/script.php?script_id=1218
	代码注释插件
	2014年1月13日 14:39:30

NERD Commenter的常用键绑定，以C/C++文件为例，详析的使用方法，请:h NERDCommenter。在Normal或者Visual 模式下：

* `\ca`，在可选的注释方式之间切换，比如C/C++ 的块注释/* */和行注释//
* `\cc`，注释当前行，或者选定块
* `\c `，切换注释/非注释状态
* `\ci`, 切换注释 individually
* `\cs`，以”性感”的方式注释
* `\cA`，在当前行尾添加注释符，并进入Insert模式
* `\cu`，取消注释
* `\c$`, 从当前光标注释到行结尾

Normal模式下，几乎所有命令前面都可以指定行数
Visual模式下执行命令，会对选中的特定区块进行注释/反注释

使用该插件需要设置 `filetype plugin on`




## minibufexpl

	minibufexpl.vim : Elegant buffer explorer - takes very little screen space 
	http://www.vim.org/scripts/script.php?script_id=159
	缓冲区查看，可以快速在已编辑过的文件之间进行切换
	2014年2月12日 09:24:34

使用命令:

* `control + [hjkl]` 切换缓冲区工作表
* `control + arrow keys` 同上 
* `control + tab` & `shift + control + tab` 在已打开的工作表中切换



## Emmet

	vim plugins for HTML and CSS hi-speed coding.
	http://www.vim.org/scripts/script.php?script_id=2981
	hmtl源码快速编辑
	参考教程：http://docs.emmet.io/abbreviations/syntax/
	2014年1月13日 14:40:41

Tips:

默认展开_功能键_为`<c-y>,` (即ctrl+y然后按逗号)  
这里个人定义一下名称: `<c-y>`: 功能键, `,(逗号)`: 执行键  
插件教程: https://raw.github.com/mattn/emmet-vim/master/TUTORIAL

示例:

1. 搭建一个标准的html模板: `html:5` , 然后使用功能键后 再 按`,`执行键
2. 常规扩展: `div>p#foo$*3>a`
3. 处理已有文本:

	test1  
	test2  
	test3

  在visual模式下选中该三行, 执行功能键+逗号, 在下面的语法提示中输入: `ul>li*` (也可以用诸如:`blockquote`), 得到:

	&lt;ul&gt;  
		&lt;li&gt;test1&lt;/li&gt;  
		&lt;li&gt;test2&lt;/li&gt;  
		&lt;li&gt;test3&lt;/li&gt;  
	&lt;/ul&gt;

4. 其它的不再列举, 参看官方文档, 这里再给一个执行键对照表


	+--------+--------------------------------------------------------------------+
	| 执行键 | 执行效果                                                           |
	+--------+--------------------------------------------------------------------+
	| ,(逗号)| 展开缩写,或对选定内部执行定义                                      |
	| d      | 向内平衡标签                                                       |
	| D      | 向外平衡标签                                                       |
	| n      | 下一个编辑点                                                       |
	| N      | 上一个编辑点                                                       |
	| i      | 给img增加size(width/height)标签                                    |
	| m      | merge合并行(Visual模式下)                                          |
	| k      | 去除当前标签(及其内容)                                             |
	| j      | 收缩或展示独立标签(<div class='foo'></div> = <div class='foo' />)  |
	| /      | 注释(或反注释)当前代码                                             |
	| a      | 将网址(需要http头)处理为a标签                                      |
	| A      | 将网址处理为网站信息引用块                                         |
	+--------+--------------------------------------------------------------------+

其它: 自定义功能键

	let g:user_emmet_settings = {
	\  'indentation' : '  ',
	\  'perl' : {
	\    'aliases' : {
	\      'req' : 'require '
	\    },
	\    'snippets' : {
	\      'use' : "use strict\nuse warnings\n\n",
	\      'warn' : "warn \"|\";",
	\    }
	\  }
	\}

	let g:user_emmet_expandabbr_key = '<c-e>'
	let g:use_emmet_complete_tag = 1




## vim-indent-guides

	A Vim plugin for visually displaying indent levels in code
	http://www.vim.org/scripts/script.php?script_id=3361
	给代码显示缩进线
	2014年1月13日 15:37:27

切换缩进线显示命令: `\ig`

	let g:indent_guides_enable_on_vim_startup = 1  "启动时开启缩进线
	let g:indent_guides_start_level = 2            "从第二级开始进行提示
	let g:indent_guides_guide_size = 1             "缩进提示线宽度为1



## Tablify

	Tablify : Plugin for making nice-loking tables from plain structured text 
	http://www.vim.org/scripts/script.php?script_id=4358
	表格转化插件
	2014年2月27日 13:58:00

将选定的文本(字段默认用|分隔, 或者用 b:tablify_raw_delimiter 在vimrc中指定)转换为线框包围的表格, 用法(功能键为右斜线 \):

* `\tl or \tt` - 将选定文本转换为表格(默认文本左对齐)
* `\tc` - 表格文本居中对齐
* `\tr` - 表格文本右对齐
* `\tu` - 反操作, 将选定的表格还原为文本
* `\ta` - 选中当前整个表格

对已经转换的表格, 还可执行如下操作:

* `\tS` - 将表格排序, 支持数字和文本排序
* `\tRL` - 表格文本重设为左对齐
* `\tRR` - 表格文本重设为右对齐
* `\tRC` - 表格文本重设为居中对齐


操作表格内的当前位置光标:
* `\tK` - move current row (where the cursor is) up
* `\tJ` - move current row down
* `\tL` - move current column (where the cursor is) right
* `\tH` - move current column left

实测, 将以下文本转换为表格:

	Artist | Song | Album | Year  
	Pantera | Cemetery Gates | Cowboys from Hell | 1990  
	Ozzy Osbourne | Let Me Hear You Scream | Scream | 2010

结果如下:

	+---------------+------------------------+-------------------+------+  
	| Artist        | Song                   | Album             | Year |  
	+---------------+------------------------+-------------------+------+  
	| Pantera       | Cemetery Gates         | Cowboys from Hell | 1990 |  
	+---------------+------------------------+-------------------+------+  
	| Ozzy Osbourne | Let Me Hear You Scream | Scream            | 2010 |  
	+---------------+------------------------+-------------------+------+

其它特殊效果:

1. 区分标题行, 将文本标题行的分隔符换为 # , 转换后的表格标题行使用波浪线包围
2. 表格太长影响展示效果时, 可以使用行内换行, 只需在较长的cell中, 适当加入 `\n` 即可

配置参数: 

	g:loaded_tablify               - 等于1时不加载该控件
	b:tablify_headerDelimiter      - 标题行的文本分隔符, 默认为 #
	b:tablify_delimiter            - 表格字段的分隔符, 默认为 |

	b:tablify_vertDelimiter        - 表格包围线, 垂直分隔线 (默认为 |)
	b:tablify_horDelimiter         - 表格包围线, 水平分隔线 (默认为 -)
	b:tablify_horHeaderDelimiter   - 表格包围线, 标题行水平分隔线 (默认为 ~)
	b:tablify_divideDelimiter      - 表格包围线, 交叉线 (默认为 +)

	b:tablify_cellLeftPadding      - 表格左对齐时, 左边留白宽度, 默认为1
	b:tablify_cellRightPadding     - 表格右对齐时, 右边留白宽度, 默认为1



## vim-airline

	vim-airline : lean & mean statusline that's light as air
	http://www.vim.org/scripts/script.php?script_id=4661
	漂漂的状态栏
	2014年3月17日 14:59:43

默认在多窗口时才显示, 如果想要只有一个窗口时也显示该状态栏, 需要在vimrc中设置 `set laststatus=2`



## py-mode

	Python-mode, Python in VIM
	https://github.com/klen/python-mode
	2014年3月15日 14:42:56

Python-mode is a vim plugin that helps you to create python code very quickly by utilizing libraries
including pylint, rope, pydoc, pyflakes, pep8, and mccabe for features like static analysis,
refactoring, folding, completion, documentation, and more.

The plugin contains all you need to develop python applications in Vim.

There is no need to install pylint, rope or any other Python libraries on your system.

* Support Python version 2.6+ and 3.2+
* Syntax highlighting
* Virtualenv support
* Run python code (<leader>r)
* Add/remove breakpoints (<leader>b)
* Improved Python indentation
* Python folding
* Python motions and operators (]], 3[[, ]]M, vaC, viM, daC, ciM, ...)
* Code checking (pylint, pyflakes, pylama, ...) that can be run simultaneously (:PymodeLint)
* Autofix PEP8 errors (:PymodeLintAuto)
* Search in python documentation (K)
* Code refactoring <rope refactoring library> (rope)
* Strong code completion (rope)
* Go to definition (<C-c>g for :RopeGotoDefinition)
* And more, more ...



## CtrlP

	ctrlp.vim : Fuzzy file, buffer, mru, tag, ... finder with regexp support. 
	http://www.vim.org/scripts/script.php?script_id=3736
	2014年6月26日 15:27:31

### 说明
类似everything的快速文件查找与切换插件, 使用`<c-p>`打开



## OTHERS TO BE ADD..
todo



---

## 附1: pathogen安装对照表

	+----------------------------------------------------+--------------------------------------+
	| PROJECT IN GITHUB                                  | LOCAL PATH                           |
	+----------------------------------------------------+--------------------------------------+
	| https://github.com/tpope/vim-pathogen              | vimfiles/bundle/vim-pathogen         |
	| https://github.com/vim-scripts/taglist.vim         | vimfiles/bundle/taglist              |
	| https://github.com/wesleyche/SrcExpl               | vimfiles/bundle/SrcExpl              |
	| https://github.com/scrooloose/nerdtree             | vimfiles/bundle/nerdtree             |
	| https://github.com/wesleyche/Trinity               | vimfiles/bundle/Trinity              |
	| https://github.com/scrooloose/nerdcommenter        | vimfiles/bundle/nerdcommenter        |
	| https://github.com/fholgado/minibufexpl.vim        | vimfiles/bundle/minibufexpl          |
	| https://github.com/mattn/emmet-vim                 | vimfiles/bundle/emmet-vim            |
	| https://github.com/nathanaelkane/vim-indent-guides | vimfiles/bundle/vim-ident-guides     |
	| https://github.com/Stormherz/tablify               | vimfiles/bundle/tablity              |
	| https://github.com/klen/python-mode                | vimfiles/bundle/python-mode          |
	| https://github.com/bling/vim-airline               | vimfiles/bundle/vim-airline          |
	| https://github.com/Shougo/neosnippet.vim           | vimfiles/bundle/neosnippet           |
	| https://github.com/Shougo/neocomplcache.vim        | vimfiles/bundle/neocomplcache        |
	| https://github.com/terryma/vim-multiple-cursors    | vimfiles/bundle/vim-multiple-cursors |
	| https://github.com/tpope/vim-surround              | vimfiles/bundle/vim-surround         |
	| https://github.com/justinmk/vim-sneak              | vimfiles/bundle/vim-sneak            |
	| https://github.com/plasticboy/vim-markdown         | vimfiles/bundle/vim-markdown         |
	| https://github.com/kien/ctrlp.vim                  | vimfiles/bundle/ctrlp                |
	| https://github.com/mattn/calendar-vim              | vimfiles/bundle/calendar             |
	| https://github.com/altercation/vim-colors-solarized| vimfiles/bundle/solarized            |
	+----------------------------------------------------+--------------------------------------+


