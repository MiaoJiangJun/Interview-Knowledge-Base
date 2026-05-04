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

 
# 
~~~c

~~~