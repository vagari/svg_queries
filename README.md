svg_queries
===========

### Playing with SVG and modifying elements internally when presented with media queries.

[Joe Harrison's][joe] [Responsive Logos][resplogos] is an interesting experiment involving SVG sprites and a responsive layout. Related to his [Responsive Icons Project][rip] it demonstrates how a logo might change at different screen sizes. Elements adjusting and shrinking to fit the space. 

Recently there was a project at work that included multiple product logos. Each logo was spit out as an SVG and depending on destination the only difference was a single color. The source is an Illustrator file with multiple artboards containing each logo varition. 

Working with those files and visiting Joe's experiment led to a few questions rolling around the ole knoggin. 

Questions like:

* Are there alternatives that don't simply recreate a raster sprite sheet as a vector one?
* How much would that reduce filesize?
* What built in features can be used to minimize code even more? Will they work across browsers?
* How much work is involved after exporting an image from a grpahics program?

Originally the plan was to share this via my web site... But cleaning that up would be a project in itself. Then [I tried Codepen][penver] but even though it works I'd like to avoid using inline SVG. Thus GitHub seems the best solution. 


[joe]:http://www.joeharrison.co.uk/
[resplogos]:http://www.responsivelogos.co.uk/
[rip]:http://www.joeharrison.co.uk/projects/responsiveicons
[penver]:http://codepen.io/vagari/pen/oiGdy