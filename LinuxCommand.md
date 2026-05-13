#  ls
~~~c
ls -lath
~~~
# cd
~~~c
cd .
   ..
   ~
   /
   -
~~~
# pwd
~~~c
pwd
     -L
     -P
~~~
# mkdir
~~~c
mkdir
        -p
        ""
        -v
~~~
# rmdir
~~~c
rmdir
        -p
        -v
        ""
~~~
# cp
~~~c
cp a b
   -r
   -p
   -a
   -i
   -n
   -v
~~~
# rm
~~~c
rm  a
    -r
    -v
    -f
    -i
    --
~~~
# mv
~~~c
mv  /A/a.txt /B/b.txt
    /A /B
    a.txt b.txt
    -i
~~~
# touch
~~~c
touch   a.txt
        -c
        -r a.txt b.txt
~~~
# find
~~~c
find  /A  -name
      /A  -iname
      /A  -type d/l/f
      /A  -size ±7M
      /A  -mtime ±7
find . -name "*.mp3" -exec cp {} /media/backup/ \; 
~~~
# locate
~~~c
locate a.txt
locate  -i
        -e

sudo updatedb
~~~
# which
~~~c
which 指令
      -a 指令
~~~
# whereis
~~~c
whereis 指令
        -b
        -h
        -s
~~~
# tree
~~~c
tree
        -L
        -d
~~~
# ln
~~~c
ln  a.txt b
    -s
    -v
~~~ 
# grep
~~~c
grep 
        -i
        -n
        -r
        -v
        -e
~~~ 
# cat
~~~c
cat -n
    a.txt > b.txt
    a.txt >> b.txt
~~~ 
# more
~~~c
more a.txt
操作：空格、回车、q、b
~~~ 
# less
~~~c
less a.txt
     -N
     -F
操作：f、b、g、G、（查找及跳到下一个）
~~~ 
# head
~~~c
head -n ±7 a.txt 
     -c      

~~~ 
# tail
~~~c
tail -n
     -f
~~~ 
# uniq
~~~c
uniq a.txt
     -c
     -d
     -u
sort a.txt | uniq

~~~ 
# sed
~~~c
sed s/a/b a.txt
sed 's/old/new/g' file.txt
sed -i 's/old/new/g' file.txt
sed -i.bak 's/old/new/g' file.txt
sed '2d' file.txt
~~~
# awk
~~~c
awk {} a.txt
awk -F: {} a.txt

NR NF 
~~~ 
# wc
~~~c
wc  -l a.txt
    -w
    -m

~~~ 
# sort
~~~c
sort -n
     -r
     -k
     -u
~~~ 
# diff
~~~c
diff a.txt b.txt
     -u
     --color
~~~
# echo
~~~c
echo ${}
     >  a.txt
     >> b.txt
     -e
~~~
# sudo/su
~~~c
sudo -u
~~~
# top
~~~c
P
M
k+PID
u
~~~
# htop
~~~c
F3
F4
F5
F6
F9
htop -d
     -u
~~~
# ps
~~~c
ps aux
~~~
# kill
~~~c
kill PID
     kill -9
~~~
# pkill
~~~c
pkill name
      -9
      -u
      -f
先pgrep在pkill
~~~
# uptime
# uname
~~~c
uname -r
      -m
~~~
# hostname / hostnamectl
~~~c
hostname -i
sudo hostname aaa
sudo hostnamectl set-hostname aaa
~~~
# df
~~~c
df
    -h
    -i
~~~
# ip
~~~c
ip  addr
    link set eth0 up/down
    route list
    route add
    route del
~~~
# ss
~~~c
ss   -a
     -t
     -u

~~~
# ping
~~~c
ping -c
~~~
# tcpdump
~~~c
tcpdump   -D
          -i any 
