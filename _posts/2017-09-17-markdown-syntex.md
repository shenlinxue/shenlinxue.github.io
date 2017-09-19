---
layout: post
title: "markdown语法"
category: markdown
tags: []
---


* ## 段落

使用空行分隔,多个空行和一个空行效果相同  
*markdown:*  
> Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
 tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam
> <br>	  
>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
 roident, sunt in culpa qui officia deserunt mollit anim id est laborum.

*效果如下:*  
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmodtempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmodroident, sunt in culpa qui officia deserunt mollit anim id est laborum.

***

* ## 换行

行尾连续输入两个空格回车

***

* ## 标题

小标题:使用"#"加上空格后输入标题内容,或者标题下一行输入一个或以上"=",显示为小标题;  
大标题:使用"##"加上空格后输入标题内容,或者标题下一行输入一个或以上"-",显示为大标题;  
注意:使用"="和"-"方法时,前一行必须为空行;

3个"#"到6个"#"依次代表三号字到六号字

*markdown:*
>\# 这是小标题
<br/>  
这是小标题  
\=
<br/>  
\## 这是大标题
<br/>  
这是大标题  
\-  
<br>
\### 这是三号字  
\#### 这是四号字  
\##### 这是五号字  
\###### 这是六号字  

*效果如下:*

# 这是小标题

这是小标题
=

## 这是大标题

这是大标题
-    

### 这是三号字
#### 这是四号字
##### 这是五号字
###### 这是六号字

***

* ## 区块引用

">"后输入的内容会显示在区块中

*markdown:*
> \>这是区块  
> 这是区块  
> 这是区块  

*效果如下:*
>  这是区块  
这是区块  
这是区块  

***

## 斜体,粗体

>\*哈哈哈哈*  
\_哈哈哈哈_  
\**哈哈哈哈**  
\__哈哈哈哈__  


*哈哈哈哈*  
_哈哈哈哈_  
**哈哈哈哈**  
__哈哈哈哈__  

***

## 列表

无序列表  
"*"或"+"或"-"加上空格后输入列表项
>\* 第一项  
\* 第二项  
\* 第三项  
<br>
\+ 第一项  
\+ 第二项  
\+ 第三项  
<br>
\- 第一项  
\- 第二项  
\- 第三项   

* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项

- 第一项
- 第二项
- 第三项

有序列表
>1. 第一项
2. 第二项
3. 第三项

1. 第一项
2. 第二项
3. 第三项

列表小项中下一行内容会自动缩进,其他段落如需跟随上一段落缩进,只需在段落前输入四个空格

* 第一项  
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,

    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,

## 链接
行内链接形式,第二条为链接增加了title属性
>`This is an [example link](http://example.com/).`  
`This is an [example link](http://example.com/ "With a Title").`

This is an [example link](http://example.com/).  
This is an [example link](http://example.com/ "With a Title").

参考链接形式,索引1增加了title属性  
>`上[百度][1]去[谷歌][2]一下`
<br>  
`[1]: http://baidu.com "baidu"`  
`[2]: http://google.com/ `  

上[百度][1]去[谷歌][2]一下

[1]: http://baidu.com "baidu"
[2]: http://google.com/ 

## 图片  
行内形式  
>`![alt text](/image/128.png "Title")`  

![alt text](/image/128.png "Title")

参考形式  
>`![alt text][id]`  
<br>
`[id]: /image/128.png "Title"`

![alt text][logo]  

[logo]: /image/128.png "Title"


## 代码  
使用反引号 "`" 来标记代码区段，区段内的代码不会被markdown或者html解析,区段内的 &、< 和 > 都会被自动的转换成 HTML 实体，这项特性让你可以很容易的在代码区段内插入 HTML 码：

>\`<h1>` 

`<h1>`

连续输入四个空格,后面整段文字都会显示为代码样式

>` `` `` `` `orem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,

    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,

## 分割线
连续输入三个"*",注意前一行必须为空行
>`***`

***

## 代码高亮

    { % highlight ruby % }
    def show
      @widget = Widget(params[:id])
      respond_to do |format|
        format.html # show.html.erb
        format.json { render json: @widget }
      end
    end
    { % endhighlight % }

{% highlight ruby %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}


