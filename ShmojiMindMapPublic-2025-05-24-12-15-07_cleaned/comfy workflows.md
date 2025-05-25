  * tracking thoughts
    * tracking learnings
      * [[2024-08-19]]
        * i wanted to make goofy/playful version of my main shmoji profile pic. i found youtube video explaining how (maybe) and comfy workflow to go with it https://youtu.be/CRURtIltf58?si=uAM6SNT-YRF-YkOc
        * can just copy json of workflow and then paste right into comfyui
        * in comfyui can go to manager and custom nodes manager to get comfyuis controlnet auxiliary preprocessors and comfyui noise
          * preprocessors - allow you to grabs masks from images (like depth maps, line art, etc) to have controlnet guide the generation
          * noise nodes - specifically we use the unsampler node - it runs the sampler in reverse to create the noise that may have generated your input image - this is useful bc allows us to RECREATE an image and make edits to an image while maintaining much of the source 
        * guy in tut said controlnet may not even be needed, but sometimes unsampler gets away from source and controlnet can help rangle back to source
        * when recreating an image, the guidance (cfg) should be 1
        * basically all this allows you to make small changes to an image without losing your source image
        * to change style of image: describe source image as good as possible in source prompt. Use that same prompt in destination prompt, but then change based on what new stuff you want. Can use double parenthesis to emphasize some aspect
        * increase the guidance (cfg) on sampler to make more creative, but also more different from source
        * in the end it seems this was good for changing style of image in precise way and not changing source image much at all. i wanted to change my image style, but in a more drastic way - and this didnt work.
  * list of good comfy workflows
    * super simple image to video (but no idea how to control how video moves): [Comfy Workflows](https://comfyworkflows.com/workflows/1f08c918-7449-4b4d-96f7-58bd13e8d948)
