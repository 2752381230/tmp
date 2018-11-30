
# 说明

```
使用正则表达式方式说明一些字符
Markdown 的绝大部分"元字符"之后都有一个空格(=\s)，仅示例一次, 不再重复
```

# 标题及引用

```
# 标题及引用  ==>  #\s标题及引用
```

> ## 二级标题且被引用 or 引用二级标题

```
> ## 二级标题且被引用 or 引用二级标题
```

### n级标题且嵌套引用
> #### (n+1)级标题且被嵌套
>> ##### (n+2)级标题且最内层嵌套
> #### 回到上层引用(n+1)级标题

```
### n级标题且嵌套引用
> #### (n+1)级标题且被嵌套
>> ##### (n+2)级标题且最内层嵌套
> #### 回到上层引用(n+1)级标题
```

一级标题,下一行以 = 开头，美观请和标题长度保持一致
==========================================

```
一级标题
=======
```

二级标题,下一行以 - 开头，美观请和标题长度保持一致
------------------------------------------

```
二级标题
-------
```

# 段落

- 段落就是连续行上的文本
- 一个或多个空行划分不同的段落 (空行的含义就只要是看起来是空行就行了,即使包含了 \s{1,} 或者 \t{1,} 等控制符也是空行) 
- 普通段落不应该使用缩进

段落1开始段落1开始段落1开始段落1开始段落1开始段落开始1段落开始1,文字表示控制字符->\n
;新段落开始新段落开始新段落开始，段落之间直接"Enter键"方式在输出时不会作为换行处理，若需要，请将段落以\s{2,}\n作为结尾  
段落3，上一段落结尾为 \s{2,}\n 段落3,或者段落之间至少一个空行

段落4和段落3之间有一个空行

```
段落1开始段落1开始段落1开始段落1开始段落1开始段落开始1段落开始1,文件表示控制字符\n
;新段落开始新段落开始新段落开始，段落之间直接"Enter键"方式在输出时不会作为换行处理，若需要，请将段落以\s{2,}\n作为结尾  
段落3，上一段落结尾为 \s{2,}\n 段落3,或者段落之间至少一个空行

段落4和段落3之间有一个空行
```

使用缩进的话，有如下几种方式

* `半方大的空白"&ensp;"或"&#8194;",注意分号符号`
* `全方大的空白"&emsp;"或"&#8195;",注意分号符号`
* `不断行的空白格"&nbsp;"或"&#160;",注意分号符号`

  
&ensp;半方开始的段落,注意分号符号

```
&ensp;半方开始的段落,注意分号符号
```

&emsp;全方开始的段落,注意分号符号

```
&emsp;全方开始的段落,注意分号符号
```

&nbsp;段落内不换行空格,&nbsp;注&nbsp;意&nbsp;分&nbsp;号&nbsp;符&nbsp;号

```
&nbsp;段落内不换行空格,&nbsp;注&nbsp;意&nbsp;分&nbsp;号&nbsp;符&nbsp;号
```


# 列表

无序列表 \[*+-\]\sitem_contentx(某系Markdown软件/网站:同类型的连续，不同类型不连续)

* item_content0
* item_content1
+ item_content2
- item_content3
- item_content4
* item_content5

```
* item_content0
* item_content1
+ item_content2
- item_content3
- item_content4
* item_content5
```

有序列表 \[0-9]{1,n}.\sitem_content, index 不需连续

1. index+point+space+item_contentx
2. index+point+space+item_contenty
1. index+point+space+item_contentz, but the index=1, display 3

```
1. index+point+space+item_contentx
2. index+point+space+item_contenty
1. index+point+space+item_contentz, but the index=1, display 3
```

列表项中含有多行(换行or多个段落); 引用的话必须进行缩减; 代码库缩减两个层次

+ 条目-部分1,以\s{2,}\r结尾  
  条目-部分2，最好缩减保持美观，下面的一个空行将会作为条目的一部分原样输出
  
