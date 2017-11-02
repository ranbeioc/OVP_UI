# 用户引导页

在线地址：http://tst01-ovp-portal-new.earth.xpaas.lenovo.com/lenovo-ovp/help/index

### 页面问题截图：![](/assets/Snip20171102_19.png)

### 页面问题描述：

```
1，页面内无数据时，应给予提示语
<p class="bg-warning text-center" style="padding:100px; color:#999;">No user guidance information has been added</p>

2，页面内隐藏域表单请设置不显示 style="display:none"
<form name="downloadf" action="/lenovo-ovp/help/download" style="display:none">
   <input type="hidden" id="fileName" name="fileName" value="">
</form>
```

编辑于 2017-11-02 16:34:51

