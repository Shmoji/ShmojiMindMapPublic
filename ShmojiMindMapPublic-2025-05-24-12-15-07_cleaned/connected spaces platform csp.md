
  * what is it?
    * me: API that makes so all spatial apps are interoperable on all devices, screens, editors, etc. Imagine projects from work where they work differently in each Game Engine. Different code for Unreal version, for Unity version, for mobile version
    * me: basically a standard enforced at binary level in your app/editor/etc that makes so multiple aspects of tech stack work together for spatial dev.
    * me: their FAQ is great. the questions help a lot, ill even put best here
    * their site:
      * library that provides developers across a range of languages and platforms with a means to build interoperable, cross-reality, multi-user applications.
      * It comes in the form of an open-source client-side library, effectively encoding in binary form the standards by which applications can interoperably communicate with one another. Standards that we can all contribute to
      * CSP is an application-side library, built for the spatial web, that does the job of handling fluent communication with other applications for you (what other apps?), the developer.
      * "rapidly stand up fully interactive solutions, with users, objects, external integrations, real-world anchoring, interactivity, and persistence across platforms" - seems their tech is focused on these metaverse areas instead of a solo game that is not multiplayer

  * questions
    * is this more like a standard for coding spatial apps anywhere? or more a standard for making sure the VISUALS of a spatial app look good on all devices and screens?
    * is Tenant ID centralized?
      * yea it looks like it. Only their team can generate it for you.
    * so, even though any service can be hosted on your own side, it seems only they can generate YOUR tenant ID - which is centralized and bad right?
      * i think so
    * does this somewhat do what DIDs do where you can bring your data and identity to different apps if they also implement the standard of CSP?
      * i think so based on their FAQ. Their site says "It gives developers across a range of languages and platforms a means to build managed, live, persistent, interoperable, cross-reality, multi-user applications, which talk fluently with other CSP-backed applications."
    * to talk to other apps, do they have to also integrate literal CSP code??
      * YES - that's how standards work