+ 通配符
  + __\*__ 任意字符串
  + __\?__ 不为空的一个字符
+ 转义字符
  + __\\__ 反斜线，逃逸字符
+ 续行符号
  + __\\__ 的后方是换行符时，上下输入的两行将视为一行  
  
+ touch
  ```bash
    touch a{1..10}
    touch {a,b}{1..10}
  ```
+ 标准I/O
  + stdin &emsp;标准输入=0
  + stdout&ensp;标准输出=1
  + stderr &ensp;标准错误=2
  + 输出重定向和输入重定向
    + \> 和 <
  + 追加输出重定向
    + \>>
+ 无名管道
  + |
  + cmd1|cmd2|cmd3...
+ 有名管道
  + mkfifo创建管道文件
    - mkfifo /tmp/testfifo
    - grep root /etc/passwd > /tmp/testfifo
    - wc -l /tmp/testfifo
  + 可以跨越终端，将两个命令协同运行
+ 前后台切换方法
  - &,nohup,ctrl+z
  - 移动后台进程到前台/移动前台进程到后台
    ```
    fg %n 或者fg一次拉取一个
    bg %n 或者bg一次拉取一个
    ```
  - jobs
  - kill