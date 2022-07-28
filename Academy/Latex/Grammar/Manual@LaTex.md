---
file_type: Manual # Manual
file_catalogue: LaTeX
CreateTime: 2022
---

#Missing 
> The file of the $\LaTeX$   can be divided to two part:
> 		1. Preamble
> 		2. Content
> 		3. Function
> 		
> <mark style="background: #ADCCFFA6;">The Reference is: 一份（不太）简短的LaTex介绍</mark> --Using'📄' indicate the page of the file.

# 1. Preamble
## 1.1. 文档类
>`\ducumentclass[<options>]{class-name}`

### 1.1.1. <font color="gray">&lt;class-name&gt;</font>

文档类型：
英文：
| Classic | External |  
| ------- | -------- | 
| article | proc     | 
| report  | slides   | 
| book    | minimal  | 


中文：
-  `ctexart`
- `ctexrep`
- `ctexbook`

### 1.1.2. <font color="gray">&lt;options&gt;</font>

Basic Option：
- `10pt`
- `a4paper`
- `onecolumn`,  `twocolumn`
- `landscape`
- `titlepage`

`More`  📄:6 

## 1.2. 宏包
>📄: 6
>Appendix：📄: B.3
>Manual： `DOS> texdoc <package-name>`

```latex
\usepackage[<optiond>]{<package-name>}
```

## 1.3. Command

```latex
\include{<filename>} % Connect files, Default: newpage
\input{<filname>}    % Insert the content from "<filename>"
\includeonly{<filename1>,<filename2>,...} % Used in preamble(make command `\include` unabled) 
```

# 2. Command
符号：📘表4.4 📄:x   */*  Ref.14
## 2.1. 内容排版
### 2.1.1. 章节和目录
```latex
% Abstract
% Only for article and report; Behind command '\maketitle' 
% Like a section for 'notitlepage' environmnet 

% Section
% --------
\chapter{<title>} % Onlt for book and report
% Need Package: titlesec
\section{<title>} \subsection{<title>} \subsubsection{<title>}
\paragraph{<title>} \subparagraph{<title>}
\part

% Table of Content
% ----------------
\tableofcontent % Default title is 'Contents'; Need Compile twice
\addcontentsline{toc}{<level>}{<title>}  % For the command like '\section*'

% Appendix
% --------
\appendix 
\frontmatter \mainmatter \backmatter % Only for book document

% Title
% -----
\title{<title>} \author{<author>} \date{<date>} % '\title' is necessary; '\date' is today by default
\thanks{} % Titlepage footnote
\maketitle % The commond should be in '\begin{documnet}...\end{document}'
\titlepage \notitlepage % article is notitlepage by default, and the book and report are another; Also can change it by writting it on \documentclass.
```
### 2.1.2. 空格、断行、断页
#### 2.1.2.1. 空格
1. `~` 表示不断行空格

#### 2.1.2.2. 断行

```latex
\\[<length>]   % 参数 <length> 用于在断行处向下增加垂直间距
\\*[<length>]  % '*' 表示不在断行处分页
\newline       % `\\`在段落中新起一行
```

#### 2.1.2.3. 断页

```latex
\newpage   % 双栏时仅另起一栏
\clearpage % 
\linebreak[<n>]  \nolinebreak[<n>] % 断行与否的合适程度，默认4，0~4 可选
\pagebreak[<n>]  \nopagebreak[<n>] % 断页与否的合适程度
```
### 2.1.3. 对齐
```latex
% Will create external interval
\begin{center}...\end{center}         
\begin{flushleft}...\end{flushleft}
\begin{flushright}...\end{flushright}

% Only change the alignment of the word.
% Usually used in table or figure.
\centering
\raggedright
\raggedleft
```
## 2.2. 特殊环境
### 2.2.1. Quote
#### 2.2.1.1. Label
```latex
\label{<lable-name>} % For section, formular, Figure, Chart, table ...
\ref{<lable-name>} \pageref{<lable-name>} 

% Example
\section{}
\label{}

\lable{sec:this}
page~\pageref{sec:this}


% footnote
% --------
\footnote{<footnote>}

% In some case, such as table environment:
% ------------------------------------
\footnotemark % Count
\footnotetext % Display
% ------------------------------------

\marginpar[<left-margin>]{} % footnote on margin
```
#### 2.2.1.2. Quote Word
```latex
% For short sentence
% Unindent first line
\begin{quote}
...
\end{quote}

% For long(or short)sentence
% Indent first line
\begin{quotation}
...
\end{quotation}

% For Poem
\begin{verse}...\end{verse}
```
### 2.2.2. List
```latex
% Ordered List:    enumerate
% Unordered List:  itemize
% Using '\item' in environment
% Loop Nest four times
% Extension: Package-enumitem


% Example:
% ————————————————————————————————————————
\begin{enumerate}
	\item e.g. 1
	\begin{enumerate}
		\item e.g. 1.1
		\item[*] e.g. 1.2
		\item[+] e.g. 1.3
	\end{enumerate}
\end{enumerate}
% ————————————————————————————————————————

% renew the icon of the list
% From i to v 

% Ondered List:    
\renewcommand{\labelenumi}

% Unodered List
\renewcommand{\labelitemi}{\ddag}
\renewcommand{\labelitemii}{\dag} 



% Usage of the '\description'
...
\item[<item title>] % '<item titile>' will be bold
...
  
```
### Code
```latex
\begin{verbatim}
...
\end{verbatim}
% OR
% The 'space' -> '_'
\begin{verbatim*}
...
\end{verbatim*}

% For short
\verb|...|
\verb*|...|

% Package
% ———————————————
% {verbatim} -> optimization verbatim
% {fancyvrb} -> Freedom Style
% {listings} -> Highlight...
% ———————————————
```
### Table
```latex
\begin{tabular}[htbp]{<column-spec>} 
% t -> top; b -> bottom; h -> here 
<item.1> & <item.2> \\
\hline
\caption{<table-name>}
\end{tabular}


% <column-spec>:
% ————————————————————————
% l/c/r      -> Align method
% p{width}   -> Set the width of the cell
% |          -> Draw line -> e.g. |<word>|<word>|
% @{<string} -> Custom: Insert the content at any place
% ┗━ '@{}' can remove the space 
% ————————————————————————

% For easy: {*{n}{column-spec*}
% e.g. ccccc = *{5}{c}


% Setting of the cell
\multicolumn{<n>}{}



% Package: {array}, {tabularx}, {booktabs}
```
# 3. Package



# 4. Problem
>The contents are on fold `"../Archive/Problem"`

```dataview
Table
Description
From "Academy/Latex/Archive/Problem"
```



# 5. Link

[LaTeX详细教程+技巧总结_NSJim的博客-CSDN博客_latex使用教程](https://blog.csdn.net/NSJim/article/details/109066847)
