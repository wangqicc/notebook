# Bash 教程

## 1 运行方式

脚本示例

```bash
#!/bin/bash
# 这是单个注释
: "
这是一段注释
"
echo "hello"
```

* 第一种：命令行中输入`./bashname.sh`。[^1]

* 第二种：命令行中输入`sh bashname.sh`。

* 第三种：如果提示没有权限，先赋予执行权限，然后运行。命令行中输入`chmod +x ./bashname.sh`赋予`bashname.sh`权限，然后输入`./bashname.sh`。

## 2 常用代码段

### 2.1 将指定目录下的文件名输出出来

```bash
for file in $(ls ./); do
  echo ${file}
done
```

### 2.2 字符串相关操作

**代码：**
```bash
# 拼接字符串（单引号中文本原样输出，双引号中文本可以转义）
str="world!"
echo 'hello '${str}
echo "hello "${str}
echo 'hello ${str}'
echo "hello ${str}"

# 字符串长度
str="string"
echo ${#str}

# 截取字符串
str="string"
echo ${str:0:3}
```
**结果：**
```text
hello world!
hello world!
hello ${str}
hello world!
6
str
```
### 2.3 传递参数

命令行中输入`./bashname.sh 11 22 33`

那么`$0`对应执行的文件名，`$1`对应`11`，`$2`对应`22`，`$3`对应`33`。

| 参数处理 | 说明 |
|:---:|:---:|
| $# | 传递到脚本的参数个数 |
| $* | 以一个单字符串显示所有向脚本传递的参数。 如"$*"用「"」括起来的情况、以"$1 $2 … $n"的形式输出所有参数。 |
| $$ | 脚本运行的当前进程ID号 |
| $! | 后台运行的最后一个进程的ID号 |
| $@ | 与$*相同，但是使用时加引号，并在引号中返回每个参数。 如"$@"用「"」括起来的情况、以"$1" "$2" … "$n" 的形式输出所有参数。 |
| $- | 显示Shell使用的当前选项，与set命令功能相同。 |
| $? | 显示最后命令的退出状态。0表示没有错误，其他任何值表明有错误。 |
| $n | $0表示执行的文件名，n 代表一个数字，1 为执行脚本的第一个参数，2 为执行脚本的第二个参数，以此类推。 |

### 2.4 输入与输出

**代码：**
```bash
# 提示语句：-p "提示内容"，变量保存到后面定义的变量名中
# 忽略转义：-r，将"\"等转义字符原样保留
read -p "data1: " a
read -rp "data2: " b
echo "data1: ${a}, data2: ${b}"
```
**结果：**
```text
data1: \n\n
data2: \n\n
data1: nn, data2: \n\n
```
### 2.5 数组

**代码：**
```bash
# 定义数组，数组之间通过空格隔开
arr=(1 2 3 4)
# 输出数组所有元素
echo "${arr[*]}"

# 遍历数组中的所有元素（通过迭代访问）
for item in "${arr[@]}"; do
  echo "${item}";
done
# 遍历数组中的所有元素（通过下标访问）
for i in "${!arr[@]}"; do
  echo "${arr[$i]}";
done

# 遍历指定范围数据
arr=(x 5 2 0 1 3 1 4)
for ((i=1; i<=7; i++)) do
  echo "${arr[${i}]}";
done
```

**结果：**
```text
1 2 3 4
1
2
3
4
1
2
3
4
5
2
0
1
3
1
4
```

### 2.6 循环和条件语句

**代码：**
```bash
arr=(5 2 0 1 3 1 4)
for item in "${arr[@]}"; do
  if [ "${item}" -lt 3 ]; then
    echo "小于3: ${item}";
  elif [ "${item}" -lt 6 ] && [ "${item}" -gt 4 ]; then
    echo "大于4小于6: ${item}"
  else
    echo "其他情况: ${item}"
  fi
done
```

**结果：**
```text
大于4小于6: 5
小于3: 2
小于3: 0
小于3: 1
其他情况: 3
小于3: 1
其他情况: 4
```
### 2.7 函数

**代码：**
```bash
demo(){
  echo "欢迎来到";
  echo "*^_^* Bash 基础知识";
}

for ((i=2; i<=5; i++)) do
  demo
done
```

**结果：**
```text
欢迎来到
*^_^* Bash 基础知识
欢迎来到
*^_^* Bash 基础知识
欢迎来到
*^_^* Bash 基础知识
欢迎来到
*^_^* Bash 基础知识
```

## 尚未解决

1. Bash 无法计算小数，只能计算整数

## 参考文档

[^1]: [Bash 脚本](https://www.w3cschool.cn/bashshell/bashshell-n2xd37ig.html)
