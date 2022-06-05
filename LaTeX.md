# LaTeX

[toc]

## 基本结构

```latex
%导言区
\documentclass{article} %还可以是book report letter

\title{My First Latex}
\author{Nan Geng}
\date{\today}

%正文区
\begin{document}
	\maketitle
	
	Hello World!
	
	Let $f(x)$ be defined by the formula
	$$f(x)=3x^2+x-1$$ which is a polynomial of degree 2.
\end{document}
```

空行 换段

\\\ 换行不缩进

$ 数学公式

$$ 行间数学公式

导言区进行环境设置

一个文档只能有一个document

![image-20220124130740047](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220124130740047.png)

## 中文环境

```latex
\documentclass{article}

\usepackage{ctex}
\newcommand\degree{^\circ} %定义一个新的命令

\title{\heiti 杂谈勾股定理} %指定字体
\author{\kaishu 张三}
\date{\today}

\begin{document}
	\maketitle
	
	勾股定理可以用现代语言表述如下：
	
	直角三角形斜边的平方和等于两腰的平方和。
	
	可以用符号语言表示为：设直角三角形 $ABC$，其中$\angle
	C=90\degree$，则有：
	\begin{equation}
	AB^2 = BC^2 + AC^2.
	\end{equation}
\end{document}
```

检查：设置——构建——XeLaTeX——编码格式UTF-8

begin{equation} 带编号的行间公式

cmd中texdoc查看帮助文档

![image-20220124131340908](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220124131340908.png)

## 字体设置

```latex
\documentclass[10pt]{article} %可选normalsize大小

\usepackage{ctex}

\newcommand{\myfont}{\textit{\textbf{\textsf{Fancy Text}}}}

\begin{document}
	%字体族的设置（罗马字体、无衬线字体、打印机字体）
	\textrm{Roman Family} \textsf{Sans Serif Family} \texttt{Typewriter Family}
	
	{\rmfamily Roman Family} {\sffamily Sans Serif Family} {\ttfamily Typewriter Family}
	
	%字体系列设置（粗细、宽度）
	\textmd{Medium Series} \textbf{Boldface Series}
	
	{\mdseries Medium Series} {\bfseries Boldface Series}
	
	%字体形状设置（直立、斜体、伪斜体、小型大写）
	\textup{Upright Shape} \textit{Italic Shape}
	\textsl{Slanted Shape} \textsc{Small Caps Shape}
	
	{\upshape Upright Shape} {\itshape Italic Shape} {\slshape Slanted Shape} {\scshape Small Caps Shape}
	
	%中文字体
	{\songti 宋体} \quad {\heiti 黑体} \quad {\fangsong 仿宋} \quad {\kaishu 楷书}
	
	中文字体的\textbf{粗体}与\textit{斜体}
	
	%字体大小（相对于normalsize而言）
	{\tiny         Hello}\\
	{\scriptsize   Hello}\\
	{\footnotesize Hello}\\
	{\small        Hello}\\
	{\normalsize   Hello}\\
	{\large        Hello}\\
	{\Large        Hello}\\
	{\LARGE        Hello}\\
	{\huge         Hello}\\
	{\Huge         Hello}\\
	
	%中文字体大小
	\zihao{5} 你好！
	
	\myfont %定义的命令
	
\end{document}
```

{} 字体作用的范围

![image-20220219220942668](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220219220942668.png)

## 篇章结构

```latex
\documentclass{ctexbook}

\usepackage{ctex}

\begin{document}
	\tableofcontents
	
	\chapter{绪论} % 需要ctexbook
	\section{引言}
	正文段落1
	
	正文段落2\\正文段落3 \par 正文段落4
	\section{实验方法}
	\section{实验结果}
	\subsection{数据}
	\subsection{图表}
	\subsubsection{实验条件}
	\subsubsection{实验过程}
	\subsection{结果分析}
	\section{结论}
	\section{致谢}
	
\end{document}
```

\par 换段落

set section 查看宏包帮助文档,改变标题格式

![image-20220219220856931](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220219220856931.png)

## 特殊字符

