# remove-drag-ghosting
Remove drag ghost

<a href="https://www.npmjs.com/remove-drag-ghosting" target="_blank"><img src="https://img.shields.io/npm/v/remove-drag-ghosting.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/remove-drag-ghosting" target="_blank"><img src="https://img.shields.io/npm/l/remove-drag-ghosting.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/remove-drag-ghosting" target="_blank"><img src="https://img.shields.io/npm/dm/remove-drag-ghosting.svg" alt="NPM Downloads" /></a>

# Demo

[Online](https://bojue.github.io/remove-drag-ghosting)

![Demo](demo.png)

## Use

- npm 

```
// npm install 
npm install remove-drag-ghosting

// javascript
import removeGhosting from 'remove-drag-ghosting';

drag(event) {
    removeGhosting(event);
}
```

- function

```javascript

// html 

<img id="dragElement" src="./kakaxi.jpg" draggable="true">

// javascript
let dragDom = document.getElementById('dragElement'); //dragElement
dragDom.addEventListener('mouseenter', removeGhosting);
dragDom.addEventListener('dragstart', removeGhosting);
dragDom.addEventListener('drag', removeGhosting);

function removeGhosting(event) {
    if(!(event instanceof MouseEvent)) {
        console.info("Parameters must be of type MouseEvent!")
        return;
    }
    let dragIcon = document.createElement('img');
    let url = 'data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7';
    dragIcon.src = url;
    dragIcon.width = 0;
    dragIcon.height = 0;
    dragIcon.opacity = 0;
    if(event.dataTransfer) {
        event.dataTransfer.setDragImage(dragIcon,0, 0);
    }
}
```
## License

[MIT](https://opensource.org/licenses/MIT)
