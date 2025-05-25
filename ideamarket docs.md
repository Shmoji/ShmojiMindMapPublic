  * anything twitter related
    * Twitter widgets API is inited inside app file in useEffect. For some reason, adding it to head tag just doesn't work
    * what i learned
      * Fastest method is to call Twitter APIs on backend and build custom tweets on your frontend
      * Using twitter factory functions is too tough because API to pull all posts gets called multiple times causing duplicate embeds and you have to wait for window.twtr.widgets to load and that is part of DOM, so all logic has to be in useEffect and it just gets too complicated.
      * 3 ways to load tweets on your site
        * 1: Using window.twtr.widget.load together with blockquote anchor tag thing passed tweetURL
        * 2: factory functions. Basically same as 1, but no load needed, you instead call window.twtr.widget.createTweet with the tweetID
        * 3: call Twitter API and build custom components for the tweets
  * Infura related stuff
    * Notes
      * In first 15 minutes of new infura endpoint for backend, eth_getBlockByNumber sent 1000 requests in one minute around :40th minute. 
      * There was one backend eth_call that sent about 40,000 infura requests, which is ridiculous. I think it might have been the user-token/sync because looks like it happened at 6 UTC which i think is when it is set to run once per day. 
    * ways to decrease infura requests sent out
      * For NFTOpinion webjob (and any others), remove getBlock. Main issue is that this is how we store the timestamp of when that rating/post/whatever was created. BUT also it requires a CRAP ton of requests. Would be better if this was calculated on the subgraphs side when event received by subgraph from chain. BUT ratings/posts dont even have a subgraph