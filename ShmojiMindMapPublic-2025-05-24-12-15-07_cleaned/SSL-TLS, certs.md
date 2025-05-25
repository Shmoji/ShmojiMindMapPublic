  * what is SSL/TLS? #memo ^gSXVN0MAF
    * me: protocol for securing network communications in multiple ways like encryption, certificates, etc. i interact with it most through HTTPS - which it is built into. it works for many kinds of network communications - not just internet connections. Ex: Many database systems use SSL/TLS to secure client-server communications without involving HTTPS (same for IoT devices/systems)
    * me: oh wow, i just realized how and where this is setup for web servers. You can do on app side, but usually it's in the reverse proxy. Reverse proxy executes SSL/TLS functionality and points to certificate. Q: how does the reverse proxy execute functionality of SSL/TLS and how does it get the certificate?
      * LLM: 
      * SSL/TLS Termination: The reverse proxy usually performs SSL/TLS termination, meaning it decrypts incoming HTTPS requests from clients and encrypts outgoing responses. This process involves:
        * Intercepting encrypted client requests
        * Decrypting the requests using the server's private key
        * Potentially performing additional operations (like load balancing or caching)
        * Re-encrypting responses before sending them back to clients
      * Certificate Management: The reverse proxy is typically configured with the SSL/TLS certificate for the domain it's protecting. This involves:
        * Storing the SSL/TLS certificate and private key on the reverse proxy
        * Presenting this certificate to clients during the SSL/TLS handshake
        * Managing certificate renewals and updates
      * Handshake Process: The reverse proxy handles the SSL/TLS handshake with clients, which includes:
        * Receiving the client's "hello" message
        * Sending the server's certificate to the client
        * Participating in key exchange to establish a shared secret
        * Setting up symmetric encryption for the session
      * Offloading: By handling SSL/TLS operations, the reverse proxy offloads this computationally intensive work from backend servers, allowing them to focus on serving content.
      * Security Enhancement: The reverse proxy can implement additional security measures, such as:
        * Hiding server IP addresses and architecture details
        * Implementing consistent SSL/TLS policies across multiple backend servers
        * Providing an additional layer of protection against attacks like DDoS
      * Certificate Verification: For backend communication, the reverse proxy may also verify certificates of upstream servers if SSL/TLS is used between the proxy and backend servers.
      * Flexibility and Centralization: Using a reverse proxy for SSL/TLS allows for centralized management of certificates and encryption settings, making it easier to update and maintain security configurations across multiple services
    * Secure Sockets Layer/Transport Layer Security
    * key features
      * Encryption: Converts data into an unreadable format that can only be decrypted by the intended recipient
      * Authentication: Uses digital certificates to verify the server's identity
      * Data Integrity: Ensures data hasn't been tampered with during transmission
    * Evolution from SSL to TLS
      * SSL was developed by Netscape in 1995.
      * TLS is the successor to SSL, introduced in 1999.
      * TLS is now the industry standard, though the term "SSL" is still commonly used
    * Q: can you have SSL/TLS without HTTPS?
      * YES, although HTTPS is one of the most common applications of SSL/TLS.
      * ## SSL/TLS Beyond HTTPS
        * Protocol Independence: SSL/TLS is a cryptographic protocol that can secure various types of network communications, not just web traffic
        * Other Applications: SSL/TLS can be used to secure:
          * Email protocols (SMTP, IMAP, POP3)
          * File transfer protocols (FTPS)
          * Instant messaging
          * Voice over IP (VoIP)
          * Virtual private networks (VPNs)
      * Q: can you have HTTPS without SSL/TLS?
        * NO. HTTPS is essentially HTTP traffic encrypted by SSL/TLS. When you see "https://" in a URL, it indicates that:
          * The website is using HTTP for communication
          * The HTTP traffic is being encrypted using SSL/TLS
        * In summary, HTTPS is intrinsically linked to SSL/TLS. The secure nature of HTTPS is entirely dependent on the encryption and authentication provided by SSL/TLS protocols. Without SSL/TLS, you would simply have standard HTTP, which does not offer the security features that define HTTPS.
    * CONFUSION POINT: mixed up SSL/TLS with how TUNNEL works. i thought it was: "ordinary NETWORK CONNECTION...EXCEPT: network-communication-protocol-formatted-data stored inside a different network-communication-protocol-formatted-data (encapsulation of network packets)" 
      * This doesnt happen for SSL/TLS. There's encryption at app layer and then everything is same as normal. Whereas tunnels get encapsulation crazay
  * questions
    * how does certificate like for HTTPS for SSL/TLS actually secure anything? and why do these certificate authorities (CAs) have that power? #memo ^VSGRIaZ-3
      * SSL/TLS certificates, which are used in HTTPS, secure communications over the internet primarily by enabling **encryption** and **authentication**
      * Q: who is authenticating?
        * called server authentication, so basically the server is - with help of CAs/certs/browser-trusted-CAs. Certificate process ensures that the client is communicating with the legitimate server it intends to connect to, rather than a malicious entity impersonating the server. So client is trusting CAs/certs/browsers and their trust list of CAs
      * 1. **Encryption (Securing Data)**
        * The website’s server sends its **public key** to your browser via its SSL/TLS certificate (which it generated keypair alone and got it signed by CA privKey)
        * Your browser uses this public key from website's server to encrypt data (like your login details) before sending it to the server (so browser actually doing the encrypting...cool)
        * Only the website’s private key, which is securely stored on their server, can decrypt this information, ensuring that the data stays confidential
        * Q: so does both the private and public key come from server of website? (and it gets to that server from the CA?)
          * Yes from server, no from CA. **Key Generation on the Server**: The website’s server generates a pair of cryptographic keys. Private key never known by anyone except server - not even CA
          * **Certificate Signing Request (CSR)**: The server then creates a **Certificate Signing Request (CSR)**, which includes the **public key** and some identifying information about the website (like the domain name). Once the CA is satisfied with the verification process, it **signs** the public key using its own private key. This creates a digital certificate that binds the website’s **public key** to its identity (thanks to trusted list of CAs being the interface and knowing details of your domain/etc)
          * ### During HTTPS Connection
            * When a browser/user visits the website, the server sends the **public key** (as part of the certificate) to the browser (happens during TLS handshake and can be seen in devtools network/security tab)
            * The browser uses this public key to encrypt data of user. Only the **private key** (which remains securely stored on the server) can decrypt this data (hence why hacking of TLS often involves control of user device or server device)
            * The browser can also verify the **CA’s signature** on the certificate to make sure the public key truly belongs to the website (this is next part on authentication)
      * 2. **Authentication (Trustworthiness)**
        * Besides encryption, SSL/TLS certificates also provide **authentication**, meaning that you know you’re/user/browser communicating with the correct website/server and not a fraudulent one.
        * The certificate contains information about the website's domain and the organization that owns it.
        * A trusted **Certificate Authority (CA)** verifies the identity of the website before issuing the SSL/TLS certificate by using its own privKey to sign server's pubKey (server devs or automation does this process)
        * Your browser automatically trusts these CAs because it has a pre-installed list of trusted CAs (root certificates) in its **trust store**.
        * me: thinking of this as authentications hurt my brain a bit. Feels more like external site/server is authenticating with you through interface with the trust network you are part of (trusted CAs and browsers)
      * NOTE: there have been recent sketchy stuff from CAs - so new models are being proposed. BUT overall they are trusted due to reputation, audits, etc. imo it feels like this could be a trustless process, but i also see benefits in having CAs - especially in certain sketchy situations...but also those benefits come at expense of risks of hacker getting in through that centralization