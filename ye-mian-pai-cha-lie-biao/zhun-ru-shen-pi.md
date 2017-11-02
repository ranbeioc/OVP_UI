# 准入审批页

在线地址：[http://tst01-ovp-portal-new.earth.xpaas.lenovo.com/lenovo-ovp/user/userAduditIndex](http://tst01-ovp-portal-new.earth.xpaas.lenovo.com/lenovo-ovp/user/userAduditIndex)

### 页面问题截图：![](/assets/Snip20171102_22.png)

### 页面问题描述：

```
1，删除页面旧标题
<h1>Access Approval <small></small></h1>

2，页面检索和数据结构区域层级错误：不能被嵌套
即
Filter搜索区域位于 box(包含box-header box-body box-footer三个区域)
dataTable数据表格区域位于 与搜索区同级的 box 标签下，不能被嵌套
```

### 标准嵌套结构截图如下：

### ![](/assets/Snip20171102_23.png)

编辑于 2017-11-02 17:59:35

