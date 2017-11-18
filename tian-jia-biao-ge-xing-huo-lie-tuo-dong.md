# 添加表格行或列拖动指导

### 1，添加表格列拖动页面配置： 

```
解决：请对比代码将页内 ReorderColumns 引用文件和配置代码替换即可
线上DEMO：http://issues.wenzhixin.net.cn/bootstrap-table/#extensions/reorder-columns.html

1，添加页面样式文件
<link rel="stylesheet" href="../plugins/dragtable/dragtable.css">

2，添加页面脚本文件
<script src="../plugins/bootstrap-table/extensions/reorder-columns/bootstrap-table-reorder-columns.js"></script>

3，添加表格参数配置：
data-reorderable-columns="true"
```

### 2，添加表格行拖动页面配置：

```
解决：请对比代码将页内 ReorderRows 引用文件和配置代码替换即可
线上DEMO：http://issues.wenzhixin.net.cn/bootstrap-table/#extensions/reorder-rows.html

1，添加页面样式文件
<link rel="stylesheet" href="../plugins/bootstrap-table/extensions/reorder-rows/bootstrap-table-reorder-rows.css">

2，添加页面脚本文件
<script src="../plugins/bootstrap-table/extensions/reorder-rows/bootstrap-table-reorder-rows.min.js"></script>

3，添加表格参数配置
data-reorderable-rows="true"

```

编辑于 2017-11-18 18:11:17

