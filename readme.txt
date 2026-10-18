
% 调节公式的上下行之间的间距
	\begin{equation*}
    \setlength{\abovedisplayskip}{3pt} %调节公式的上行之间的间距
    \setlength{\belowdisplayskip}{3pt} %调节公式的下行之间的间距
	   \nabla f(x) = \left[ \frac{\partial f(x)}{\partial x_1}, \frac{\partial f(x)}{\partial x_2}, \cdots, \frac{\partial f(x)}{\partial x_n} \right]^{\mathrm{T}}.
	\end{equation*}


定义环境
\begin{definition}[域]\label{def:field}
	设$S$为一个非空集合，其上有“加法”（记作$+$）与“乘法”（记作$\cdot$）两种代数运算. 若满足以下条件，则称$(S,+,\cdot)$构成一个域(field).
	\begin{enumerate}[label={\rm{\roman*)}}]
		\item $(S,+)$构成一个交换群.
		\item 若记$S^{*}=S-\{0\}$，其中$0$为群$(S,+)$中的单位元，则$(S^{*},\cdot)$也构成一个交换群.
		\item 乘法对加法有分配律：$a ( b + c ) = a b + a c$.
	\end{enumerate}
\end{definition}

引理环境
\begin{lemma}\rm{\cite{Azizov2003On}}\label{lem:Weierstrass}
	实轴上任一有界无限点集$S$至少有一个聚点。
\end{lemma}

推论环境
\begin{corollary}
	根据引理\ref{lem:Weierstrass}，我们可以得到柯西收敛准则。
\end{corollary}

定理环境
\begin{theorem}[望远镜公式]\label{thm:telescope}
	$\left[\mathbb{Q}(a, b) : \mathbb{Q}\right]=\left[\mathbb{Q}(a, b) : \mathbb{Q}(a)\right]\left[\mathbb{Q}(a) : \mathbb{Q}\right] $
\end{theorem}

注环境
\begin{remark}\label{rem:reversible}
	每个操作都可逆。
\end{remark}

证明环境
\begin{proof}
	\autoref{thm:telescope} 告诉我们，对任意$s\in S$，均有$\lvert Orb(s)\rvert \cdot \lvert Stab(s)\rvert=\lvert G\rvert=p$。 于是$\lvert Orb(s)\rvert $整除$p$，这里$p$是一个素数。
	从而$\lvert Orb(s)\rvert $等于1或$p$，也就是说，\textbf{所有轨道的大小要么为1，要么为$p$}。
	于是整个集合$S$就被划分为两部分，一部分是大小为1的轨道，另一部分是大小为$p$的轨道，如图9.4所示。
	
	假设大小为1的轨道有$m$个，大小为$p$的轨道有$n$个，则有
	\begin{equation}
		m+p\cdot n=\lvert S\rvert 
	\end{equation}
	注意到定义\ref{def:field}，\textbf{那些$\lvert Orb(s)\rvert =1$的元素$s$即为稳定元}，这就表明有$m$个稳定元。从上式立刻看出$\lvert S \rvert \equiv  m\; (\bmod\; p)$。
\end{proof}
 

例子环境
\begin{example}
	用数列的柯西准则证明确界有界。
\end{example}

这一节给出的是一些表格的例子。先给出一个简单的表格样式\autoref{tab:example}，具体可看tex文件源代码。

一个更为简便的方法是利用Texstudio自带的表格助手，点击菜单栏的向导，有两种表格类型的图形化界面，不再赘述。
\begin{table}[!htp]
	\centering
	\bicaption{中文表格名}
	{English表格名}\label{tab:example}
	\begin{tabular}{c|c|c|c}
	\hline
		列1	&	列2	&	列3	&	列4\\
	\hline
		条目1	& 条目2	&	条目3	&	条目4 \\
		条目1	& 条目2	&	条目3	&	条目4 \\
		条目1	& 条目2	&	条目3	&	条目4 \\
		条目1	& 条目2	&	条目3	&	条目4 \\
	\hline
	\end{tabular}
	\label{table1}
\end{table}



XeLatex 可以很方便地插入PDF、PNG、JPG格式的图片。插入PNG/JPG的例子如\autoref{fig1}所示。
这两个水平并列放置的图共享一个“图标题”(table caption)，没有各自的小标题。

\begin{figure}[htp]
	\centering
	\includegraphics[width=6cm]{figure/example/model1_1000.png}
	\hspace{1cm}
	\includegraphics[width=6cm]{figure/example/model1_10000.png}
	\bicaption{中文题图}
	{English caption}
	\label{fig1}
\end{figure}

这里还有插入EPS图像和PDF图像的例子，如\autoref{fig2} 和\autoref{fig3}。这里将EPS和PDF图片作为子图插入，每个子图有自己的小标题。子图标题使用subcaption宏包添加。

\begin{figure}[htp]
	\centering
	\subcaptionbox{PDF 图像\label{fig2}}[3cm] %标题的长度，超过则会换行，如下一个小图。
	{\includegraphics[height=2.5cm]{figure/example/m2.pdf}}
	\hspace{4em}
	\subcaptionbox{EPS 图像，如果标题很长的话，它会自动换行\label{fig3}}
	{	\includegraphics[scale=0.5]{figure/example/purfer_left.eps}}
	\bicaption{插入eps和pdf的例子（使用 subcaptionbox 方式）}{An EPS and PDF demo with subcaptionbox}
	\label{fig4}
\end{figure}。


中文字体：

思源黑体（Noto Sans CJK）
思源宋体（Noto Serif CJK）
霞鹜文楷 lxgw

https://github.com/adobe-fonts/source-han-sans

https://github.com/adobe-fonts/source-han-serif

英文字体：
Montserrat
Open Sans

数学字体：
https://blog.csdn.net/weixin_42772106/article/details/132267193

https://www.cnblogs.com/Undefined443/p/18428926

https://github.com/CyanoHao/OpenType-MATH-TTF