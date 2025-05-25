  * tracking thoughts
    * tacking learnings
      * [[2024-08-01]]
        * CORS allows you to block domains from calling your backend api, BUT it doesnt block curl or postman requests
        * it is good way to only allow your frontends to use your backend
        * it's interesting to think about if my auth system requires a browser to work - or could it work through curl/postman...tbh idk
      * [[2024-11-14]] why cant local frontend files on computer use other local files inside of them bc blocked by CORS when using through browser? memo Qs below #[[fast memo]]
        * OBSERVATION: just opening file in browser no work when using files inside files (even if path of files correct)
        * me tryna recall rn, come back next time and try to see if i can delete a lot and just keep this (likely not but who knows)
          * browser default enforces sameOrigin policy
          * CORS is config that relaxes SO-pol
          * CORS originates and is controlled from server, but enforced by browser
          * SO-pol blocks all other local files for file protocol bc only that one local file is being served and any other local file is considered not SO
          * file protocol riskyyy bc inputs/fileinput libraries can be exploited as vulnerabilities to access other local files. This bc local file being viewed is served from local file system - rather than being served from HTTP server which only allows access to those files being served - cant access local file system nope nope
        * When you try to load local files (e.g., using file:/// URLs) in a browser, you often run into CORS (Cross-Origin Resource Sharing) issues because browsers consider local files as separate ORIGINs. The security policy Same-Origin Policy (SOP) prevents files from different origins from accessing each other, even if they're local. CORS is essentially a way to relax the SOP and enable controlled cross-origin access.
        * SOP izza security measure of BROWSERS. CORS is way to config/relax this security measure
        * **Security decision**: The server is the owner of the data and decides who can access it. By configuring CORS, the server asserts which origins it trusts and under what conditions the data can be accessed.
        * NOTE: CORS only useful if server ur interacting with is not adversarial
          * **Client-Side Only**: CORS policies are enforced client-side by browsers. If the server is compromised, it can simply ignore these policies or set them to be overly permissive, which browsers will then FOLLOW.
          * **No Protection Against Server Misbehavior**: CORS does not protect against SERVERS that might misbehave by sending incorrect or harmful data back to clients, EVEN if the origin checks are bypassed.
        * analogy: Think of CORS like a **guest list** for a private event. The **server** is the host that creates the guest list (CORS configuration). The **browser/SOP** is the security guard at the entrance, checking guests against the list. Even though the security guard enforces the rule, the host (server) sets who is allowed in...for YOU the user of browser/site. They could let you in and then kill you lol
        * so in the past, my backend of different origin needed to use specific header to allow frontend of differing origin to request the endpoint that sets cookies
        * FIX of OG issue: run HTTP server in your project folder using "python -m http.server 8000" - This will serve files from the CURRENT directory at http://localhost:8000 - iz like making HTTP API that serves those files in that directory #[[how to run quick http server]]
        * Q: what is a local server?
          * a software program that runs on your computer and serves files or data over a network—essentially allowing your computer to act as a mini web server. It uses the http:// or https:// protocol to make your files accessible in a way that mimics how web servers work on the internet (HTTP requests/responses)
          * A local server listens for HTTP requests (e.g., opening a webpage) on your local network (localhost). When you navigate to http://localhost:8000, the server receives the request and responds with the files or data in your project directory. (can request using curl too)
          * This is more secure and compatible with modern web practices compared to the file:/// protocol, which runs directly from your file system and lacks the protections and capabilities of a server-based environment.
          * browser executes frontend stuff in sandboxed env away from local file system. Only files served from that origin are allowed. File protocol serves from local file system and vulnerability could be used in that one file to access other local files
        * Q: in localhost, if you call a backend endpoint from frontend and then that backend endpoint calls a different API endpoint...will CORS block that?
          * No bc When your backend (e.g., http://localhost:5000) makes a call to another API (e.g., https://external-api.com), this is a **server-to-server** request. Browsers are not involved here, so CORS does not apply.
          * BUT if your backend or some other API tries to set/read cookie on your frontend, THAT will be blocked by CORS if needed CORS headers not set up to allow that origin to do that
        * Q: cant anyone on the network access your localhost (127.0.0.1) server tho?
          * actually nope, just your device. if u want this, set static IP for ur device and make sure other person knows what port ur app is on
        * Q: if file:/// is more local, how is it more dangerous and gives more access to local resources even tho CORS doesnt allow it?
          * iz bc file protocol doesnt have much security measures
          * note: while SOP and CORS do prevent file protocol from using imported files, the vulnerabilities below could allow user to use them anyways and it would work! imagine using html input to somehow access a local file
          * ex of vulnerability: html input, FileReader API. So origin could be in some far away folder on compooter and thaz AOKAY to change with file protocol. Whereas http protocol, SOP, and CORS no allow this
        * Q: tying this back to something tangential
          * CORS does not work for securing or limiting your backend API, you need server-side controls like authentication, authorization, IP whitelisting, and rate limiting. CORS should not be relied upon as the sole means of preventing unauthorized access to an API.
          * oh wowww, yea, i just used from rando directory: curl http://localhost:8000/PointerLockControls.js and it got the file from the running local server. 
          * oh woww x2 - i just did curl of w backend api and yep it gives you data right away. While all that CORS stuff protects from browsers...defs doesnt protect access from non-browser sources (origin null). i did same thing from termux on my phone lmao
        * Q: do people typically secure frontend files or no? just wondering since curl could be used to fetch them
          * not really. Keep server side if need security
          * **Minification and Obfuscation**:
            * **Obfuscate your JavaScript** to make it harder to understand if someone tries to inspect or copy your frontend code. Tools like Webpack, Terser, or UglifyJS can minify and obfuscate your files. NOTE: this is just one thing webpack does and not main thing
            * **Note**: This doesn't make your code truly secure but can act as a deterrent for basic users or scrapers.
        * memo updates
          * [[2024-11-20]]
            * ur browser executes stuff, so you dont want bAd origins returning you results that then get executed to do bad stuff (so SOP blocks all origins except one of website currently on and CORS has config (defined by server of that site) saying what origins are allowed)
