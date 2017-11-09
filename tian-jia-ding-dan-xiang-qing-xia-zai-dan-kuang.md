# 添加订单详情下载弹框

本示例是根据 /Dev/orderdetail/showOrderDetailScenario2.html 修改添加的



1，添加弹窗结构：

```
<div class="modal modal-dafault fade" id="modal-download" style="display: none;">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">×</span></button>
          <img src="../dist/img/lenovo-logo.png" style="width:20%;">
      </div>
      <div class="modal-body text-left">
        <div class="row">
          <div class="col-md-12">
            <div class="radio">
              <label>
                <input type="radio" name="optionsRadios" id="optionsRadios1" value="option1" checked>
                MS Excel
              </label>
            </div>
            <div class="radio">
              <label>
                <input type="radio" name="optionsRadios" id="optionsRadios1" value="option1" checked>
                Comma Separate Value
              </label>
            </div>
            <div class="radio">
              <label>
                <input type="radio" name="optionsRadios" id="optionsRadios1" value="option1" checked>
                XML
              </label>
            </div>
            <div class="radio">
              <label>
                <input type="radio" name="optionsRadios" id="optionsRadios1" value="option1" checked>
                HTML
              </label>
            </div>

          </div>
        </div>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-default pull-left" data-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary" >Download Now</button>
      </div>
    </div>
    <!-- /.modal-content -->
  </div>
  <!-- /.modal-dialog -->
</div>
```

2，在标题栏添加按钮：

```
<div class="box-header with-border">
 <h3 class="box-title">Order Detail</h3>
 <div class="pull-right box-tools">
  <button type="button" class="btn btn-primary btn-sm" data-toggle="modal" data-target="#modal-download">
    <i class="fa fa-download"></i> Download</button>
 </div>
</div>
```

编辑于 2017-11-09 18:38:09

