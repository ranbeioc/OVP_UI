# 添加表格固定首列

DEMO页面

```
Dev/customreport/reportTemplates-Admin.html
```

修改方式

```
1，添加样式引用
<link rel="stylesheet" href="../plugins/bootstrap-table/extensions/fixed-column/bootstrap-table-fixed-columns.css">

2，添加脚本引用
<script src="../plugins/bootstrap-table/extensions/fixed-column/bootstrap-table-fixed-columns.js"></script>

3，添加脚本配置
$('#table').bootstrapTable('destroy').bootstrapTable({
    fixedColumns: true,
    fixedNumber: 3
});

```

在线样例地址

```
http://issues.wenzhixin.net.cn/bootstrap-table/#extensions/fixed-columns.html
```



