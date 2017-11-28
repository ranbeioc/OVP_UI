# 样式集合指导

处理时间：2017-11-28 10:47:31

本页面是根据生产和测试环境修改的

### 1，订单详情页订单号过长的修改

样例页面地址 /search/showdetail?orderNumber=4330250876

```
添加全局 OVP.CSS 样式
.popover-content{
  word-break:break-all;
}
```

### 2，搜索页订单号过长

样例页面地址 /search/searchIndex

```
A，修改浮层消息DOM结构 nubs 改为 title
<input id="searchValueHidden" name="searchValueHidden" type="hidden" 
value="<li title=4330250876>4330250876</li>
<li title=MJ04ZX62,MJ052EZB,MJ052EZJ,MJ052EZL,MJ04ZX63,MJ04ZX64,MJ04ZX65,MJ052EZA>
MJ04ZX62,MJ052EZB,MJ052E...</li>
<li title=4330250876>4330250876</li>">

B，修改对应赋值脚本 nubs 改为 title
......
$('ol.htyLogs li').click(function() {
   txa.val($(this).attr('title'));
});
......

C，判断并过滤 LI 内容文本长度为 24个字符 加上 3个省略号，例如：
<li title=MJ04ZX62,MJ052EZB,MJ052EZJ,MJ052EZL,MJ04ZX63,MJ04ZX64,MJ04ZX65,MJ052EZA>
   MJ04ZX62,MJ052EZB,MJ052E...
</li>
```

### 3，修改页面按钮统一规范

```
A，搜索类按钮 样式类 Class 为 btn-info（浅蓝色）

B，表单提交按钮 样式类 Class 为 btn-primary（深蓝色）

C，其他按钮统一样式类 Class 为 btn-default（浅灰色）
```

### 4，修改用户信息页侧栏颜色

样例页面地址 /user/profileIndex

```
修改 OVP.CSS 如下样式

.sidebar-menu>li:hover>a, .sidebar-menu>li.active>a, .sidebar-menu>li.menu-open>a {
    background: #ccc!important;
    color:#00a6ff!important;
}
.skin-black .sidebar-menu>li.active>a {
    border-left-color: #ccc;
}
```



