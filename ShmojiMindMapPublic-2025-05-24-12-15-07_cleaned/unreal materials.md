
  * what are parent materials and material instances?
    * Rob: a material you create once using blueprint and then dont touch again. i think the blueprint part can get complicated. You then create material instance linked to the correct parent material
    * Rob: this makes it so that instead of you creating new material for every single thing, you reuse it
    * me: basically lets you create material with common properties and then use material instances to reuse that parent for performance sake
    * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/importing meshes, textures, models#^GPkPXX03K|you create parent materials in Unreal for sake of reusability and minimizing draw calls - not totally sure how or why that works - or if unity does anything like that]]