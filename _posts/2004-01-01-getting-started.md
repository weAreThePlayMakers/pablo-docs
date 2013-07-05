--- 
category: overview
heading: Getting started
---

Download either the <a href="http://pablojs.com/downloads/pablo.js" target="_blank">full script</a> for development or the <a href="http://pablojs.com/downloads/pablo.min.js" target="_blank">minified script</a> for production and reference it in your web page's HTML:

    <script src="pablo.min.js"></script>

Check that the browser supports basic SVG <a id="has-browser-support" href="http://caniuse.com/#search=svg" target="_blank"> </a>:  
_Click the 'Run' button_

    if (Pablo.isSupported){
        alert('Yes!');
        /* Put Pablo-dependent code here */
    }
    else {
        alert("Noo");
        /* Fallback content */
    }

<script>
    if ('addEventListener' in document){
        document.addEventListener('DOMContentLoaded', function(){
            isSupportedText = Pablo.isSupported ? ' (yours does)' : "yours doesn't";
            document.getElementById('has-browser-support').textContent = isSupportedText;
        }, false);
    }
</script>

_Note: in this documentation, all code snippets with 'Run' buttons are editable (except on mobiles)_.

Start drawing:

    /* Inside an HTML element, append an <svg> root */
    Pablo(demoElement).svg({height:200})
        /* Create <circle> element, with attributes */
        .circle({cx:90, cy:90, r:90, fill:'blue'})
        /* Add a click listener */
        .on('click', function(el){
            Pablo(this).attr('fill', 'red');
        });

<div class="showhide">
Something a bit more ambitious... (<span class="showhide-control">show</span>)
<div class="showhide-content">
<pre><code>/* Inside an HTML element, append an &lt;svg> root */
var paper = Pablo(demoElement).svg({height:220}),
/* Create &lt;circle> element, with attributes */
circle = paper.circle({
    cy: '50%',
    fill: 'rgba(127, 159, 95, 0.2)',
    stroke: '#777'
});

/* Duplicate the element */
circle.duplicate(20)
/* Modify attributes */
.attr({
    /* Attribute functions, called for each element */
    cx: function(el, i) {return i * 4 + 1 + '%'},
    r:  function(el, i) {return i + 1 + '%'}
})
/* Add a listener for mouseover &amp; touchstart events */
.on('mouseover touchstart', function(){
    /* Wrap this element in a Pablo collection */
    var circle = Pablo(this),
        /* Create a random position and colour */
        r = parseInt(circle.attr('r'), 10),
        xMax = 100 - r * 2,
        cx = xMax * Math.random() + r + '%',
        hue = Math.random() * 360,
        color = 'hsla(' + hue + ', 90%, 50%, 0.2)';

    / * Apply new attributes to the &lt;circle> element */
    circle.attr({cx:cx, fill:color});
});</pre></code>
</div>
</div>

**See the [API Reference][api] for full details.**

<script>
    if ('addEventListener' in document){
        document.addEventListener('DOMContentLoaded', function(){
            var jQuery = satya.jQuery;
            jQuery('.showhide').each(function(i, el){
                var container = jQuery(el),
                    control = ('.showhide-control', container),
                    content = ('.showhide-content', container),
                    hidden  = control.text() === 'show';

                if (hidden){
                    content.hide();
                }

                control.toggle(function(){
                    hidden = !hidden;
                    if (hidden){
                        content.hide();
                        control.text('show');
                    }
                    else {
                        content.show();
                        control.text('hide');
                    }
                });
            });
        }, false);
    }
</script>


[pablo-site]: http://pablojs.com
[api]: http://pablojs.com/api/