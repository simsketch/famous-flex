<a name="module_NavBarLayout"></a>
#NavBarLayout
Navigation-bar layout consisting of optionaly left and right items and a
title in the middle.

When no item-width is specified, the width of the renderable itsself is used.

|options|type|description|
|---|---|---|
|`[margins]`|Margins|Margins to use (see Margins)|
|`[itemWidth]`|Number|Width of the left & right items|
|`[leftItemWidth]`|Number|Width of the left items|
|`[rightItemWidth]`|Number|Width of the right items|
|`[itemSpacer]`|Number|Space in between items|

Example:

```javascript
var NavBarLayout = require('famous-flex/layouts/NavBarLayout');

new LayoutController({
  layout: NavBarLayout,
  layoutOptions: {
    margins: [5, 5, 5, 5], // margins to utilize
    itemSpacer: 10,        // space in between items
  },
  dataSource: {
    background: new Surface({properties: {backgroundColor: 'black'}}),
    title: new Surface({content: 'My title'}),
    leftItems:[
      new Surface({content: 'left1'})
    ],
    rightItems: [
      new Surface({content: 'rght1'}),
      new Surface({content: 'rght2'})
    ]
  }
})
```

