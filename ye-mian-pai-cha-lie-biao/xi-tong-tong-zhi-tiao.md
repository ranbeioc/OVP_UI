# 系统通知条

在线地址：系统内均有

### 消息标题黄色标头被文本覆盖问题：

```
1，由于消息体插入函数置于页面头部，而依赖的页面脚本框架都在页面底部，会引起错误阻塞样式错乱：

例如：addOutageMessage 依赖 jquery
function addOutageMessage(data){
    var len = $("#outage li").length;
    $("#outage").prepend('<li style="display: block;"><a href="#"> '+(len+1)+','+data+'</a></li>');
    addMsg("outage-li",data);
    $("#outageBdy").show();
    updateCount("outage-count");
    updateCount("total-count");
}
建议将以下区域代码移植到页面底部
<script type="text/javascript" src="http://cdn.jsdelivr.net/sockjs/1/sockjs.min.js"></script>
<script type="text/javascript">
/******************************************* */
/**
 * LOCALHOST:
     DOAMIN:localhost:8080
 * SIT:
 *      DOMAIN:    
 * UAT:
 *   DOMAIN:tst01-ovp-portal-new.earth.xpaas.lenovo.com
 *
 * DEMO SHOW
 *     DOMAIN:ovp-portal-demoshow.earth.xpaas.lenovo.com
 */

/*********************************************/
websocket = null;
//var domain = "localhost:8080";
var domain = "tst01-ovp-portal-new.earth.xpaas.lenovo.com";
//var domain = "ovp-portal-demoshow.earth.xpaas.lenovo.com";
var context = "/lenovo-ovp";
if(websocket){

}else{
    if ('WebSocket' in window) {
        websocket = new WebSocket("ws://"+domain+"/lenovo-ovp/portal/websocket");
    } else if ('MozWebSocket' in window) {
        websocket = new MozWebSocket("ws://"+domain+"/lenovo-ovp/portal/websocket");
    } else {
        websocket = new SockJS("http://"+domain+"/lenovo-ovp/portal/websocket/sockjs");
    }
}


/**
 * callback for connection open
 */
websocket.onopen = function() {
     //websocket.send("2||Webscoket Opened Success");
};

/**
 * callback for message arrive
 */
websocket.onmessage = function(e) {
    if((typeof(e) != "undefined") && e && e.data){
        if(e.data.indexOf("||") > 0){
            var messs = e.data.split("||");
            var type = messs[0];
            if(type=="1"){
                addOutageMessage(messs[1]);
            }else{
                addOtherMessage(messs[1]);
            }
        }else{
            addMessage("2||"+e.data);
        }
    }
};

/**
 * callback for connection colsed
 */
websocket.onclose = function() {
    //console.log('close');
};
/**
 * callback for connection errored
 */
websocket.onerror = function() {
    //addOtherMessage("Websocket Connection error");
};

function webscoketTest() {
    websocket.send("2||test");
    return false;
}

function addMessage(data){
    var len = $("#message-top li").length;
    $("#message-top").prepend('<li style="display: block;"><a href="#"> '+(len+1)+','+data+'</a></li>');
    $("#abc").prepend('<li style="display: block;"><a href="#"> '+(len+1)+','+data+'</a></li>');
}

function addOutageMessage(data){
    var len = $("#outage li").length;
    $("#outage").prepend('<li style="display: block;"><a href="#"> '+(len+1)+','+data+'</a></li>');
    addMsg("outage-li",data);
    $("#outageBdy").show();
    updateCount("outage-count");
    updateCount("total-count");
}
function addOtherMessage(data){
    var len = $("#otherNotice li").length;
    $("#otherNotice").prepend('<li style="display: block;"><a href="#"> '+(len+1)+','+data+'</a></li>');
    addMsg("other-li",data);
    $("#oNoticesBdy").show();
    updateCount("other-count");
    updateCount("total-count");
}
function updateCount(id){
    var outageCount = $("#"+id).text();
    if(outageCount){
        outageCount = outageCount.trim();
        $("#"+id).text(parseInt(outageCount)+1);
    }
}

function addMsg(id,msg){
    var html = "<a href=\"javascript:void(0);\" onclick=\"alertDetail('"+msg+"');\" data-toggle=\"modal\" data-target=\"#modal-alert-detail\">";
        html += "<i class=\"fa fa-users text-aqua\"></i>";
        html += msg;
        html += "</a>";
    /**$("#"+id).append(html);*/
}

function alertDetail(body){
    $("#alertbody").html(body);
    $("#modal-alert-detail").show();
}




/** ***************************************** */
</script>
```

### 标准样例截图：![](/assets/Snip20171101_15.png)

### 页面修改描述：

```
1，修改顶部通知条DOM结构：需要过滤消息标题长度，并配置提示参数
<div class=" calloutfixedtop noticesBdy" >
   <div class="BreakingNewsController easing" id="breakingnews2">
    <div class="bn-title"></div>
    <ul id="abc">
      <li><a href="#" data-container="body" data-toggle="popover" data-trigger="hover"  data-placement="bottom" title="System Notices" data-content="1, System data will be updated 24 hours later during system maintenance.">1, System data will be updated 24 hours...</a></li>
      <li><a href="#" data-container="body" data-toggle="popover" data-trigger="hover" data-placement="bottom" title="System Notices" data-content="2, Guterres: 'Pressure needed to stop Myanmar carnage'">2, Guterres: 'Pressure needed to...</a></li>
      <li><a href="#" data-container="body" data-toggle="popover" data-trigger="hover" data-placement="bottom" title="System Notices" data-content="3, St Louis police killing: Fresh protest breaks out in city">3, St Louis police killing Fresh protest...</a></li>
    </ul>
    <div class="bn-arrows"><span class="bn-arrows-left"></span><span class="bn-arrows-right"></span></div>
  </div>
</div>

2，修改页尾脚本配置如下：注意修改过长的标题
  $('#breakingnews1').BreakingNews({
          title: 'Notices',
          titlebgcolor: '#f39c12',
          linkhovercolor: '#099',
          border: '1px solid #099',
          timer: 4000,
          effect: 'slide'
      });

    $('#breakingnews2').BreakingNews({
      		title: '<i class="fa fa-exclamation-triangle" aria-hidden="true"></i>',
              fonttextsize: "14px",
            titlebgcolor: '#f39c12',
            linkhovercolor: '#099',
            border: '1px solid #099',
            timer: 4000,
            effect: 'slide'
        });

3，更新全局样式文件 ovp.css 参见第1.4节描述；

4，更新全局脚本文件 ovp.js 参见第1.4节描述；
function setTltBtm(){
    $('.cdfbtm').width( $('.main-footer .container').width() - 50);
    //$('.temp2f .fedsdrop').height($('.temp1').height());
    //$('.tempm').height($('.temp1').height()-200);
    $('.calloutfixed').width( $('.main-footer .container').width());
    //$('.calloutfixedtop').width( $('.main-footer .container').width() - 450);

    $('.calloutfixedtop').css({
      "width": $('body').width() - ($('#opv-tlt').width() + 80 +  $('.navbar-custom-menu').width()),
      "left": $('#opv-tlt').width() + 80
    })

  };
```

编辑于 2017-11-02 15:43:52

