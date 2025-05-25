  * tracking thoughts
    * tracking learnings from experiences
      * [[2024-09-17]] first time using ngrok, what is ingress? #[[fast memo]]
        * it allows you to run localhost backend (like expressjs api) and get secure public URL for anyone on internet to access your localhost app
        * their site: ngrok allows you to create secure ingress to any app, device or service without spending hours learning arcane networking technologies.
        * ingress: BODYGUARD process. process or method by which external traffic (typically from the internet) is allowed into a network or system, often through a specific entry point. "in"
        * Q: how does ngrok make your localhost app accessible to public?
          * by creating a secure tunnel between your local machine and an external, publicly accessible URL (which is ngrok cloud servers basically).
          * user accessing ur pubLink: domain -> ngrok pubIP of cloud servers network -> some port of theirs (maybe multiple redirects) -> to your pubIP of privNetty -> to localhost port running from your device (using encapsulated tunnel and outbound connection instead of inbound, so skips certain security measures)
          * NOTE: i learned what a tunnel is due to this, but not memoing here
          * **Ngrok Client**: Ngrok runs as a client on your local machine. When you start Ngrok with a command like ngrok http http://localhost:3000, it opens a connection to the Ngrok cloud service.
          * CONNECTION INITED FROM INSIDE: One of the main reasons Ngrok can access your local server is because the connection is initiated from **inside your network** (your local machine running the Ngrok client). This bypasses typical firewall and Network Address Translation (NAT) issues that prevent unsolicited incoming traffic from reaching your local server.
          * you dont have to open any ports on your router/network thanks to tunneling
            * Since the connection is initiated from your local machine to the ngrok server (outbound), there’s no need to open the port on your router or firewall to allow inbound connections.
            * Inbound traffic to your local service is handled by ngrok, which means you don’t have to configure your router or firewall to permit that traffic.
            * HTTP traffic (App Layer 7) is encapsulated inside SSL/TLS (Transport Layer 4) so it's skipping security measures of higher layers of OSI model IN LOCAL DEVICE'S NETWORK. those higher layer's still provided by ngrok servers and this security vulnerability is only bc YOU initiated an OUTBOUND connection (opposed to inbound person trying to access ur network). NOTE: for inbound packets, ur router is checking security of higher layers. For outbound, daz you so it aint. ngrok inited outbound connection bb
            * so networks know when connections are JUST transport layer vs connections that are higher level like HTTP
            * basically: bc it's outbound, dont gotta worry about ports and higher layer security (for outbound or inbound traffic - it's skipping that part of ur networks security bc outbound) but HAS to be Layer 4 connection. bc it' using tunneling, you can still send data AS IF HTTP is being used
          * NOTE TO SELF: this is how easy it is to get hacked lmao. install ngrok/whatevs and then shoot the connection request from inside