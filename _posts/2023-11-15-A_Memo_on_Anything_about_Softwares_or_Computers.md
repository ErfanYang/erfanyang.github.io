## Mathematica
### Basic commands in case that I forget
**Greek letter** [键入希腊字母—Wolfram 语言参考资料](https://reference.wolfram.com/language/howto/TypeAGreekLetter.html.zh)
```
\[Delta] (*In lowercase*)
\[CapitalDelta] (*In uppercase*)
```
**Annotation**
```
(*your annotation*)
```
**Import files, fit, show**
```
data = Import["X1Y1.csv", "Data"][[16 ;; 32, 1 ;; 3]] (*Line 16 to 32, Column 1 to 3 (including 1 and 3)*)(*To get column 1 and 3, use [[16 ;; 32, {1 , 3}]]*)
FindFit[data, Sqrt[b*b + (b*b)/(a*a)*(z - c)*(z - c)], {a, b, c}, z] (*define the formula and variables*)
Show[ListPlot[data, PlotStyle -> Red], 
 Plot[Sqrt[b*b + (b*b)/(a*a)*(z - c)*(z - c)] /. {a -> 5.15585 , 
    b -> 0.0666391, c -> 111.586}, {z, 34.55, 194.55}]]
```
[Part—Wolfram 语言参考资料](https://reference.wolfram.com/language/ref/Part.html.zh)
**Solve equations**
```
f = 150;
M2 = 1.0690;
\[Lambda] = 632.8*10^{-6};
dd = 0.0666391;
zz = 111.586; 
NSolve[zz == 
   f + ((z - f)*f^2)/((z - f)^2 + (Pi/\[Lambda]/M2)*(d/2)^2)^2 && (dd/
      2)^2 == (f^2*(d/
         2)^2)/((z - f)^2 + (Pi/\[Lambda]/M2)*(d/2)^2)^2, {z, d}] (*formula+variables*)
```
**Short cuts**
enter: next line
ctrl+enter: start to run
## Github and Git
See *Make a personal site*
## LaTeX & Markdown
Multicolumn
```
\begin{multicols}{2}
强制换到右栏\columnbreak
调整环境内外（切换单栏与双栏中间默认空一行）\setlength\multicolsep{-0.2\baselineskip}
\end{multicols}
```

| 表                               | 头                         |
| -------------------------------- | -------------------------- |
| 摁tab到右边一个单元格，摁enter到下面一个单元格          | 输完这一行后摁enter        |
| 表头下方-的数量可以控制列宽      | ---前后加:可以控制对齐方式 |
| 表格上一行必须为空行，不然不输出 | 血的教训。。。             |
## Network & VPN
### 只能上QQ微信不能上网页
常为DNS问题，可能是VPN未在运行，但退出时没有关闭代理(proxy)
首先win+R打开cmd，输入ping baidu.com，检查是否可以访问网页，以下是正常的 ![[Pasted image 20230719211406.png]]
尝试去设置-network & internet-proxy-manual proxy setup改成关/改成开（输入特定的proxy ip address和port）
### 其他
iPhone QQ小程序提示没有对应的版本，是因为在海外
## Machine Learning
- conda：是一个跨平台的包管理器和环境管理器，可以用来安装、管理和卸载多个不同版本的软件包。它可以管理Python包以及其他编程语言的包，是科学计算领域中常用的工具之一。
- anaconda：是一个基于Python的数据科学平台，包含了常用的数据科学工具和包。它包含了Python解释器以及常用的数据科学库，如numpy、pandas、matplotlib等，也包括了conda包管理器。
- pip：是Python的一个包管理器，可以用来安装、升级和卸载Python包。
- torch/pytorch：是由Facebook开发的一个开源机器学习框架，支持张量计算和动态构建神经网络，可以在GPU上进行高效的计算。pytorch是torch的Python接口，提供了更方便的使用方式和更丰富的API。
- tensorflow：是由Google开发的一个开源机器学习框架，支持静态图和动态图两种计算模式，可以在CPU和GPU上进行高效的计算。
https://www.zhihu.com/question/393886526/answer/2986776670  
## Python
**Divide a string**
```python
string='你好'
list(string) #['你','好']
[string] #['你好']
```
**深浅拷贝与赋值**
[python中append函数使用后list被添加值覆盖的问题 - xloading - 博客园 (cnblogs.com)](https://www.cnblogs.com/Xloading/p/15226696.html)
**循环命名**
[python3 关于循环命名(一)-CSDN博客](https://blog.csdn.net/lp1502064247/article/details/104450794)
**数据清洗**
[Pandas 数据清洗 | 菜鸟教程 (runoob.com)](https://www.runoob.com/pandas/pandas-cleaning.html)
**终端 解释器 编辑器**
[一文读懂Python解释器，终端，编辑器区别和联系 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/99066152)
1.  终端 (shell)
 3 ways to open shell:
-   Win+R, cmd
-   Win, find Windows powershell (管理员)
-   Vscode-terminal-pip or enter python interpreter by input \"python\" directly
![](000_Python_000.png)
2.  解释器
在终端使用，对输入的Python代码进行解释和执行，每行前有\>\>\>
3.  编辑器
写代码。Simplest: notepad, IDLE
**Error about the path**
Syntax error: unicode error
Substitute"\\" by "/" or "r\"
**Break, continue, pass**
[Python学习08: while 、break、continue、pass的介绍和使用_python while pass_几何DDDMm的博客-CSDN博客](https://blog.csdn.net/DINGMANzzz/article/details/112866900?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-0-112866900-blog-116173185.235^v38^pc_relevant_yljh&spm=1001.2101.3001.4242.1&utm_relevant_index=3