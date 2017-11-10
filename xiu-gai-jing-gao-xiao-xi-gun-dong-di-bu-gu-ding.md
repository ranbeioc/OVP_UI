# 修改警告消息滚动底部固定

本示例可在以下页面查看效果 /Dev/common/notes.html



1，修改警告消息部分 ovp.css 全局样式：

```
.calloutfixed, .cdfbtm{
  position: fixed;
  bottom: 0;
  z-index: 999;
  margin: 0 0 0 0;
  background-color: rgba(255,255,255,0.7);
}
```

2,，接着修改背景透明样式 ovp.css ：

```
.BreakingNewsController{width:100%; overflow:hidden; background-color:transparent; height:auto; position:relative;}
.BreakingNewsController ul{padding:0; margin:0; display:block; list-style:none; position:absolute; left:180px; right:50px;  background-color:transparent}
```

3，修改警告消息部分 ovp.js 全局脚本文件：

```
  $(window).scroll(function() {
    var winPos = $(window).scrollTop();
    var vo = $('#ovp-logo'), vt = $('#opv-tlt'), vb=$('.tltbtm'), vn = $('#navbar-collapse2');
    var winBdy = $(".main-footer").offset().top - ($(window).scrollTop() + $(window).height());
    if(!device){
      vo.attr("src","../dist/img/logo1s.png");
      vt.css({"padding":"0 0 0 70px","margin-top":"10px"});
      vb.hide();
      vn.css("border-top","2px solid #e22319");
      if(!winPos){
        vo.attr("src","../dist/img/logo1m.png");
        vt.hide().css({"padding":"0 0 0 70px"}).show();
        vb.show();
        vn.css("border-top","1px solid #f1f1f1");
      };      
      if(winBdy >= 0){
        $('.noticesBdy').addClass('calloutfixed').css('margin-bottom','0');
      }else{
        $('.noticesBdy').css('margin-bottom','10px').removeClass('calloutfixed');
      };
    }
  });
```

4，修改警告消息的背脊配置脚本 ovp.js : 

```
$('#breakingnews1').BreakingNews({
    title: 'Notices',
    background: 'transparent',
    titlebgcolor: '#f39c12',
    linkhovercolor: '#099',
    border: '1px solid #ccc',
    timer: 4000,
    effect: 'slide'
});
```

编辑于 2017-11-10 14:58:07

