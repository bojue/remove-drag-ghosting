# remove-drag-ghosting
Remove drag ghost，消除拖拽鬼影

## 在线预览

[预览](https://bojue.github.io/remove-drag-ghosting)

## 使用

1. npm install

```
npm install remove-drag-ghosting

import removeGhosting from 'remove-drag-ghosting';
```

2. function

```javascript

function removeGhosting(event) {
    if(!(event instanceof MouseEvent)) {
        console.info("Parameters must be of type MouseEvent!")
        return;
    }
    let dragIcon = document.createElement('img');
    dragIcon.src = 'data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7',
    dragIcon.width = 0;
    dragIcon.height = 0;
    dragIcon.opacity = 0;
    if(event.dataTransfer) {
        event.dataTransfer.setDragImage(dragIcon,0, 0);
    }
}
```
