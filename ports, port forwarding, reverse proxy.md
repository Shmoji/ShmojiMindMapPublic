  * what is a port? #memo ^PdV9FA9E_
    * basically an ID or endpoint to access and direct data to a specific service or application within a device and network. the ip address/domain name IDs the network and then the port IDs the app/service/whatevs which is ran on some device(s) on the network
  * what is port forwarding #memo ^IcBxwHC5P
    * meme: literally just opening a port to public to access resource there
    * you got private netty. you FORWARD certain things through to certain devices/apps OR reject certain incoming traffic
    * part of ingress
    * Port forwarding is a technique used to allow external devices to access services on a private network. Here's how it works:
      * Purpose: It directs incoming traffic from the internet to the correct device on your local network.
      * Process:
        * You configure your router to forward specific ports to particular devices on your network.
        * When external traffic arrives on those ports, the router knows which internal device should receive it.
    * Security Considerations:
      * Only open necessary ports to minimize security risks. Remember, while port forwarding can be useful, it also exposes your devices to the internet, so it should be done carefully and with proper security measures in place.
      * Use a firewall to protect against unauthorized access.
    * often people setup reverse proxy server listening on 443 and 80 and only port forward those ports for that reason. Traffic then goes from reverse proxy to port of service where app/service is running (which could be many different devices on netty bc of load balancing. 4 same reason could also be one of many app instances with different ports running on one single device)
  * what is reverse proxy? #memo ^_RLyO7df7
    * A reverse proxy is a server that sits between client devices and web servers, acting as an intermediary for requests from clients seeking resources from those web servers.
    * seems like it can do all kinds of different functionality
    * not REQUIRED for security, but definitely adds more security
    * seems it can make handling certificates for SSL/TLS much easier to create and update. Otherwise your backend handles certs and likely have to shut down API each time you update - dont have to do that with reverse proxy
    * Q: do most backend api servers use reverse proxy?
      * While not mandatory, reverse proxies are commonly used with backend API servers due to the numerous benefits they provide in terms of security, performance, and management. For home server setups, the decision to use a reverse proxy depends on your specific needs and the complexity of your setup. As your infrastructure grows or if you're exposing services to the internet, implementing a reverse proxy becomes increasingly beneficial.
    * Nginx and Apache are both web servers that can be configured to act as reverse proxies. So they can be the proxy between incoming connections and your API server. How it works:
      * Express.js API runs on localhost:3000 (or another port)
      * Nginx/Apache listens on port 80/443 (gotta make sure those ports are open/port-forwarded in router settings - or external devices cant access)
      * Nginx/Apache configuration FORWARDS requests to localhost:3000
    * prob important to note this can run on any device on the network. just another app running constantly - like a bodyguard to your server
    * Q: why is it called a reverse proxy
      * bc it reverse of forward proxy which sits in front of clients and receives/sends requests from those clients to servers and returns responses from servers back to clients. Whereas reverse proxy sits in front of servers and receives requests from clients and sends those to servers. then returns responses from server back to client.
      * The verb "proxy" means to act as a substitute or representative for someone else.
      * me: it's reverse bc it's not A CLIENT'S proxy. it's a proxy for A SERVER - representing that server (both input AND output). forward proxy is representing CLIENT UR USING (input AND output). me: client is closer to you so just easier to remember that is forward and client represents you better (and thing further from you and representing others, so it's reverse). kinda confusing but kinda makes sense
      * Q: wouldnt the forward proxy of someone else be a reverse proxy for you?
        * no bc it's based on config and architecture.
        * Even if you're interacting with someone else's forward proxy, from your perspective, it's still functioning as a forward proxy because:
          * It's configured on their client side
          * It's helping their clients access external resources (which might include your server)
      * The reverse proxy represents and acts on behalf of servers, which is the "reverse" of how a forward proxy operates
      * Perp: Key Differences
        * Direction of proxy: A forward proxy proxies outgoing traffic from clients, while a reverse proxy proxies incoming traffic to servers
        * Client awareness: With a forward proxy, clients are typically aware they are using a proxy. With a reverse proxy, clients are usually unaware - they think they're communicating directly with the server.
        * Purpose:
          * Forward proxies are often used for client anonymity and accessing restricted content
          * Reverse proxies are used for load balancing, security, caching, and other server-side optimizations
        * Location: Forward proxies are usually closer to clients, while reverse proxies are closer to (or part of) the server infrastructure
  * how TOs
    * how to use port forwarding to direct incoming traffic to your custom expressjs api backend domain name pointing to home server ^Jn2-RYXLi
      * NOTE: it depends if using reverse proxy or not
      * NOT using reverse proxy
        * in router home page, setup port forwarding straight to port your app is running on and local IP of device
      * using reverse proxy
        * in router home page, setup port forwarding for 443 and 80 for HTTPS and HTTP to direct to local IP of device running API app
        * then, reverse proxy config will define to FORWARD to correct port of the API app (like 3000)
    * how to setup reverse proxy
      * NOTE: reverse proxy has many functionality - you can decide which ones to use. i want basic setup and certs for HTTPS/TLS/SSL for my home server. No load balancer yet
      * used this vidya: https://www.youtube.com/watch?v=YH0guj1kFxI
      * basics of setup:
        * install nginx: apt install -y nginx
        * sudo nano /etc/nginx/sites-available/default
        * copy and paste and edit server block from vidya and save - points port 80 (incoming traffic to ur netty) at your running app and port it's on
        * systemctl restart nginx
        * make sure everything is good with nginx and config:
          * nginx -t
          * systemctl status nginx - then check if it says active
        * at this point your domain can prob access your running local app, but just on HTTP
      * setting up HTTPS/TLS/SSL and certs and whatnot:
        * install certbot: apt install certbot
        * install nginx plugin for certbot: apt install python3-certbot-nginx
        * use command to issue the certificate for your domain: certbot --nginx -d api.domain.com
          * after command it shows locations of certs and keys
          * this will auto-edit your server block config for nginx - but still need to add few other things
          * on both listen directives auto-added, add http2 like in vidya
        * systemctl restart nginx
        * certbot already automates the renewal process for your cert once expired. Cron Job or Systemd Timer: Most distributions automatically install a cron job or systemd timer to handle regular renewal checks. This is typically set up during the Certbot installation process.
      * enable firewall
        * not even sure this is part of reverse proxy aspect, but vidya does this
        * ufw status to check if active
        * ufw app list to check options to use
        * ufw allow 'Nginx Full'
        * ufw enable
        * ufw status

  * questions
    * so if you port forward port 80 and 443 to a local device - this wont cause internet issues for other devices on the network that are just trying to play games and watch shows and whatnot
      * no wont cause issues
      * there's a difference between NEW connections and ongoing - outgoing connections for your devices doing gaming/whatevs are obv ongoing once data comes back and thanks to NAT it is known they were initiated inside ur network
      * When your device (the client) initiates a connection, it uses a randomly assigned high-numbered port (usually between 49152 and 65535). it connects to the server (maybe youtube?) through 443 (https). Then data is returned in reverse order (NAT membuhs this stuff as an ongoing connection)
      * Port forwarding rules for 80/443 only affect NEW incoming connections
      * They don't impact the return traffic for connections initiated from inside your network
    * do i need to open just the port to my expressjs api app - or do i need to port forward 443 and 80 too?
      * depends if using reverse proxy or not: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ports, port forwarding, reverse proxy#^Jn2-RYXLi|how to use port forwarding to direct incoming traffic to your custom expressjs api backend domain name pointing to home server]]