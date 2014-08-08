---
layout: post
title: javascript function对象内置函数caller callee call apply
---

# Function对象的隐含参数 arguments

{% highlight javascript %}
function ArgTest(a, b){
   var i, s = "The ArgTest function expected ";
   var numargs = arguments.length;     // 获取被传递参数的数值。
   var expargs = ArgTest.length;       // 获取期望参数的数值。
   if (expargs < 2)
      s += expargs + " argument. ";
   else
      s += expargs + " arguments. ";
   if (numargs < 2)
      s += numargs + " was passed.";
   else
      s += numargs + " were passed.";
   s += "\n\n"
   for (i =0 ; i < numargs; i++){      // 获取参数内容。
   s += "  Arg " + i + " = " + arguments[i] + "\n";
   }
   return(s);                          // 返回参数列表。
}

// caller demo {
function callerDemo() {
    if (callerDemo.caller) {
        var a= callerDemo.caller.toString();
        alert(a);
    } else {
        alert("this is a top function");
    }
}
function handleCaller() {
    callerDemo();
}

{% endhighlight %}

call ,apply函数的目的都是要改变函数的上下文
