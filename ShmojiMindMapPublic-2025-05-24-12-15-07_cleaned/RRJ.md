  * issues with WebXR RRJ
    * The VR player is using totally different package in WebXR than in non-WebXR. WXR is using VRTK and nonWXR is using XR interaction toolkit. This means dev done to nonWXR version is separate from dev for WXR version.
  * how TOs
    * how to find high res scene
      * On design branch in the HDInOneScene scene
    * how to get basic webXR teleportation working in RRJ

      * use try 2 here. If doesnt work, then maybe try options below this. [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/web xr - webxr#^IcSEoLwup|how to create VR player in Unity for WebXR]]
      * to get teleport on up press of thumbstick: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/vrtk#^2hknRQU5Y|Follow this tut, but we use proxy for both hand and controller, so just add the DeactivateWithinAxisDeadzone to the proxies as a source: https://www.youtube.com/watch?v=NDsbFGkRvFs]]
      * other options that may or may not work
        * first half of this vid shows what to import. 2nd half not needed since rrj doesnt pick up items: [Setting up WebXR with VRTK4 in Unity3D - YouTube](https://www.youtube.com/watch?v=behdvI-G_oQ)
        * how to teleport: [WebXR with VRTK setting up teleport and axis move in Unity - YouTube](https://www.youtube.com/watch?v=EbKGVkPpojE)
  * RRJ standards
    * develop branch version
      * Can snap turn using horizontal axis on both thumbsticks
      * Can teleport using up on both thumbsticks
      * Controller always showing and always has ray being casted straight out of it. Ray turns green when interacting with interactable
    * design branch version (HD version)
      * Can snap turn using horizontal axis on both thumbsticks
      * Can teleport using up on both thumbsticks
      * Controller always showing and always has ray being casted straight out of it. Ray turns green when interacting with interactable
