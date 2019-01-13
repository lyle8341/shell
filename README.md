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
+ cd命令
  ```bash
  cd -  返回进入此目录之前所在目录 
  cd !$ 把上个命令的参数作为cd的参数使用
  ```  
+ 特殊变量
  + $? 代表上一个命令执行后的返回值
  + $0 shell或shell脚本的名字
  + $$ 代表所在命令的PID
  + $! 代表最后执行的后台命令的PID
  + !$ 上一个命令的最后一个参数
  + $0-$9,${10}-${n} 参数位置
  + $* 所有参数位置视为一个字符串
  + $@ 所有参数位置视为一个串行多个字符串组成
  + $# 参数个数
+ 数组
  + 设置数组元素值
    - A[0]=1;A[2]=2
    - A=(1 2 3 4 5)
    - A=([2]=11 [1]=22 [5]=55)
  + 使用数组元素
    - echo ${A[@]} 包括空元素
    - echo ${A[*]} 只输出有效元素
    - echo ${#A[@]}或 ${#A[*]}
    - echo ${#A[2]}可以取出数组元素字符串的长度
    - echo ${A[1]}
    - echo ${A[1+2]}
+ 变量
  + ${变量名} 变量扩展
  + $(命令) 命令替换
  + $((算术式)) 或 $[算术式] 算数扩展
  + 变量设置
    - ${变量名:-默认值} 变量为空时回传默认值
    - ${变量名:=默认值} 变量为空时设置为默认值
    - ${变量名:?提示信息} 变量为空时停止程序显示提示信息
    - ${变量:位置起点} 由指定的位置开始，截取字符串到结尾
    - ${变量:位置起点:长度}
    - ${#变量} 返回变量值的字符串长度
+ if语法
  ```bash
  if test; then
    ls
  elif test1; then
    pwd
  else
    ll
  fi
  ```
+ case语法
  ```bash
  case 待测项 in
    样式串行1) ls;;
    样式串行2) pwd;;
    a | b) echo "a|b";;
    *) rm -f ;;
  esac
  ```
+ for语法
  ```bash
   for var in 串行
   do
     ls
   done
  ```  