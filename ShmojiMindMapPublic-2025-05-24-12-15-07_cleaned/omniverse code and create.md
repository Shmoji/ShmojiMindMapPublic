  * issues
    * when adding reference or payload, the materials never come through
  * questions
    * what is it?
      * an IDE built using omniverse kit SDK that powers users to build Omniverse Extensions, Applications, and Microservices.
    * what is difference in CODE and Create/USD composer?
      * They are basically same, but code is more friendly for dev workflows (dont know specifics of how tho)
    * layers and USD files
      * when should you make changes to a layer versus opening the USD file and making changes there?
        * Changes should be made to a layer when you want to maintain a non-destructive workflow. This means that changes made to a layer will propagate and update through all the layers accordingly. On the other hand, changes made to the USD file directly will be destructive and will not propagate through the layers. Therefore, it is recommended to make changes to a layer rather than directly to the USD file.
  * useful stuff
    * useful stuff for physics, character controllers, etc
      * Window -> simulation -> demo scenes
        * a ton of demo physics stuff
  * terms
    * Deltas
      * what are they?
        * they are CHANGES. They allow you to change anything in scene/layer without changing the BASE USD file.
        * they denote adjustments to assets introduced in lower order layers
      * notes
        * You can delete deltas to remove changes from lower layer
      * they are noted by little white  triangle symbols in layer tab
      * how TOs
        * how to merge deltas permanently
          * https://docs.omniverse.nvidia.com/app_create/prod_extensions/ext_layers.html#merging-deltas
    * Asset Payloads
      * what are they?
        * A composition arc that functions similar to reference to let you create layers. Difference is that payloads can optionally not be loaded. Less hefty things to load.
        * Payloads denote assets introduced in a layer (compared to deltas)

      * Shown with blue arrow markers in layers tab
      * Questions
        * My guess is you dont update these in Omniverse?
        * How do you update this with new version from Blender?
    * References
      * Denoted by orange arrow in stage/layer tabs
      * what are they?

    * Opinions
      * what do they do
        * non-destructively give variations to scene file
        * teammates can show off their version of scene without destroying other teammate's work
      * notes
        * opinions are both layers and USD files.
    * Layer
      * how TOs
        * how to change model in a layer without changing the original USD file?

      * what is it?
        * a new or referenced USD file. Can be edited independently and update any other layer/scene that may use them. Very awesome for libraries of data that need to span multiple projects.
        * YT vid says layers are critical pathway to collaborative workflows and success using live mode
      * key points
        * Layer stack
          * Each layer builds upon previous layer in the stack bottom to top
          * Manages USD references. Layers are just USD files attached to another USD file. For each layer you see, so to does a USD file. 
          * If 2 layers share changes on some asset, higher layer wins
        * authoring layer - defines which layer your changes will affect
        * if you are INSIDE some USD file scene, and you delete something in nested layer (which is also USD file) - you also delete that from the actual USD file. So, seems it's okay to work from the layer or the base USD file. Depends on if you need context of rest of scene or not.
          * they say this in docs here and show non-destructive workflow: When a USD is imported as a SubLayer, actions done are committed directly to the SubLayers File. This can be very dangerous in practice and should be used cautiously. For example, if a mesh is native to the SubLayer and it is deleted, the mesh is deleted from the USD SubLayer file and is permanent. This can result in lost work. As a best practice, it would be wise to instead create a new SubLayer then reference the usd by dragging it in from the file browser. This method will result in changes being considered as deltas on the Layers USD leaving the referenced USD file untouched.
  * how TOs
    * how to get copied code from ANY command in CODE editor
      * do command (such as create code) -> open "commands" tab -> at bottom "select commands" to copy -> paste right into your code
    * how to create TEXT
      * 3d Text extension. You can edit text by clicking on "generate_3d_text" inside ActionGraph inside main xform.
  * random thoughts and discoveries
    * it's easier to understand layers in terms of big concepts/scenes. Not so much for small concepts, like one single imported model.