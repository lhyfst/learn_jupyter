# 遇到了问题？
<br>
<br>
<br>
<br>
<br>


## 1. 如何在同一服务器账号下建立两个互不干扰的jupyter环境？

我原本认为只需要在不同的虚拟环境下启动jupyter就可以使用完全不同的环境了，但事实证明，这样建立的jupyter之间是有干扰的。主要是由于jupyter的环境变量和不同jupyter实际上是共享配置配置文件导致的。其中有一些值得注意的地方，故将其过程记录下来。

我刚开始的时候按[这篇博文](https://blog.csdn.net/JJwho/article/details/75102045)中的解决方法，只写了一份新的配置文件jupyter_notebook_config.py ,于是我指定新的配置文件，启动了新的jupyter 
`jupyter notebook --config /home/.../jupyter_notebook_config.py `

(注：在新虚拟环境里执行上述命令时可能会报错 `socket.gaierror: [Errno -5] No address associated with hostname` .我也没搞清楚这是为什么，但我发现了个小trick：把配置文件jupyter_notebook_config.py中 `c.NotebookApp.ip = '*'` 改为 `c.NotebookApp.ip = '0.0.0.0'` 即可解决问题。)

结果发现，这个新的配置文件只改变了启动的端口、密码等信息，启动后使用的虚拟环境、插件和核心仍和原先的jupyter相同。

深究原因，发现在不同的虚拟环境下，jupyter 的各种路径居然是相同的
`jupyter --paths`
![x8k43ia j7 db kmul3 v d](https://user-images.githubusercontent.com/29816816/47408242-1c4f7800-d791-11e8-8f37-6b778046d584.png)
![w3vz 4g39 ag agf072xx 5](https://user-images.githubusercontent.com/29816816/47408243-1d80a500-d791-11e8-9071-70b66b1beca6.png)
![eq52cg7fdj0pw k3owyy4 n](https://user-images.githubusercontent.com/29816816/47408246-207b9580-d791-11e8-8dfc-3e3a9d3cc3f3.png)

也就是，即便在不同的虚拟环境中，jupyter使用的数据和配置文件都是相同的，难怪这些jupyter长得都一样。

查了很多资料，没看到怎么修改这些paths。但我相信，程序是人写的，是写出来的就一定能改，如果写程序的人没留外面修改的命令和接口，那为什么不直接改源码呢？于是我查看了jupyter的源码，在jupyter-core 模块找到了paths.py文件。

(注：如果不清楚该文件的位置，可以用如下方式找到：
在虚拟环境下进入Python
![image](https://user-images.githubusercontent.com/29816816/47409205-a9e09700-d794-11e8-90b8-cbe9186447c1.png)
)

阅读，发现果然是我要找的文件。对该文件中部分代码进行简单粗暴的修改
![image](https://user-images.githubusercontent.com/29816816/47409501-84a05880-d795-11e8-8a1f-5fd597643969.png)

![image](https://user-images.githubusercontent.com/29816816/47409533-9c77dc80-d795-11e8-92ee-75b692b6ceb7.png)

另外，还有个文件migrate.py，里面定义了ipython的位置，也可以改一下，但对启动新jupyte来说似乎不是必要的。
![image](https://user-images.githubusercontent.com/29816816/47409673-0bedcc00-d796-11e8-8e5a-bf4416b275df.png)

现在再查看 `jupyter --paths`, 发现已经更改为想要设置的新路径了
![image](https://user-images.githubusercontent.com/29816816/47409776-5ec78380-d796-11e8-9283-562bac04acb2.png)

这时候再次启动 `jupyter notebook` ，环境配置已经设置为新的了，成功！
