对一些不做限制的网站请求时ok，但是就如之前所讲的，很多网站对没有设置请求头的请求都是禁止访问，所以我们的爬虫中都设置了标题，那么在scrapy如何设置请求头呢？

问题分析，我们设置请求头很大一部分实际上是在于标题，所以我们在scrapy中设置user-agent实际上就完成了请求标题头部的设置。

scrapy shell -s USER_AGENT =“” request_url就可以完成带头部的请求添加，如请求知乎（不带标题请求时400错误）：
scrapy shell -s USER_AGENT =“ Mozilla / 5.0（Windows NT 10.0; Win64; x64 ; rv：61.0）Gecko / 20100101 Firefox / 61.0“ https://www.zhihu.com/question/285908404
