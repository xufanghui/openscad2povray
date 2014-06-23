# openscad2povray

OpenSCAD2POV-Ray is a OpenSCAD library that allows you to convert OpenSCAD scripts to POV-Ray scripts. 

## Setups:


### Direct wrapper function substitutions
* Advantage: 
 * custom colors
 * custom textures could be possible too
* Disadvantage
 * Limited support for alternative parameters specification
* Examples:
 * module 'test1()' and module 'test2()' in povray.scad

### Include OpenSCAD CSG file 
* Advantage
 * 'mirror' supported
* Disadvantage
 * Extra step of export of CSG file
* Examples
 * radial6 from thingiverse 
  * preview model radial6.scad 
  * export as CSG -> radial6.csg
  * subsitute $(\s*)([a-z]) by $1_$2 -> radial6.pov.csg
  * create radial6.pov.scad
   * use <povray.scad>
   * pov_init();
   * openscad_background();
   * openscad_camera(type="perspective", distance=500, width= 16, heigth= 9);
   * openscad_light_source();
   * include <radial6.pov.csg>
  * preview model radial6.pov.scad
  * copy & paste all ECHO POVRAY lines (use right mouse click) -> radial6.pov
  * remove ECHO: "POVRAY: and trailing "
  * render in POV-Ray

