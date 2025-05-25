  * tracking thoughts
    * tracking progress with setting up
      * [[2024-03-21]]
        * the github says "oh just run this docker command" and then it didnt work
        * ended up i just had to change the first port to 3001 because 3000 was taken - this is the host machine port and next port is one used inside docker container
      * [[2024-04-10]]
        * soemtimes if you run docker container and everything looks good but still doesnt run, try deleting container and recreating with port 3001 for host machine instead of 3000 - sometimes port 3000 is taken for no friggin reason

  * what is it?
    * this is basically everything ChatGPT can do except local holy crap
  * how TOs
    * how to setup vocally talking
      * open settings and make speechtotext engine local whisper. if you want to only start record your voice when you decide, keep "conversation mode" off.