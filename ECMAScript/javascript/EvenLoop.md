#### 为什么要使用

> 由于JavaScript是单线程的语言，在同一时间只能处理一件事，而如果这件事比较复杂，处理时间需要很久，那么势必会造成页面的卡顿，从而引入EvenLoop则可以解决此问题

#### 什么是evenloop
> EvenLoop是解决浏览器在同一时间只能做一件事的一种解决方案，即在主线程外去执行比较耗时的操作，例如ajax请求

#### EvenLoop分为以下两种

> 微任务：promise、process.nextTock(nodejs中才有)、MutationObserver

> 宏任务：setTimeout、setInterval、setImmediate、I/O、浏览器UI rendering
