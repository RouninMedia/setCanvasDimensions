# setCanvasDimensions
*A helper function which initialises an HTML `<canvas>` element's `height` and `width` attributes after parsing CSS*

Unusually for an HTML element, `<canvas>` ***must*** have its `width` and `height` attributes declared explicitly in its markup or else it will default to:

 - `width="300"`
 - `height="150"`

**MDN** explains:

> ### Sizing the canvas using CSS versus HTML

> The displayed size of the canvas can be changed using CSS, but if you do this the image is scaled during rendering to fit the styled size, which can make
> the final graphics rendering end up being distorted.

> It is better to specify your canvas dimensions by setting the width and height attributes directly on the <canvas> elements, either directly in the HTML or 
> by using JavaScript.
  
> **Source:** https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas
  
_________

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
