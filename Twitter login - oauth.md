  * tracking learnings
    * [[2024-07-31]]
      * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/how to set cookies#^ZRyp8wPA9|MY LEARNING 1: if your backend domain and frontend domain are different, you just cant set your cookies on backend it seems. i was stuck on this foreverrr and solution was making backend endpoint a subdomain of frontend endpoint]]
  * NOTE: This page is all about logging in with Twitter on an external website
  * key points
    * JWT cookie is set and named on backend (doesnt have to, but more secure)
    * after cookie is set, the backend literally redirects user back to frontend
    * Twitter login uses OAuth which requires user to go to Twitter and then be redirected back to og site
    * Signing in cant just be one backend API call due to oauth. So, it's a bit split up. User is technically signed in once they have JWT stored in cookie that was generated from completeVerification on backend. Because only way to get JWT back with twitter user info is to login to real twitter account. Then, need to use jwt authenticate/decode method stuff on routes to double check JWT is correct when making changes to profile or rating or etc
  * my projects
    * emote is most up to date example - even more up to date than the twitter template - that repo doesnt have latest update where cookie set on backend

  * Process (probably outdated and needs to be rewritten)
    * Click on external site to login to Twitter
    * Redirected to twitter site that asks user if they want to authorize IM to have access to Twitter account. This is first time that oauth_token is seen in URL (of Twitter site). This oauth_token is generated on your backend by twitterOAuth. Also, oauth_token_secret and oauth_callback_confirmed is retrieved in same way as prev sentence. Then, we store requestToken and requestTokenSecret in DB. It's actually after all this previous sentences happens that authURL is sent to frontend and THEN user redirected to Twitter site. But it happens pretty instantly.
    * After user accepts, it redirects to callbackURL set on DEV twitter profile (and in backend config) that was used as input to API call at very beginning when clicking "login twitter" button. Here twitter sends back the oauth_verifier and oauth_token for first time in the URL.
    * Then, you send completeVerification request to backend with 2 new data points from Twitter. You check that oauth_token is same as one you entered in DB earlier. 
    * Then, you call twitter API /accessToken with oauth_token and oauth_verifier from twitter. This oauth_verifier only works one time and then never again. This returns back oauth_token, oauth_token_secret, user_id, screen_name, and maybe more. What's important to know here is that these token and token secrets are ACCESS tokens, so they are different than the REQUEST tokens from earlier. So, you need to store these in DB if they are non null.
    * At this point, if access tokens are non null, you can now insert new user into DB with twitterUsername and ID OR not if user already there.
    * Lastly, this step is only needed if Twitter is used as authentication method in your app. Need to send some sort of token to frontend so we know if user is authenticated with Twitter or not. Probably a JWT. So, as final thing of completeVerification is to do generateAuthToken like in user-token signin method of IM backend and then send it back to frontend
    * The rest is up to frontend basically. Will be similar to IM frontend ClientWrapper logic, except will be ran on page that twitter got callbacked to. Will need to set JWT as global value like in IM frontend and then can use that to determine if logged in or not.
  * random notes
    * notes on how tokens are named
      * requestToken is same as oauth_token for initiateVerification
      * requestTokenSecret is same as oauth_token_secret for initiateVerification
      * accessToken is same as oauth_token for completeVerification
      * accessTokenSecret is same as oauth_token_secret for completeVerification
  * related
    * [[user auth]]
