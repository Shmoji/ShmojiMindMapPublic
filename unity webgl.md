  * questions
    * is unity webgl a specific type of webgl?
      * GPT4: Unity WebGL is not a specific type of WebGL, but rather a way Unity, the popular game and graphics engine, exports and runs its content using WebGL technology
        * its confusing bc it seems like webgl allows microphone use in web, but unity webgl doesnt
          * GPT4:
            * WebGL Capabilities: WebGL itself is primarily a graphics API for rendering 2D and 3D graphics in web browsers. It doesn't directly handle audio or microphone input; these functionalities are typically managed by other web APIs. For instance, the Web Audio API and the MediaStream API in modern web browsers can be used for audio processing and accessing the microphone, respectively.
            * Unity WebGL Limitations: When Unity exports a project to WebGL, it essentially converts your game or application into something that can run in a web browser using WebGL for graphics rendering. However, Unity's WebGL build does not inherently include full support for all browser functionalities, including microphone access. This limitation is due to various reasons, such as security considerations, browser sandboxing, and the complexity of integrating with various web APIs. As a result, certain features available in Unity's other build platforms (like desktop or mobile) might not be directly available or fully functional in the WebGL build.