```latex
\documentclass{article}

\usepackage{ctex}

\begin{document}
	\section{空白符号}
	% 空行分段，多个空行为1个
	% 自动缩进，不能使用空格代替
	% 英文中多个空格为1个，中文自动忽略
	% 汉字间距自动处理
	% 禁止使用中文全角空格
	
	% 1em（当前字体中M的宽度）
	a\quad b
	
	% 2em
	a\qquad b
	
	% 约1/6em
	a\,b a\thinspace b
	
	% 0.5em
	a\enspace b
	
	% 空格
	a\ b
	
	% 硬空格
	a~b
	
	% 1pc=12pt=4.218mm
	a\kern 1pc b
	
	a\kern -1em b
	
	a\hskip 1em b
	
	a\hspace{35pt}b
	
	% 占位宽度
	a\hphantom{xyz}b
	
	% 弹性宽度
	a\hfill b
	
	\section{LaTeX控制符}
	\# \$ \% \{ \} \~{} \_{} \^{} \textbackslash \&
	
	\section{排版符号}
	\S \P \dag \ddag \copyright \pounds
	
	\section{TeX标志符号}
	\TeX{} \LaTeX{} \LaTeXe{}
	
	\section{引号}
	` ' `` '' ``Hello''
	
	\section{连字符}
	- -- ---
	
	\section{非英文字符}
	\oe \OE \ae \AE \aa \AA \o \O \l \L \ss \SS !` ?` 
	
	\section{重音符号（以o为例}
	\`o \'o \^o \''o \~o \.o \=o \u{o} \v{o} \H{o} \r{o} \t{o} \b{o} \c{o} \d{o}
	
\end{document}
```

TeX特殊字符可以通过宏包引入

![](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220219221056946.png)

## 插图问题

```latex
\documentclass{ctexart}

\usepackage{ctex}

\usepackage{graphicx}
% 语法：\inludedgraphics[<选项>]{<文件名>}
% 格式：EPS PDF PNG JEPG BMP
\graphicspath{{LaTeX/}} % 图片在当前工作目录下的LaTeX目录

\begin{document}
	\LaTeX{}中的插图:
	
	\includegraphics{figure1}
	\includegraphics{figure2}
	\includegraphics{figure3}
	
	\includegraphics[scale=0.3]{figure1}
	\includegraphics[scale=0.03]{figure2}
	\includegraphics[scale=0.3]{figure3}
	
	\includegraphics[height=2cm]{figure1}
	\includegraphics[height=2cm]{figure2}
	\includegraphics[height=2cm]{figure3}
	
	\includegraphics[width=2cm]{figure1}
	\includegraphics[width=2cm]{figure2}
	\includegraphics[width=2cm]{figure3}
	
	\includegraphics[height=0.1\textheight]{figure1}
	\includegraphics[height=0.1\textheight]{figure2}
	\includegraphics[height=0.1\textheight]{figure3}
	
	\includegraphics[width=0.2\textwidth]{figure1}
	\includegraphics[width=0.2\textwidth]{figure2}
	\includegraphics[width=0.2\textwidth]{figure3}
	
	\includegraphics[angle=-45,width=0.2\textwidth]{figure1}
	\includegraphics[width=0.2\textwidth]{figure1}	
	\includegraphics[angle=45,width=0.2\textwidth]{figure1}	

\end{document}
```

## 表格排版

```latex
\documentclass{article}

\usepackage{ctex}

\begin{document}
	\begin{tabular}{|l||c|c|c|p{1.5cm}|}
		\hline
		姓名 & 语文 & 数学 & 英语 & 备注 \\
		\hline \hline
		张三 & 87 & 100 & 93 & 优秀 \\
		\hline
		李四 & 75 & 64 & 52 & 补考另行通知 \\
		\hline
		王二 & 80 & 82 & 78 & \\
		\hline
	\end{tabular}
\end{document}
```

![image-20220219221131030](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220219221131030.png)

## 浮动体

