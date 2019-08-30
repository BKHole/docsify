# mac终端命令指南

> 未完待续

## 目录操作

| 命令  | 描述             | 举例                        |
|-------|------------------|-----------------------------|
| mkdir | 创建一个目录       | mkdir dirname               |
| rmdir | 删除一个目录       | rmdir dirname               |
| mvdir | 重命名或移动目录   | mvdir dir1 dir2
| cd    | 改变当前目录       | cd dirname                  |
| pwd   | 显示当前目录的路径名 | pwd                         |
| ls    | 显示当前目录内容   | ls                          |
dircmp|比较两个目录内容|dircmp dir1 dir2

## 文件操作

| 命令 | 描述          | 举例           |
|-----|---------------|----------------|
| cat | 显示或连接文件  | cat filename   |
| cp  | 复制文件或目录  | cp file1 file2 |
| rm  | 删除文件或目录  | rm filename    |
| mv  | 重命名或移动文件 | mv file1 file2
open|使用默认的程序打开文件|open filename
file | 显示文件类型| file filename
cat| 显示或连接文件 |cat filename
pg| 分页格式化显示内容|pg filename
more | 分屏显示文件内容 |more filename
find| 使用匹配表达式查找文件 |find .-name"*.c" -print
diff | 比较并显示两个文件的差异|diff file1 file2
uniq |去掉文件中的重复行|uniq file1 file2
wc|统计文件的字符数、词数和行数|wc filename
uname|显示系统相关信息 |uname -a
clear|清除屏幕或窗口内容|clear
du|查询磁盘使用情况|du -k subdir
df|显示文件系统的总空间和可用空间| df /tmp

