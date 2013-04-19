--- 
category: select
heading: select(fn, [ctx])
---

Passes each element in the collection through an iterator function, returning a new collection of all the elements for which the iterator returns true. The iterator is passed two arguments: the element and its index.

The context of the callback function is that of the collection unless specified otherwise as the `ctx` argument.

*Note: This method is analgous to `Array.filter` and `Underscore.select`. It is not called `.filter()` because that method already exists - it creates an SVG `<filter>` element.*

    var col           = Pablo(),
        consideredBig = 30, // try changing this
        filtered;

    col.push(Pablo.circle({r: 40, cx: 40,  cy: 70, fill: 'red'}));
    col.push(Pablo.circle({r: 20, cx: 100, cy: 70, fill: 'green'}));
    col.push(Pablo.circle({r: 50, cx: 170, cy: 70, fill: 'blue'}));
    col.push(Pablo.circle({r: 60, cx: 280, cy: 70, fill: 'cyan'}));
    col.push(Pablo.circle({r: 30, cx: 370, cy: 70, fill: 'purple'}));

    // Select only the big circles
    filtered = col.select(function (elem) {
      if (Pablo(elem).attr('r') >= consideredBig){
        return true;
      }
    });

    Pablo(demoElement).svg({height: 140}).append(filtered);