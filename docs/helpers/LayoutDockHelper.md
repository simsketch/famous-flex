<a name="module_LayoutDockHelper"></a>
#LayoutDockHelper
LayoutDockHelper helps positioning nodes using docking principles.

**Example:**

```javascript
var LayoutDockHelper = require('famous-flex/helpers/LayoutDockHelper');

function HeaderFooterLayout(context, options) {
  var dock = new LayoutDockHelper(context);
  dock.top('header', options.headerHeight);
  dock.bottom('footer', options.footerHeight);
  dock.fill('content');
};
```

You can also use layout-literals to create layouts using docking semantics:

```javascript
var layoutController = new LayoutController({
  layout: {dock: [
    ['top', 'header', 40],
    ['bottom', 'footer', 40],
    ['fill', 'content']
  ]},
  dataSource: {
    header: new Surface({content: 'header'}),
    footer: new Surface({content: 'footer'}),
    content: new Surface({content: 'content'}),
  }
});
```

<a name="exp_module_LayoutDockHelper"></a>
##class: LayoutDockHelper ⏏
**Members**

* [class: LayoutDockHelper ⏏](#exp_module_LayoutDockHelper)
  * [new LayoutDockHelper(context, [options])](#exp_new_module_LayoutDockHelper)
  * [layoutDockHelper.parse(data)](#module_LayoutDockHelper#parse)
  * [layoutDockHelper.top([node], [height])](#module_LayoutDockHelper#top)
  * [layoutDockHelper.left([node], [width])](#module_LayoutDockHelper#left)
  * [layoutDockHelper.bottom([node], [height])](#module_LayoutDockHelper#bottom)
  * [layoutDockHelper.right([node], [width])](#module_LayoutDockHelper#right)
  * [layoutDockHelper.fill(node)](#module_LayoutDockHelper#fill)

<a name="exp_new_module_LayoutDockHelper"></a>
###new LayoutDockHelper(context, [options])
**Params**

- context `LayoutContext` - layout-context  
- \[options\] `Object` - additional options  
  - \[margins\] `Object` - margins to start out with (default: 0px)  
  - \[translateZ\] `Number` - z-index to use when translating objects (default: 0)  

<a name="module_LayoutDockHelper#parse"></a>
###layoutDockHelper.parse(data)
Parses the layout-rules based on a JSON data object.
The object should be an array with the following syntax:
`[[rule, node, value], [rule, node, value], ...]`

**Example:**

```JSON
[
  ['top': 'header', 50],
  ['bottom': 'footer', 50],
  ['fill', 'content']
]
```

**Params**

- data `Object` - JSON object  

<a name="module_LayoutDockHelper#top"></a>
###layoutDockHelper.top([node], [height])
Dock the node to the top.

**Params**

- \[node\] `LayoutNode` | `String` - layout-node to dock  
- \[height\] `Number` - height of the layout-node, when ommited the height of the node is used  

**Returns**: `LayoutDockHelper` - this  
<a name="module_LayoutDockHelper#left"></a>
###layoutDockHelper.left([node], [width])
Dock the node to the left

**Params**

- \[node\] `LayoutNode` | `String` - layout-node to dock  
- \[width\] `Number` - width of the layout-node, when ommited the width of the node is used  

**Returns**: `LayoutDockHelper` - this  
<a name="module_LayoutDockHelper#bottom"></a>
###layoutDockHelper.bottom([node], [height])
Dock the node to the bottom

**Params**

- \[node\] `LayoutNode` | `String` - layout-node to dock  
- \[height\] `Number` - height of the layout-node, when ommited the height of the node is used  

**Returns**: `LayoutDockHelper` - this  
<a name="module_LayoutDockHelper#right"></a>
###layoutDockHelper.right([node], [width])
Dock the node to the right.

**Params**

- \[node\] `LayoutNode` | `String` - layout-node to dock  
- \[width\] `Number` - width of the layout-node, when ommited the width of the node is used  

**Returns**: `LayoutDockHelper` - this  
<a name="module_LayoutDockHelper#fill"></a>
###layoutDockHelper.fill(node)
Fills the node to the remaining content.

**Params**

- node `LayoutNode` | `String` - layout-node to dock  

**Returns**: `LayoutDockHelper` - this  
