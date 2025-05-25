  * questions
    * what are fragments
      * a pixel is the physical unit on a screen, while a fragment is a virtual unit used during the rendering process that corresponds to a pixel. Fragments contain additional information and undergo various calculations before they are converted into the final pixel color.
        * i almost feel like a fragment is sort of like the metadata of a pixel. The pixel is simple - a color value. The fragment is complex and helps determine the pixel value.

    * can 1 pixel only have 1 fragment?
      * In most graphics systems, each pixel corresponds to exactly one fragment. This one-to-one correspondence ensures that each pixel on the screen has a defined color value.
      * HOWEVER, there are cases where multiple fragments can affect the final color of a pixel. This situation typically arises due to various rendering techniques such as anti-aliasing, transparency, or post-processing effects.