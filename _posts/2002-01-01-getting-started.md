--- 
heading: Getting started
category: overview
---


Either [download the code](#download) or clone the repo:
`git clone git://github.com/dharmafly/pablo.git`

Include the minified script in your HTML:

	<script src="pablo.min.js"></script>


Start drawing with Pablo:
	
	<script>
	// Check browser support
	if (Pablo.isSupported){
		// Wrap an HTML container element (or CSS selector, array or nodeList)
		Pablo(htmlElement)
			// Create an SVG root element
			.root({height:60})
			// Draw something
			.circle({cx:30, cy:30, r:30});
	}
	</script>

The rest is just details...