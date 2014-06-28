# Vim���������

��������������װ��¼��Ŀǰ�����Ҫ���python����ʹ��
����`gVim Portable` [(offical_site)](http://portableapps.com/apps/development/gvim_portable) ��������������

��Ŀ�����ļ�λ��`../gVimPortable/Data/settings`Ŀ¼��

ʹ��Pathgen���в����ͳһ����, ���Github, �ܺú�ǿ��

version: 2, based on the first conf: [vim-set](https://github.com/fatway/vim_set)

refer: http://lostjs.com/2012/02/04/use-pathogen-and-git-to-manage-vimfiles/

--- 

## Pathogen

	Easy manipulation of 'runtimepath', 'path', 'tags', etc
	http://www.vim.org/scripts/script.php?script_id=2332
	ͳһ������ (����Ĳ��)

�ò����̬����bundle�µ����в��, �����ͷ����������Ķ�������, ��������

### ��װ���:

	$ git submodule add �����Git�ֿ��ַ vimfiles/bundle/�������

���ڼ��ص���Ҫ, ��pathogen.vim �ֶ�����autoloadĿ¼��, �Է����䶯̬�����������

### �������

  * �������������ֻҪ�Ƚ�����Ŀ¼��Ȼ��ִ�У�

	$ git checkout master; git pull

  * ͨ��git submodule foreach������һ��������ȫ�������

	$ git submodule foreach 'git checkout master && git pull'

	ȷ����master��֧�µĻ�, ʹ��������и���
	$ git submodule foreach 'git stash && git pull && git stash clear'

### ɾ�����

	$ rm -rf bundle/�����
	$ git rm -r bundle/�����



## trinity

	Trinity : the Trinity of taglist, NERDtree and SrcExpl: an IDE works like "Source Insight"
	http://www.vim.org/scripts/script.php?script_id=2347
	һվʽ�������ɲ��������taglist,tree,srcexpl����������к����б��ļ�Ŀ¼
	2014��1��13�� 14:21:32

������vimrc�ļ��е�������������Ӧ�Ĺ��ܴ���

	nmap <F8>   :TrinityToggleAll<CR>             " �л����������ʾ
	nmap <F9>   :TrinityToggleSourceExplorer<CR>  " �л�Դ����ʾ���
	nmap <F10>  :TrinityToggleTagList<CR>         " �л������б���
	nmap <F11>  :TrinityToggleNERDTree<CR>        " �л��ļ�Ŀ¼���


��������������£�����Ҫ�ٶ���������������趨��

	��
	 |-- taglist.vim
	 |     http://www.vim.org/scripts/script.php?script_id=273
	 |     ��Ҫ����Դ����Ĺ���Ctags(http://ctags.sourceforge.net/)��
	 |     ��ѹ���󿽱�ctags.exe��app�µ�vim��װλ�ã����߷���system32
	 |     ��ݼ�:
	 |		`<CR>`         ���������tag�������λ�ã������˫����tag����Ҳһ��
	 |		`o`             ��һ���´򿪵Ĵ�������ʾ�����tag
	 |		`<Space>`       ��ʾ�����tag��ԭ�Ͷ���
	 |		`u`             ����taglist�����е�tag
	 |		`s`             ��������ʽ���ڰ���������Ͱ�����˳��������л�
	 |		`x`             taglist���ڷŴ����С������鿴�ϳ���tag
	 |		`+`             ��һ���۵���ͬzo
	 |		`-`             ��tag�۵�������ͬzc
	 |		`*`             �����е��۵���ͬzR
	 |		`=`             ������tag�۵�������ͬzM
	 |		`[[`            ����ǰһ���ļ�
	 |		`]]`            ������һ���ļ�
	 |		`q`             �ر�taglist����
	 |		`<F1>`          ��ʾ����
	 |
	 |-- SrcExpl
	 |     http://www.vim.org/scripts/script.php?script_id=2179
	 |     �����ڶ�����ת�趨
	 |-- The NERD tree
	 |     http://www.vim.org/scripts/script.php?script_id=1658
	 |     Ŀ¼�����, ��ݼ�:
	 |		`o`	չ�����ĳ��Ŀ¼���ٰ�һ�¾��Ǻϲ�Ŀ¼ 
	 |		`t`	���� Tab �д�ѡ���ļ�/��ǩ���������� Tab
	 |		`T`	���� Tab �д�ѡ���ļ�/��ǩ������������ Tab
	 |		`P`	���������
	 |		`p`	���������
	 |		`q`	�ر� NerdTree ����



## NERD_commenter

	http://www.vim.org/scripts/script.php?script_id=1218
	����ע�Ͳ��
	2014��1��13�� 14:39:30

NERD Commenter�ĳ��ü��󶨣���C/C++�ļ�Ϊ����������ʹ�÷�������:h NERDCommenter����Normal����Visual ģʽ�£�

* `\ca`���ڿ�ѡ��ע�ͷ�ʽ֮���л�������C/C++ �Ŀ�ע��/* */����ע��//
* `\cc`��ע�͵�ǰ�У�����ѡ����
* `\c `���л�ע��/��ע��״̬
* `\ci`, �л�ע�� individually
* `\cs`���ԡ��ԸС��ķ�ʽע��
* `\cA`���ڵ�ǰ��β���ע�ͷ���������Insertģʽ
* `\cu`��ȡ��ע��
* `\c$`, �ӵ�ǰ���ע�͵��н�β

Normalģʽ�£�������������ǰ�涼����ָ������
Visualģʽ��ִ��������ѡ�е��ض��������ע��/��ע��

ʹ�øò����Ҫ���� `filetype plugin on`




## minibufexpl

	minibufexpl.vim : Elegant buffer explorer - takes very little screen space 
	http://www.vim.org/scripts/script.php?script_id=159
	�������鿴�����Կ������ѱ༭�����ļ�֮������л�
	2014��2��12�� 09:24:34

ʹ������:

* `control + [hjkl]` �л�������������
* `control + arrow keys` ͬ�� 
* `control + tab` & `shift + control + tab` ���Ѵ򿪵Ĺ��������л�



## Emmet

	vim plugins for HTML and CSS hi-speed coding.
	http://www.vim.org/scripts/script.php?script_id=2981
	hmtlԴ����ٱ༭
	�ο��̳̣�http://docs.emmet.io/abbreviations/syntax/
	2014��1��13�� 14:40:41

Tips:

Ĭ��չ��_���ܼ�_Ϊ`<c-y>,` (��ctrl+yȻ�󰴶���)  
������˶���һ������: `<c-y>`: ���ܼ�, `,(����)`: ִ�м�  
����̳�: https://raw.github.com/mattn/emmet-vim/master/TUTORIAL

ʾ��:

1. �һ����׼��htmlģ��: `html:5` , Ȼ��ʹ�ù��ܼ��� �� ��`,`ִ�м�
2. ������չ: `div>p#foo$*3>a`
3. ���������ı�:

	test1  
	test2  
	test3

  ��visualģʽ��ѡ�и�����, ִ�й��ܼ�+����, ��������﷨��ʾ������: `ul>li*` (Ҳ����������:`blockquote`), �õ�:

	&lt;ul&gt;  
		&lt;li&gt;test1&lt;/li&gt;  
		&lt;li&gt;test2&lt;/li&gt;  
		&lt;li&gt;test3&lt;/li&gt;  
	&lt;/ul&gt;

4. �����Ĳ����о�, �ο��ٷ��ĵ�, �����ٸ�һ��ִ�м����ձ�


	+--------+--------------------------------------------------------------------+
	| ִ�м� | ִ��Ч��                                                           |
	+--------+--------------------------------------------------------------------+
	| ,(����)| չ����д,���ѡ���ڲ�ִ�ж���                                      |
	| d      | ����ƽ���ǩ                                                       |
	| D      | ����ƽ���ǩ                                                       |
	| n      | ��һ���༭��                                                       |
	| N      | ��һ���༭��                                                       |
	| i      | ��img����size(width/height)��ǩ                                    |
	| m      | merge�ϲ���(Visualģʽ��)                                          |
	| k      | ȥ����ǰ��ǩ(��������)                                             |
	| j      | ������չʾ������ǩ(<div class='foo'></div> = <div class='foo' />)  |
	| /      | ע��(��ע��)��ǰ����                                             |
	| a      | ����ַ(��Ҫhttpͷ)����Ϊa��ǩ                                      |
	| A      | ����ַ����Ϊ��վ��Ϣ���ÿ�                                         |
	+--------+--------------------------------------------------------------------+

����: �Զ��幦�ܼ�

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
	��������ʾ������
	2014��1��13�� 15:37:27

�л���������ʾ����: `\ig`

	let g:indent_guides_enable_on_vim_startup = 1  "����ʱ����������
	let g:indent_guides_start_level = 2            "�ӵڶ�����ʼ������ʾ
	let g:indent_guides_guide_size = 1             "������ʾ�߿��Ϊ1



## Tablify

	Tablify : Plugin for making nice-loking tables from plain structured text 
	http://www.vim.org/scripts/script.php?script_id=4358
	���ת�����
	2014��2��27�� 13:58:00

��ѡ�����ı�(�ֶ�Ĭ����|�ָ�, ������ b:tablify_raw_delimiter ��vimrc��ָ��)ת��Ϊ�߿��Χ�ı��, �÷�(���ܼ�Ϊ��б�� \):

* `\tl or \tt` - ��ѡ���ı�ת��Ϊ���(Ĭ���ı������)
* `\tc` - ����ı����ж���
* `\tr` - ����ı��Ҷ���
* `\tu` - ������, ��ѡ���ı��ԭΪ�ı�
* `\ta` - ѡ�е�ǰ�������

���Ѿ�ת���ı��, ����ִ�����²���:

* `\tS` - ���������, ֧�����ֺ��ı�����
* `\tRL` - ����ı�����Ϊ�����
* `\tRR` - ����ı�����Ϊ�Ҷ���
* `\tRC` - ����ı�����Ϊ���ж���


��������ڵĵ�ǰλ�ù��:
* `\tK` - move current row (where the cursor is) up
* `\tJ` - move current row down
* `\tL` - move current column (where the cursor is) right
* `\tH` - move current column left

ʵ��, �������ı�ת��Ϊ���:

	Artist | Song | Album | Year  
	Pantera | Cemetery Gates | Cowboys from Hell | 1990  
	Ozzy Osbourne | Let Me Hear You Scream | Scream | 2010

�������:

	+---------------+------------------------+-------------------+------+  
	| Artist        | Song                   | Album             | Year |  
	+---------------+------------------------+-------------------+------+  
	| Pantera       | Cemetery Gates         | Cowboys from Hell | 1990 |  
	+---------------+------------------------+-------------------+------+  
	| Ozzy Osbourne | Let Me Hear You Scream | Scream            | 2010 |  
	+---------------+------------------------+-------------------+------+

��������Ч��:

1. ���ֱ�����, ���ı������еķָ�����Ϊ # , ת����ı�������ʹ�ò����߰�Χ
2. ���̫��Ӱ��չʾЧ��ʱ, ����ʹ�����ڻ���, ֻ���ڽϳ���cell��, �ʵ����� `\n` ����

���ò���: 

	g:loaded_tablify               - ����1ʱ�����ظÿؼ�
	b:tablify_headerDelimiter      - �����е��ı��ָ���, Ĭ��Ϊ #
	b:tablify_delimiter            - ����ֶεķָ���, Ĭ��Ϊ |

	b:tablify_vertDelimiter        - ����Χ��, ��ֱ�ָ��� (Ĭ��Ϊ |)
	b:tablify_horDelimiter         - ����Χ��, ˮƽ�ָ��� (Ĭ��Ϊ -)
	b:tablify_horHeaderDelimiter   - ����Χ��, ������ˮƽ�ָ��� (Ĭ��Ϊ ~)
	b:tablify_divideDelimiter      - ����Χ��, ������ (Ĭ��Ϊ +)

	b:tablify_cellLeftPadding      - ��������ʱ, ������׿��, Ĭ��Ϊ1
	b:tablify_cellRightPadding     - ����Ҷ���ʱ, �ұ����׿��, Ĭ��Ϊ1



## vim-airline

	vim-airline : lean & mean statusline that's light as air
	http://www.vim.org/scripts/script.php?script_id=4661
	ƯƯ��״̬��
	2014��3��17�� 14:59:43

Ĭ���ڶര��ʱ����ʾ, �����Ҫֻ��һ������ʱҲ��ʾ��״̬��, ��Ҫ��vimrc������ `set laststatus=2`



## py-mode

	Python-mode, Python in VIM
	https://github.com/klen/python-mode
	2014��3��15�� 14:42:56

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
	2014��6��26�� 15:27:31

### ˵��
����everything�Ŀ����ļ��������л����, ʹ��`<c-p>`��



## OTHERS TO BE ADD..
todo



---

## ��1: pathogen��װ���ձ�

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


