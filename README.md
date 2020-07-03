# remove-drag-ghosting
Remove drag ghost

# Demo

[online](https://bojue.github.io/remove-drag-ghosting)

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
dragDom.addEventListener('mouseenter', drag);
dragDom.addEventListener('dragstart', drag);
dragDom.addEventListener('drag', drag);

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