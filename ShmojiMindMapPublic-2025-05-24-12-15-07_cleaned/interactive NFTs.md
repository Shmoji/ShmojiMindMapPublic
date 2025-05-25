  * tracking thoughts on how i wanna create with interactive NFTs
    * [[2024-01-05]]
      * i wanna create a continuing story using interactive NFTs - can get inspiration from sources below
      * sometimes i'd like to include people that buy prior NFTs in the new NFTs
      * this isnt necesarrily what i will do, but recently been feeling lil mini stories as NFTs. Like the Quantum telepathy story idea. Dont have to come up with full on story - just enough to get the point across.
      * this looks like explanation of how to make interactive NFTs that can show up on all NFT marketplaces. ALSO, it looks like you can use GLTF...which means i could put friggin webXR experiences up on NFT marketplaces....woahhh
      * okay i want to find out if i can do multiple things related to interactive NFTs:
        * create simple image that when clicked goes to next image (for mini stories) that shows on all NFT marketplaces
        * create webXR experience that shows on all NFT marketplaces
        * best tut for this so far despite from 2021: https://medium.com/@mondoir/mint-html-on-opensea-6b00283834f7
    * [[2024-01-06]]
      * checked and seems most ETH NFT markets dont allow you to search by tags. Superrare does, but you have to go through their centralized process to get put on their market. Surprised opensea doesnt have this functionality. You can still create interactive nfts nonetheless
      * im gonna try creating interactive NFT on ETH. if that doesnt work, ill put on Tezos instead. May just do both
    * [[2024-01-10]]
      * it seems localstorage is not allowed in HTML NFT. it will cause your NFTs to not show up on markets due to security issues

  * sources of people literally making interactive NFTs
    * [0xElegy](https://x.com/BasedGhouls/status/1742080643889074557?s=20):
      * it says it is PNG - so how he made it interactive??
      * it shows up on all NFT marketplaces so that's dope!
    * Shinobu_takeru: scratchable NFTs (and more functionality)
      * somehow uses a JS script even tho it's just a PNG. Maybe using an iframe??
      * doesnt look like he uses same "animation_url" metadata in same way that Kyle Tut and 0xElegy does - that's where meat of their content is coming through to be shown on NFT markets. How he do it then?
      * okay i think he is using "mimeType":"application/x-directory" - but not totally sure - you can see his metadata [here](https://ipfs.io/ipfs/Qmb4gEHtwBgGoQDYvrDKt1ZagzRKnMMjZXPuhQrTKgs8mL).
      * figured it out: objkt allows minting of interactive NFTs - i need to research more to now how decentralized it really is - but [here is guide](https://docs.objkt.com/product/product-guides/minting-a-token/interactive-tokens) ^18R3aY42D
    * soursoup.co: depending on whether page is light mode or dark mode, his NFT looks different
      * also using JS, but idk how. Think it's similar to Shinobu_takeru using mimeType. 
      * also noticed they both used https://objkt.com/mintV2 as "mintingTool" in metadata...interesting
      * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/interactive NFTs#^18R3aY42D|figured it out: objkt allows minting of interactive NFTs - i need to research more to now how decentralized it really is - but [here is guide](https://docs.objkt.com/product/product-guides/minting-a-token/interactive-tokens)]]
    * Kyle Tut shows how to make [HTML page into NFT](https://www.pinata.cloud/blog/how-to-mint-an-html-nft)
    * hicetnunc has whole thing of interactive NFTs and guide for creating them
    * okay after looking at hicetnunc NFTs, im realizing there are bunches of them - including webXR and more very creative stuff
  * how TOs
    * how to create interactive NFTs?
      * on all chains ^xMAE_NjiC
        * for HTML NFT
          * create React page (i just used react and tailwind template repo) with what you want and then npm run build it
          * move all files into one single folder (i typically just use root build folder) - you do dis bc paths in ipfs are a pain and experimenting showed me this way works while evrything else i tried didnt work lol. Then just search for "static" and remove all dat shiz. Also, in html file, change the logo and logo in manifest.json AND favicon in HTML. Maybe change other metadata like description if you want (just need this node, but nested nodes give context)
            * tried all dis previously with no luck, but also this is basically explaining issues i ran into: tldr: paths are the issue. Also you still gotta remove the old nested folder paths now that everything is in one folder
              * to test this will work on IPFS, in build folder, edit generated index.html (and all other files) so that all [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/absolute path]] "/static" is turned to [[relative path|absolute path]] "/static" is turned to [[relative path]] 
                * this is bc when you open index.html directly in a browser (using file:// protocol), these absolute paths don't resolve correctly because there's no [[web server]] to serve these assets from the ROOT (/) path.
                * To make it work as a standalone file, you need to convert these absolute paths to relative paths. This means changing references like /static/js/main.c7744756.js to static/js/main.c7744756.js (removing the leading /). This way, the browser can correctly find and load these assets RELATIVE to the location of index.html
                * you can already get idea for how you have to do something similar for ipfs. Good text from GPT: Use relative paths instead of absolute paths for linking your CSS, JS, and other assets. This ensures that the paths remain valid regardless of the IPFS gateway being used.
          * upload to [[web3.storage]]
            * if just one or a few separate files: use console.web3.storage (doesnt work for CAR files rn)
            * if entire connected folder: use w3 cli - web3.storage has docs on how do https://web3.storage/docs/how-to/upload (w3 up build --no-wrap)
          * continue to specific chain tuts now i think
      * on ETH
        * follow [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/interactive NFTs#^xMAE_NjiC|on all chains]] first
        * https://docs.manifold.xyz/v/manifold-studio/tutorials/minting-html-pages
        * think about traits you want. think about description and title you want.
        * you can edit the collection details that show in opensea after if you like - not super important
      * on Tezos
        * 1) use [objkt guide](https://docs.objkt.com/product/product-guides/minting-a-token/interactive-tokens):

  * questions ^TmaljIO3n
    * how to find interactive NFTs
      * search certain tags on the marketplaces: like webapp, interactive, etc