  * tracking thoughts and learnings
    * tracking key points for getting setup
      * [[2024-01-22]]
        * i tried getting started with my own sample next needle project connected to a Unity project but it failed - not sure why
        * also learned if your Animator Controller has more than 2 states, you gotta pay a license to Needle - you can just go into controller and delete unneeded states to fix that blocker
        * to get the bad boi running, the export object needs to be setup which basically seems like getting the 1) project folder and 2) compiler directory right. With my cloned next needle project i couldnt get the compiler directory working for some reason. So, i used sample scene that already has those plugged up. But then that didnt work after pressing play. BECAUSE you need to open up the frontend code and npm install and npm start that. May need to change the port too, but dat easy
      * [[2024-02-06]]
        * figured out how to get compiler directory working. just install @needle-tools/helper in web project - that generates /node_modules/@needle-tools/needle-component-compiler/src - which then you set that folder in unity Component Generator component on the Export gameobject ^L0dUZAahn
      * [[2024-05-19]]
        * setting up whyspia scene and big learnings: make sure that next and typescript and react packages are up to date: i wasted hours and that was solution lol
  * key points of Needle
    * Needle basically adds a Unity-like editor to Three.js AND STILL has typical webdev flow
      * issue with three.js is there was no editor and left doing complex js code just to move simple object
    * Needle projects exported as GLTF file which is legit just HTML element and can be styled on webpage however you want to style the HTML element. Great example: [Needle Engine Samples](https://engine.needle.tools/samples/?room=422&open=1#html-custom-layout)
  * questions
    * why use Needle instead of just using Three.js?
      * look at key points above
      * Three.js has no editor and you have to code every small aspect of app.
    * Are there any benefits over Three.js that Needle has?
      * looks like all of Three.js is just JS code. No editor like with Unity. This gives Needle pretty big advantage if im right about this. Needle basically adds a Unity-like editor to Three.js
    * in needle, do scripts not written in javascript work?
      * Correct. But once you write a TS script, it is converted to C# to use in unity editor
    * where is local dev browser for Needle? (like what url on VR browser)
      * https://localhost:3000 - i think defined in vite.config.js in needle web project. or maybe the generated/meta.json
    * what does needle require you to PAY for and if you dont pay you dont get?
      * for free your models can have 2 states of animations in an animatorcontroller, but any more states (which typically you need more) - and you gotta pay at least indie version ($20 per month) ^_ZgcDh1lQ
    * what to know about for ANIMATIONS in needle?
      * Note: Sub-states and Blend Trees are not supported
      * only 1 layer in a AnimatorController is supported
      * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/needle tools#^_ZgcDh1lQ|for free your models can have 2 states of animations in an animatorcontroller, but any more states (which typically you need more) - and you gotta pay at least indie version ($20 per month)]]
  * needle dev
    * how TOs
      * how to write your own logic and have it triggered on interaction of VR controller and mouse
        * using DragControls
          * Out of box in needle, they give you the DragControls class. Drop this on objects in unity that you want to be draggable
          * To detect drag events, create a new script and also put on objects to drag. To detect drag events use dragControls.addDragEventListener for detecting a mouse drag. Looks like onPointerEnter and onPointerExit (which are also on DragControls) can be used for detecting VR controller interactions. Can find example of this in RRJ_UnityXR project, webxr_HD_needle branch, MinimalNeedleTestScene, Stonk.ts file.
        * using EventTrigger component
          * for VR pointers
            * On component can listen to PointerDown and Up events and execute your own logic
          * for mouse
            * TODO
      * how to write a script that can be used in Unity editor
        * in assets/Needle in unity project you will find src/scripts. Create ts/js scripts here and they are auto converted into C# files that can be placed on gameobjects in unity
      * how to get a component that is on the gameobject your script is on
        * Ex using DragControls: const dragControls = this.gameObject.getComponent(DragControls) as any;
      * how to get collision
        * just add collider (and sometimes rigidbody is also needed for some reason - maybe just for moveable objects)
        * there are also onCollision methods for components that you can use
      * how to choose if some unity gameobject is shown on browser/ar/vr/1st-person/3rd-person
        * just add XR Flag component to any gameobject - easy
      * how to create Unity part of Needle project?
        * create 3D core project from unity hub
        * download Needle installer unitypackage from [Needle Engine Documentation](https://engine.needle.tools/docs/getting-started/#prerequisites) and just double click it with unity project open to install

      * how to connect an exported GLTF file (or Unity part of Needle project) to a Next.js project
        * [GitHub - needle-engine/nextjs-sample: Vercel sample project to add Needle Engine — www.needle.tools](https://github.com/needle-engine/nextjs-sample)
          * clone repo, npm i, npm run dev = ur in business on Next.js side. if you're converting old nextjs project may be bit more complex, but i think you just need to follow this: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/needle tools#^0ueWTMxOx|how to convert nextjs project to next AND needle project]]
          * now create unity side. prob start with needle template. it will have export object. Chose project folder as the Nextjs top level folder of that project.

      * how to convert nextjs project to next AND needle project ^0ueWTMxOx
        * in next project, yarn add @needle-tools/helper @needle-tools/engine three @babel/runtime (not sure babel one is needing anymore)
        * create Unity needle project
        * On export object, choose your nextjs project (root folder)
        * do dis: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/needle tools#^EIgsiQP7s|how to set Compiler Directory on Unity export object Component Generator component]]
        * Match this sample repo https://github.com/needle-engine/nextjs-sample
        * notes
          * if your next project has babel.config.js - you gotta remove it (this can mess up SVGs if using babel svg thing, so be aware of that)
          * if play button in unity doesnt work, you can just run from console of next project
      * how to set Compiler Directory on Unity export object Component Generator component ^EIgsiQP7s
        * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/needle tools#^L0dUZAahn|figured out how to get compiler directory working. just install @needle-tools/helper in web project - that generates /node_modules/@needle-tools/needle-component-compiler/src - which then you set that folder in unity Component Generator component on the Export gameobject]]
      * how to call public method from inside unity editor
        * the method name needs to start with lowercase letter - aside from that it is same as usual in unity
      * how to show tooltip on hover of object in scene
        * add script to hoverableobject gameobject with public method that will display tooltip
        * add "Event trigger" to hoverableobject and onPointerEnter - display tooltip using public method
        * how to create tooltip and get tooltip to display
          * i actually dont know lol too hard
      * how to use Unity types from C# in your TS files
        * i think it's called codegen. Here is example:
          * // declare custom AudioClip type somewhere
          * type AudioClip = string;
          * // in your script:@serializable()
          * myClips : AudioClip[]; // < the component compiler will use known types, in this case it'll know AudioClip from UnityEngine.AudioClip
        * EDIT: actually this only allows you to use data of C# file, not the file itself...what the hecc does that even mean??
      * how to show colliders in browser
        * add "?showcolliders" to end of URL
      * how to fix COLLIDER issues
        * Sometimes mesh colliders just dont work in needle rn, so try box collider

