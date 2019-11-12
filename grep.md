# grep笔记

a_file的内容为

```
boot
book
booze
machine
boots
bungie
bark
aardvark
broken$tuff
robots
```

#### 1.基本使用

```
grep -n "boo" a_file
```
这个命令会找出a_file中包含有boo的行并打印在屏幕上
```
boot
book
booze
boots
```
#### 2.选项
* -n, --line-number  

    ```
    grep -n "boo" a_file
    ```

    找出a_file中包含有boo的行并将该行内容以及行号打印在屏幕上

    ```
    1:boot
    2:book
    3:booze
    5:boost
    ```
* -v, --invert-match

    ```
    grep -v "boo" a_file
    ```
    
    找出a_file中不包含有boo的行并将其打印在屏幕上

    ```
    4:machine
    6:bungie
    7:bark
    8:aardvark
    9:broken$tuff
    10:robots
    ```
* -c, --count

    ```
    grep -c "boo" a_file
    ```

    统计a_file中包含有boo的行数，将总的行数打印到屏幕上

    ```
    4
    ```

* -l, --files-with-matches

    ```
    grep -l "boo" *
    ```

    打印输入文件中有匹配到boo的文件名（输入不能是目录，只能是文件）

    ```
    a_file
    ```

* -i, --ignore-case

    ```
    grep -i "BOO" a_file
    ```

    忽略模式PATTERN和输入文件中的大小写的区别

    ```
    boot
    book
    booze
    boost
    ```
* -x, --line-regexp

    ```
    grep -x "boo" a_file
    ```

    打印能精确匹配boo的一行的内容，即只会打印boo

* -A <u>NUM</u>, --after-context=<u>NUM</u>

    ```
    grep -A2 "mach" a_file
    ```

    打印出紧随匹配的行之后的下文<u>NUM</u>行

    ```
    machine
    boots
    bungie
    ```
#### 3.正则匹配

* 参考man grep文档