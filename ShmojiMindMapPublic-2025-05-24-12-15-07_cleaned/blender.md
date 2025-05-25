  * old notes from Evernote
    * **6 Object Visibility Modes**
      * **Wireframe** **Mode**: can see through items AND select items behind front item. Located at top right, very left of 4 buttons. Pic is sphere that is hollow
    * **0 Very Bottom Bar**
      * Tells what each button on mouse does based on what hovering over and what hotkeys being held down
    * **1 Pannels**
      * Can click button in top/bottom left of any panel to change to ANY type of pannel
      * To create a panel, right click a boundary and press split panel
      * To delete panel, right click a boundary and press join area
      * To make panel take up ENTIRE focus, hover over panel and press Ctr-Space. Press again to defocus
    * **2 Workspaces**
      * Blender has several already made for you and you can make your own
      * Each one is made for different workflows. They are groups of panels and editors
      * These are all shown on very top middle bar
      * Default is Layout workspace
    * **3 Quick Menus**
      * Press T or left click tiny arrow at top left for Quick Tools menu (has select box, move, rotate, scale, etc). Also, can use **Shift-Space** to get this same menu except at cursor location and labelled
      * Press N or left click tiny arrow at top right for additional quick settings (objects transformation data, etc)
    * **4 Pi Menus**
      * Quick wheel menus that appear around cursor after a hotkey is pressed
      * 3 options when navigating a pi menu:
      * 1) right click to cancel if you changed your mind
      * 2) press and hold hotkey to initiate pi menu, drag cursor to desired choice, then let go of hotkey to select
      * 3) let go of hotkey that initiated before moving cursor, then just use left click to select option desired
    * **5 Timeline **
      * Below viewport
      * Controls playback of your animation
    * **6 Collections**
      * Panel in very top right. Shows all objects in scene
    * **7 Properties Editor**
      * *Eventually, will probably make separate sections for each tab here, but keep general definitions here, they good*
      * Will define the tabs top to bottom:
      * Top-most tab shows info on current tool (pic of wrench and smthn)
      * There is space below ^ because next set of buttons are all properties of current SCENE
      * (Pic of backfacing camera): render tab: change render engines, sampling, engine specific props, and other settings that effect final image
      * (Pic of printer): Output tab: change resolution, framerate, file path, file type, etc
      * (Pic of stack of photos): View/Render Layer Tab: used to separate background and character passes for easy compositing after a render (no idea what any of this is)
      * (Pic of person and cone): General Scene Tab: other scene settings like active camera, units, and rigidbody settings
      * (Pic of globe): World Tab: properties of the sky and air of scene
      * There is more space under above tab, the next section is all properties of the selected object
      * (Pic of square): Object tab: basic info like location, rotation, scale, parent child relationships, visibility
      * (Pic of just wrench): Modifiers Tab: allows for powerful manipulations of objects using predefined modifiers
      * (Pic of xyz axis): Particles Tab:
      * (Pic of atom): Physics Tab:
      * (Pic of objects together): Constraints Tab: deals with relationships of objects
      * (Pic of green triangle): Mesh Data Tab: defines shape. Can manipulate vertex groups (also known as weight maps), shape/blend keys, and UV Maps
      * (Pic of sphere): Materials Tab: where you control how object is shaded during render. Effects color, shininess, roughness
      * (Pic of bulb): Lamp Props: only when lamp is selected. Control brightness, radius of light, shadows, and type of lamp
      * (Pic of camera): Camera props: only when camera is selected
      * (Pic of checkerboard): Texture Tab: not object specific.
    * **1 ---Interface---**
    * **2 ---Object Transforms---**
    * **Reset Object Back After Transform **(you changed it with move, scale, or rotate)
      * Press Alt + G to reset a move to default
      * Press Alt + R to reset a rotate "
      * Press Alt + S to reset a scale "
    * **Move Object To 3D Cursor**
      * Top left of viewport button called Object -> Snap -> Selection to Cursor OR Shift + S and use Pi Menu
    * **Use Local Axis of Selection Instead of Global XYZ**
      * Topmid of Viewport to left of pivot point -> change to Local
      * For hotkey users, press XY or Z twice after initiating transformation to change to local axis
    * **Have Items Snap Based on Position of other Items By Using Snap**
      * Topmid of viewport magnet button (OR press Shift + TAB) and then choose what it snaps to with button to right of magnet
    * **2 ---Object Transforms---**
    * **3 3D Cursor (dashed red/white circle)**
      * This is where new items spawn and things sometimes pivot around if set to
      * To put somewhere new: Shift + right click
      * To recenter: Shift + S -> cursor to world origin
      * CHANGE PIVOT POINT(what selected item rotates/other around) TO 3D CURSOR: click button at topmid of viewport that has magnet to right -> select 3D cursor
    * **4 Deleting in Edit Mode**
      * Hotkey X -> dissolve options are good for getting rid of loopcuts or extra subdivisions
      * X -> edge collapse = turn two vertices into one in middle OR just collapse all into one
      * X -> edge loops (does opposite of mesh extrusion) = reduce selection geometry to next edge loop available
    * **5 Collections**
      * Same thing as layers in other software. Can nest collections
      * Any objects you add will be added to the collection currently selected at the time
      * Add/change an objects collection: select in Viewport-> right click-> move to collection (can also use M)
    * **6 Workspaces**
      * *Eventually, will probably make separate sections for each tab here, but keep general definitions here, they good*
      * **Modeling Workspace** puts you in **edit mode**. Also, can change to edit mode by pressing TAB or by changing button at top left of viewport. MW also removes timeline
      * **Sculpting Workspace** is like MW except you can create models by manipulating meshes with a brush and it puts you in **Sculpt Mode**. Sculpting is more free form method of creating models and results in higher polycounts not usable for animation, but is gr8 for starting creation process and reoptimize it later.
      * **UV Editing Workspace** is used for editing UV projection maps, which means: "i skinned this object and stretched its skin across a flat surface." Very handy for texturing objects bc textures must be 2D, but projected onto 3D object
      * **Texture Paint Workspace** lets you paint texture directly onto 3D object to be seen on UV map (opposite of UV editing).
      * **Shading Workspace** used for manipulating materials with node-based shaders. Workspace puts viewport into **LookDevMode**, showing **realtime** render of object with material (what it would look like at render). Can also activate this mode by using buttons in top right of Viewport (where Wireframe Mode is) OR press Z and use pi menu.
      * **Animation Workspace**: obvious. **Dopesheet** is where all keyframe manipulations happen. If you want to use **Graph Editor**, create new panel and choose panel type to be G.E. However, typically not needed, but can be useful (according to Blender tut guy, maybe i will form my own opinion).
      * The **Rendering Workspace** is used for testing or finalizing the output of your file. Same panel type as **Image Editor**, HOWEVER, **image selected**(by button at top) is **Render Result** which lets you use **Slots** (to compare renders. Can press N to pull them up).
      * **Compositing Workspace **is used for post-processing and after-effects that adds beautification to renders such as glow, blur, mask. Very similar to node-based shader editor. To start using, check Use Nodes at top of Viewport; this will create layer node(used to combine diff passes) and composite node(final output).
      * **Scripting Workspace **is used for code.
      * To create new workspace: add button at right-end -> set it up-> File -> Default -> Save Startup File. Now it will be in every new Blender project
    * **7 Object/Edit Mode and Meshes**
      * Mesh = defines what a shape is using vertices, edges, and faces(also called polys)
      * Non-mesh objects: armatures, curves, lattices (they have edit mode, but is different)
      * If you add object while in edit mode of object, they are grouped as one Mesh. Not the case if you add in Object Mode
      * Can edit multiple separate Meshes at once by selecting all and then going to edit mode. Will not be able to have any of 2 objects mesh data interact (like connecting vertices of 2 objects with F will not work)
      * Can **join** objects into 1 Mesh in Object Mode. Select them -> Object -> Join OR Select -> Ctrl + J
      * To **separate** some selection into a new mesh in Edit Mode, Select whatever -> Mesh -> Separate OR Select -> press P
    * **8 Selecting**
      * In edit mode, can change whether selecting vertices, edges, or faces at top left beside Edit Mode button. Can shift click to select multiple. Can press 1, 2, or 3 to change Selection Modes or Shift + 1,2,3 to select multiple
      * Can select loop of edges or faces by pressing **Alt + left click**. When selecting **face loop**, you click an edge and it selects faces **perpendicular** to that edge
    * **9 Extrude Tool**
      * In edit mode, click face and press Extrude tool in quick tools (or E)
      * If you right click to cancel extrude, it will not remove duplicate faces. Allows to create new geometry at originally selected geometry
      * If you click and drag to right the Extrude Tool icon in Quick Tools menu, you get 4 options:
      * 1: Extrude region = regular extrude
      * 2: Extrude along normals = may be prefered if selecting multiple faces pointing in different directions. Will allow to push each face outwards while still being connected to each other (great for adding layer of thickness to mesh)
      * 3: Extrude individual: helpful for allowing certain faces to extend out independently from its neighbors (like #2 except don't stay connected and will often look the same but have more faces on inside. Imagine chair example). Good for creating spikes or stylized bumps on a surface.
      * 4: Extrude to cursor: allows to extrude face(s) to wherever you left click (will still be along viewing plane). In edit mode, can use this anytime by holding control and right clicking
    * **10 Loop Cut Tool**
      * Press tool icon OR ctrl + R
      * If you use Hot Key, can use scroll wheel to change # of loopcuts
      * After creating loopcut, at bottom left of VP, a menu appears that is IMPORTANT, can edit loop cuts very precisely
    * **11 Bevel Tool**
      * Allows you to keep the realism in your hard edges (no edges are perfectly sharp, so typically want to bevel it)
      * 2 method: use bevel tool in edit mode OR use bevel modifier
      * Bevel Tool: select -> left click drag to add bevel (OR Ctrl + B)
      * As always, operator panel appears in bottom left. **Segments**: the more you have, the rounder the edges. **Profile**: changes curvature of beveled edges. **Material**: lets you choose material in Material List to color bevel area
      * Bevel Modifier: main difference is Limit Method -> it allows to limit by angle and more (ex: if angle is x, don't bevel)
    * **12 Knife Tool**
      * Used to form new edge loops and vertices
      * Edit mode -> tool -> left click drag or just tap left click to cut into meshes. To disengage knife tool drawing mode: double left click or press E. Right clicking will cancel all cuts just made. To confirm cuts press Space or Enter.
      * Good tool to cut stuff in half, except use subtool called **Bisect**. Click and drag Knife Tool Icon to access it. Operater menu options are most important.
    * **13 ---Creating Low Poly Character---**
      * Find 'character turnaround' concept, download it, and drag into Viewport. Press M on it and move to new 'background' collection. Use clear tools to put it in default positions (Alt+buttons). Scale it larger and rotate 90 degrees around X-axis. Use G to move frontview of character so it's feet are just above X-axis. Go to side view and use G along Y-axis to move concept back a bit
      * Shift + Right click on mid of concept head to move 3d-cursor. Shift+A a cube mesh. Press N and reset Location-Y to 0. Use cube mesh for everything as beginner because it has least amount of polygons
      * Duplicate background concept to use a side concept image: shift+D -> right-click -> Rotate around Z by 90. Rename collections to side and front. He moves to other side so can model from 3 Numpad side. Line side mesh with box (he uses concept looking left).
      * Now can start reshaping. Start by getting cube to be approximately same size as concept head. numpad 1 and starts scaling each axis to fit concept (uses G to move it too). Does same from numpad 3.
      * Then, make shape more accurate. Add loopcut horizontally in middle and scale out on X-axis. Top is a bit big so use Alt+Z for X-ray Mode and scale in using X-axis. Do tons of scaling and moving until you like it. Can add two more loopcuts if you want it even more accurate, but don't recommend too many loopcuts.
      * Go to object mode and numpad 3. Shift right click top of neck. Shift+A cube. Scale down, rotate, grab into position. Use Local axis to scale if needed. Go to numpad 1 -> G on X-axis to lign neck up.
      * Restart neck process except with torso. On numpad 1, add loopcut a bit above middle of cube.
      * All about simple thinking and movements
    * **13 ---Creating Low Poly Character---**
    * **14 ---Key Lessons Learned---**
      * START already using the mirror modifier
    * **14 ---Key Lessons Learned---**
    * **15 ---Shading---**
      * Used to get beautiful colors and lighting
      * (All these notes will assume you're in Shading worspace). To change materials, click Slot # dropdown. This is synced with material list in Material tab in Properties Editor. Change Slot to change material you are editing in the shader editor
      * Can replace material in current slot using material dropdown to right of Slots
      * To edit the **World Shader**, in shader Editor, change top left DD from Object to World
      * In render tab in Prop Editor, there is Render Engine tab with 3 engines: **Eevee**: blender realtime render engine that can render physically-based shaders in realtime like a Game Engine. **Cycles**: slower render engine, but more accurate lighting. **Workbench**: blender's preview render engine. Lets you quickly render preview instead of calculating all the lighting and shaders. To do this, switch Render Engine to Workbench -> Render -> Render Animation OR render viewport(regardless of engine selected): View -> Viewport Render Animation (will render exactly as you see it, which is diff than WB way that allows you to set options to change it up)
      * It is possible to have more than 1 output node, but only one can be displayed at a time (last selected)
    * **To Add Some Texture (like wood)**Drag pic into shader editor. Left click drag color output to Base Color on shader OR select both nodes -> Node -> Make Links OR " -> F
      * Ctrl + left click drag to move node **outputs** that are already connected.
      * Mute nodes so they no longer workin: Select -> Right Click -> Toggle Node Mute OR Press M
    * **15 ---Shading---**
    * **16 ---Texturing---**
      * One of tools used to fully customize your shader. A **texture** is an image or pattern used to drive certain aspect of your shader. Ex: color texture of a wall could be image of bricks. Textures get projected onto **materials**.
      * **Procedural textures**: texture created using algorithm. Can scale infinitely and more efficient in data size. In add menu of Node Editor in Shading WS, excluding Image, Environment, and IES textures--all others are procedural
    * **UV Mapping/Unwrapping **
      * Process of skinning your object onto 2D surface for texturing
      * Unwrapping: in Shading Workspace -> UV (or U hotkey) -> Unwrap -> unwraps based on **seems** you have
      * **Seems**: edge loops for Blender to cut open mesh when skinning it. UV -> mark seem
    * **16 ---Texturing---**
    * **17 ---Lighting---**
      * To see lighting, cannot be in Solid Mode, need to change to Rendered Mode (top right of VP) or use Z hotkey
      * **Point Light**: emit light in all directions with a fall-off
      * **Sun light**: emits global light from specifed vector direction regardless of where light object is located
      * **Spot light**: works how you think
      * **Area light**: like point lights except biased for certain direction, so rotation matters
      * In Cycles, can use **Emission shaders** to light up a scene. If you give object an ES, it will cast light on its environment
    * **3 Point Lighting**
      * Standard setup for lighting that has worked long time
      * Consists of 3 lights: key, fill, and rim
      * **Key**: main light. Defines light source in scene.
      * **Fill**: fills or softens the shadow that the key light casts. Usually least bright light, but very important. Keeps shadows from being too dark
      * **Rim(or back)**: cast onto back of subject. Usually the brightest light, but just gives brightness around edges of subject (an outline or rim). Helps it stand out from background
    * **17 ---Lighting---**
    * **18 ---Rendering/Render Tab---**
      * Render still image: Render->render image (F12). Render entire playback range: render->render animation (Ctrl + F12).
      * **View animation**: Render -> View Anim
      * Sampling allows you to choose how many Samples to take during render, both in viewport and at rendertime. The higher the samples, the more accurate the engine will render your shaders
      * **Film**: setting shared by all engines and used a lot. Used for **transparent **checkbox -> this replaces the sky with transparency for your output image.
      * **Simplify**: reduces subdivisions and polys at render to make run smoothly
    * **18 ---Rendering/Render Tab---**
    * **19 ---Output Tab---**
      * **Dimensions**: resolution of final output image. **Render Region **checkbox very important for rendering small region of camera. To use it, go to View -> View Regions -> Render Regions (Ctrl+B).
    * **19 ---Output Tab---**
    * ****
    * ****
    * **20 ---Rigging---**
    * ****
    * **1 General**
      * The act of assigning relationships between objects so that moving one object, moves another
      * **Pose Mode** - Where can select and transform each individual bone to deform your mesh. Adds individual bone data for inserting into keyframes (Bone data in prop editor). Edit mode just has data for entire armature..i think
      * **Weight Paint Mode** - Allows you to better control how mesh is deformed
      * **Controller** - Does not deform mesh directly, use to drive other bones in some way. Usually used to make animating easier (easier to use the rig)
    * **2 Parenting** (fundamental part of Rigging process)
      * Parent child relationship. Child inherits transformations of parent, but has its own solo transformations too. When inheriting, pivot point of child is ignored
      * ex: parenting fingers to a hand, paper/objects to a desk, or leaves to a tree
      * How to: shift + left click both objects -> right click -> Parent -> Object (or Ctrl+P). HOWEVER, important to remember to select intended parent LAST
      * Can only have one parent. However, can have **chain** of parents (grandparents?)
      * Random term: **EMPTIES**: show nothing visual, but have transformation data. Good for organization and using them as parent (Ex: parenting all desks in a class to an empty)
      * **Clear parent** (Alt+P)= gets rid of parent and returns child to before any parent tansformations. **Clear parent and keep transformations** = obvious.
    * **3 Armatures**
      * Tab = edit mode. Ctrl + TAB = Pose mode
      * Bone is made of head (large, not tip, is pivot point), body, and tail (at tip). Can choose head/tail to edit parts individually or select body for everything
      * Ctrl+P Menu gives 2 options: 1) **Connected** = moves child's head to parent's tail (gr8 for bone chains like spines) 2) **Keep offset** = acts like normal parent
      * Can create multiple bones out of one big one by selecting -> right click -> subdivide
      * Can extrude new bones from head/tail of other bones
      * Alt+P = **Disconnect** = same as keep offset and **Clear Parent** completely removes Parent
      * **Roll Tool** - Allows to rotate bone.
      * View axis of all bones: Armature tab of properties editor -> viewport display -> axes
      * In pose mode can add **keyframes**: select bone -> right click -> insert keyframe -> locrotscale
      * How to make sure **bones move character**:  in object mode -> select mesh -> shift+select armature -> parent menu -> 3 options under **Armature Deform** (**with Automatic weights** is recommended). Now, if you select mesh and go to modifiers, you see it has new Armature modifier
    * **4 Constraints**
      * Allows relationships between bones and objects
      * 2 main type of constraints: object constraints and bone constraints (can use interchangably if wanted)
      * Copy location = copies location, but ignores rotation and scale.
      * Limit = like copy except just one object using world coordinates (good for keeping monkey inside box)
      * **Tracking Constraints**: **trackTo** = can make monkey look at certain object at all times. **The rest**: same as trackTo except a little different. **clampTo**: only works with curves
    * **5 Character Rigging**
      * I Learned: can get premade meshes anywhere..I like this one: https://cloud.blender.org/p/animation-fundamentals/5d69ab4dea6789db11ee65d1. Can also use MakeHuman software
      * How to add pre-made base-human armature: Edit->Preferences->Addons-> Search Rigify(auto-rigging system)-> turn it on -> now can use add menu in Armature and there is Human option
      * Once added, go to edit mode. Change pivot point to 3D cursor so you can scale and feet of armature stay perfectly on ground. Uses collar bone to match with mesh. Delete face bones if not needed.
      * To mirror edits of bones on one side to other side: open right-viewport menu (N) -> Tool -> X-axis mirror. Adjust bones as you like
      * Why are Rigify rigs called Meta-rigs? Because they can be in between step. You can use them as your rig or as step to help generate BETTER rig. To generate better rig, do not delete any essential bones (ones used in **basic** human rig) -> go to **armature data tab** -> scroll down and **click generate rig** -> still need to parent mesh and to rig.
      * MY THOUGHTS: seems generated rig is PERFECT for quick rigging (which is PERFECT for me who cares not much about details of rigging)
      * After parenting mesh to generated rig: you notice you cannot rotate arms or legs in pose mode. This has to do with Inverse Kinematics (IK) and Forward Kinematics (FK). Your rig has two way of moving arms and legs: IK and FK; you can  choose the behavior using the IK/FK slider on the N properties panel. (Rig Main Props->IK-FK slider..all the way left for IK..and right for FK). Make sure Rig Layers section below this has correct layers enabled.
    * **6 Difference in IK and FK**:
      * **What is Inverse Kinematics?**
      * There are two main ways to pose a chain of bones:
      * *"Forward Kinematics" (FK)* is the normal way of manipulating a bone chain, based on parent-child relationships. You need to rotate each bone individually. Parents influence child(forward) bones
      * *Inverse Kinematics (IK)* is another way, where the movement of the chain is determined by a "target" bone (and optionally a "pole  target" bone) instead of the normal parent-child relationships. Child bone can influence parents, unlike with FK. Basically you position the end of the chain, and the IK solver calculates what the rest of the bones need to do in order to make that happen.
      * Use auto-IK: select bone -> N -> Tool -> auto IK (good for moving arm). Doesn't give full control in pose mode and doesn't work for animation (it does, but not good)
      * IK Bone Constraint (better control): Pose Mode -> select forearm bone -> add IK bone constraint. Make target the hand bone. This gets complicated, just use this vid if needed: https://www.youtube.com/watch?v=S-2v_CKmVE8&list=WL&index=4&t=1s
      * **Why do we need the Inverse Kinematic constraint in rigging?**
      * We don't need it, it just makes life easier. Often *much* easier.
      * **When should I use it?**
      * In every situation where you need the end of the bone chain to be in a  specific place - like characters grabbing something, or the foot on the  floor while walking. I read that IK is not used for animation itself, but as an animation TOOL..so sounds not needed, but may help when lots of joints.
      * **What does it do to the armature?**
      * Rotates the bones of the chain into position according to the two control bones (target, pole).
    * ****
    * **20 ---Rigging---**

  * tracking learnings on viewport options
    * [[2025-01-28]] Blender Low Poly Landscapes chapter 1 #[[fast memo]]
      * CENTER the spot YOU/view pivot around so it be center of whatever is selected: View > frame selected. So if multiple objects, will be center of ALL. This also solves issue of when you cant mouse-scroll-wheel at normal speeds or you shifted away lol
      * PERFECT ORTHO VIEWPOINTS: since i have no numpad, you can get different views like front, back top, left, etc with: View > Viewpoint. OR can just click on the axis viewpoint you want in top-right
      * WHERE FRONT: can know you are looking at front of objects by: POS Y going away from you and X going across perp to you. meme: y u goin away + X is perp since no longer seeing them
      * REALLY USEFUL FOR ALIGNING OBJECTS: switching from perspective to orthographic/isometric. Can do this in View menu OR just click bottom-most button right under axis at top-right of VP. NOTE: when you go to a perfect viewpoint like top, front, left - it default puts you in orthographic mode. EDIT: Grant Abit said isometric, but thaz actually diff than orthographic that Blender uses. wont memo details lol. Just know iz KiNdA opposite of perspective and better for aligning objects precisely, DESPITE being unrealistic view
      * just A selects all (Alt-A to deselect all). shift that A to add new geometry like bb. Stuff added at cursor bc curses! MOVE CURSOR itself: shift+right-click...to add new innovation in diff LOCATIONS in 2025, we had to shift right lol
      * HOW TRANSFORMS INCREMENT: if u scale object when mouse close to center of selected, it scales in BIG increments. if mouse far, it scales in much SMALLER increments. Same 4 all transforms
      * can EXCLUDE axis when transforming by just going to the correct ortho perfect viewpoint (can also lock axis in object props to side). When scaling can exclude axis with shift+that-axis...but note other transforms like rotate dont seem to work the same.
      * using ortho perfect viewpoints is good way to align objects precisely - like putting object on ground plane. NOTE: i like using CTRL button while transforming for precise alignment too...but not sure how it works tbh, i think it just increments at fixed/snapped interval from starting point - so make sure at good starting point first
      * esc works to cancel transform - but it seems right-click does too
      * DIFF in MATERIAL MODE and RENDER MODE: material mode just uses one big light called HDRI - render uses the lights in your scene.
      * ISSUE: your editors (which is each lil panel you can edit in diff ways depending on editor type...which is set using DD at top-left of all editors) are all messed up and cant fix. Solution: just add new default workspace of type needed (like Shading) and delete old one (and prob rename)
      * COLOR:
        * saturation = X1-COLOR:NOT-X1-COLOR (can be BorW depending on tone)...saturated with specific color...or not
        * tone/value = BLACK:WHITE...like skin tone
        * hue = WHICH COLOR going from red (0) back to red (100%)...idk hue just sounds pretty, like the options to choose
      * WHERE EDIT MATERIALS: can do in material props to side, but best to do in Shader Editor for more options/details
      * WHEN USE MATERIAL MODE vs RENDER:
        * 1) PERFORMANCE: often lights in scene are taxing on hardware and can make things slow. material mode just uses HDRI light, so gud
        * 2) SHADING OPTIONS: you can add in textures/colors/materials to objects without influence from lights in scene to start - then can add atmosphere with lights after 
        * tldr: for most part stick to material mode until end when start lighting objects in render mode
    * [[2025-01-29]] Blender Low Poly Landscapes chapter 2.1-2.3 #[[fast memo]]
      * HOW TO GET REFERENCES IN BLENDER: create new image editor. open it up in there and thaz basically it. if run into issues, just go back to this tut
      * KB SHORTCUT 4 SWITCHING BETWEEN VERTICES, EDGES, FACES: legit just 1,2,3 lol
      * HOW 2 SEE NUM objects, vertices, edges, faces, triangles SELECTED: overlays button DD (looks like circle overlayed on another circle) > Statistics - dis p cool tbh
      * MERGING: m btn duh. 2 main confoosing options: 1) collapse: basically same as merge center EXCEPT if multiple NON-CONNECTED selections, it merges to each separate SELECTION'S center of selection; whereas merge center would find center between all those selections 2) merge by distance: you set distance and any vertices within that distance to each other will merge. REALLY nice when vertices on top of each other instead of merging one by one
      * when selecting vertices, white colored is last selected. meme: white last during woke times
      * COMMON ADDING NEW OBJ ISSUE: adding while in edit mode. you know bc it says mesh at top of menu when trying to add in edit mode and wont see cameras and whatnot. can fix by separating selected OR just undo and readd
      * COMMON TRANSFORM ISSUE 4 ROTATED OBJECTS: scale on global axis when house rotated and you scale on wrong axis. Use local. Can help make this obv by going to VP Gizmos (bow n arrow button beside overlays) and turning on Move Gizmo
      * QUICK SCALE/TRANSFORM in LOCAL: click axis name one time for global and 2 times for local
    * [[2025-02-05]] Blender Low Poly Landscapes chapter 2.4-2.5 #[[fast memo]]
      * JUST EDIT OBJECT IN GLOBAL: sometimes iz just easier to edit object in global and then add weird rotations and give object its own local axis later (and can easily change back to global from local anytime for rotation)
      * ALT: just like alt-a for removing all selected, you use alt for removing all rotation/scale/etc with correct keys. AND alt-click for selecting loops
      * WEN SELECTING LOOP DOESNT WORK: if any vertex in loop has <3 connections/edges-coming-in. needs >=4. EDIT: certain edge-of-object-loops can have 3 and it works
      * LOOP CUT: ctr+R. LC wanna create QUADS, so wont go through triangles. if using loopcut and not going through, may be bc u not using quads on that face. meme: more control by using LC retard (imagine pointy mountain)
      * DUPLICATE: shift+D or Mesh>Duplicate
      * seParate: P key. Pull object out. (dont forget to go back to objMode, then edit mode with new obj)
    * [[2025-02-14]]
      * ORIGIN POINT: only moves in OBJECT MODE. if you move object in edit mode, OP no move
      * mirror modifier uses the OP to know where middle of mirror is. Seems MM always uses local axis
        * Mirror Object: You can choose an object as Mirror Point, instead of OP...thaz p cool
        * MM Clipping: if on, the 2 halves will collide instead of going through each other (imagine roof top gap closing and colliding). Once they collide, they then stick together. To unstick, have to turn clipping off
      * N: can bring up transform data in OBJECT MODE with N. sometimes better than going to object props in Properties Editor
