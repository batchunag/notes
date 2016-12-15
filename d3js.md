#number formatting in c3 generate
if (index==="rate") axis_y.tick = {format: d3.format(".1f")};
[for more](http://c3js.org/gettingstarted.html)

#Features
http://www.coppelia.io/2014/07/an-a-to-z-of-extra-features-for-the-d3-force-layout/

#Fix node coordinate
root = node[0][0];
root = d3.select(root).select("circle")[0][0];
console.log(root);
root.cx = width / 2;
root.cy = height / 2;