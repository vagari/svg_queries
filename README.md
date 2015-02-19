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

By using the `object` element and modifying the underlying `svg` code it _is_ definitely possible to shrink file size, reduce elements, and still function in `svg` compatible browsers. 

Considering the logo variations mostly involve removing elements it began with organizing elements and toggling them with CSS. Similar to an example in [Jason Grigsby's _Media Queries in SVG images_][jg] objects appear/disappear as the viewport changes. One thing that's a little more complicated with the simplified version is adjusting element sizes to maximize space and keep things centered. It requires a bit of math and a combo of [`defs`][jjdef] and [transforms][jjtransform]. In this case specifically, taking the harp and repositioning/enlarging it via a [matrix][somatrix]. 

### And those questions? 

Well we know there's an alternative. How about the rest of the pieces? Filesize is definitely reduced. Though that is not too difficult to believe. We're stripping redundant elements and pulling out their relevant code. In the case of the Guinness logo the original file is 37 KB. The new file clocks in at 13 KB, 35% of the original. As mentioned using the `defs` and `use` features of `svg` elements can be reused. The only difficult part is that there can be a lot of extra work after exporting the graphic. 


[somatrix]:http://stackoverflow.com/questions/6711610/how-to-set-transform-origin-in-svg (coordinate transformation - How to set transform origin in SVG - Stack Overflow)
[jjtransform]: http://tutorials.jenkov.com/svg/svg-transformation.html (SVG Transformation)
[jjdef]:http://tutorials.jenkov.com/svg/defs-element.html (SVG defs Elements)
[jg]:http://blog.cloudfour.com/media-queries-in-svg-images/
