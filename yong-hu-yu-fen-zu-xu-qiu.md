# 用户与分组等需求指导

本内容是根据 2017-11-10 要求依次列出的，具体参见分条描述：

### 1，底部系统通知条在页面无滚动时宽度的修改：

```

if( $(document).height() ==  $(window).height() ){
  $('#breakingnews1').parent().css({'margin-bottom':'3px', 'left':$('.main-footer .container').offset().left + $('.main-footer span:last').width() + 30, 'width':$('.main-footer .container').width() - 500});
}

```

### 2，用户分组推荐控件 jsTree 使用 Ajax 示例如下：

Demo：http://jsfiddle.net/vakata/2kwkh2uL/4480/

```
Populating the tree using AJAX

Building off of the previous example, let's see how to have jstree make AJAX requests for you.

<div id="container"></div>


<script>
$(function() {
  $('#container').jstree({
    'core' : {
      'data' : {
        "url" : "//www.jstree.com/fiddle/",
        "dataType" : "json" // needed only if you do not supply JSON headers
      }
    }
  });
});
</script>


The server response is:

[{
  "id":1,"text":"Root node","children":[
    {"id":2,"text":"Child node 1"},
    {"id":3,"text":"Child node 2"}
  ]
}]


Instead of a JS array, you can set core.data to a jQuery AJAX config. jsTree will hit that URL, and provided you return properly formatted JSON it will be displayed.

If you cannot provide proper JSON headers, set core.data.dataType to "json".

The ids in the server response make it possible to identify nodes later (which we will see in the next few demos), but they are not required.

WHEN USING IDS MAKE SURE THEY ARE UNIQUE INSIDE A PARTICULAR TREE
```

3，用户分组使用JSON数据配置说明如下：

DEMO：http://jsfiddle.net/vakata/2kwkh2uL/4479/

```
The data you use must be in a specific format, each branch of the tree is represented by an object, which must at least have a text key. The children key can be used to add children to the branch, it should be an array of objects.

Keep in mind, you can use a simple string instead of an object if all you need is node with the given text, the above data can be written as:

[ { "text" : "Root node", "children" : [ "Child node 1", "Child node 2" ] } ]
There are other available options for each node, only set them if you need them like:

id - makes if possible to identify a node later (will also be used as a DOM ID of the LI node). Make sure you do not repeat the same ID in a tree instance (that would defeat its purpose of being a unique identifier and may cause problems for jstree).
icon - a string which will be used for the node's icon - this can either be a path to a file, or a className (or list of classNames), which you can style in your CSS (font icons also work).
data - this can be anything you want - it is metadata you want attached to the node - you will be able to access and modify it any time later - it has no effect on the visuals of the node.
state - an object specifyng a few options about the node:
selected - if the node should be initially selected
opened - if the node should be initially opened
disabled - if the node should be disabled
checked - checkbox plugin specific - if the node should be checked (only used when tie_selection is false, which you should only do if you really know what you are doing)
undetermined - checkbox plugin specific - if the node should be rendered in undetermined state (only used with lazy loading and when the node is not yet loaded, otherwise this state is automatically calculated).
type - types plugin specific - the type of the nodes (should be defined in the types config), if not set "default" is assumed.
li_attr - object of values which will be used to add HTML attributes on the resulting LI DOM node.
a_attr - object of values which will be used to add HTML attributes on the resulting A node.
Here is a new demo with some of those properties set:

<div id="container"></div>

<script>
$(function() {
  $('#container').jstree({
    'core' : {
      'data' : [
          {
              "text" : "Root node",
              "state" : {"opened" : true },
              "children" : [
                  {
                    "text" : "Child node 1",
                    "state" : { "selected" : true },
                    "icon" : "glyphicon glyphicon-flash"
                  },
                  { "text" : "Child node 2", "state" : { "disabled" : true } }
              ]
        }
      ]
    }
  });
});
</script>

```



编辑于 2017-11-13 00:45:51

