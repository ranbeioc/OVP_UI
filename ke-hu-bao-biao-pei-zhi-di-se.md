# 客户报表突出无配置项字段样式

本示例是根据 /Dev/customreport/CreateTemplate1-re.html 修改

1，添加页面内脚本函数（示例）$\(domReady\) 内

```
    function setNoBGC($item){
        for(var i = 0; i < $item.length; i++){
          var im = $item[i];
          var ids = getfedIndex($(im));
          if($(ids).length == 0){
            $(im).css({"background-color":"#ccc"});
          };
        };
    }
```

2，修改页面内拖动列表脚本函数（示例）receive 事件内加入setNoBGC\(item.item\);

```
    $('ul.fedsdrop').multisortable({
      ..........
      receive: function(event, item) {
        console.log("M_R",item);
        setSetID();

        setNoBGC(item.item);
      },
      .........
    });
```

3，修改页面内拖动项点击事件函数（示例）IF-ELSE 判断内加入 setNoBGC\($item\);

```
    function clickSTE($item,event){
        if(event.target.tagName == 'LI'){
          ..........
          if($(ids).length>0){
            .........
          }else{
            .........
            setNoBGC($item);
          }
        };
    };
```

4，修改反向拖回项还原样式函数（示例）receive 事件内添加 $\(item.item\).css\({"background-color":"\#f1f1f1"}\)

```
    $('ul.fedslist').multisortable({
      receive: function(event, item) {
        console.log("M_L")
        $(item.item).css({"background-color":"#f1f1f1"});
        $(item.item).removeClass('selected').unbind('click');
        hideFeds();
      }
    });
```

编辑于 2017-11-18 17:21:01

