  * tracking thoughts
    * [[2023-12-05]]
      * Ran into permission issues with termux-setup-storage which allows you to access your phone's regular storage in termux (bc termux uses separate isolated storage). Basically the fix was going into termux app settings, revoking permissions, clearing cache, regiving permissions, reopening termux and rerunning termux-setup-storage

  * noteworthy stuff
    * there is difference in Termux on Google Play and F-Droid - research this difference if it ever comes up lol
  * termux plugins
    * Termux:Widgets from F-droid ^qRlZgGsT0
      * tracking thoughts
        * [[2023-12-05]]
          * on install, supposed to create .shortcuts folder, but did not for me. Nice - you can just create it yourself. GPT4: Once the .shortcuts folder is created, you can place executable scripts or create symbolic links to scripts within this folder. These scripts then appear as widgets that you can add to your home screen, allowing quick access to various functions or commands within Termux.
          * this process is crucial for git sync of logseq graphs
