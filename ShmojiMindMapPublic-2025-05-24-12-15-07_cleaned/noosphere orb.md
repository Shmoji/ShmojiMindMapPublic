  * what is it?
    * this is the CLI of noosphere (not just a TS thing - typically referencing rust implementation)
  * how TOs
    * how to get orb command working in cli
      * open admin command prompt and paste: docker run --name noosphere-container -e HOST_IP=192.168.1.9 --expose 3000 -p 3000:3000 -v //c/Users/jackj/Projects/noosphere-stuff/noosphere:/src -t -i tecnickcom/alldev /bin/bash
      * this creates docker container for noosphere using a linux OS template (bc they didnt build it for windows so who knows if you can get windows working). It also hooks src inside docker container to //c/Users/jackj/Projects/noosphere-stuff/noosphere - which is noosphere repo you should have cloned from github
      * install rust which also installs cargo - which is what is needed: https://rustup.rs/#
      * after install, the terminal tells you to do some other command, make sure to do that
      * go to src/rust/noosphere-cli and run "cargo install --path ."
      * so i guess this means you dont need to cargo install all noosphere crates to use orb? just need the cli crate i guess
  * questions
    * what are steps to use orb (in general if getting started)
      * 1) create key for yourself - orb key create <nameOfKey> 
      * this gives you DID to identify key
      * 2) create folder for your sphere and cd into it
      * 3) initialize sphere using orb cli - orb sphere create --owner-key=<nameOfKey>
      * NOTE: so a key/DID owns a sphere
      * DID created to identify the sphere. You also get a secret phrase that can use to change OG owner-key in case OG key gets compromised or just need to rotate or whatevs. So obv, dont let anyone know secret.
      * after creating sphere there is already .sphere folder - which contains all sphere content - very similar to .git folder
      * 4) create file into sphere folder (tut uses .subtext file - does it only support subtext bc idk??)
      * can check changes using: orb sphere status in folder of that sphere
      * 5) orb sphere save - actually saves updated file(s) to your sphere. But doesnt do much if only local so far. Need to setup gateway to sync data back and forth between gateway and sphere
      * 6) do same process on another device - so create key for gateway and sphere for gateway
      * 7) take DID of sphere on local machine to tell gateway that is the sphere it wants to receive updates from: orb sphere config set counterpart <DIDofSphere>
        * this is pain bc you have to get DID from one device to the other
      * 8) on gateway: orb serve -i 0.0.0.0 (bind to all interfaces on this machine - i think could also use IP address here and that's more specific??). You can choose port here with "-p <port>". I had to choose port 3000 bc when i setup docker container - i bound port 3000 in container to 3000 on host - so can only access inside container with 3000
      * 9) get IP of gateway with ifconfig (eth0 inet number) or ipconfig on windows (ipv4). Since in docker container, i had to get IP of device running container. On local client sphere do: orb sphere config set gateway-url <ip> (http://<ip found with ifconfig>:<port you see after running orb serve>)
      * 10) orb sphere sync - on local client - and then should see data go from local client to gateway
      * at this point it looks like the sync worked (despite not getting same terminal messages as tut) - but i noticed i dont see the actual files i created in the gateway. maybe they arent visible like that on a gateway? maybe theyre indexed or something.
      * tut note: every client should have one key. But does this mean every sphere should have one key? Ex: i dont have 3 devices for this tut so if i make another sphere...does it need another key too?
      * 11) create new key in same way (im doing on same laptop so we'll see how it goes)
      * 12) on 2nd sphere: orb sphere join --local-key <2ndKeyNAMEnotDID> --gateway-url <url> <DIDof1stsphere>
        * ex: orb sphere join --local-key other-shmoji --gateway-url http://192.168.1.4:3000 did:key:z6Mkhj4BF7fDQZEWeKbpqBUiM3gEM7nXEtFCozDKxhAEiFVt
      * 13) it will give orb sphere auth command - copy and paste and run it from 1st sphere
        * you do this and this authorizes 2nd key to access 1st sphere
        * IMPORTANT: You MUST sync the 1st sphere to enable your gateway to recognize the authorization
        * another interesting note: the auth itself gets an identity - this is what you enter back at the other-shmoji client to save the auth
      * final thoughts
        * orb sphere save - this seems like git commit
        * orb sphere sync - this seems like git push and git pull
  * questions
    * where are CLI commands defined in code?
      * rust\noosphere-cli\src\native\cli.rs is maybe most top level declarations of cli commands
      * rust\noosphere-cli\src\native\mod.rs and then they call the actual method that is imported in. you can search repo for method they call to see functionality