~~~
# scp
~~~c
scp 用户名@远程IP:/远程/文件.txt /本地/目录/
scp /本地/文件.txt 用户名@远程IP:/远程/目录/
~~~
# rsync
~~~c
rsync -av
rsync -av ./data/ ./backup/
rsync -av /本地/文件 用户名@远程IP:/远程/目录/
rsync -av 用户名@远程IP:/远程/文件 /本地/目录/
~~~
# ssh
~~~c
ssh user@ip
~~~
# tar
~~~c
tar -czf backup.tar.gz /你要打包的目录/
tar -xf archive.tar.gz
tar -t archive.tar.gz
~~~
# gzip
~~~c
gzip a.txt
gzip -d -n a.txt
gzip -k a.txt
~~~
# zip
~~~c
zip k.zip a b ...
zip -r 
~~~
# unzip
~~~c
unzip
      -l
      -d
~~~

# chmod
~~~c
chmod 644 a.txt
     755 run.sh
     -R 755 dir/
~~~
# chown
~~~c
sudo chown user:user a.txt
          -R user:user dir/
~~~
# du
~~~c
du -sh .
   -h --max-depth=1
~~~
# free
~~~c
free -h
~~~
# file
~~~c
file a.txt
     -i a.txt
~~~
# stat
~~~c
stat a.txt
~~~
# man / --help
~~~c
man ls
man 5 passwd
ls --help
~~~
# history
~~~c
history
!!
!100
~~~
# alias / unalias
~~~c
alias ll='ls -lath'
unalias ll
~~~
# env / export / printenv
~~~c
env
printenv PATH
export NAME=linux
echo $NAME
~~~
# cut
~~~c
cut -d: -f1 /etc/passwd
cut -c1-5 a.txt
~~~
# tr
~~~c
tr 'a-z' 'A-Z' < a.txt
tr -d ' ' < a.txt
~~~
# tee
~~~c
echo hello | tee a.txt
command | tee -a log.txt
~~~
# xargs
~~~c
cat list.txt | xargs -n1 echo
find . -name "*.log" | xargs rm -f
~~~
# pgrep
~~~c
pgrep bash
     -a
     -f
     -u
~~~
# curl
~~~c
curl https://example.com
curl -I https://example.com
curl -O https://example.com/a.txt
~~~
# wget
~~~c
wget https://example.com/a.txt
wget -O index.html https://example.com
~~~
# lsof
~~~c
lsof -i :8080
     a.txt
~~~
# jobs / bg / fg / nohup
~~~c
command &
jobs
bg %1
fg %1
nohup command > app.log 2>&1 &
~~~
# systemctl
~~~c
systemctl status ssh
         restart ssh
         enable ssh
~~~
# journalctl
~~~c
journalctl -u ssh
          -xe
          -f
~~~

---

# Linux 指令实战复习场景

下面这些场景按“文件操作 -> 文本处理 -> 权限与环境 -> 压缩同步 -> 进程排查 -> 网络排查”来排。你可以逐个做，也可以把它们当成面试前的综合自测题。

## 场景 1：搭一个练习目录，把文件和目录操作跑一遍

要求：

1. 先用 `pwd` 确认当前位置，再用 `mkdir -p linux_lab/{docs,src,backup,tmp}` 创建目录结构。
2. 用 `cd` 分别练 `.`、`..`、`~`、`/`、`-` 的切换。
3. 进入 `linux_lab/docs`，用 `touch a.txt b.txt c.log` 创建文件。
4. 用 `echo` 往 `a.txt` 写入三行内容，再用 `cat -n` 查看。
5. 用 `cp` 复制 `a.txt` 到 `b.txt`，再用 `mv` 把 `b.txt` 改名为 `note.txt`。
6. 用 `ls -lath` 查看目录，再用 `tree -L 2` 看整体结构。
7. 用 `ln a.txt a_hard` 创建硬链接，再用 `ln -s a.txt a_soft` 创建软链接。
8. 用 `rm -i` 删除一个测试文件，再用 `mkdir empty && rmdir empty` 练空目录删除。
9. 用 `file` 和 `stat` 查看 `a.txt` 的类型与元数据。

