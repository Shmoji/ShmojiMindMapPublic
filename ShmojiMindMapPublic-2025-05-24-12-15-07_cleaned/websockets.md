  * tracking thoughts from other people
    * [[2024-05-02]]
      * Anselm Eickhoff: doesnt want to be married to websockets bc there's more interesting things coming up like WebTransport and QUIC that helps if you need to sync lots of values independently bc with websockets it's single TCP connection and can get Head of Line blocking where if you sync a huge value, everything else has to wait to be synced - whereas with WebTransport and QUIC you can sync stuff in parallel and prioritize it and gives lot smoother experience for complex apps. With jazz, you dont have to worry about any of this tho
  * tracking thoughts when setting up myself
    * [[2024-05-14]]
      * today i set it up in emote project on backend and frontend. was a bit more difficult since this project is already a bit further along, but eventually got it
      * biggest stuckpoint was not realizing i needed to set cors on backend when creating io variable - after that i finally started connecting from frontend
  * what are they?
    * client and server can talk in real-time without needing to continuously make requests like HTTP - only sends one initial request/handshake
      * altho, websockets are just HTTP upgrade - they use same TCP connection over ws:// or wss://
      * only sends headers once - in initial handshake where server and client agree to upgrade to websockets, that's only HEADER sent - the rest is just sending data back and forth
      * in network inspector, you can find that request by filtering by WS. Then you can click on "Frames"/Messages tab to see all data flowing
    * communication protocol that enables real-time, two-way communication between a client (like a web browser) and a server over a single, long-lived connection. They allow for continuous data exchange, making them ideal for applications requiring frequent updates or real-time interactions, like chat applications, online gaming, or collaborative editing tools.
  * questions
    * are websockets similar to HTTP?
      * GPT3.5
        * Yes, WebSockets are related to HTTP (Hypertext Transfer Protocol) in that they both facilitate communication between clients and servers over the internet. However, they operate differently:
          * HTTP: It's a request-response protocol, meaning that a client sends a request to the server, and the server responds with the requested data. Each request establishes a new connection, and once the response is sent, the connection is closed.
          * WebSockets: Unlike HTTP, WebSockets allow for bidirectional communication, where both the client and server can send messages to each other at any time over a single, long-lived connection. This enables real-time, full-duplex communication, making it suitable for applications that require constant data exchange without the overhead of repeated connection establishment like in HTTP.
        * In summary, while HTTP is suited for traditional web applications where data exchange is initiated by the client's requests, WebSockets are designed for applications requiring real-time, continuous communication between client and server.

    * does websockets clash with session-based auth - like sign in with X?
      * no, it seems not. Actually maybe quite useful to use your session token to identify user when they connect to websocket server
    * would websocket server have to be different server than the backend API server?
      * No. In fact, many WebSocket implementations are built into the same server as the backend API to simplify the architecture and reduce latency.
    * is a websocket connection made for each user?
      * yes almost always. separate websocket connection and thus separate TCP socket per user/client.
        * interesting note: TCP sockets are identified by a unique 4-tuple (source IP, source port, destination IP, destination port), allowing servers to handle over 65,536 concurrent connections by utilizing different source ports
      * This allows the server to independently send and receive data to/from each connected user over their individual WebSocket connection. Having separate TCP sockets per user enables efficient real-time communication, facilitating independent state management and messaging for each client.
      * while the WebSocket protocol itself is full-duplex over a single TCP socket, web servers typically open a new WebSocket connection per user/client to facilitate independent communication channels
    * what are alternatives to websockets?
      * up and coming
        * WebTransport
        * QUIC
      * maybe outdated, but still used
        * short polling
        * long polling
        * server sent events