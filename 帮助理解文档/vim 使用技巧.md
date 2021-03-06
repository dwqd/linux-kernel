#                        vim 常用使用技巧

## 1. vim多窗口使用技巧

1. 打开多个窗口
     打开多个窗口的命令以下几个：
     横向切割窗口
     :new+窗口名(保存后就是文件名)
     :split+窗口名，也可以简写为:sp+窗口名
     纵向切割窗口名
     :vsplit+窗口名，也可以简写为：vsp+窗口名

2. 关闭多窗口
     可以用：q!，也可以使用：close，最后一个窗口不能使用close关闭。使用close只是暂时关闭窗口，其内容还在缓存中，只有使用q!、w!或x才能真能退出。
     :tabc 关闭当前窗口
     :tabo 关闭所有窗口

3. **<u>窗口切换-------------------这个用的比较多</u>**
     :ctrl+w+j/k，通过j/k可以上下切换，或者:ctrl+w加上下左右键，快速双击ctrl+w依次切换窗口。

     快速双击ctrl+w依次切换窗口 ->>>>最喜欢用的

     ```
     :qall -- 关闭所有窗口，退出vim。 ----这个是用的最多的 :qa
     :wall -- 保存所有修改过的窗口。
     :only -- 只保留当前窗口，关闭其它窗口。(CTRL-W o)
     :close -- 关闭当前窗口，CTRL-W c能实现同样的功能。 (象 :q :x同样工作 )
     ```

4. 窗口大小调整
     纵向调整
     :ctrl+w + 纵向扩大（行数增加）
     :ctrl+w - 纵向缩小 （行数减少）
     :res(ize) num  例如：:res 5，显示行数调整为5行
     :res(ize)+num 把当前窗口高度增加num行
     :res(ize)-num 把当前窗口高度减少num行
     横向调整
     :vertical res(ize) num 指定当前窗口为num列
     :vertical res(ize)+num 把当前窗口增加num列
     :vertical res(ize)-num 把当前窗口减少num列

5. 给窗口重命名
     :f file

6. vi打开多文件
     vi a b c
     :n 跳至下一个文件，也可以直接指定要跳的文件，如:n c，可以直接跳到c文件
     :e# 回到刚才编辑的文件

7. 文件浏览
     :Ex 开启目录浏览器，可以浏览当前目录下的所有文件，并可以选择
     :Sex 水平分割当前窗口，并在一个窗口中开启目录浏览器
     :ls 显示当前buffer情况

8. vi与shell切换
     :shell 可以在不关闭vi的情况下切换到shell命令行
     :exit 从shell回到vi
     
     

## 2.vim使用：全局搜索并跳转

```shell
1. 只搜索当前文件 vim /main/ % | copen

2. 只搜索当前目录 vim /main/ * | copen

3.  搜索上级目录下，并递归 vim /main/ ../** | copen

4. 可以在多个路径中搜索  vim /main path1/** path2/** | copen

h vimgrep  查看跟多用法
	vimgrep /main()/* | copen  查找并显示出所以 main() 字符串
```

