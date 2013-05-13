--- 
heading: nextSiblings([selector/fn/element])
category: nextSiblings
---

Returns a collection of all the collection’s siblings after it in the DOM.

    var paper = Pablo(demoElement).svg({height: 60});

    paper.append(Pablo.circle({r: 30, cx: 30, cy: 30}))
         .append(Pablo.circle({r: 30, cx: 100, cy: 30, fill:'green'}))
         .append(Pablo.circle({r: 30, cx: 170, cy: 30}))
         .append(Pablo.circle({r: 30, cx: 240, cy: 30}));

    paper.children('circle[fill=green]')
         .nextSiblings()
         .attr({'fill': 'purple'})