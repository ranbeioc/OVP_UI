# 添加订单详情MFG表格

本示例是以 /Dev/orderdetail/showOrderDetailScenario13.html 为基础介绍操作方法

1，添加MFG按钮，并设定 mfgBtn 类：

```
<div class="row">
  <Div class="col-md-3">
    <button type="button" class="btn btn-block btn-default sysBtn">System Details</button>
  </Div>
  <Div class="col-md-3">
    <button type="button" class="btn btn-block btn-default mfgBtn">MFG Status Details</button>
  </Div>
</div>
```

2，添加MFG表格结构，与 syshide 同级：

```
<div class="row mfghide">
  <Div class="col-md-12">

    <div class="table-responsive no-padding">
      <table class="table table-striped">
        <tbody>
          <tr class="status_table_th bundle_detail_th">
            <td valign="bottom">
              <div class="commom_text_a3">Item</div>
            </td>
            <td valign="bottom">
              <div class="commom_text_a2">Quantity</div>
            </td>

            <td valign="bottom">
              <div class="a4">Milestone</div>
            </td>

            <td valign="bottom">
              <div class="a9">Date</div>
            </td>

          </tr>

          <tr>
            <td>
              <div>10</div>
            </td>
            <td>
              <div>
                5
              </div>
            </td>

            <td >
              Assmebly Start
            </td>

            <td >
              6.21, 2017
            </td>


          </tr>

          <tr>
            <td>
              <div>10</div>
            </td>
            <td>
              <div>
                5
              </div>
            </td>

            <td >
              Final Start
            </td>

            <td >
              6.20, 2017
            </td>


          </tr>

          <tr>
            <td>
              <div>10</div>
            </td>
            <td>
              <div>
                5
              </div>
            </td>

            <td >
              Release Start
            </td>

            <td >
              6.20, 2017
            </td>


          </tr>

          

        </tbody>
      </table>

    </div>

  </Div>
</div>
```

3，添加和修改 ovp.js 脚本控制

```
  $('.sysBtn').click(function() {
      $('.syshide').toggle();
      $('.mfghide').hide();
  });
  $('.mfgBtn').click(function() {
      $('.mfghide').toggle();
      $('.syshide').hide();
  });
```

4，添加页面头部区域内的css样式：

```
  .mfgBtn{margin: 10px 0  10px 0;}
  .mfghide{display: none;}
```

编辑于 2017-11-08 21:54:35

