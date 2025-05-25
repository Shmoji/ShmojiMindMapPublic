  * tracking learnings from experiences
    * [[2024-09-16]]
      * you can login with ANYTHING - phone, passkey, email, X, discord. And then the first time this generates a privKey and pubKey for you. At same time, can also auth with a backend server to get a JWT if needed
      * gotta be careful with passkey tho bc those are device/platform dependent. my windows passkey is not available on my android device
      * you can go to any other device and same process happens (i tested between multiple devices)...but im not sure how it ties your email/social to the private key it returns back to you. Maybe it only stores pubKey and then the auth server that gives JWT uses functions to verify the privKey with PubKey without seeing your privKey
      * so...even tho user auths with email/social/phone first - they are actually authing with their wallet key pair AND a signature (of message that came from your backend). this is basically SIWE
      * Q: when the user logs in again using email with thirdweb for a second time, how does the user get their private key back again? did some server store it for them because that wouldnt be good?
        * kinda yes. When a user first logs in, a wallet is generated on their device. The private key is then split into three shards using Shamir's Secret Sharing algorithm. Shard A is on user device. Shard B is on thirdweb servers encrypted by a key known to thirdweb. Shard C is also on thirdweb servers, encrypted by user auth (their user auth i guess?)
        * on their site under Threshold Secret Sharing:
          * Using threshold secret sharing, thirdweb cannot reconstruct a user's private key, thereby providing a non-custodial wallet. Additionally, a customer's assets are safe even if thirdweb or the application developer (you) is compromised. In a compromised situation, an attacker may only be able to access one of three shards, which is inadequate to reconstruct the wallet's private key.
        * docs are here: https://portal.thirdweb.com/connect/in-app-wallet/security
        * thirdweb is always scoped to specific app. if user uses same email to login to different app, it will be totally different wallet. They say: In-App Wallets are scoped to applications per API key.
        * think this security method is called Threshold secret-sharing cryptography
        * technically i could create my own version of this using my own servers, but could see that being hard
        * i found that particle network is doing something very similar. Will compare
          * Except particle may be free. thirdweb's has a cost once you hit certain number of users
          * Particle says SSS that thirdweb uses isnt secure enough and what they use is better
          * honestly ima go off vibes and try particle network. Then if no good, ill just use thirdweb. Here are thirdweb links if needed:
            * https://playground.thirdweb.com/connect/auth
            * https://github.com/thirdweb-example/thirdweb-auth-express
          * one issue im seeing with Particle: how will i do the auth thing to get JWT for my app?
