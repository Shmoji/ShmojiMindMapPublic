  * how TOs
    * how to improve performance (make that shiz no more laggy)
      * ROB: go to wireframe mode (v easy in unity) and check poly count by just looking. Can clearly see when tons of polys
      * ROB: if asset/mesh-renderer has more than 2 material slots, prob not good - find way to reduce (how??)
      * ROB: 4K materials prob not needed (we saw material with name "4K"). Can get less complex materials instead. But how do you know when a meterial is complex and how do you reduce complexity?
  * notes from resources (instead of stuff i experienced)
    * tools to fix or improve performance
      * Unity
        * Unity Profiler
          * GPT: powerful tool that provides insights into your app's performance. Use the profiler to identify any performance bottlenecks or expensive operations within your code. Look for sections that consume significant CPU time or trigger a large number of draw calls.
    * techniques to fix or improve performance (go through each of these and check off one by one)
      * Batching
        * Unity
          * Unity automatically batches static and dynamic objects with the same materials to reduce draw calls. Ensure that your scene is properly set up for batching by combining meshes, using GPU instancing, or enabling static batching when appropriate.
            * TODO: do more research here
      * LOD (Level of Detail)
        * Implement level of detail techniques to reduce the complexity of distant or less important objects.
        * Unity
          * Unity provides built-in LOD systems that you can use to optimize performance.
      * Occlusion Culling
        * Enable occlusion culling to prevent rendering objects that are not visible to the camera. This feature improves performance by skipping the rendering of occluded objects.
      * Scripting Optimization: Review your C# scripts to ensure efficient and optimized code execution
        * Object Pooling: Minimize the creation and destruction of objects during runtime by implementing object pooling. Reusing objects instead of instantiating and destroying them can significantly reduce the performance impact.
        * Memory Management: Avoid unnecessary memory allocations in critical sections of your code. Use the Unity Profiler's memory profiling feature to identify areas where memory allocation is high and optimize them.
        * Scripting Best Practices: Follow best practices for scripting in Unity, such as caching references, minimizing the use of heavy operations within update loops, and optimizing loops and data structures.
      * Asset Optimization: Review your assets (models, textures, audio, etc.) for optimization opportunities:
        * Texture Compression: Ensure that your textures are using appropriate compression formats and sizes. Use texture atlases or sprite sheets to reduce texture swapping during rendering.
        * Model Optimization: Optimize your 3D models by reducing the polygon count, removing unnecessary details, and using efficient mesh compression formats.
        * Audio Compression: Compress audio files using appropriate formats and bitrates without sacrificing quality.
      * Unity Editor Settings: Explore Unity's various editor settings and configuration options to optimize the app's performance:
        * Quality Settings: Adjust the quality settings for different platforms and ensure that they are appropriately set for VR.
        * Graphics Settings: Experiment with different rendering settings and effects to find the balance between visual quality and performance.
        * Player Settings: Configure player settings such as scripting backend, API compatibility level, and optimization options specific to your target platform.
      * Unity Asset Store: Take advantage of Unity Asset Store's performance-related assets and plugins. There are several tools available that can help optimize rendering, reduce draw calls, improve memory management, and more.