+ ## 二级标题样式的条目
+ 正常单行条目
+ 条目中包含多个段落，不能让处于条目的段落为空，否则后续append,即使使用\s{2,}\r作为空行处理     
  ;第二个段落和第一个段落之间必须有一个空行，否则将会 apped 到上一段落尾部
  ;各段落必须空行隔离，否则将不会起到段落的效果，该段落将 append 到上一段落尾部;
  
  该段落必须空行隔离，否则将不会起到段落的效果，该段落将正常展示
  
  该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行
  
  各段落必须以4个 \s or 1个 \t 开头

该段落直接顶格，导致列表展示形式断裂
+ 正常单行条目
+ > 引用也可嵌套
+ 条目中包含引用
  ;必须有一个空行，否则append到上一行的尾部

  > 引用的话必须4个 \s or 1个 \t 开始,然后引用处理;
  > 非空行间隔和正常的引用一样处理
  > ;该行同样append到上一行尾部
  > ;该行尾部以\s{2,}\r作为结尾  
  > 该行单独展示
  
  > 中间以空行作为间隔，将作为该条目的一个单独割裂引用展示
 + 代码部分,8个 \s or 2个 \t
    ```shell
    #!/bin/bash
    echo "The code block need 8 space or 2 tab as the begin of the block\n"
    ```
  4个 \s or 1个 \t 导致条目断裂  
  ```shell
  #!/bin/bash
  echo "The code block need 8 space or 2 tab as the begin of the block\n"
  ```
````
+ 条目-部分1,以\s{2,}\r结尾  
  条目-部分2，最好缩减保持美观，下面的一个空行将会作为条目的一部分原样输出
  
+ ## 二级标题样式的条目
+ 正常单行条目
+ 条目中包含多个段落，不能让处于条目的段落为空，否则后续append,即使使用\s{2,}\r作为空行处理     
  ;第二个段落和第一个段落之间必须有一个空行，否则将会 apped 到上一段落尾部
  ;各段落必须空行隔离，否则将不会起到段落的效果，该段落将 append 到上一段落尾部;
  
  该段落必须空行隔离，否则将不会起到段落的效果，该段落将正常展示
  
  该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行该段落很长的一行
  
  各段落必须以4个 \s or 1个 \t 开头

该段落直接顶格，导致列表展示形式断裂
+ 正常单行条目
+ > 引用也可嵌套
+ 条目中包含引用
  ;必须有一个空行，否则append到上一行的尾部

  > 引用的话必须4个 \s or 1个 \t 开始,然后引用处理;
  > 非空行间隔和正常的引用一样处理
  > ;该行同样append到上一行尾部
  > ;该行尾部以\s{2,}\r作为结尾  
  > 该行单独展示
  
  > 中间以空行作为间隔，将作为该条目的一个单独割裂引用展示
 + 代码部分,8个 \s or 2个 \t
    ```shell
    #!/bin/bash
    echo "The code block need 8 space or 2 tab as the begin of the block\n"
    ```
  4个 \s or 1个 \t 导致条目断裂  
  ```shell
  #!/bin/bash
  echo "The code block need 8 space or 2 tab as the begin of the block\n"
  ```
````

# 链接

内联格式: 提示文本注意引号

\[展示文本\]\(链接的地址 "提示文本"\)

