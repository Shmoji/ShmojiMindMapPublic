  * how TOs

    * how to press play and see your app instantly in Quest headset

      * Download Oculus XR package in Unity. It will already be in package manager ready to install.
      * Think you also have to go to Project Settings -> turn Oculus plugin provider on.
        * Just used Oculus link with this set to OpenXR.
      * Make sure you have Oculus app on your PC and signed in. Enable unknown sources in Oculus app settings on PC. 
      * In project settings -> OpenXR -> Play Mode OpenXR runtime, choose option. If using SteamVR, obv need that open on PC. Otherwise, just choose Oculus.
      * Plug headset in once in Quest Link lobby and press play
    * how to press play and see your app instantly in Pico 2 headset ^YQ9P5Rtnz
      * EDIT: can no longer get this to work with RRJ
      * Download Steam VR
      * Download Pico Streaming Assistant on PC and Pico if not there
      * In project settings -> xr plugin management -> plugin providers -> enable OpenXR
        * Just PICO enabled doesnt work
        * Firs time this worked, but now OpenXR enabled makes unity freeze on play
      * In project settings -> OpenXR -> play mode openxr runtime = SteamVR
      * In project settings -> OpenXR -> add oculus touch controller profile so hands will work
    * how to test VR app without a headset
      * Setup
        * xr interactions toolkit (default in package manager) provides simulator for testing without headset.
        * After import, you must drag simulator prefab to hierarchy. Is in a samples folder.
      * Controls
        * press t for moving left controller and y for moving right controller (can deactivate by pressing same button)
        * Hold middle mouse button to aim raycast from controller and left mouse to click stuff.
        * how to move character: need to activate a controller. Then, AD to turn. WS to move. Aiming/looking same as explained above.
        * how to look around??
        * how to change your height from ground (and move sideways): right click and drag
    * how to build ANY Unity VR app for webXR
      * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/web xr - webxr#^ckNqBc4NP|how to locally build and run any unity VR app to webxr
]]
  * Common issues for debugging VR apps ^We_xnEWYY
    * Vr headset look around not right when testing. Make sure to disable headset simulator in hierarchy.
    * I can only use Quest if steamVR is open reeee
      * When using Quest headset, make sure OpenXR runtime is set to Oculus in Oculus desktop app. Same in Unity project settings if used there.
  * [[web xr - webxr]]