# 路由链接

请打开 `view/_layout/header.blade.php`  
我们找到 `a` 标签中的 `href=""`, `href=""` 中的地址就是用户点击后跳转的地址.  
现在给对应的 主页、帮助、关于添上相应的链接:

~~~~ blade
href="/"
href="/help"
href="/about"
~~~~

现在我们访问 `http://thinkphp.test` 点击顶部栏的文字就可以访问到对应的地址了.  
可是有一个问题,如果我们更改了路由中的链接,那么模板中的所有地址也要一一修改,这在一个大型项目中是不允许出现的,所以使用 `URL 生成`,就能很好的解决这个问题.

## URL 生成

找到上面修改的链接,分别更改为:

~~~~ blade
{{ url('welcome/index/home') }}
{{ url('welcome/index/help') }}
{{ url('welcome/index/about') }}
~~~~