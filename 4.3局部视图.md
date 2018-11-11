# 局部视图

回到 `default.blade.php`, 如果将所有代码都堆积到 `default.blade.php`, 可读性会变得极差,并且为以后的维护增加阻碍. 所以我们需要将 `header` 单独拆分,成为一个独立的模板文件.

## 头部视图

在 `view/_layout` 下创建 `header.blade.php` 和 `footer.blade.php`
并将 `default.blade.php` 文件中 `<header> </header>` `<footer> </footer>` 的内容全部剪切到 `header.blade.php` `footer.blade.php`  
将 `default.blade.php` 中 `<div class="container"> </div>` 替换为:

~~~~ blade
@include('_layout.header')
<div class="container">
@yield('content')
</div>
@include('_layout.footer')
~~~~

`@include` 是 `Blade` 模板引擎中视图引用方法.