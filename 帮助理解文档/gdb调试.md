```html
gdb  *array@length  // 这个length是你想查看的长度
```

参数 f 的可选值：

- x 按十六进制格式显示变量。
- d 按十进制格式显示变量。
- u 按十六进制格式显示无符号整型。
- o 按八进制格式显示变量。
- t 按二进制格式显示变量。
- a 按十六进制格式显示变量。
- c 按字符格式显示变量。
- f 按浮点数格式显示变量。

 

参数 u 的可选值：

- b 表示单字节
- h 表示双字节
- w 表示四字节
- g 表示八字节

```
 (gdb) print arr
$5 = {1, 2, 3, 4, 5, 6, 7, 8, 9, 0}
(gdb) x /10dw arr
0x7fffffffdfb0:  1    2    3    4
0x7fffffffdfc0:  5    6    7    8
0x7fffffffdfd0:  9    0
(gdb) print main
$7 = {int (void)} 0x5555555546aa <main>
(gdb) x  0x5555555546aa
0x5555555546aa <main>:     -443987883
```

`