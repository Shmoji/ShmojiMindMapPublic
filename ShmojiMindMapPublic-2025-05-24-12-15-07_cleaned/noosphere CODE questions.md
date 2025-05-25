  * NOTE: more specific questions will be asked on more specific pages - for example #[[noosphere gateway]]
  * general code questions
    * where are the endpoint strings defined for the Noosphere API?
      * best entry point to find them seems to be noosphere/rust/noosphere-gateway/src/gateway.rs - you'll see router being created with a bunch of different routes defining the endpoint strings
      * looks like most of those endpoint strings are defined in noosphere-core/src/api
      * looks like all the code/logic for the endpoints are defined in noosphere-gateway/src/handlers
  * related
    * [[noosphere orb]]