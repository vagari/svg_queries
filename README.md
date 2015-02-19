svg_queries
===========

### Playing with SVG and modifying elements internally when presented with media queries.

[Joe Harrison's][joe] [Responsive Logos][resplogos] is an interesting experiment involving SVG sprites and a responsive layout. Related to his [Responsive Icons Project][rip] it demonstrates how a logo might change at different screen sizes. Elements adjusting and shrinking to fit the space. 

Recently there was a project at work that included multiple product logos. Each logo was spit out as an SVG and depending on destination the only difference was a single color. The source is an Illustrator file with multiple artboards containing each logo variation. 

Working with those files and visiting Joe's experiment led to a few questions rolling around the ole noggin. 

Questions like:

* Are there alternatives that don't simply recreate a raster sprite sheet as a vector one?
* How much would that reduce filesize?
* What built in features can be used to minimize code even more? Will they work across browsers?
* How much work is involved after exporting an image from a graphics program?

Originally the plan was to share this via my web site... But cleaning that up would be a project in itself. Then [I tried Codepen][penver] but even though it works I'd like to avoid using inline SVG. Thus GitHub seems the best solution. 

[joe]:http://www.joeharrison.co.uk/
[resplogos]:http://www.responsivelogos.co.uk/
[rip]:http://www.joeharrison.co.uk/projects/responsiveicons
[penver]:http://codepen.io/vagari/pen/oiGdy

### The result?

By using the `object` element and modifying the underlying `svg` code it **is** definitely possible to shrink file size, reduce elements, and still function in `svg` compatible browsers. 

Considering the logo variations mostly involve removing elements it began with organizing elements and toggling them with CSS. Similar to [Jason Grigsby's, _Media Queries in SVG images_][jg]. But one thing that Joe did was switch to a larger, simpler graphic once a size had been reached. To emulate that required a bit of math and a combo of [`defs`][jjdef] and [transforms][jjtransform]. Specifically taking the harp and repositioning it, along with enlarging it, via [matrix][somatrix]. 


[somatrix]:http://stackoverflow.com/questions/6711610/how-to-set-transform-origin-in-svg (coordinate transformation - How to set transform origin in SVG - Stack Overflow)
[jjtransform]: http://tutorials.jenkov.com/svg/svg-transformation.html (SVG Transformation)
[jjdef]:http://tutorials.jenkov.com/svg/defs-element.html (SVG defs Elements)
[jg]:http://blog.cloudfour.com/media-queries-in-svg-images/
