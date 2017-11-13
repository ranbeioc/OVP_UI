# 数据表格顶部按钮指导

本示例是根据 /Dev/customreport/reportTemplates-Admin.html 进行修改的

### 实际效果如下截图：![](/assets/Snip20171113_1.png)1，为数据表格配置自定义工具条区域：data-toolbar="\#toolbar" 

```
 <table id="table"
        data-toggle="table"
        data-height="500"
        data-toolbar="#toolbar"                      
        data-show-columns="true"
        data-pagination="true"
        data-pagination-v-align="both"
        showPaginationSwitch="true"
        data-sort-name=""
        data-sort-order="desc"
        data-id-field="id">
 .......     
```

### 2，在数据表格前添加工具条按钮结构：更具实际需求添加按钮（与底部按钮区域相同）

```
<div id="toolbar">
    <div class="form-inline" role="form">
        <button type="botton" class="btn btn-default">Create New</button>
        <button type="botton" class="btn btn-default" data-toggle="modal" data-target="#modal-default">Share</button>
        <button type="botton" class="btn btn-default">Transfer</button>
        <button type="botton" class="btn btn-default">Revoke</button>
        <button type="botton" class="btn btn-default">Archive</button>
        <button type="botton" class="btn btn-default">Trash can</button>
      </div>
</div>
<table id="table"
    data-toggle="table"
    data-height="500"
    data-toolbar="#toolbar"  
.......
```

编辑于 2017-11-13 17:55:48

