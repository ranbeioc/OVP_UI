# 详情页弹出层问题修正 修正3

2018-03-02 13:10:39

1，在 ovp.css 中修改样式如下：

~~.popover {~~

~~    max-width: 400px;~~

~~    max-height: 250px;~~

~~    overflow-y: auto;~~

~~}~~

```
.popover {
    max-width: 400px;
}
.popover-content {
    max-height: 250px;
    overflow-y: auto;
}
```

2，还原 ovp.js 中 $\('\[data-toggle="popover"\]'\).popover\(\) 代码为如下：

~~ $\('\[data-toggle="popover"\]'\).popover\({~~

~~        html: true,~~

~~        trigger: 'manual',~~

~~        placement: function \(context, source\) {~~

~~            return "top";~~

~~        }~~

~~  }\);~~

~~ $\('\[data-toggle="popover"\]'\).on\("click", function\(\){~~

~~    $\('\[data-toggle="popover"\]'\).popover\("toggle"\);~~

~~  }\);~~

```
  $('[data-toggle="popover"]').popover();
```

3，删除滚动隐藏浮层代码，位于 ovp.js 的 $\(window\).scroll\(\) 函数中：

~~ $\('\[data-toggle="popover"\]'\).popover\("hide"\);~~

4，在订单详情页内按钮增加4项参数如下：

data-placement="top"

data-trigger="click"

data-html="true"

title="Serial Number&lt;a class='close mpop' aria-label=Close&gt;&lt;span aria-hidden=true&gt;×&lt;/span&gt;&lt;/a&gt;"

```
<button type="button" class="btn btn-default btn-xs" 
data-container="body" 
data-toggle="popover" 
data-placement="top" 
data-trigger="click" 
data-html="true" 
title="Serial Number<a class='close mpop' aria-label=Close><span aria-hidden=true>&times;</span></a>" 
data-content="MM110093  MM110093  MM110093 MM110093  MM110093  MM110093 MM110093  MM110093  MM110093 MM110093  MM110093  MM110093 MM110093  MM110093  MM110093 MM110093  MM110093  MM110093 MM110093  MM110093  MM110093 MM110093  MM110093  MM110093 MM110093  MM110093  MM110093 MM110093  MM110093  MM110093 MM110093  MM110093  MM110093 MM110093  MM110093  MM110093  MM110093  MM110093  MM110093 MM110093  MM110093  MM110093  MM110093  MM110093  MM110093 MM110093  MM110093  MM110093  MM110093  MM110093  MM110093 MM110093  MM110093  MM110093  MM110093  MM110093  MM110093 MM110093  MM110093  MM110093  MM110093  MM110093  MM110093 MM110093  MM110093  MM110093  MM110093  MM110093  MM110093 MM110093  MM110093  MM110093  MM110093  MM110093  MM110093 MM110093  MM110093  MM110093  MM110093  MM110093  MM110093 MM110093  MM110093  MM110093  MM110093  MM110093  MM110093 MM110093  MM110093  MM110093">More</button>
```

5，页面内增加脚本并修改：

&lt;script&gt;

$\(function\(\) {

~~        $\("\[data-toggle='popover'\]"\).popover\(\);~~

}\);

&lt;/script&gt;

```
  $(function () {
    $('[data-toggle="popover"]').on('shown.bs.popover', function () {
      var _this = $(this);
      $('a.mpop').click(function () {
        _this.click();
      });
    });
  });
```

最后编辑于 2018-03-02 13:10:28