本场景覆盖：`pwd` `mkdir` `cd` `touch` `echo` `cat` `cp` `mv` `ls` `tree` `ln` `rm` `rmdir` `file` `stat`

## 场景 2：查找文件、浏览内容、做基础文本统计

准备：

1. 在 `linux_lab/docs` 下新建 `app.log`，内容自己写 10 行，至少包含 `INFO`、`WARN`、`ERROR`。
2. 再新建一个 `users.txt`，写几行重复姓名。

要求：

1. 用 `find` 找出当前目录下所有 `.txt` 和 `.log` 文件。
2. 如果本机可用，试 `locate app.log`，然后执行一次 `updatedb` 的帮助或理解其用途。
3. 用 `which`、`whereis` 分别查 `grep`、`ssh`、`tar` 的位置。
4. 用 `more` 和 `less -N` 浏览 `app.log`。
5. 用 `head -n 3`、`tail -n 3` 看头尾内容，再用 `wc -l -w -m` 统计。
6. 用 `sort users.txt | uniq -c` 统计重复项。
7. 用 `diff -u a.txt note.txt` 比较两个文件差异。

本场景覆盖：`find` `locate` `updatedb` `which` `whereis` `more` `less` `head` `tail` `wc` `sort` `uniq` `diff`

## 场景 3：把一份日志清洗成“面试可讲”的结果

准备：

把 `app.log` 改成类似下面这种内容：

~~~c
2026-05-01 INFO start service
2026-05-01 ERROR open config
2026-05-01 WARN retry connect
2026-05-01 ERROR open config
2026-05-01 INFO finish
~~~

要求：

1. 用 `grep -n` 找出所有 `ERROR` 行，再用 `grep -v` 去掉 `INFO`。
2. 用 `sed 's/ERROR/ERR/g'` 预览替换效果，再用 `sed -i.bak` 真正替换。
3. 用 `sed '2d'` 删除指定行做实验。
4. 用 `awk '{print $2, $3}' app.log` 取出级别和动作。
5. 用 `awk -F:` 处理一份冒号分隔的测试文本。
6. 用 `cut -c1-10 app.log` 取出日期列。
7. 用 `tr 'a-z' 'A-Z' < app.log` 转大写看看效果。
8. 用 `sort`、`uniq -c` 统计重复错误。
9. 用 `tee` 把过滤结果同时输出到终端和 `result.txt`。
10. 用 `xargs` 把 `list.txt` 中的多个文件名逐个打印，理解它的批处理作用。

本场景覆盖：`grep` `sed` `awk` `cut` `tr` `sort` `uniq` `tee` `xargs`

## 场景 4：权限、环境变量、帮助系统

准备：

1. 在 `linux_lab/src` 下创建 `run.sh`，内容为 `echo hello linux`。

要求：

1. 先直接执行 `./run.sh`，观察没有执行权限时的报错。
2. 用 `chmod 755 run.sh` 增加执行权限，再执行它。
3. 如果你有 sudo 权限，用 `chown` 改一下文件属主；没有就只记住命令格式。
4. 用 `env`、`printenv PATH` 查看环境变量。
5. 用 `export NAME=linux_lab`，再用 `echo $NAME` 验证。
6. 用 `alias ll='ls -lath'` 创建别名，再执行 `ll`，最后用 `unalias ll` 删除。
7. 用 `man ls`、`ls --help`、`man 5 passwd` 感受帮助系统。
8. 用 `history` 看命令历史，再试 `!!` 或 `!数字`。

本场景覆盖：`chmod` `chown` `env` `printenv` `export` `echo` `alias` `unalias` `man` `--help` `history`

## 场景 5：打包、压缩、备份、下载

准备：

1. 在 `linux_lab` 目录里准备几个文本文件和一个子目录。

要求：

