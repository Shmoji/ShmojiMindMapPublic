  * tracking thoughts
    * tracking experiences with pushing to frontend repo under an org
      * [[2024-07-30]]
        * if repo is under an org, you have to pay for pro sub of vercel. although, you can get around by using vercel CLI to deploy locally.
        * i think it actually forced me to take free trail. so i may need to look at perplexity query once trial runs out and setup hook for deploying locally and whatnot
        * i was getting ERR_TOO_MANY_REDIRECTS so i tried making records in cloudflare that vercel TOLD me to put in there as "DNS only" instead of proxied. Doesnt seem to be working tho. Actually it just worked in decentr, but not in arc...why?
        * i think it's possible what vercel recommended was fine and somehow DNS stuff getting cached locally. Gonna give it some time and check later with default recommended by vercel. It does say you can reset cache by resetting computer or your internet tho
        * RESOLVED: ahh okay, so it was 2 things: 1) default recommended from vercel works and just took time 2) use DNS only proxy status in cloudflare bc proxied no work