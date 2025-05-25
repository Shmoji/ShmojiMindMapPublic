  * common issues
    * common issues with lighting and shadows
      * if having these issues, try to build lighting only, not just "build all levels"
    * common issues with importing models
      * the model is broken into pieces
        * you can either have designer/self join it in blender/whatever or there is setting in unreal when importing to combine all meshes
    * imported material
      * imported material is not transparent like it should be
        * double click into it -> right click in node-editor -> on left in details, change Blend Mode to Translucent -> add ScalarParameter -> default value to what you want (can also change this on the instance level by creating material instance from the main material) 

  * notes
    * blue print class -> actor -> static mesh
    * Collision
      * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/Unreal engine#^kSbcja6RR|StaticMesh can have collision of their own separate from Actor collision it is attached to]]

  * terms
    * blueprints ^Ew00VhAA2
      * BP how TOs: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/Unreal engine#^Ew00VhAA2|blueprints]]
      * similar to prefabs in unity, except can skip coding by using node-base editor
      * special assets that provide node-based interface to create new types of Actors and script-level events without needing code
      * what i learned
        * I created sphere using unreal UI and it already had collisions. I wanted to create sphere without collisions and first step is to create blueprint class. Specifically chose Actor for type.
      * the level blueprint
        * Event BeginPlay is when level loads, not when you press play
      * pins
        * connecty things on nodes
        * execution pins - white pins - only executed once previous execution pin says. Basically defining call stack
      * FXs
        * PURE FX
          * no execution pins
          * define these whenever you need FX to return IMMEDIATE value
          * call stack doesnt define when this FX is called. It is called whenever needed with CURRENT value. Good for getting position of actor since you dont want that old value cached
        * general notes on FXs
          * cannot have nodes that take time to execute inside FX. Ex: delay node wont work. HOWEVER, macros can do this.
            * So is macro just a FX that literally can use any node? plus some other diffs?
          * Can be used across different BPs.
      * Macros
        * Cannot be used across different BPs. Only local to own BP. FXs can be used across different BPs.
      * Structs
        * Similar to classes, but cant have functions in your structs with BPs. Although, can create library to make that happen. 
      * EVENTS
        * on component begin overlap
          * other actor pin is the actor that overlapped with the collider
          * Can use "cast to" to filter what kind of actor that event should respond to
    * Actor
      * any object that can be placed into a level
        * ex: camera, static mesh, player start location
        * Seems same as Unity GameObject maybe?
    * StaticMesh
      * Basic unit to create world geometry
      * StaticMesh can have collision of their own separate from Actor collision it is attached to ^kSbcja6RR
  * Different modes
    * Landscape Mode
      * ways to create environments like mountains, hills, holes, etc
  * useful shortcuts
    * while hovering on viewport, press F11 to fullscreen it
    * Press ~ button in order to type into console
    * When actor is selected
      * W - move actor position
      * E - rotate actor
      * R - scale actor
      * END button - snaps actor to ground
    * blueprints
      * drag box -> press C to create comment box
  * how TOs
    * CATEGORY: lighting
      * how to get rid of shadows and just have even lighting everywhere?
        * go to your sunlight and just turn cast shadows off. If that doesnt fully work, make sure it is pointing straight down
    * how to view framerate and max framerate
      * can use console commands
      * can also use menu button in viewport. it has "show fps" option
    * viewport
      * how to move around in viewport (when not playing)
        * Hold right mouse button and WASD. Scroll wheel to move faster or slower.
        * Also button on viewport at top right to change camera speed
    * how to setup playable character
      * how to setup binding keys to certain player actions
        * DEPRACATED: Project settings -> search bindings -> under action mappings and axis mappings can bind buttons to named event. Then, that event can be used in Actor character controller
        * new version is called enhanced input actions. Not sure how to setup for regular player, but VR player example here: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/Unreal engine#^jFtRtgPPd|how to setup playable VR character]]
      * how to setup playable VR character ^jFtRtgPPd
        * copy VRCharacter from Unreal's VR template project. Can also take BP_VRPawn from trade POC (best to import VR pawn last after these next steps tho)
        * project settings -> maps and modes -> set default game mode to one you created (which really just sets the default pawn class) -> make sure you have that default pawn class (maybe can just get from template project? i got from trade POC)
        * project settings -> type enhanced -> Plugins - OpenXR input (make sure have plugin) -> need template here and that template needs many things. Can use VR template project to get these to default
        * VrPawn will need another asset/BP from MannequinsXR (no idea where this came from, maybe VR template project) - this is the XR hand and everything involved
    * how to choose map that loads first - project settings in maps and modes
    * blueprints
      * how to add reference to some object in level to blueprint
        * select actor in outliner -> go to BP -> right click and add reference option is now there
        * prob some way to text search too
      * how to do conditional nodes in BPs
        * can use SWITCH nodes
        * can use SELECT nodes
        * can use BRANCHING
        * how to do conditional ACTOR (only do stuff if this type of actor)
          * use CAST TO
      * how to organize nodes
        * CollapsedGraphs - seems these organize nodes almost like a folder. 
        * Comments - obvious
      * how to do LOOPS
      * how to find and open LEVEL blueprint
        * top toolbar, Window, Levels, lil graph icon
    * transforms
      * how to make actor transform movable (you may notice it wont move)
        * Set transform mobility to movable
    * how to COLLISION
      * how to add collision to random asset with no collision
        * if there is static mesh file, open that file. Press collision button. If basic shape collision doesn't work, use "auto convex collision"
    * how to VARIABLES
      * how to create global variables where you define value in editor like you see in Unity ^wIfUhooA9
        * go to blueprint, create variable in variables tab to left, click on var, set "Instance EDitable" or it wont show in editor, then click on actor in level, in details tab you can change value of that global var
    * high level non-unreal-keyword HOW TOs
      * how to get web browser working in unreal
        * create web browser widget https://unrealcommunity.wiki/web-browser-widget-13f406
        * Creating a Custom Actor Blueprint as Actor/GO that inits logic for WB Widget
          * in content browser, create Blueprint anywhere
        * Adding Logic to the Actor Blueprint
          * Add a BeginPlay event if it's not already there (right-click in the event graph and search for "BeginPlay").
          * From the BeginPlay event, drag out a node and create a Create Widget node, selecting your Widget Blueprint as the class.
          * Add an Add to Viewport node connected to the Create Widget node to display the widget
        * Drag your Actor Blueprint from the Content Browser into the level
    * how to create logic to add to environment Actors like a youd add a component on a unity GameObject?
      * you have to create a ActorComponent. Then can add that component to the env actor in editor
    * CATEGORY: how to UI in unreal
      * how to store multiple nested widgets?
        * you first need a top level overlay or panel (think thats what its called)
      * how to create text that floats in 3D world
        * method 1: Rob's method of using material that i dont really remember
        * method 2:
          * just create blue print actor and search text and choose Text Render Actor (or something like that)
          * i noticed you can reuse this one actor for many different instances (so different pieces of text)
  * [[learning unreal journal]]