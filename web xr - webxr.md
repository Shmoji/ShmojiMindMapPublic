  * common issues for webxr
    * webxr app not detecting headset
    * Unity settings issues
      * Not 100% sure necessary, but in player settings -> publisher settings, enable decompression fallback. Saw at least 2 person recommend this online.
    * Local server needs to be HTTPS for webxr. How to do that is below
    * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/Debugging VR apps in Unity and more#^We_xnEWYY|Common issues for debugging VR apps]]
  * webXR options (tools for building webXR apps)
    * webXR options for unreal
      * experimental Pixel Streaming
        * This seems closer to CloudXR bc app runs on some other device. WebXR runs in users web browser.
        * [Unreal Engine 5.2 - Experimental Pixel Streaming to WebXR - YouTube](https://www.youtube.com/watch?v=FQgsQLodcZM)
        * [Unreal Engine 5.2 New Feature - Streaming Multiple Cameras - YouTube](https://www.youtube.com/watch?v=VpgfPCkt4uI)
    * Wonderland Engine
    * Pure JS options
      * [[Babylon.js]]
      * A-Frame
      * [[Three.js]]
    * Needle Tools (seems to be JS mixed with Unity if you want)
  * how TOs

    * how to test if webXR app performance is good or not
      * what is frame rate app is getting? is it what you want? if no, then that be BAD
      * in any VR app, every frame must complete its CPU and GPU work in a set amount of time, usually measured in milliseconds - in order to hit a certain frame rate. So, you can look at log of frames and see how many ms each frame took. If one frame is a million ms, then there be an issue
        * how to do this measurement? i will cover here: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/web xr - webxr#^YsAm3Wy9z|how to test WHAT is making webXR app performance BAD]]
      * ms per frame to hit certain frame rates:
        * 60 FPS = 16.6 ms per frame
        * 72 FPS = 13.7 ms per frame
        * 90 FPS = 11.1 ms per frame
      * Browser defaults to a refresh rate of 72 FPS on Quest 1 and 90 FPS on Quest 2...so you want those FPS or better
    * how to test WHAT is making webXR app performance BAD ^YsAm3Wy9z
      * for Quest headsets
        * Meta Quest Developer Hub [[MQDH Performance Analyzer]]
      * step by step
        * the first goal is to discover if your app is GPU bound or CPU bound.
          * one way to do this: disable camera in scene -> rebuild -> check if frame rate improved -> if so, app is likely GPU bound - otherwise, it is CPU bound
        * if GPU bound
          * now determine if vertex-bound app or fragment bound app. This will lead to determining where the GPU bottleneck is. GPU-bound apps usually fall into one of these two categories:
            * what are these categories?
              * A vertex-bound app has issues with scene complexity (too much geometry being rendered).
              * A fragment-bound app has issues with the number of fragments being rendered, the cost of the fragments being rendered, or possibly both. You’ll sometimes also hear this described as fill rate bound.
            * how to determine this?
              * you can differentiate between vertex and fragment bound by simply rendering fewer pixels and seeing whether your frame time improves. This can be done by setting the app’s render scale to something small, like 0.01. This will cause many fewer fragments to be rendered while keeping the scene complexity constant.
                * i could change Render Scale in RRJ by going to Project Settings -> Quality -> go to Render Pipeline Asset and should find it there
              * When you are done testing, look at your results and consider the following:
                * If performance is not affected, the app is likely vertex bound.
                * If performance improves, the app is likely fragment bound.
                  * When the app is fragment bound, you must 1) reduce the number of fragments being rendered, 2) the cost of the fragments being rendered, or possibly both. [[fragments in rendering]]
                    * 1: How to Reduce the Number of Fragments
                      * Use RenderDoc to analyze the draw order of objects in the scene. It captures a snapshot of the entire rendering process for a single frame. In that capture, you can see each individual draw call, the order that draw calls are issued, and much more.
                      *  Issue i ran into, was the above point gives ton of info, but no idea how to tell where any issues lie - it all looks normal
        * if CPU bound
    * how to create VR player in Unity for WebXR ^IcSEoLwup
      * try1 (didnt work - well teleporting worked, but not snap turn)
        * 1: https://www.youtube.com/watch?v=behdvI-G_oQ&t=284s
        * 2: https://www.youtube.com/watch?v=EbKGVkPpojE&t=208s
      * try 2
        * clone this repo and copy hierarchy from sampleScene to your project https://www.youtube.com/watch?v=e7hVROj9qm4
        * make sure your assembly definition file is in assets folder and same as cloned repo. If your project needs more assemblies included, then figure out what to add in that list when clicking on the assembly file
        * Add EventSystem to hierarchy if not there
        * If values did not fill correctly when pasting, fix these in hierarchy:
          * Add LeftH and RightH in correct places in InputActions
          * Just go through and fix all details of InputActions by comparing to SampleScene. There will be many things different.
        * Make sure all needed scripts are copied over from cloned repo
    * how to test HEADSET functionality of WebXR in browser WITHOUT headset ^G4v-EySlR
      * Emulator: https://chrome.google.com/webstore/detail/immersive-web-emulator/cgffilbpcibhmcfbgggfhfolhkfbhmik
    * how to use VR headset with webxr app
      * specific headsets
        * how to use webxr with pico 2
          * Same as this, but without Unity parts: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/Debugging VR apps in Unity and more#^YQ9P5Rtnz|how to press play and see your app instantly in Pico 2 headset]]

    * how to locally build and run any unity VR app to webxr

      * in build settings, switch platform to WebGL
      * In de panther unity webxr export repo, use getting started in docs. 
        * it doesn't mention to add scene to the build

        * you will have to remap your camera/interactions from regular VR to depanther's like he has in sample scene. I dont have good process for this yet

          * Notes on how the hierarchy works in webXRConverter

            * CameraMain is 2D camera. Other 4 cams are for vr and ar

            * In many tutorials people replace webXR controller interactions script with VRTK
      * how to setup local HTTPS server
        * starting a 9:40 - https://www.youtube.com/watch?v=e7hVROj9qm4
  * pros and cons of VR app converters to webXR
    * pros
      * quickly convert apps made for VR right to webXR (especially good if team already knows Unity dev but not webXR JS libraries)
    * cons
      * Dealing with WebGL compilation process and dealing with optimization (youre not gonna feasibly use HDRP and keep a solid framerate)
  * pros and cons of JS libraries for webXR
    * pros
      * Much closer to rest of JS ecosystem and smaller overall bundle sizes than what you get exporting out of game engine. Gonna run better on web.
    * cons
      * Lot more learning than converter
  * unity project to webXR converter
    * depanther webxr converter
      * WebGL templates
        * These are static HTML pages for serving up your app's content. When you build and see index.html, that is the compiled version of the WebGL template.
        * You can edit the HTML file if you want, but why need to? Prob dont need to.
    * Needle Tools - seems they do similar as depanther's and more
      * https://engine.needle.tools/docs/getting-started.html
      * Questions i asked
        * Needle Tools can convert Unity VR app to webXR?
          * answers
            * Well, no not really. Needles tools use Unity as tool. So you create scenes, use the node shader graph etc. But code is written in type script and it gets converted to C# scripts to use in Unity so it can be package up as a three.js build.
  * debugging webXR
    * in browser
      * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/web xr - webxr#^G4v-EySlR|how to test HEADSET functionality of WebXR in browser WITHOUT headset]]
      * Oculus Developer Hub
        * monitor performance and resource usage
        * send URLs to view in headset
      * RenderDoc
        * capture, replay, and debug scenes on the GPU (lets you see stepbystep what GPY is doing and SEE how scene gets rendered)
      * Regular browser devtools
        * can attach adb to browser instance running on your meta headset
        * Can view console output, track asset loading, etc
  * good videos on webXR
    * https://www.youtube.com/watch?v=xdr4BM0jgF8
      * shows how meta is doing webXR (using three.js and devtools)
