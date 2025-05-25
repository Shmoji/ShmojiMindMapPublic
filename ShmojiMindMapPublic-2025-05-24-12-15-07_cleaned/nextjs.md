  * tracking learnings
    * [[2024-09-22]] new nextjs app router - byebye page router #[[fast memo]]
      * components by default are server side components now and you have to put "use client" at top to make them client side components
      * if using state or anything like that, gotta be client side component
      * i dont really know how getServerSideProps works anymore and i dont think pulling data how i always have using reactQuery is any diff, but im not totally sure - ill find out one day if needed
      * layouts are done differently now
      * you can import and use client side components inside server side components - this is how i created default layout so it can use server side features of defining webpage metadata, but still import in client stuff of bringing in all the context things (like GlobalContext and one for reactQuery)
  * noteworthy stuff
    * was trying to use next to create HTML #[[interactive NFTs]] which is literally just HTML file - but learned creating one HTML file that can store all the JS and CSS together is toughhh with next. This is bc one of the big benefits of Next is code splitting which decreases your bundle size. If you need to do this - seems React is better - but dont have confirmation of that yet. EDIT: i think plain React was better, but still had some issues