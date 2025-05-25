  * threejs notes to review and see if keep and how to organize
    * Dec 2024: what webGL, why are shaders boss, webGL complexxx #[[fast memo]]
      * webGL: rendering bunch of triangles on ur GPU very quickly. iz api. Web Graphics Library
      * SHADERS ARE BOSS: the CPU/GPU instructions for position and color of each point on screen (pixel) are INSIDE shaders
      * drawing a single triangle on canvas would take at least 100 lines of code on ur own (in webGL...threejs fixed dis)
    * [[2025-01-19]] 2 pieces to a three mesh, rotate issue and value for HALF rotation, position length, position normalize #[[fast memo]]
      * 2 pieces to make a mesh: 1) the geometry object 2) the material object
      * rotations
        * ROTATE ISSUES: if you run into issue when doing more than 1 differing-axis rotation, you may need to set the order (can just google method or look at Bruno tuts). You can prioritize one axis over another. Like FPS char needs to rotate on y before on x
        * PI = HALF ROTATE: using Math.pi to set a rotation axis will rotate by HALF a rotation exactly...which is 180 degrees
      * POSITION LENGTH: position object has length value that tells distance from object to center of scene. Also has distanceTo method for telling distance from object to something passed in like camera
      * POSITION NORMALIZE: position object has normalize method that will transform distance of object to center of scene to exactly 1 which is pretty cool. This will literally move object closer to center of scene. Q: so if you have an object at distance of 5 and object right behind it at distance of 7, will they end up in same exact spot after normalized? A: yes, if they really are along same direction
    * [[2025-01-20]] three FPS issue, anim libraries, Camera, y-axis in three, controls in three #[[fast memo]]
      * DIFF FPS ISSUE: by default if you use a tick method with window.requestAnimationFrame(tick) inside of it - objects will transform differently for diff FPS each user's hardware has. there are few diff fixes for this:
        * 1: get time at start of tick method. get time at end tick method. subtract them to get deltaTime and then multiply transformations of meshes by this deltaTime. it makes FPS same/sync despite actual FPS of each device...ACTUALLY: it just changes WORLD-movement/change-amounts to make VISUALS APPEAR same on all devices - FPS doesnt actually change on devices
          * deltaTime: which represents the time it took to render and update one frame. time-chunk/wavelength/bit-period/deltaTime (diff for each device)
          * **Frame Independent Movement:** This technique decouples the SPEED of your game world from the frame rate, providing a consistent gameplay experience regardless of whether the game runs at 30 FPS, 60 FPS, or any other rate.
          * me: interesting, iz like gameworld moves things/changes at diff speeds for each person, but they appear about the same thanks to deltaTime applied to changes that syncs things
          * NOTE: sometimes gotta do the fixedUpdate and fixedTimestep way instead when need more precise consistency of variable values - like physics. Need CHANGE of rate of change to be consistent and deltaTime doesnt allow that
          * **sync between devices**:
            * On a device with high FPS, deltaTime will be SMALL, so even though there are more updates per second, each update applies less CHANGE (to whatever is being transformed/modified), keeping the overall effect consistent.
            * On a device with lower FPS, deltaTime will be LARGER, so each update applies more CHANGE, compensating for the fewer updates per second.
          * Q: is deltaTime how most games sync diff devices up? even big games? grok2: yes. it decouples changes of gameworld from FPS of devices
        * 2: THREE.Clock
      * CHOOSING ANIM LIB: there's external libraries that are good at animation (like GreenSock). They even have their own internal tick, so you dont have to put them inside your tick. Sounds like can just animate using your own code/tick for simple stuff, but then external are mostly needed for more complex stuff like player swinging sword
      * PerspectiveCamera
        * FoV: first arg is FoV VERTICALLY. A small FoV will: make things look BIGGER and vice versa. meme: gamerz use bigger FoV to catch as much detail as possible and bc they gud and can precisely target small details
        * ASPECT RATIO: 2nd arg is aspect ratio which is cam width / cam height
        * NEAR and FAR: next 2 args are those. Anything less than "near" the cam doesnt see; anything more than "far" cam doesnt see (i think they literally dont get rendered - good for performance)
      * OrthoCamera: not too much memo, but if you use it and have issue with things being mis-shaped iz prob bc canvas is rectangle and cam is square. Fix explained in this tut and can return to it if needed.
      * Y-AXIS in THREE: in THREE, y-axis is 0 at bottom and positive at top - the OPPOSITE of how DOM works (which is where you can get stuff like mouseX and Y - so can be confusions with those 2)
      * CONTROLS in THREE: these are classes in three that make easy to do specific types of transforms of CAMERA. Search control in three docs to see all.
        * PointerLockControls is one im familar with from three FPS example. Bruno doesnt recommend bc getting and locking mouse movement with JS is easy. it seems PointerLockControls just uses "pointer lock JS API" and he recommends just using the API directly.
        * OrbitControls: just like Needle scene where can just orbit some island. This has vertical limit tho. TrackballControls is basically same except without limit.
        * CONTROLS NOT ALWAYS ABOUT CAMERA: TransformControls basically let you create an editor like in Blender...neat. DragControls is same - you can drag objects on a PLANE PERP to you/view lineOfSight.
        * me: can import these from three examples path - which imo is in path like that to explictly allow you to use them, but signal you should prob implement yourself...and not use an example lib lol
        * after update controls, like updating the target (where camera looks), you need to call controls.update() after. Depending what doing, sometimes this can be outside your tick (updating target) and sometimes inside your tick (like damping/friction/acc of cam movement)
        * when use these controls vs your own? if you look at example of one and it does everything you need, go for it. Otherwise, just copy one and make your own
    * [[2025-02-01]] pixel ratio, geometry, mesh, material, attribute, values per vertex #[[fast memo]]
      * HOW TO MAKE CANVAS TOTALLY FILL VIEWPORT OF PAGE: just some CSS lol. if needed, can just copy style.css from fullscreen-and-resizing Bruno lesson
        * RESIZING: if user resizes window, just static CSS doesnt work to fill viewport. Have to handle in JS. Basically anywhere sizes var were used (camera and renderer), need to be updated on resize (bc sizes var CHANGES to be new viewport width/height). ALSO: update renderer pixel ratio JUST IN CASE user moved page to new screen/device with different PR
      * ISSUE: blurry render or stairstep edges on objects. WHY? A: likely because of a device's PIXEL RATIO (also known as screen pixel density). This is ratio of software pixel to physical pixel set by device. if ratio is 1, iz obv they mapped. if 2, then 1 software pixel RENDERS 4 physical pixels. So more tough on GPU
      * Bruno: apparently phones have highest pixel ratio, but thaz just wrong and marketing. Apparently after 2, you dont even notice difference visually but will notice performance issues. DUE TO THIS: he recommends always setting renderer pixelratio to Math.min(window.devicePixelRatio, 2) - this solves the blur/stairstep issue as much as possible and avoids performance issues on phones with PR of like 5.
      * HOW TO FULLSCREEN: user trigger > call method to invoke fullscreen lol. Can find it in this Bruno lesson - i prefer to use version that works for even old browsers using webkit
      * GEOMETRIES LESSON:
      * Q: in three, what is difference in mesh and geometry?
        * attribute: a TYPE of vertex data with specific valuesPerVertex
        * Q: in threejs, is an attribute a part of a material?
          * NO, a material can use attributes INSIDE custom shaders, but it does not "contain" them - the geometry contains them. You can use attributes to define per-vertex material properties. **BUT**, standard materials like `MeshStandardMaterial` won’t use custom attributes. You need **`ShaderMaterial` or `RawShaderMaterial`** to access custom attributes INSIDE shaders. (me: it seems typically you dont do this and just use MeshStandardMaterial)
        * geometry: basically vertices. each vertex contains many ATTRIBUTES and each attribute has differing numValues per vertex (sometimes just 1, like with Particles): like position, UV, Normal, anything really. iz just data. it has visual props AS data, but those only get expressed visually through mesh meshing it with a material lol
        * mesh: COMBINES geometry with material to create VISIBLE object. mesh is the rendered entity where geo provides form and material how that form looks (color, texture, shininess, etc). meme: mesh meshes geo with material
      * my guess is ill rarely use manually created geometries like he shows off so much in tuts - id use my assets i create in blender. But note: first 3 args of BoxGeo is x,y,z and next 3 args are telling how many triangles you want basically on your shape - by defining num of subdivisions/segments. EX: if creating mountainous terrain using plane. Few subdivisions dont allow for mountains unless you want a pyramid, but more subdivisions allow more details and rounded mountains
      * HOW TO SEE TRIANGLES/VERTICES in THREE: "wireframe: true" on Material (prob some way to do for all materials at once i bet)
      * HOW TO LITERALLY MANUALLY CREATE SHAPES/geometry in THREE from the BASE/GENERAL BufferGeometry:
        * create BufferGeometry
        * define values that will go INTO each vertex. ex: defining 1s or 0s for xyz of each vertex in positionArray. Values will always be stored in Float32Array with one arg defined by how many vertices you want (but will be diff depending on attribute being created bc 1 vertex is diff sizes depending on attribute). EX: position attribute has vertex be 3 values for xyz. UV has 2 values per vertex. Particles has 1 value per vertex
        * create BufferAttribute. This takes in Float32Array attribute data and number representing values per vertex. Defined by matrix and how many values per vertex. Your job to match vertices between different attributes that have diff valuesPerVertex...if doing manually
        * geometry.setAttribute('position', positionAttribute) - this sends specificlyNamed attribute to a shader (which i guess ill learn more about that low level stuff later). You can create your own shaders, but iz confusing bc it so lowlevel...where would you even create it at??
        * INDEX BufferAttribute for PERFORMANCE: many times several faces share the same vertex. Can specify these indexed vertices instead of creating them multiple times on top of each other - gud 4 performance. Kinda complex tho and uncertain if can only do that for manually created geometries - can do for ur blender models??

    * [[2025-02-06]]
      * DEBUGGING 3JS APP WITH IN-GAME EDITOR YOU MAKE: several libs 4 creating ur own editors. Bruno teaches us lil-gui. Iz honestly so simple.
      * REPLACING GEOMETRIES AT RUNTIME: if do this, make sure to call dispose method to remove old geometries...trash collection.
      * LIKE UNIT TESTS: add lil debug tweaks/params as you go from START. youll prob not do it once in deep of code lol
