  * what is ping? #[[fast memo]] ^of7_6QQAG
    * ME: program/tool to measure the time it takes for a packet of data to travel from YOUR device to a remote host (like game servers in their network) and back. You want it low.
    * BAD PING: Bad ping is more frequently a problem due to the player's network connection (local setup), distance from servers, or internet quality (ISP stuff).
    * Q: isnt player's network connection same as internet quality?
      * **Network Connection**: This term refers more specifically to the player's local setup. It includes things like the **type of connection** (Wi-Fi, wired Ethernet, 4G/5G mobile), the **router quality**, and **signal strength**. Issues here might include poor Wi-Fi signal, outdated routers, or interference in the local network.
      * **Internet Quality**: This refers more broadly to the overall **performance of the internet connection** provided by the ISP (Internet Service Provider). It includes factors like the **bandwidth** (upload/download speed), **latency**, and **packet loss**. This could be affected by things like network congestion, the speed tier you’ve subscribed to, or problems on the ISP’s infrastructure. NOTE: ur local stuff can affect these too
      * ping vs latency: ping is tool that measures latency. latency is the time delay of round trip data packet from device to remote host. altho, they often used as same word. The measurement can describe delays in various parts of the network, including within the user's local setup, the ISP’s network, or the destination server - as just described b4
    * GOOD PING: 0–30 ms is good. Anything more starts getting more average and then bad
  * questions
    * what is point of it, usecases, why
      * verifying that the target host is available
      * determining round-trip time (RTT) or latency
        * RTT is a measure of how long it took to receive a response. Measured in milliseconds (ms), the process starts when a browser sends a request to a server and is completed when a response from the server is received. RTT is a key performance metric of web applications.
    * what ping do you want?
      * a lower ping is generally better for gaming because it means less delay in communication between your device and the game server, leading to a more responsive and enjoyable gaming experience