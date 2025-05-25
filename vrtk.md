  * what is it?
    * No-code (mostly) package to setup VR player and everything involved.
    * Works very well with WebXR exporter package
  * how TOs
    * how to setup VR teleporting
      * GENERAL: you map buttons to actions on a proxy gameObject that has BooleanAction script with sources of buttons (which are GameObjects with ControllerTouchAction script on them)
      * how to setup indicator curved objectpointer for teleporting on up press of right thumbstick
        * learnings
          * i thought this was solution, but didnt work. (CombinedAction.AngleRangeToBoolean worked tho):
            * tut for converting float action to boolean action (needed bc pointer facade script's activation action only accepts boolean): https://github.com/ExtendRealityLtd/Tilia.Input.UnityInputManager/tree/master/Documentation/HowToGuides/ConvertingAFloatActionToABooleanAction
        * under trackedAlias > right controller alias > add R.TeleporterOrigin object that has Teleporter indicator offset script with correct hand as controller
        * Under teleport DemoInteractions > curved objectpointer > on PointerFacade script, change Follow Source to correct teleporter origin
        * Follow this tut, but we use proxy for both hand and controller, so just add the DeactivateWithinAxisDeadzone to the proxies as a source: https://www.youtube.com/watch?v=NDsbFGkRvFs ^2hknRQU5Y
        * if you get issue where things break on build, you need to replace the proxy with just the controller input. Not sure how to have both controller and handtracking at the moment.
    * how to setup raycaster that comes out of VR controllers and setup interactable button with that raycaster
      * Create 2 straight pointers. I just stored under Interactions -> button interactables
      * I made the follow source the controlleralias from trackedalias. This tut showed me to do that: https://www.youtube.com/watch?v=nQ2YDr8ruqQ
      * For pointer Select action, need to give what triggers the select (some booleanAction). I gave XR trigger press from InputActions.
      * in same place, create a Tilia Indicators.SpatialTargets.Dispatch prefab. The tut above shows what to do with that. Basically adding DoDispatch on 3 diff events
      * ~~On your button, as child, add tilia prefab Indicators.SpatialTargets.Target. On this add any button logic needed on any event needed (make sure that event type is coming from dispatcher of course)~~
      * instead of above point, add Spatial Target script to your button and catch events and add logic there (make sure that event type is coming from dispatcher of course)
      * related
        * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/vrtk#^9zvNzmBXO|how to stop pointer from locking on to targets]]
        * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/vrtk#^PkC8xIIaI|how to define the collider you want for your spatial target / button]]
    * how to keep pointer raycast displaying at all times
      * go into prefab and for all GO under PointerElements, make "Element Visibilty" = Always on
    * how to have pointer activated by default instead of needing to press a button for activation AND a button for selection
      * on prefab, under logic > actions > activate - make the initial and default value to true
    * how to stop pointer from locking on to targets ^9zvNzmBXO
      * Go to internal GO -> find SourceLocking and disable it
      * If just using SpatialTarget script, this issue doesnt happen
    * how to define the collider you want for your spatial target / button ^PkC8xIIaI
      * ~~In prefab for spatial target, youll find DefaultCollider and that is what's used. You can change that collider to whatever shape. What idk is how to use some other random game object's collider OR if DefaultCollider can be something other than Box Collider.~~
      * If spatial target script is on same GO as collider, it will use that collider (or maybe collider doesnt even matter? idk)
  * step by step processes
    * algo for interacting with various different interactables using a pointer
      * (Spatial target script on a GameObject with a collider) receives Activated event, Deactivated, and few other events from some place. When event received, logic you define can be called. This is how logic for that button/interactable is called. Where does the events come from?
      * The events come from a Straight Pointer prefab. Specifically, from the parent GO that has PointerFacade script
  * questions
    * what is purpose of tracked alias?
      * to allow you to separate your logic from the actual SDK camera-rigs (still not sure what this means)
  * VRTK and [[RRJ]]
    * questions
      * why does regular RRJ exported to webXR have a VR player that doesnt work (XR interaction toolkit by Unity)...but converting it to VRTK does work?
        * Bc XRIT doesn't support WebGL: https://github.com/De-Panther/unity-webxr-export/issues/95
        * One person made XRIT work with WebXR exporter, but not maintained and XRIT still not natively supporting WebGL (can find link in GH issue above)
