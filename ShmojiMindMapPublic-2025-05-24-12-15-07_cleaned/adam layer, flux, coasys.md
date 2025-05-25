  * tracking thoughts
    * tracking thoughts on use for Emote
      * [[2023-12-30]]
        * went through about all their docs. it's not obvious this is good choice for Emote
        * i like their visions of being fully interoperable with any data storages, networks, and whatnot - but idk how real that is
        * very early so about all the tech is buggy and confusing
        * all the apps i used required auth from ADAM launcher running locally, but everything in those apps were web apps - which confused me. And they were web apps on their own domains, not web apps running on localhost
        * thinking best bet is to write some code using their docs and use that to inform me - plus ill learn about holochain too probably
    * tracking thoughts on 1st Adam Hello World app (coasys-example-app, calendar app)
      * [[2024-01-14]]
        * first thing you have to do is connect Adam Launcher you installed AND setup (a process, but fairly easy if you dont get lost or confused what to do next) to THIS APP. Before that you are blocked from using app. Connecting can also get confusing. User may not realize to open adam launcher in disk tray if it doesnt open itself
        * next you have to SELECT PERSPECTIVE or CREATE NEW PERSPECTIVE. It's not intuitive what this even means and it bugged out in this app and didnt show up on first few refreshes. i about gave up bc didnt know how to continue

  * what is it?
    * their site: framework for building distributed social spaces which replaces the concept of apps. It's a social network engine, and a new distributed web in which all these apps interoperate seamlessly.
    * built on top of [[holochain]] but you dont even need to use holochain
  * features, tech
    * Perspectives
      * local graph DBs
    * SocialDNA
      * allows agents to query data in social spaces
    * Language
      * a [Deno](https://deno.com/) bundle that provides specific functions within the ADAM Layer. These Languages provide the core functioning of social spaces in ADAM. Allowing developers to easily build applications across ecosystems and leverage the work of developers that came before them.
    * Link
      * A [Link](https://docs.ad4m.dev/jsdoc/classes/Link) in a Neighbourhood consists of “triples” (subject-predicate-target). These triples serve as the foundational pillars in LinkLanguage, forming an intricate **web of interconnected knowledge**. The potential applications are immense; from LinkLanguages that operate over existing platforms like Wikipedia or Discord to ones that birth entirely unique spaces.
    * THEIR APPS
      * Adam Launcher
        * what is it?
          * me: thing you download and run on your computer
          * me: basically a graphql server on your computer that stores data of every app you connect to (i think??)
        * anecdotes
          * Nicolas Luck: All UIs we currently have (Flux, Perspect3ve, apps.ad4m.dev) are hosted and available through the web, but all the data comes from Adam
            * to me this sounds like vulnerability by trusting app that is hosted through web like this - BUT not all apps will be - where it is hosted is customizable - could be ran on user's computer instead - like [[Pinokio computer]]
        * what it do?
          * starts a local graphql server which is what ad4m-connect connects to
            * so, even a web app can connect to this server and interact with it
            * all data is stored locally and in the logs you can see the port it's running on 
  * questions
    * CAN APP BE RAN IN BROWSER, BUT LOCAL TO DEVICE?: like with Flux - that is hosted on amazon servers - so couldnt someone extract data due to that. You dont know if their frontend or backend code is calling APIs. Whereas if the app literally ran locally on user's device - there would be no chance for someone to extract data IF THEIR INTERNET IS OFF - right?
      * me: my guess is that you can use centralized hosting OR NOT - it's customizable - you could totally have app literally run from their device for webapp
      * me: just bc you sign using Adam, it doesnt seem to guarentee that data isnt going off somewhere else other than your local graphql server and device. An app hosted on AWS could totally be sending your data somewhere else from frontend or backend. Could even do it locally on your device - BUT if you turned internet off and app no longer can do stuff with data, you'd know something is fishy
        * i think this may be point of [[synergy engine]] - you can check with others on the reputation of apps, users, etc - but idk this 4 sure
      * me: technically an app could write logic so that if offline, store data locally - and once you go online, it sends all your data somewhere you dont want with some hidden API
    * is all data stored in files on user's device? or is there some DB? are there times when data is stored somewhere else? does it depend on app being used?
    * to store data using Adam, does the user HAVE to auth with adam launcher? what if i dont wanna burden user with that UX of connecting to Adam?
    * questions after doing hello world callendar map?
      * is all data stored locally in .ad4m/ad4m/data/links.json ?
      * what is difference in Perspective and a Neighborhood?
        * Answer in docs: Neighbourhoods are essentially just Perspectives (graph databases) that are shared and synced between Agents.
      * how to query data i made in calendar at http://127.0.0.1:12000/playground ?
    * apps like Flux using Adam layer dont require gas fees despite using ETH, why?
      * shared spaces in Flux and ADAM are implemented using either holochain or centralized servers depending on user's choice. Connection to ETH happens via signature binding DIDs -> ETH so does not require interacting onchain
  * related
    * [[synergy engine]]