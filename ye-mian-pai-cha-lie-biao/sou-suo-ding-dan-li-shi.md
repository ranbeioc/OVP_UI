# 搜索订单历史页

线上地址：[http://tst01-ovp-portal-new.earth.xpaas.lenovo.com/lenovo-ovp/search/searchIndex](http://tst01-ovp-portal-new.earth.xpaas.lenovo.com/lenovo-ovp/search/searchIndex)

### 页面问题截图：![](/assets/Snip20171101_12.png)

### 页面问题描述：

```
1，内页左右边距与导航目录条不一致：
更新全局样式表文件 ovp.css 参见1.4章节描述

2，修改日历周期选择结构为：
<div class="row">
   <div class="col-md-12">
       <label for="">Start & End Date </label>

       <div class="form-group"  style="width:100%">
         <div class="input-group date"  style="width:100%">
          <div class="input-group-addon">
            <i class="fa fa-calendar"></i>
          </div>
          <input type="text" class="form-control pull-right datepicker" id=""  style="width:100%;">
         </div>
       </div>

   </div>
</div>

3，修改日历周期选择脚本配置：向上居中弹出控件
$('.datepicker').daterangepicker({
    opens: "center",
    drops: "up",
    locale: {
       format: 'YYYY-MM-DD'
     }
});
```

### 标准页面截图：

### ![](/assets/Snip20171101_13.png)

### 参考地址：

```
Dev/search/OrderSearch.html
```



编辑于 2017-11-01 15:41:30

