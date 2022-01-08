<h1 align='center'>Jupyter实用教程</h1>
<img src="images/jupyter_icon.png"  alt="jupyter_icon" />

>版本: 1.0 <br>
>作者: 李贺元 <br>
>邮箱: lhyfst@gmail.com <br>
>版权归 李贺元(lhyfst)所有 ,如需转载请与作者联系，不得用于商业用途 <br>


使用 [Nbviewer](http://nbviewer.jupyter.org/github/lhyfst/learn_jupyter/blob/master/readme.ipynb) ，体验更顺畅！(Github中部分锚点失效，且加载较慢)

---

### 目录

- [1. **下载Jupyter**](1-install.ipynb)
- [2. **远程登录**](2-remote-login.ipynb)
- [3. **添加Nbextensions插件**](3-nbextensions.ipynb)
- [4. **Jupyter基本使用**](4-jupyter-basic.ipynb)
- [5. **魔法命令**](5-magic-command.ipynb)
- [6. **Tips & Tricks**](6-tips-and-tricks.ipynb)
- [7. **未来计划内容**](7-future.ipynb)

---

## 使用Jupyter，打开新世界  

### 什么是Jupyter？

jupyter是一款以浏览器为基础的在线交互式代码编辑器。其轻便、强交互、可展示的特性和活跃的社区给人以无限的遐想。<br>
本篇教程即通过jupyter notebook 编写。

### 为什么使用jupyter？

**Jupyter在一定程度上反映了数据科学生态圈的现在，预测了数据科学生态圈的未来。**

jupyter的以下优点让频繁与数据打交道的你不得不认真思考是否入坑：

* **多语言支持**：<br>
jupyter = ju(lia) + pyt(hon) + r
<br>jupyter 即意味着多语言支持。更妙的是，jupyter可以在同一文件中支持多语言，让你能左手Python右手R地完成工作。

* **强交互性**：<br>
jupyter让你实时掌控你的数据流。在数据工作者的工作中，有大量的数据探索、数据清洗工作。在同一个.ipynb文件中，所有cell共享变量空间，这意味着你可以写一行代码，运行一下结果，一步一步地完成工作。

* **jupyter + 服务器**：<br>
jupyter实际上就是一个网络app。搭建自己的jupyter服务器，让它在后台挂起，你便可以随时随地随意地使用服务器强大的资源，你甚至可以在手机上监控并编写你的程序！

* **轻量级，强定制**：<br>
使用过许多大型的IDE后，我越来越讨厌大而全的IDE，反而喜欢轻巧自由的编辑器。jupyter就是这样一款编辑器。随开随用,关闭也不妨碍在后台运行程序(与服务器结合)。<br>
网页的形式时时冲击你的想象。你无法想象富媒体的网页可以让数据可视化、汇报文档变得多么有活力！尤其当你会一些前端知识时！

* **魔法**：<br>
还有很多tips值得你发掘。<br>
这里仅举最常用的：兼容latax、兼容Markdown、兼容40余种编程语言、可以当做命令行直接与服务器交互...


当然，作为仍在快速迭代发展的项目，jupyter确实有一些缺点。<br>
如强烈依赖网络环境(与服务器结合),有难免的网络延迟(与服务器结合)，有难免的网页渲染时间，代码提示和补全功能有些简陋，偶尔kernel抽筋等等。
<br><br>
但瑕不掩瑜，相对jupyter的明显优点，这都不是问题！<br>
喜不喜欢，不试试怎么能知道呢？<br>
<br>
Have a try!  https://try.jupyter.org/

### 本教程目标

* 搭建自己的jupyter服务器(Ubuntu环境)
* 学习使用jupyter的基本操作
* 学习使用基于jupyter的拓展

---
### 参考链接

jupyter 官网  http://jupyter.org/  <br>
jupyter 官网教程  http://jupyter.org/documentation <br>
ipython Cookbook  https://github.com/ipython/ipython/wiki/Cookbook%3A-Index <br>
jupyter basic  https://jupyter-notebook.readthedocs.io/en/latest/examples/Notebook/Notebook%20Basics.html <br>
jupyter kernels  https://github.com/jupyter/jupyter/wiki/Jupyter-kernels <br>
ipython tutorial  http://nbviewer.jupyter.org/github/ipython/ipython/blob/4.0.x/examples/IPython%20Kernel/Index.ipynb <br>
A gallery of interesting Jupyter Notebooks  https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks <br>
nbextensions  http://jupyter-contrib-nbextensions.readthedocs.io/en/latest/index.html <br>
装扮你的Jupyter  https://zhuanlan.zhihu.com/p/26739300?group_id=843868091631955968 <br>
Jupyter Notebook的27个秘诀，技巧和快捷键  https://www.zybuluo.com/hanxiaoyang/note/534296 <br>
