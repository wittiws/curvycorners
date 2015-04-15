## Introduction ##

CurvyCorners now has limited support for dynamic HTML. In particular, you may change the contents of a box and have the box re-sized (re-drawn) to fit. However, because of the technique CurvyCorners uses to draw the corners, this cannot happen automatically. Instead, read on...

## First steps ##

  1. Specify the corners using the new CSS style and not the old onload-function style;
  1. Give the box elements to be re-drawn the (additional) special class-name `curvyRedraw`; and
  1. in your JavaScript, explicitly call the function `curvyCorners.redraw()`.

`curvyCorners.redraw()` takes no parameters and returns no usable value.

### Changing attributes or styling ###

If you need to change some attributes or styling of the redrawable elements, this should not be done directly through the DOM. Instead, having identified the DOM object (e.g. with `document.getElementById()`), call
```
curvyCorners.adjust(DOMObj, propertyName, newValue);
```

where:

<dl>
<dt><var>DOMObj</var></dt>
<dd>is the element object with className <code>curvyRedraw</code> that needs to be changed;</dd>
<dt><var>propertyName</var></dt>
<dd>is the name of the property without a leading dot;<br>
if it is a style property, it should be<br>
expressed as <code>'style.property'</code>.</dd>
<dt><var>newValue</var></dt>
<dd>is the new value, e.g. <code>'none'</code>.</dd>
</dl>

`curvyCorners.adjust()` must take all three parameters described above. It returns no useful value.

An extensive example of this technique is contained in
<a href='http://www.curvycorners.net/includes/examples/demo5.html'>demo<br>
5</a>.

## Handling window resize events ##

CurvyCorners supports redrawing curved boxes in response to a change in the browser window size. If you wish to take advantage of this, you can add an event handler to trigger a redraw. However, some DOM changes will fire spurious window resize events in some browsers. These can happen in the midst of DOM changes (including those that CurvyCorners itself makes whilst redrawing). Therefore, do _not_ make your handler call `curvyCorners.redraw()` directly. Instead, set your resize handler function to call `curvyCorners.handleWinResize()`.

Next, if you find that some of your code is triggering window resize events (which will cause a noticeable delay!), surround the code with:

```
curvyCorners.setWinResize(false); // block redraw on resize
 // ... your DOM-manipulating code here
curvyCorners.setWinResize(true); // re-enable redraws on window resize
```

An example of this technique is contained in [demo 5](http://www.curvycorners.net/includes/examples/demo5.html).