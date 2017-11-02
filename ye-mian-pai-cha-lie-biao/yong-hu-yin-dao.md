# 用户引导页

在线地址：[http://tst01-ovp-portal-new.earth.xpaas.lenovo.com/lenovo-ovp/help/index](http://tst01-ovp-portal-new.earth.xpaas.lenovo.com/lenovo-ovp/help/index)

### 页面问题截图：![](/assets/Snip20171102_19.png)

### 页面问题描述：

```
1，页面内无数据时，应给予提示语
<p class="bg-warning text-center" style="padding:100px; color:#999;">No user guidance information has been added</p>

2，页面内隐藏域表单请设置不显示 style="display:none"
<form name="downloadf" action="/lenovo-ovp/help/download" style="display:none">
   <input type="hidden" id="fileName" name="fileName" value="">
</form>

3，页面尾部结构为：
<footer class="main-footer">
    <div class="container">
      <!-- To the right -->
      <div class="pull-right hidden-xs">
        <a href="https://www.lenovo.com/legal/tw/zh/" target="_blank">Terms Of Use</a> | <a href="https://www.lenovo.com/privacy/tw/zh/" target="_blank">Privacy</a> | <a href="https://www.lenovo.com/sitemap/tw/zh/" target="_blank">Site Map</a>
      </div>
      <!-- Default to the left -->
      <strong> &copy; 2011-2017 <a href="#">Lenovo</a>.</strong> All rights reserved.
    </div>
  </footer>
```

编辑于 2017-11-02 16:34:51

