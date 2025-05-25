  * tracking gamedev learnings
    * [[2025-02-12]] components, monobehavior, updating camera #[[fast memo]]
      * COMPONENTS: in game engines you typically have Components. These are just modular/single-responsibility piece of fx that attach to GameObjects. Typical: an abstract BaseComponent class (shared base functionality for all components) and 1) RegularComponent (no lifecycle methods) 2) MonoBehavior (lifecycle methods). GameObjects almost always have transform COMPONENT by default
      * UPDATING CAMERA: best to do in lateUpdate lifecycle method after all physics/movement stuff already happened - prevents weird issues