```latex
\documentclass{article}

\usepackage{ctex}

\usepackage{graphicx}

\graphicspath{{LaTeX/}}

\begin{document}
	这是墙纸1
	\LaTeX{}中的插图见图\ref{fig-高楼}: % 交叉引用
	\begin{figure}[htbp]
		\centering % 居中排列
        \includegraphics[scale=0.2]{figure1}
        \caption{\TeX 高楼}\label{fig-高楼} % 设置标题以及标签
	\end{figure}
	
	这是墙纸2
	\LaTeX{}中的插图见图\ref{fig-代码}:
	\begin{figure}[htbp]
		\centering
        \includegraphics[scale=0.2]{figure2}
        \caption{\TeX 代码}\label{fig-代码}
	\end{figure}
	
	这是墙纸3
	\LaTeX{}中的插图见图\ref{fig-白云}:
	\begin{figure}[htbp]
		\centering
        \includegraphics[scale=0.2]{figure3}
        \caption{\TeX 白云}\label{fig-白云}
	\end{figure}
	
	\LaTeX{}中的表格见表\ref{表格序号}：
	\begin{table}[h]
		\centering
		\caption{表格标题}\label{表格序号}
        \begin{tabular}{|l||c|c|c|p{1.5cm}|}
            \hline
            姓名 & 语文 & 数学 & 英语 & 备注 \\
            \hline \hline
            张三 & 87 & 100 & 93 & 优秀 \\
            \hline
            李四 & 75 & 64 & 52 & 补考另行通知 \\
            \hline
            王二 & 80 & 82 & 78 & \\
            \hline
        \end{tabular}
	\end{table}
	
\end{document}
```

## 数学公式——初步

```latex
\documentclass{article}

\usepackage{ctex}
\usepackage{amsmath}

\begin{document}

	\section{简介}
	\section{行内公式}
	\subsection{美元符号}
	交换律是 $a+b=b+a$,如 $1+2=2+1=3$。
	\subsection{小括号}
	交换律是 \(a+b=b+a\),如 \(1+2=2+1=3\)。
	\subsection{math环境}
	交换律是 \begin{math}a+b=b+a\end{math},如 \begin{math}1+2=2+1=3\end{math}。
	\section{上下标}
	\subsection{上标}
	$3x^2-x+2=0$ \\
	$3x^{3x^2-x+2}-x+2=0$
	\subsection{下标}
	$a_0,a_1,a_2,...,a_{100}$
	\section{希腊字母}
	$\alpha$
	$\beta$
	$\gamma$
	$\epsilon$
	$\pi$
	$\omega$
	
	$\Gamma$
	$\Delta$
	$\Theta$
	$\Pi$
	$\Omega$
	
	$\alpha^3+\beta^2+\gamma=0$
	\section{数学函数}
	$\log$
	$\sin$
	$\cos$
	$\arccos$
	$\arcsin$
	$\ln$
	
	$\sin^2x+\cos^2x=1$
	
	$\sqrt{2}$
	$\sqrt{x^2+y^2}$
	$\sqrt{2+\sqrt{2}}$
	$\sqrt[4]{x}$
	
	\section{分式}
	大约是原体积$3/4$。
	大约是原体积的$\frac{3}{4}$。
	$\frac{\sqrt{x-1}}{\sqrt{x+1}}$
	\section{行间公式}
	\subsection{美元符号}
	交换律是
	$$a+b=b+a$$
	如$$1+2=2+1=3$$。
	\subsection{中括号}
	交换律是
	\[a+b=b+a\]
	如
	\[1+2=2+1=3\]。
	\subsection{displaymath环境}
	\begin{displaymath}
		2x^2+5x+3=6	
	\end{displaymath}
	\subsection{自动编号公式equation环境}
	交换律见\ref{eq:commutative}
	\begin{equation}
		a+b=b+a \label{eq:commutative}
	\end{equation}
	\subsection{不编号公式equation*环境}
	\begin{equation*}
		a+b=b+a
	\end{equation*}
	
\end{document}
```

![image-20220219221228807](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220219221228807.png)

## 数学公式——矩阵

