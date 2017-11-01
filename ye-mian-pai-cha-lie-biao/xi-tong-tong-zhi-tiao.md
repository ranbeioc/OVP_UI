# 系统通知条

在线地址：系统内均有

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
    		title: '!',
              fonttextsize: "14px",
    		titlebgcolor: '#f39c12',
    		linkhovercolor: '#099',
    		border: '1px solid #099',
    		timer: 4000,
    		effect: 'slide'
    	});

3，更新全局样式文件 ovp.css 参见第1.4节描述；

4，更新全局脚本文件 ovp.js 参见第1.4节描述；
```

编辑于 2017-11-01 21:30:43

