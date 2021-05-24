## 1. Github使用之git回退到某个历史版本

​	1、 查找历史版本

​				使用`git log`命令查看所有的历史版本，获取你git的某个历史版本的id

​    			假设查到历史版本的id是`fae6966548e3ae76cfa7f38a461c438cf75ba965`

​	2、 恢复到历史版本

```shell
$ git reset --hard fae6966548e3ae76cfa7f38a461c438cf75ba965
```

3.  把修改推到远程服务器

```shell
$ git push -f -u origin master  
```

