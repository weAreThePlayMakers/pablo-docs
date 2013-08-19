--- 
category: api
heading: Collections
---

When creating elements, or selecting SVG and HTML content from the page, Pablo encloses these elements inside an [array][array]-like "collection". Elements are usually manipulated and filtered via the methods on the collection object, though the elements are also available to work with directly.

Methods are generally chainable:

    /* Wrap an HTML element */
    Pablo(demoElement)
        // Append an <svg> element
        .svg({width:140, height:140})
        // Append a <rect> to the <svg>
        .rect({width:100, height:100})
        // Transform the rect
        .transform('translate', 70)
        .transform('rotate', 45);


Many methods can both read and write changes to SVG elements:

    var shape = Pablo(demoElement)
              .svg({width:120, height:120})
              .rect({width:100, height:100})

    // Set an attribute
    shape.attr('fill', 'purple');

    // Get the attribute
    alert(shape.attr('fill'));


[array]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array