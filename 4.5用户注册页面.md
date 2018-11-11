# 注册路由

> 本章只是书写前端的静态页面,不涉及数据库操作
打开 `route/router.php`,添加

~~~~ php
Route::get('/signup', 'user/auth/create');
~~~~

现在我们要创建一个单独的 user 模块来处理用户功能,而 auth 控制器则集中处理验证方面的问题.

## 生成控制器

请按下 Ctrl+Shift+` 并切换到终端  
使用 Think 命令来生成控制器:

~~~~ shell
// 默认生成 资源控制器
php think make:controller user/Auth
~~~~

打开 `application/user/Auth.php`,并找到 `create()` 方法,键入:

~~~~ php
return view();
~~~~

现在再创建一个视图文件：`application/user/view/auth/create.blade.php`,如果你不清楚路径为什么会这样,请回到本书 3.2 静态页面 仔细阅读.

~~~~ blade
@extends('_layout.default')
@section('title', '注册')
@section('content')
<section class="jumbotron text-center">
    <div class="container">
        <h1 class="jumbotron-heading">注册</h1>
    </div>
</section>
@stop
~~~~

并且把 `welcome/view/_layout` 文件夹复制到 `user/view/`
现在按下 `Ctrl+Shift+F`,并在第一个框中填写:`<a class="btn btn-outline-success my-2 my-sm-0" href="#">注册`  
第二个框中填写 `<a class="btn btn-outline-success my-2 my-sm-0" href="{{ url('user/auth/create') }}">注册`
然后点击框框右边的按钮进行全局替换并保存.