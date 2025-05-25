  * Unity editor
    * how TOs
      * how to find events that are triggered to run logic
        * In editor you can click object and you'll see "activate"...so basically just click object and youll see the event listeners and logic called by them
      * how to import packages
        * from disk
          * literally just find the package.json file (maybe other ways in different languages?)
        * Related to importing into unity
          * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/Debugging in Unity#^qtzoarWSv|how to use a newly imported package in Visual Studio]]
      * Check here too: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/Debugging in Unity#^RisYOH69U|how TOs]]
      * how to send events from anywhere and listened to from anywhere (dont have to be in same scene)
        * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/Unity dev#^Pf8CBhmKo|Scriptable Object Events]]
      * how to export hierarchy from one project to another
        * drag hierarchy objects into assets to create prefab
        * drag new prefabs into new project
  * StreamingAssets
    * Good explanation: https://blog.logrocket.com/how-to-use-streaming-assets-unity/
  * Scriptable Object Events ^Pf8CBhmKo
    * key point: allow events to be sent from anywhere and listened to from anywhere (dont have to be in same scene)
    * This vid shows all details at 10:30: https://www.youtube.com/watch?v=J01z1F-du-E&t=756s
    * steps
      * Write listener and event classes
      * Put where they need to be
      * Create event object in assets
      * Hook errthing up and add any logic you need
  * onTriggerEnter and onCollisionEnter
    * why is it not detecting my collider?
      * 1: **Missing RigidBody** (the most common). At least one of the GameObjects involved needs to have a RigidBody. (check if at least one of them have a RigidBody attached and, if you are using OnCollisionEnter, does not have the "Is Kinematic" checked). See the below collision matrix for more information.