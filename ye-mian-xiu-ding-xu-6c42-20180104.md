# 页面修订需求

2018-01-04 17:52:38



1，在全局样式OVP.CSS文件修改如下：

```
删除 .calloutfixedtop  内的  min-width: 450px; 
```

```
新增加 
.navbar-nav>.user-menu>.dropdown-menu>li.user-header{ height: auto; }
```

2，页面头文件修改：

```
增加移动端用户图标
加入 <span class="glyphicon glyphicon-user"></span>

如下结构：
<a href="#" class="dropdown-toggle" data-toggle="dropdown">
    <!-- The user image in the navbar-->
    <!-- <img src="../dist/img/user1-128x128.jpg" class="user-image" alt="User Image"> -->
    <span class="glyphicon glyphicon-user"></span>
    <!-- hidden-xs hides the username on small devices so only the image appears. -->
    <span class="hidden-xs">Agiridhar</span>
</a>
```

```
新增移动端快捷搜索框，
注意：提交后需要后端开发支持，本搜索框编号变为 quickForm-xs 和 quickSearch-xs

加入如下结构：
<form class="form-inline hidden-md hidden-lg" id="quickForm-xs" role="search" action="/lenovo-ovp/fullsearch/toSearch" method="post">
  <div class="form-group col-xs-9" style="padding-top:8px;margin-bottom:5px;">
    <input type="text" class="form-control" name="value" id="quickSearch-xs" placeholder="Quick Search">
  </div>
</form>

后续原有结构：
<button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar-collapse2">
 <i class="fa fa-list"></i> MENU
</button>
```

最后编辑于 2018-01-04 18:01:08

