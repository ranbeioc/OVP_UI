# 登陆页（B2B）

线上地址：[http://tst01-ovp-portal-new.earth.xpaas.lenovo.com/lenovo-ovp/login](http://tst01-ovp-portal-new.earth.xpaas.lenovo.com/lenovo-ovp/login)

### 页面问题截图：![](/assets/Snip20171101_3.png)页面问题描述：

```
1，头部区域删除标题标签
<p class="login-box-msg" style="color:red" id="msg"></p>

2，去除隐藏域表单高度(margin)：
<form action="/lenovo-ovp/user/loginIndex" name="languageForm" id="languageForm" method="get" style="margin:0">
    <input type="hidden" name="lang" id="lang" value="">
</form>

1，页脚区域层级错位，结构如下：
  <div class=box-footer>
    <!-- Main Footer -->
      <div class="container">
        <!-- Default to the left -->
        <strong> &copy; 2011-2017 <a href="#">Lenovo</a>.</strong> All rights reserved.
        <div class="hidden-xs">
            <a href="https://www.lenovo.com/legal/tw/zh/" target="_blank">Terms Of Use</a> | <a href="https://www.lenovo.com/privacy/tw/zh/" target="_blank">Privacy</a> | <a href="https://www.lenovo.com/sitemap/tw/zh/" target="_blank">Site Map</a>
          </div>
      </div>

  </div>
  <p class="well">*The recommended web browser is Firefox, Chrome, or Internet Explorer 10 or above.</p>
```

### 标准页面截图：

### ![](/assets/Snip20171101_4.png)

### 参考地址：

```
Dev/usermanage/login.html
```

编辑于 2017-11-01 14:14:03

