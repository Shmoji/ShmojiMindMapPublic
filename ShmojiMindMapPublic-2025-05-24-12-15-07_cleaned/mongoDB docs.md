  * how TOs
    * how to filter or sort by nested field from a join?
      * gotta use aggregate. Can use manual app logic, but doesnt really scale unless you a pro.
      * here is ex: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/mongoDB docs#^VzcHFfGZJ|how to do aggregate lookup between stringID and ObjectID (like _id)]]
    * how to do aggregate lookup between stringID and ObjectID (like _id) ^VzcHFfGZJ
      * ```javascript
const emoteNotifDocs = await EmoteNotifModel.aggregate([
      {
        $addFields: {
          convertedEmoteID: { $toObjectId: "$emoteID" } // Convert emoteID from string to ObjectId
        }
      },
      {
        $lookup: {
          from: 'emotes', // the collection to join
          localField: 'convertedEmoteID', // field from the input documents
          foreignField: '_id', // field from the documents of the "from" collection
          as: 'emoteData' // output array field
        }
      },
      {
        $unwind: '$emoteData' // makes emoteData not an array with 1 element - instead returns that 1 element
      },
      {
        $match: {
          'emoteData.receiverSymbol': 'Shmojii'
        }
      }
    ])```
    * how to disregard case when doing Mongo query
      * like dis (the regex does it): ```javascript
await UserTokenModel.findOne({ twitterUsername: { $regex: new RegExp(*username*, 'iu') }, })```
  * prompts for mongoDB stuff
    * set up a model, a route for inserting data into that model in way developer desires, and a route for fetching that data in way developer desires. Use code already present as a reference.
      * step by step process
        * create model in models folder
        * create controller in controllers folder
        * create service in services folder
        * create route in routes folder
        * create util in utils folder
        * create type in types folder
        * create validation in validations folder
      * what developer desires:
        * how to insert data into new model:
        * how to fetch data from new model
        * random desires:
  * questions
    * what does $match do?
      * filters documents based on specified criteria and passes only the documents that match the criteria to the next stage in the aggregation pipeline
    * what does $lookup do?
      * aggregation pipeline operator used to perform a left outer join between documents from two collections. It allows you to combine documents from different collections based on a specified condition.
      * After the $lookup stage, the resulting documents will contain an additional field that holds an array of documents from the foreign collection that match the specified condition
        * So, to clarify, the array in the new field will include documents from both the primary and foreign collections, as determined by the join condition specified in the $lookup stage.
      * useful for scenarios where you need to combine data from multiple collections in a single query, such as when you're dealing with relational data or performing complex data analysis across multiple datasets
