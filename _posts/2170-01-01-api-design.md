--- 
heading: API design
category: api
---

Pablo provides methods like `circle()` and `line()` to create each kind of SVG element. It has methods for manipulating SVG and HTML, to change the appearance, size, position or some other property. It also has methods for filtering and sorting the elements. It has a simple plugin system, allowing new functionality to be added.

Using Pablo is to use SVG, so a growing knowledge of SVG goes hand-in-hand with using the library. See the [Resources][resources] page for links and books on SVG.


## Pablo Collections

When creating elements, or selecting SVG and HTML content from the page, Pablo encloses these elements inside an [array][array]-like "collection". Elements are usually manipulated and filtered via the methods on the collection object, though the elements are also available to work with directly.

Methods are generally chainable:

    var shape = Pablo.rect({width:100, height:100})
                     .attr('stroke', 'red')
                     .appendTo(demoElement);

Many methods can both read and write changes to SVG elements:

    var shape = Pablo.rect({width:100, height:100})
                     .appendTo(demoElement);

    shape.attr('fill', 'yellow');    // set the value
    alert(shape.attr('fill')); // get the value


[array]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array
[resources]: /resources/