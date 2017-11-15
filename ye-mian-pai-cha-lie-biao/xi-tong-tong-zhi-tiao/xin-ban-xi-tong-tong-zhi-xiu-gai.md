# 新版系统通知条修改指导

本示例是根据 /Dev/common/notes.html 修订

1，修改全局样式表 ovp.css 文件：

注意以下样式类中UAT特别配置的 height：42px 等数值需要依据UAT实际效果修改

```
.calloutfixedtop{
  position: absolute;
  top: 9px;
  left:350px;
  z-index: 99999;
}

.BreakingNewsController ul{padding:0; margin:0; 
    list-style-type: decimal!important;
    list-style-position: inside;
    position:absolute; left:180px; right:50px;  background-color:transparent}

.BreakingNewsController ul li{padding:3px 10px; overflow:hidden;}

.BreakingNewsController ul li a{ overflow:hidden;text-align: center; width:90%;text-decoration:none; color:#333; display:inline-block; padding:2px 0; font-family: sans-serif,'Helvetica Neue',Helvetica; font-weight: 500; font-style: italic; font-size: 14px;}
```

2，修改全局脚本 ovp.js 文件：

```
A，修改 $(window).scroll 函数内

$('#breakingnews1').parent().css({'margin-bottom':'8px', 'left':$('.main-footer .container').offset().left + $('.main-footer span:last').width() + 30, 'width':$('.main-footer .container').width() - 500});

B，修改 setTltBtm() 函数内

if( $(document).height() ==  $(window).height() ){
  $('#breakingnews1').parent().css({'margin-bottom':'8px', 'left':$('.main-footer .container').offset().left + $('.main-footer span:last').width() + 30, 'width':$('.main-footer .container').width() - 500});
}

C，替换以下组件全段函数

!function(l){$.fn.BreakingNews=function(l){var i={background:"#FFF",title:"NEWS",titlecolor:"#FFF",titlebgcolor:"#5aa628",linkcolor:"#333",linkhovercolor:"#5aa628",fonttextsize:14,isbold:!1,border:"none",width:"100%",autoplay:!0,timer:3e3,modulid:"brekingnews",effect:"fade"},l=$.extend(i,l);return this.each(function(){function i(i){"next"==i?$(l.modulid+" ul li").length>d?d++:d=1:d-2==-1?d=$(l.modulid+" ul li").length:d-=1,"fade"==l.effect?($(l.modulid+" ul li").css({display:"none"}),$(l.modulid+" ul li").eq(parseInt(d-1)).fadeIn()):$(l.modulid+" ul").animate({marginTop:-($(l.modulid+" ul li").height()+6)*(d-1)})}l.modulid="#"+$(this).attr("id");var t,o=l.modulid,d=1;t=1==l.isbold?"bold":"normal","slide"==l.effect?$(l.modulid+" ul li").css({display:""}):$(l.modulid+" ul li").css({display:"none"}),$(l.modulid+" .bn-title").html(l.title),$(l.modulid).css({width:l.width,background:l.background,border:l.border,"font-size":l.fonttextsize}),$(l.modulid+" ul").css({left:$(l.modulid+" .bn-title").width()+40}),$(l.modulid+" .bn-title").css({background:l.titlebgcolor,color:l.titlecolor,"font-weight":t}),$(l.modulid+" ul li a").css({color:l.linkcolor,"font-weight":t,height:parseInt(l.fonttextsize)+3}),$(l.modulid+" ul li").eq(parseInt(d-1)).css({display:""}),$(l.modulid+" ul li a").hover(function(){$(this).css({color:l.linkhovercolor})},function(){$(this).css({color:l.linkcolor})}),$(l.modulid+" .bn-arrows span").click(function(l){i("bn-arrows-left"==$(this).attr("class")?"prev":"next")}),1==l.autoplay?(o=setInterval(function(){i("next")},l.timer),$(l.modulid).hover(function(){clearInterval(o)},function(){o=setInterval(function(){i("next")},l.timer)})):clearInterval(o),$(window).resize(function(i){$(l.modulid).width()<360?($(l.modulid+" .bn-title").html("&nbsp;"),$(l.modulid+" .bn-title").css({width:"4px",padding:"3px 0px"}),$(l.modulid+" ul").css({left:4})):($(l.modulid+" .bn-title").html(l.title),$(l.modulid+" .bn-title").css({width:"auto",padding:"3px 10px"}),$(l.modulid+" ul").css({left:$(l.modulid+" .bn-title").width()+40}))})})}}(jQuery);
```

编辑于 2017-11-15 14:33:12

