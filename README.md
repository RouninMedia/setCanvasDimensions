# setCanvasDimensions
*A helper function which initialises an HTML `<canvas>` element's `height` and `width` attributes after parsing CSS*

## JavaScript
```js
const setCanvasDimensions = (canvas) => {
  canvas.setAttribute('width', window.getComputedStyle(canvas).width.replace('px', ''));
  canvas.setAttribute('height', window.getComputedStyle(canvas).height.replace('px', ''));
}

let myCanvas = document.querySelector('canvas');
setCanvasDimensions(myCanvas); // <= INITIALISES CANVAS DIMENSIONS

let ctx = myCanvas.getContext('2d');
ctx.fillStyle = 'rgb(255, 127, 0)';
ctx.fillRect(0, 0, 200, 100);

[...]
```
