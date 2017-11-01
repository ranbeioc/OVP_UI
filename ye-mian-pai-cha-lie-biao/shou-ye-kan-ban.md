# 登录首页看板

线上地址：[http://tst01-ovp-portal-new.earth.xpaas.lenovo.com/lenovo-ovp/dashboard/index](http://tst01-ovp-portal-new.earth.xpaas.lenovo.com/lenovo-ovp/dashboard/index)

### 页面问题描述：

```
1，内页左右边距与导航目录条不一致：
更新全局样式表文件 ovp.css 参见1.4章节描述

2，在页头修改菜单区块的最大高度内部样式滚动
.sortable .box-primary .box-body {
  min-height: 200px;
  max-height: 200px;
  overflow: auto;
  overflow-y: auto;
  overflow-x: hidden;
}

3，在页头添加菜单选项最大高度内部样式混动：
#dashlist{
  max-height: 200px;
  overflow: auto;
}
```

### 标准页面截图：![](/assets/Snip20171101_11.png)参考地址：

```
Dev/dashboard/dashboard.html
```



编辑于 2017-11-01 15:41:42

