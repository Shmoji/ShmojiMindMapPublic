  * what is it?
    * their site:
      * browser that lets you install, run, and automate any AI applications and models automatically and effortlessly. No more opening the terminal. No more git clone. No more conda install. No more pip install. No more messing with execution environments. All of them automated with one click, as easy as using a browser.
      * Pinokio is a dynamic and easy-to-setup virtual computer - like ones ive ran in past
  * tech to try that is on Pinokio

  * tech, features
    * Whisper-WebUI
      * tracking thoughts
        * [[2023-12-04]]
          * you can transcribe with timestamps, but does not have diarization yet.
          * also cannot transcribe in real-time, sadge
    * ComfyUI, Stable Diffusion (image and video)
      * what is it?
        * allows you to do "text to image", "text to video"
      * how TOs
        * how to fix errors that come up
          * in browser when app is running, click on manager -> install all missing custom nodes
      * tracking thoughts
        * [[2023-12-04]]
          * tried Stable Video Diffusion. I copied workflows from [Comfy Workflows](https://comfyworkflows.com/). Could only get one to work with small number of nodes. I successfully made my image move around. No idea how to control how each image you input moves tho
          * tried some more complicated workflows. tried one that is text to image to video - but couldnt get it working for some reason.
          * i think comfyUI is app that lets you use many things like SD, so need to figure out differences
    * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/text to video#^v2Z4kQ8hS|LaVie: Text-to-Video generation]]
    * [[LEDITS++]]
    * SDXL Turbo
      * what is it?
        * generates in real-time as you type prompt
        * text to image or text+image to image
      * tracking thoughts
        * [[2023-12-05]]
          * out of all pinokio tech i tried today, i liked this the most. Had success. Then i took the image i made here and made into crappy video using ComfyUI SD

    * Bark Voice Cloning
      * tracking thoughts
        * [[2024-02-10]]
          * thought this may be better than RVC - ended up being garbage - the output was audio in like 4 different voices even tho audio i uploaded was one single voice

    * [[open webUI]]
    * Forge
      * tracking experience
        * [[2024-10-07]]
          * i had goal to change my main profile pic into silly version and couldnt do it with this. I bet i could if i knew everything, but after hour or so of trying - no luck
    * instantstyle
      * tracking experience
        * [[2024-10-07]]
          * tried on strong computer/GPU (papas) and it takes over an hour just to generate one image (20 inference steps which is default - what is deal?)
          * apparently only runs good on 24GB VRAM. But they said can try to reduce size of output images and maybe itll work on less vram - ill try soon and see. EDIT: no good
  * noteworthy stuff
    * about details of the tech
      * [Everything is a file](https://github.com/pinokiocomputer/docs.pinokio.computer/blob/main/fs/overview#everything-is-a-file): Everything in Pinokio exists as a file. There is no complex protocol you need to follow, as making modules interact with each other is as simple as reading and writing files.
      * [Everything is expressed as JSON](https://github.com/pinokiocomputer/docs.pinokio.computer/blob/main/fs/overview#json-protocol): Everything is expressed in JSON, from data to code, to everything else. The JSON structure acts as the unified interface that makes it trivial to **extend logic**, **extend data**, **communicate among modules**, and more.
