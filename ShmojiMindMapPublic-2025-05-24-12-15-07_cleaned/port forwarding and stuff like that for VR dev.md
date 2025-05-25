  * what is port forwarding?
    * using example: Any time you browse to a given local port on your Quest (e.g. http://localhost:1234), we want to forward that to a port on your computer. Fortunately, adb has built-in support to do this sort of port forwarding!
    * Regular port forwarding means we would be forwarding a port from our computer to a port on the Quest (or whatever)
  * what is reverse port forwarding?
    * route from one port on your Quest’s (or whatever) localhost back to one on your computer — so that’s considered “reverse” forwarding.
  * how to debug built web app when local network ports are blocked
    * build web app
    * use "npx vite --host" to start local web server
    * "adb reverse tcp:3000 tcp:5173" (5173 was default that vite used - use whatever port vite uses) (3000 can be anything - i just made that up)
    * open https://localhost:3000 on browser in VR headset and boom - works