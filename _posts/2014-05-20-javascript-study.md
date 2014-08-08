---
layout: post
title: 函数编程的一些特性学习
---

# 高阶函数

如果函数作为参数或返回值使用时，就称为高阶函数

# 闭包

当内嵌函数中使用外部函数作用域内的变量时，就是使用了闭包．

用一个常用的类比来解释闭包和类的关系，类是带函数的数据，闭包是带数据的函数

在JavaScript编程中，不知不觉就会使用到闭包，闭包的这个特性在带来易用的同时，也容易带来类似内存泄露的问题。

# 类构造函数

这里我想要说的是，JavaScript函数作为类构造函数使用时的返回值问题。

由于带返回值的构造函数会产生奇怪的结果，因此不要在构造函数中调用返回值的返回语句


下面两段是 jekyll代码高亮的示例

{% highlight ruby %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}

{% highlight javascript %}
{
        "body":"another post",
        "id":21,
        "approved":true,
        "favorite_count":1,
        "status":null
}
{% endhighlight %}


# 个人总结 javascript几个最难理解的问题

这些问题都在一本叫做[javascript秘密花园](http://bonsaiden.github.io/JavaScript-Garden/zh/)的书里

变量作用域的问题

变量类型的问题

对象继承关系的问题

以及无数函数的相互嵌套

JavaScript中的数据类型

原始类型　
string  "foo"

number  1.2

true    boolean

合成类型　

array

new Function("")        function

object

{% highlight javascript %}
function is(type, obj) {
    var clas = Object.prototype.toString.call(obj).slice(8, -1);
    return obj !== undefined && obj !== null && clas === type;
}

is('String', 'test'); // true
is('String', new String('test')); // true
{% endhighlight %}

为了使代码易懂尽量在javascript函数中少使用全局变量

# 理解基于原型(prototype)继承的原理
