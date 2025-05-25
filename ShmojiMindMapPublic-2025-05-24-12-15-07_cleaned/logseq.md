  * tracking thoughts
    * tracking thoughts on syncing
      * [[2023-12-29]]
        * found out you need to git pull from command line if using desktop version after commiting using mobile version...yea that makes sense

  * what is it?
    * Logseq is a block-based outliner, allowing you to organise information into a tree-like structure using bullet-points (just like Roam) ^DPxDXucS4
  * difference between logseq and [[obsidian kms]] ^HsMpakwVa
    * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/logseq#^DPxDXucS4|Logseq is a block-based outliner, allowing you to organise information into a tree-like structure using bullet-points (just like Roam)]] - and [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/obsidian kms#^cw9subMsu|Obsidian is a page-based application that functions like a long-form text editor, similar to a Microsoft Word document.]]
  * useful things that could be created for logseq
    * automate process of syncing using git
  * questions
    * what is the benefit of Roam over logseq
      * Roam is web-oriented, so i can just sign in on web very quickly and edit notes. Downside is roam is like $15 per month and they can delete access to your data at any moment (centralized entity). But it also gives you ability to make your graph public if you want (and i do) and you can export your data with like 2 clicks. So anyone can see your daily notes real-time which is awesome.
      * Methods to sync data on logseq:
        * 1) their $5 per month sync service (doesnt make it a public webpage tho, just allows owner to sync across different devices)
        * 2) use github - but requires commiting every single darn change yikes. EDIT: just found out they have setting that does this automatically every x amount of time you set - it's seamless
      * Methods to make logseq graph public:
        * Use some random github repo that turns your graph into webapp and publishes it. Again, gotta commit changes and relying on their frontend design - which are 2 issues. Although, can also code it yourself, but prob not easy
    * why choose logseq over Roam
      * if privacy matters to you - you can get complete privacy with logseq
      * if you want OFFLINE version of your Roam graph (this could be v important)
      * if you want to BACKUP your roam graph AND have it with same nice visuals (basically same point as one above but emphasizes can use logseq as a backup)
      * Their Graph view seems much better than Roams
      * Their whiteboard feature seems really nice for visual people and idea-generation
    * is logseq completely open source?
      * it appears so, but should do more research
    * how is data stored in logseq?
      * ME: on your local device and that's it - unless you setup some cloud solution - which is not the default
      * The files in Logseq are stored locally on the disk of your device, making it possible to work offline. All the files created by Logseq sit on your local hard disk and are not stored in the cloud. You are the master of your domain, you take ownership and responsibility for where your data is stored.
    * can you make your logseq data public?
  * how TOs
    * how to setup git for syncing data
      * tracking retries
        * [[2024-04-26]]
          * today decided to get shmoji universe graph on my laptop so had to do this
          * 1) i cloned repo to laptop
          * 2) instead of doing auto commits, i decided to use logseq plugin to manually do all git stuff myself instead of commits happening in background. i guess decided this bc i have to do same on phone. if phone would autocommit, then maybe id change this decision
          * that was it
      * desktop: make root of logseq graph git repo attached to remote repo. Then, follow this: https://github.com/CharlesChiuGit/Logseq-Git-Sync-101/wiki/For-Windows-users. there's Good and Geeky video that is better tut than this guide tho.
      * android: pain in the ass, but possible: https://github.com/CharlesChiuGit/Logseq-Git-Sync-101/wiki/For-Android-users
        * tracking thoughts
          * [[2023-12-05]]
            * my phone did not have .shortcuts, but i figured it out [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/termux#^qRlZgGsT0|Termux:Widgets from F-droid]]
            * another hard part was just finding out where the paths i needed were on my phone and then typing errthing out. grep and copy/paste came in handy
            * then i got stuck with an error related to GIT_DISCOVERY_ACROSS_FILESYSTEM - basically git having trouble due to termux env being separate from phone filesystem. Fix is to add setting of that env var into push script
            * also i may need to find a way to not need my github user and pw every single time