1. 用 `tar -czf backup.tar.gz linux_lab/` 打包压缩。
2. 用 `tar -t` 查看压缩包内容，再解压到测试目录。
3. 用 `gzip -k a.txt` 保留原文件压缩一份。
4. 用 `zip -r lab.zip linux_lab/` 再打一个 zip 包。
5. 用 `unzip -l lab.zip` 查看压缩包内容。
6. 用 `rsync -av ./linux_lab/ ./linux_lab_copy/` 做本地同步备份。
7. 用 `du -sh .` 和 `df -h` 分别查看目录大小与磁盘空间。
8. 用 `curl -I https://example.com` 和 `wget -O index.html https://example.com` 练下载和请求头查看。

本场景覆盖：`tar` `gzip` `zip` `unzip` `rsync` `du` `df` `curl` `wget`

## 场景 6：远程复制与登录（条件场景）

说明：

这个场景需要另一台 Linux 主机或虚拟机，没有环境时先把命令手敲一遍。

要求：

1. 用 `ssh user@ip` 登录远程主机。
2. 用 `scp` 把本地文件传到远端，再从远端拉回一份。
3. 再用 `rsync -av` 试一次目录同步，对比和 `scp` 的区别。

本场景覆盖：`ssh` `scp` `rsync`

## 场景 7：进程、后台任务和服务排查

准备：

1. 启动一个长时间运行的命令，例如 `tail -f app.log` 或 `python -m http.server 8000`。

要求：

1. 用 `ps aux` 找到它。
2. 用 `pgrep -a` 或 `pgrep -f` 再找一遍。
3. 用 `top` 或 `htop` 观察进程资源占用，试试排序和筛选。
4. 用 `lsof -i :8000` 找出占用端口的进程。
5. 把一个命令放到后台运行，练 `jobs`、`bg`、`fg`。
6. 用 `nohup command > app.log 2>&1 &` 启动后台任务。
7. 用 `kill PID` 正常结束，用 `kill -9` 强制结束。
8. 用 `pkill -f` 按名字结束，注意先 `pgrep` 再 `pkill`。
9. 如果系统使用 systemd，再用 `systemctl status ssh` 和 `journalctl -u ssh` 看服务状态与日志。

本场景覆盖：`ps` `pgrep` `top` `htop` `lsof` `jobs` `bg` `fg` `nohup` `kill` `pkill` `systemctl` `journalctl`

## 场景 8：系统与网络巡检

要求：

1. 用 `uptime` 看系统运行时长和平均负载。
2. 用 `uname -r -m` 看内核版本和架构。
3. 用 `hostname -i` 看主机 IP。
4. 用 `free -h` 看内存，用 `df -h` 和 `df -i` 看磁盘和 inode。
5. 用 `ip addr` 查看网卡信息，理解 `link set`、`route list` 的用途。
6. 用 `ss -t -u -a` 查看 TCP/UDP 连接。
7. 用 `ping -c 4 8.8.8.8` 测试连通性。
8. 如果你有 sudo 权限，用 `tcpdump -D` 看网卡列表，再用 `tcpdump -i any` 抓包观察。

本场景覆盖：`uptime` `uname` `hostname` `free` `df` `ip` `ss` `ping` `tcpdump`

## 综合自测要求

1. 不看笔记，从头创建 `linux_lab` 练习目录并完成场景 1 到场景 5。
2. 第二轮只看场景标题，不看“覆盖命令”，看看自己还能不能想起命令。
3. 第三轮把每个命令的常用参数口述出来，例如为什么 `cp -a`、`rm -i`、`grep -n`、`tar -czf` 常用。
4. 对有环境要求的命令单独列出来复习：`ssh` `scp` `tcpdump` `systemctl` `journalctl` `chown`。

如果你愿意，我下一步可以继续把这份文档整理成“面试高频 Linux 指令 7 天复习版”，或者给你再补一个“按开发排障流程串起来的综合大作业”。