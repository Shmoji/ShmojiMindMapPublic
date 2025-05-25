  * tracking thoughts
    * tracking experiences trying to use it
      * [[2024-05-29]]
        * got very basic TODO app working that syncs between devices by using S3 storage. encrypted CAR files are stored in S3 bucket
        * CORS is disabled in file:// urls for security reasons, so to use locally they recommend using live server in VSCode (which ive never done)
      * [[2024-05-30]]
        * tried getting the firehouse-chat demo running. i added my AWS credentials generated from last tut. Locally it wouldnt work. But then if i deployed to partykit it worked on that new url generated for deployment. However, i noticed it wasnt even using my S3 bucket - so i guess it's just storing data in partykit somehow - bc it was indeed persisted across devices.
        * it may just be that the DB in the server.ts is different than the DBs in the react components. You see those latter ones only connect to partykit...yea the team confirmed it
    * tracking talking with their devs
      * [[2024-05-30]]
        * metadata in localstorage and car tx in indexDB
  * questions
    * where is data stored?
      * their docs: By default, Fireproof stores data in the browser's local storage. This is great for development, but once your app is ready to share, you'll want to [connect it to cloud storage.](https://use-fireproof.com/docs/connect) For now, you can manage and delete the encrypted data from your browser developer tools. There are two components to the data, the header and the encrypted files. The header is kept in localStorage under the key fp.useFireproof. The files are stored in IndexedDB under the key fp.<keyId>.useFireproof. This arrangement means that files can be stored with an untrusted provider, and the header can be stored securely. For instance, you can keep the encrypted data files in IPFS or a public S3 bucket, and keep the headers locally or in your applications session store.
    * is this right: you need a connector to persist data across different devices? but you dont need connector to persist on one device?
      * correct correct