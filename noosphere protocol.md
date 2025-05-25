  * tracking thoughts
    * [[noosphere TODO and my sentiment on using it]]
    * tracking trying to setup noosphere typescript https://github.com/subconsciousnetwork/noosphere/tree/main/typescript
      * [[2024-01-23]]
        * seems only linux and mac support for dependences, so WSL it is
        * i think maybe for certain tests using webdriver you need to go into "Downloads\chromedriver_win32" and run that application?? idk tho
        * cargo test didnt work in WSL - always hangs - even tho i installed everything on WSL, somehow cargo test worked on windows
      * [[2024-01-25]]
        * okay so im trying to do setup on windows even though team has never done it before. Maybe i can lead the way since it is OS project. If this doesnt work i will try docker of linux distro
        * okay so i installed all dependencies through a mix of getting executable installs and using chocolate and converting the linux commands in noosphere tut into windows commands using GPT. that worked. Then all tests worked except one using webdriver. it said noosphere crate cant be found
        * think i finally fixed that by going into /rust/noosphere and running cargo build - i found that at top level cargo.toml. Think this worked. But now i have new errors
      * [[2024-01-28]]
        * jesus christ finally figured out how to get past the rust setup. Last error was something about cc. Found out i was running out of ram, so i had to increase RAM my docker container and WSL could use. This fixed it yayyy
        * tear tear, but chromedriver cargo test still fails. EDIT: found in .github/workflows/run_test_suite.yaml how to download chrome and chromedriver from cli and then run this test successfully
        * also learned and documented tf out of [[selenium]] and [[webdriver, chromedriver]] 
      * [[2024-01-29]]
        * omg if i run app in docker container, i cant use that in browser outside container unless i do port forwarding nonsense. Making the decision to retry WSL again since i figured out that RAM issue. Prayge
        * WSL hangs on cargo test fuuuuuuuuc
      * [[2024-01-30]]
        * when i first created docker container i mapped 3000 to 3000. Luckily, found way to change port in config file in container for noosphere-guide so i could access it in browser outside container. WOOO first running app
        * according to cdata on discord, this link and discord are best place for docs rn: https://docs.rs/noosphere/latest/noosphere/
      * [[2024-02-01]]
        * tried getting sphere-viewer and orb ts packages working, but sooo many errors
        * first error:
          * :x: [generate_wasm] exited with exit code 127. Output:
          * /bin/sh: 1: ./scripts/generate-wasm-artifacts.sh: not found
        * first fix: in package.json for orb, use this "command": "/usr/bin/bash './scripts/generate-wasm-artifacts.sh'", bc otherwise it uses sh and it just doesnt work.
        * okay i undid the last point and that error is still gone....huhhhhh. Maybei showed it where bash was and then it was somehow now good idek. EDIT: the actualy fix was changing from CRLF to LF (line endings)
        * then i ran into errors with .d.ts files. Inside they just had like /lib files - but no imports or exports. I literally fixed this by deleting the src/ versions that were symbolic links that are literally in the github repo. They were maybe needed in the beginning to do the build?? but maybe okay to delete once lib/ is generated??? idk
        * then ran into issues of index.ts and test importing noosphere.js from wrong place instead of lib/ - easy fix to import from lib - but i have hint that this could cause issue in long run
        * /bin/sh: 1: ./scripts/finalize-index-html.sh: not found
          * solved: change CRLF to LF just like before
        * okay everything builds yay
        * npm run serve of sphere-viewer put it on wrong port since i only have one port forwarding from docker container to outside device. Fixed this by changing sphere-viewer package.json serve command to this "command": "web-dev-server -r ./dist --port 3000"
        * now i got sphere-viewer running but just infinite loader in browser...what next? rethinking why i even started diwn this route (hint: to build my project on top of this)
        * random note: i had to run exit command a billion times to get out of docker container and then i saw a bunch of bash commands, so i may have nested a crap ton of bash instances woooops
      * [[2024-02-10]]
        * im trying to get index.test.js inside orb package to run because i realized it is example of using noosphere to read and write data - but cant get it to work due to some error maybe related to puppeteer, chrome, or something
        * i double checked and cargo tests still work - even one that uses chrome. So why doesnt this chrome tests work? is it bc these are ts instead of rust or wasm?
        * AHA i got ORB unit test working. i had to add some code to web-test-runner.config.js - i think that somehow got puppeteer to use the right version or something idk. [dis](https://modern-web.dev/docs/test-runner/browser-launchers/overview/#configuring-browser-launchers) da code

  * questions
    * if all data is stored local first, what if you have a TON of data and it cant all fit on your device?
    * what is orb?
      * orb is kinda like git except your own local git
    * me: does noosphere deal with creation of data schemas at all? Like if you're dev making app similar to Subconscious, would noosphere be a part of the process for creating data schema and models for your app? Or would that all be handled by your app?

ive read some of the swift code of Subconscious and see it's using SQLite3

not sure i know the right question to ask, but maybe im confused about how an app (such as subconscious) connects to noosphere. If i created MVP app and connected to noosphere, what would that code look like? (although im not apple dude, so not too interested in swift)
      * gordon:
        * Noosphere deliberately has no opinions about data schema. It's a general-purpose protocol like HTTP. Memos (the core data structure) contain key-value headers, and a body part. A Content-Type header tells you what the schema/format of the body part is (this is also how HTTP and email work)
        * Our feeling is having schemas as a separable layer on top of the lower-level protocol allows for evolution and innovation https://subconscious.substack.com/i/40057285/allow-all-bless-some
        * Re: how does an app connect to Noosphere? The literal answer is over HTTP to the gateway, but the practical answer is that you would use the rust client library. This handles all the details of signing and syncing local-first data.
    * how is it different from Ceramic?
      * it is use-case driven towards enabling decentralized note-taking / knowledge-creation - whereas Ceramic is open-ended or not use-case driven