This is a [google](http://www.google.com "提示文本") link.

```
This is a [google](http://www.google.com "提示文本") link.
```

引用格式: 

\[展示文本\]\[锚点\]

\[锚点\]: 链接的地址 "提示文本"

- 视为软链 `shell:  ln -s`
- 锚点可在文件中的任何单独一行
- Github 上锚点失效：锚点的上一行即使 \s{2,}\r or 显示的 `<br />` 作为结尾; 但是多个连续锚点没问题
- 保险的话，第一个锚点(区域)开始作为一个段落进行处理

有效的一个引用链接   
this is an [apple][alink] site, and this is an [apple.cn][alink.cn] site

[alink]: http://www.apple.com  'Apple'
[alink.cn]: http://www.apple.cn  'Apple.CN'

```
有效的一个引用链接   
this is an [apple][alink] site, and this is an [apple.cn][alink.cn] site

[alink]: http://www.apple.com  'Apple'    
[alink.cn]: http://www.apple.cn  'Apple.CN'
```

某些markdown软件/网站上无效的引用链接示例   

- 锚点的上一行按照段落 \s{2,}\r 结尾      
  > this is a [amazon][zlink] site       
  > [zlink]: http://www.z.cn
  > 
- 锚点的上一行最后以显示`<br />` 结尾     
  > this is a [ebay][elink] site<br />     
  > [elink]: http://www.ebay.com
  
```
某些markdown软件/网站上无效的引用链接示例   

- 锚点的上一行按照段落 \s{2,}\r 结尾      
  > this is a [amazon][zlink] site       
  > [zlink]: http://www.z.cn
  > 
- 锚点的上一行最后以显示`<br />` 结尾     
  > this is a [ebay][elink] site<br />     
  > [elink]: http://www.ebay.com
```

自适应的链接 <http://www.example.com>, 邮件地址: <admin@google.com>

`自适应的链接 <http://www.example.com>, 邮件地址: <admin@google.com>`

# 水平线

可使用的“元字符”,  \[*-_\]{3}, 下划线的一二级标题

***

```
***
```

---

```
---
```

___

```
___
```

# 字体设置

|\[\*\_\]文本文本\[\*\_\]|_文本中斜体_|
|-|-|
|\[\*\_\]\{2\}文本文本\[\*\_\]\{2\}|**文本中强调**|
|-|-|
|\[\*\_\]\{3\}文本文本\[\*\_\]\{3\}|***文本中斜体强调***|

- 需成对出现; 单个字符的话就是字面意思
- 部分markdown软件/网站上不能混排/仅使用一种格式
- \*\_前后有空格做为字面意思

单行*斜体*单行_斜体_单行斜体单行斜体

单行_斜体_单行斜体单行*斜体*单行斜体

___斜体强调___强调突出单行强调单行**强调**       
      
AB * C*D*EF _ G _ HIJKLMNOPQRSTUVWX__Y__Z

```
单行*斜体*单行_斜体_单行斜体单行斜体

单行_斜体_单行斜体单行*斜体*单行斜体

___斜体强调___强调突出单行强调单行**强调**     
      
AB * C*D*EF _ G _ HIJKLMNOPQRSTUVWX__Y__Z
```

# 代码及原始引用

单行中使用单个一对反引号`` `code` `` 扩起来

- ![#指代个数](https://placehold.it/15/f03c15/000000?text=+) 指代自身的话，比指代个数最大值+1
- 单行的话前后各一空格就好
- 多行的话直接头尾单行(3个反引号)包起来就好
- 可参看本段的原始值
- 编程语言明确情况下3个反引号+编程语言的方式处理

In Shell Program, `echo` means `printf()` in C

Now, you can use this code to replace yours :)
```shell
#!/bin/bash
echo "Hello World!"
```

````
单行中使用单个一对反引号`` `code` `` 扩起来

- ![#指代个数](https://placehold.it/15/f03c15/000000?text=+) 指代自身的话，比指代个数最大值+1
- 单行的话前后各一空格就好
- 多行的话直接头尾单行(3个反引号)包起来就好
- 可参看本段的原始值
- 编程语言明确情况下3个反引号+编程语言的方式处理

In Shell Program, `echo` means `printf()` in C

Now, you can use this code to replace yours :)
```shell
#!/bin/bash
echo "Hello World!"
```
````

# 图片

内联格式: 

\!\[图片Alter\]\(img_link "title")

This img ![googleicon](https://www.google.com/favicon.ico "Google") belong to Google.com

引用格式: 

\!\[图片Alter\]\[锚点\]

\[锚点\]: link "title"

This icon ![ebay-icon][ebayicon] belong to Ebay.com

[ebayicon]: https://www.ebay.com/favicon.ico "Ebay"

# 需要转义字符

```
\   backslash
`   backtick
*   asterisk
_   underscore
{}  curly braces
[]  square brackets
()  parentheses
#   hash mark
+   plus sign
-   minus sign (hyphen)
.   dot
!   exclamation mark
```
