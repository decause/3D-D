3D-D
====

This repository mostly just contains files created and generated during my
initial attempts to 3D print a version of my gravatar on a Lulzbot TAZ 3:
http://lulzbot.com


First Flight
=====

[Inkscape] (http://inkscape.org)
-----

 - import .svg version of gravatar
 - convert each object to a path
 - 'Union' all the paths
 - save result as a .dxf
 - create a box slightly larger than gravatar
 - convert to a path
 - save result as a .dxf
 - BONUS: I exported in `UTF8` and clicked the `gcode friendly` option when
   saving.

[OpenSCAD] (http://openscad.org)
-----

 - Using this tutorial
   http://repraprip.blogspot.com/2011/05/inkscape-to-openscad-dxf-tutorial.html
   I was able to discern the best methods for using my weapon of choice
   (inkscape) as a starting point. 

 - Praux-Tip: Use the preferred child() import method (listed in the comments)
   to import files, like so:

```
linear_extrude(height = 1.5) import("/home/decause/inkscapes/pixelremy_3D_nomouth_small_final.dxf");
linear_extrude(height = .5) import("/home/decause/inkscapes/pixelremy_3D_boxonly_final.dxf");
```

 - Once objects are loaded, Press `F6` to compile and build the model
 - After all is compiled and rendered, click `export` and save the result as a
   `.stl` file

[Slic3r] (http://slic3r.org)
-----

Not knowing anybetter, I opened the `.stl` file in Pronterface, which looked
like it was going to work, but then totally "phantom printed" (Meaning, traced
all the paths without extruding any filament)


 - press `add` button to open `.stl` file in slic3r 
 - press `Export G-code...` button on the right 

[Pronterface] (https://github.com/kliment/Printrun)
-----

 - Set extruder and bed temps appropriately
 - click `load` button and open your `.gcode` file
 - BONUS: Use `Tools -> Plater` option to position model
 - click `print` button, and actually have enough filament to complete the job
