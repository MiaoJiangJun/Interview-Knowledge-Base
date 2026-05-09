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
# hostname
~~~c
hostname -i
sudo hostname aaa
sudo hostname set-hostname
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
ssh user ip
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
# 
~~~c

~~~
# 
~~~c

~~~
# 
~~~c

~~~
# 
~~~c

~~~
# 
~~~c

~~~



# 
~~~c

~~~