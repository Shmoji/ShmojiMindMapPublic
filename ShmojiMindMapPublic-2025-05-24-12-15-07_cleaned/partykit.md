  * tracking thoughts
    * tracking experiences trying to use it
      * [[2024-05-28]]
        * tried using for desires app for vibecamp, but got lost in the sauce. couldnt tell where data was being persisted to or how. Didnt want to use S3 or AWS lambda
  * how TOs
    * how to figure out value of NEXT_PUBLIC_PARTYKIT_HOST?
      * this is generated from terminal when doing "npx partykit deploy"
        * useful docs: https://docs.partykit.io/tutorials/add-partykit-to-a-nextjs-app/7-deploy-your-app/
      * so i guess this real-time server is being hosted by partykit
      * i guess this server they are hosting is also where data for Room.storage (way to persist data) is stored, but im not sure. may also be that each server has connected cloudfare account and that's where data is stored for Room.storage
  * questions
    * what persists data? where is it persisted? how?
    * what is a connection in partykit?
      * it's basically a WebSocket connecting to Party.Room - so basically a WS connection
    * what is a Room?
      * Room represents a single, self-contained, long-lived session.
    * what is Room.storage?
      * A per-room key-value storage is what docs says...but like where? in the cloud?
    * when is Party.server constructor called?
      * at least in react, it looks like only called when usePartySocket is used. i had other component with "connect.partykitS3(database, PARTYKIT_HOST as string)" and that didnt cause constructor to be called
    * what is difference in dev UX when using `import { makeStores, ConnectS3 } from '@fireproof/connect'` VS `this.party.storage`?
      * the S3 one can just use useDoc in React component frontend to save data directly from frontend component
      * this.party.storage seems to only work from backend Party.server i think