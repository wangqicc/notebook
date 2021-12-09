# Linux 常用命令

## 1 常用命令

### 1.1 查看环境变量

**输入：**
```bash
# 显示所有的环境变量
export
# 显示某个变量的环境变量
export $HOME
```

**结果：**
```bash
export HOME='/home/studio-lab-user'
/usr/bin/sh: 1: export: /home/studio-lab-user: bad variable name
```

### 1.2 查找可执行文件位置

**输入：**
```bash
# 查找可执行文件 bash 所在位置
whereis bash
# 查找当前目录可执行文件位置
which bash
```

**结果：**
```bash
bash: /usr/bin/bash /etc/bash.bashrc
```

### 1.3 文件操作

**输入：**
```bash
# 修改文件时间
# [[CC]YY]MMDDhhmm[.SS]
touch a.txt
stat a.txt
touch -t 199705201314.02 a.txt
stat a.txt

# 显示文本文件
cat a.txt
# 复制文件，将文件 a.txt 和文件 b.txt 复制到 c.txt 中
cat a.txt b.txt > c.txt

# 显示文件第一部分，按空格继续显示，输入 q 则停止
more a.txt
# 显示文件前 10 行
head a.txt
# 显示文件后 10 行
tail a.txt

# 移动文件到另一个位置
mv file1 file2
# 复制文件到另一个位置
cp file1 file2
# 删除指定文件
rm file
# 比较两个文件的不同
diff file1 file2
# 更改文件权限，-x 赋予执行权限
chmod -x file

# 压缩文件
gzip file
# 解压文件
gunzip file
# 查看压缩文件
gzcat file

# 打印文件
lpr file
# 查看打印队列
lpq
# 移除打印队列中指定内容
lprm job_num
```

**结果：**
```bash
  File: a.txt
  Size: 0         	Blocks: 0          IO Block: 4096   regular empty file
Device: 10303h/66307d	Inode: 50340952    Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/studio-lab-user)   Gid: (  100/   users)
Access: 2021-12-09 11:44:14.964973764 +0000
Modify: 2021-12-09 11:44:14.964973764 +0000
Change: 2021-12-09 11:44:14.964973764 +0000
 Birth: -
  File: a.txt
  Size: 0         	Blocks: 0          IO Block: 4096   regular empty file
Device: 10303h/66307d	Inode: 50340952    Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/studio-lab-user)   Gid: (  100/   users)
Access: 1997-05-20 13:14:02.000000000 +0000
Modify: 1997-05-20 13:14:02.000000000 +0000
Change: 2021-12-09 11:44:15.308972799 +0000
 Birth: -
```

### 1.1 `export`

**输入：**
```bash

```

**结果：**
```bash

```

### 1.1 `export`

**输入：**
```bash

```

**结果：**
```bash

```

## 参考文档

[^1]: [ 10分钟学会Linux常用bash命令](https://www.cnblogs.com/savorboard/p/bash-guide.html)

[^2]: [ Linux教程](http://c.biancheng.net/view/726.html)

[^3]: [ 修改时间戳](https://blog.csdn.net/tjjingpan/article/details/89403075)