```latex
\documentclass{ctexart}

\usepackage{ctex}
\usepackage{amsmath}

\begin{document}
	\[
	\begin{matrix} % 无括号
		0 & 1 \\
		1 & 0
	\end{matrix} \qquad
	\begin{pmatrix} % 圆括号
		0 & -i \\
		i & 0
	\end{pmatrix} \qquad
	\begin{bmatrix} % 方括号
		0 & -1 \\
		1 & 0
	\end{bmatrix} \qquad
	\begin{Bmatrix} % 大括号
		1 & 0 \\
		0 & -1
	\end{Bmatrix} \qquad
	\begin{vmatrix} % 单竖线
		a & b \\
		c & d
	\end{vmatrix} \qquad
	\begin{Vmatrix} % 双竖线
		i & 0 \\
		0 & -i
	\end{Vmatrix} \qquad
	\]
	
	%可以使用上下标
	\[
	A = \begin{pmatrix}
        a_{11}^2 & a_{12}^2 & a_{13}^2 \\
        0 & a_{22} & a_{23} \\
        0 & 0 & a_{33}
	\end{pmatrix}
	\]
	
	% 常用的省略号用:\dots,\vdots,\ddots
	\[
   	\begin{bmatrix}
        a_{11} & \dots & a_{1n} \\
        & \ddots & \vdots \\
        0 & & a_{nn}
    \end{bmatrix}_{n \times n} % 排版维数
    \]
    
    % 分块矩阵
    \[
    \begin{pmatrix}
    	\begin{matrix} 1&0\\0&1 \end{matrix} & \text{\Large 0} \\
    	\text{\Large 0} & \begin{matrix} 1&0\\0&1 \end{matrix} % text为临时切换到文本
    \end{pmatrix}
    \]
    
    % 三角矩阵
    \[
    \begin{pmatrix}
        a_{11} & a_{12} & \cdots & a_{ln} \\
        &a_{22} & \cdots & a_{2n} \\
        &		& \dots & \vdots \\
        \multicolumn{2}{c}{\raisebox{1.3ex}[0pt]{\Huge 0}}
        &		&a_{nn}
    \end{pmatrix}
	\]
    
    % 跨列省略号：\hdotsfor{<列数>}
    \[\begin{pmatrix}
        1 & \frac 12 & \dots & \frac ln \\
        \hdotsfor{4} \\
        m & \frac m2 & \dots & \frac mn
    \end{pmatrix}
    \]
    
    %行内小矩阵(smallmatrix)环境
	复数$z=(x,y)$也可以用矩阵
	\begin{math}
   		\left( % 需手动加上左括号
            \begin{smallmatrix}
            x & -y \\ y & x
            \end{smallmatrix}
   		\right) % 需手动加上右括号
	\end{math}来表示
    
    %array环境(类似表格环境tabular)
    \[
    \begin{array}{r|r}
        \frac 12 & 0 \\ % frac可以不加分子
        \hline
        0 & -\frac abc\\
    \end{array}
    \]
    
\end{document}
```

![image-20220219221259513](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220219221259513.png)

## 数学公式——多行公式

```latex
\documentclass{ctexart}

\usepackage{amsmath}
\usepackage{amssymb}

\begin{document}
	\begin{gather}
		a + b = b + a \\
		ab ba
	\end{gather}
	
	% 不带编号公式
	\begin{gather*}
		3 + 5 = 5 + 3 \\
		3 \times 5=5 \times 3
	\end{gather*}
	
	% 在\\前加入\notag
	\begin{gather}
		3^2+4^2=5^2 \notag \\
		a^2+b^2=c^2
	\end{gather}
	
	%align和align*环境(用&对齐)
	%带编号
	\begin{align}
		x &=t+\cos t+1\\
		y &=2 \sin t
	\end{align}
	%不带编号
	\begin{align*}
        x &=t+\cos t+1\\
        y &=2 \sin t
	\end{align*}
	
	%split环境(对齐采用align环境的方式，编号在中间)
	\begin{equation}
	\begin{split}
        \cos 2x &=\cos^2 x- \sin^2 x\\
        &=2\cos^2 x-1
	\end{split}
	\end{equation}	
	
	%case环境
	%每行公式中使用&分隔为两部分
	%通常表示值和后面的条件
	\begin{equation}
		D(x)=\begin{cases}
		1,& \text{如果} x \in \mathbb{Q};\\
		0,& \text{如果} x \in \mathbb{R}\setminus\mathbb{Q}
		\end{cases}
	\end{equation}
	
\end{document}
```

![image-20220219221329877](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220219221329877.png)

## 参考文献BibTeX

先生成example.bib文件：

```latex
@article{konishi:1999ab,
 	author = {Konishi, Seiki and Nakajima, Kyoichi and Uchida, Idai and Kikyo, Hideyuki and Kameyama, Masashi and Miyashita, Yasushi},
 	title = {Common inhibitory mechanism in human inferior prefrontal cortex revealed by event-related functional MRI},
 	journal = {Brain},
    volume = {122},
    number = {5},
    pages = {981},
    year = {1999},
}
```

```latex
\documentclass{ctexart}
\usepackage{apacite}
\bibliographystyle{apacite}
\begin{document}
    \citeA{konishi:1999ab} 进行了一项研究。

    研究成果表明XXXXX~\cite{konishi:1999ab}。

    这项 研究是由~\citeauthor{konishi:1999ab} 在~\citeyearNP{konishi:1999ab} 完成的。

    \bibliography{example}
\end{document}
```

