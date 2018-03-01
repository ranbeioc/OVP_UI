# 详情页弹出层问题修正 补充2

2018-02-28 01:12:54

1，在 ovp.css 中添加样式如下：

```
.popover {
    max-width: 400px;
    max-height: 250px;
    overflow-y: auto;
}
```

2，修改 ovp.js 中 $\('\[data-toggle="popover"\]'\).popover\(\) 代码为如下：

```
  $('[data-toggle="popover"]').popover({
        html: true,
        trigger: 'manual',
        placement: function (context, source) {
            return "top";
        }
  });
  $('[data-toggle="popover"]').on("click", function(){
    $('[data-toggle="popover"]').popover("toggle");
  });
```

3，滚动隐藏浮层为前期需求，位于 ovp.js 的 $\(window\).scroll\(\) 函数中：

```
 $('[data-toggle="popover"]').popover("hide");
```

最后编辑于 2018-03-01 18:02:25

