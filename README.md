# Vim���������

��������������װ��¼��Ŀǰ�����Ҫ���python����ʹ��
����`gVim Portable` [(offical_site)](http://portableapps.com/apps/development/gvim_portable) ��������������

��Ŀ�����ļ�λ��`../gVimPortable/Data/settings`Ŀ¼��

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
	 |-- SrcExpl
	 |     http://www.vim.org/scripts/script.php?script_id=2179
	 |     �����ڶ�����ת�趨
	 |-- The NERD tree
	 |     http://www.vim.org/scripts/script.php?script_id=1658
	 |     Ŀ¼��



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




## Pydiction

	Tab-complete your Python code
	http://www.vim.org/scripts/script.php?script_id=850
	python���벹ȫ���
	2014��1��13�� 14:41:29

Codingʱ,ʹ��`<TAB>`��������ȫ�б�, �������ִ�еĲ���:

* `CTRL-Y`    Accept the currently selected match and stop completion.
* `<Space>`   Accept the currently selected match and insert a space.
* `CTRL-E`    Close the menu and not accept any match.

��Ҫ�����������ļ����趨'�ֵ�·��' ��'��ȫ�б��С'(��ѡ)

	filetype plugin on
	let g:pydiction_location = 'C:/vim/vimfiles/ftplugin/pydiction/complete-dict'
	let g:pydiction_menu_height = 20  "The default menu height is 15.



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




## OTHERS TO BE ADD..



---

## ��1: pathogen��װ���ձ�

	+------------------------------------------------------+----------------------------------+
	| PROJECT IN GITHUB                                    | LOCAL PATH                       |
	+------------------------------------------------------+----------------------------------+
	| git://github.com/tpope/vim-pathogen.git              | vimfiles/bundle/vim-pathogen     |
	| git://github.com/vim-scripts/taglist.vim.git         | vimfiles/bundle/taglist          |
	| git://github.com/wesleyche/SrcExpl.git               | vimfiles/bundle/SrcExpl          |
	| git://github.com/scrooloose/nerdtree.git             | vimfiles/bundle/nerdtree         |
	| git://github.com/wesleyche/Trinity.git               | vimfiles/bundle/Trinity          |
	| git://github.com/scrooloose/nerdcommenter.git        | vimfiles/bundle/nerdcommenter    |
	| git://github.com/fholgado/minibufexpl.vim.git        | vimfiles/bundle/minibufexpl      |
	| git://github.com/mattn/emmet-vim.git                 | vimfiles/bundle/emmet-vim        |
	| git://github.com/nathanaelkane/vim-indent-guides.git | vimfiles/bundle/vim-ident-guides |
	| git://github.com/Stormherz/tablify.git               | vimfiles/bundle/tablity          |
	| git://github.com/rkulla/pydiction.git                | vimfiles/bundle/pydiction        |
	| git://github.com/klen/python-mode.git                | vimfiles/bundle/python-mode      |
	+------------------------------------------------------+----------------------------------+

