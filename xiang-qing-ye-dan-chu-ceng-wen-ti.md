# 详情页弹出层问题修正

2018-02-28 01:12:54

1，在 ovp.css 中添加样式如下：

```
.popover {
    max-width: 400px;
    max-height: 200px;
    overflow-y: auto;
}
```

2，修改 ovp.js 中 $\('\[data-toggle="popover"\]'\).popover\(\) 代码为如下：

```
  $('[data-toggle="popover"]').popover({
        html: true,
        trigger: 'click',
        placement: function (context, source) {
            var position = $(source).position();

            if (position.left > 515) {
                return "left";
            }

            if (position.left < 515) {
                return "right";
            }

            if (position.top < 110){
                return "bottom";
            }
            return "top";
        }

  });
```

3，滚动隐藏浮层为前期需求，可将 ovp.js 其 $\(window\).scroll\(\) 中清除如下代码即可：

```
 $('[data-toggle="popover"]').popover("hide");
```

最后编辑于 2018-02-28 01:18:58

