
  * how TOs
    * how to setup DDNS using cloudflare and crontab for automating this script on linux
      * used this vid: https://www.youtube.com/watch?v=rI-XxnyWFnM&t=141s
      * you basically write/use script to every x amount of time (thanks crontab) to run your script and set your ONE domain to point to public IP address if it changed from last time (bc dat thang dynamic)
      * NOTE: you could just put this on raspberry pi if worried about resources this automation uses. But LLMs say it's such little resources, could just run on your backend server if you want
      * clone repo, cd in, nano or vim into template, add in ur info as seen in vid
      * ONE DIFF FROM VIDYA: set auth_method to "global" instead of "token"
      * run script once to test it and check in cloudflare to validate
      * run: "crontab -e" and here you can create new cronjobs that will start running as soon as u save dat shiz
  * related
    * [[domain name]]