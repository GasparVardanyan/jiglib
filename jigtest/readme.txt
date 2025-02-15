Testbed for jiglib - written by Danny Chapman 2005 
http://www.rowlhouse.co.uk
danny@rowlhouse.freeserve.co.uk

Either run jigtest-release.exe directly, or use one of the batch files that select a different config file.

Note - if there's a jigtest-opt.exe file, then it's been compiled to use SSE2 - if it runs it may well run significantly (20%) faster than the bog-standard jigtest.exe, so IF it works, I suggest you replace jigtest.exe with jigtest-opt.exe.

Keys:

'F1': Dumps a screenshot in ppm format (OK in Paint shop Pro, not in photoshop?!)
'F2': Dumps a screenshot every 2 physics steps (by default - see config file) for movie generation
't':  Resets everything
'y':  Removes all physical objects
'\':  Create a ragdoll
'/':  Create a compound object
'z':  Create a sphere
'x':  Create a box
'n':  Create a capsule
'c':  Create a car (first car is under human control)
'm':  Create a first-person character (very primitive movement etc for now)
'ARROWS': Control the first car or the current object (if no car)
'k':  toggle rendering collision/contact points
'b':  toggle rendering AA bounding boxes
'v':  toggle viewing sleeping objects transparent
'wasdqe': move camera
'1':  toggle fixed/follow camera
'h':  toggle the physics "shock" step
'p':  toggle pausing the physics
'o':  pause and single step the physics
'r':	toggle rendering updates 
'f':	toggle the freezing algorithm
'='/'-'	select the next/previous object as a camera target
'SPACE' takes the object the camera is focussed on and shoots it
'PAGEUP/PAGEDOWN' increase/decrease the texturing etc
'ESC'	Quit

Pressing control when you create an object shoots it from the camera. Otherwise 
it gets created in its default location (specified in the config file)

You can select objects with the left mouse button. Right mouse button picks objects up (and 
freezes the camera) - you can move the object towards/away from the camera with the mouse wheel.
Pressing the mouse wheel fires the object from where it is. Note that picking an object doesn't
actually select it.

Lots of stuff can be configured by editing jigtest.cfg (or the config file matching the 
batch file) with a text editor.

The meshes are in the xml format that is generated by the Ogre3D plugin for the free-to-use 
DeleD editor.

TODO:

- Swept tests for collision detection (currently only sphere/box/capsule against mesh implemented)

- Better solver for contacts with multiple points

- Support other integration methods (more than just Euler)

- general collision detection speedups

- contact groups

- render more stuff as debug output - not (just) in console either!

- cylinder collision primitive, and non-static meshes

- sweep'n'prune (or something like that) rather than N^2 collision detection

Notes on the jigtest code:

"framework" stuff, that could be lifted out and put into any jiglib
project, lives in framework. Probably end up in JigUtilsLib one day...

"application" stuff lives in application.

Building jiglib requires just standard C++. The test framework requires OpenGL, 
SDL and libpng and libxml2

--------------------------------


