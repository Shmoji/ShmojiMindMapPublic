  * terms
    * directives
      * me: @<directive>
      * they have a list of these directives you can find
      * composeDB docs: ComposeDB comes with a list of different directives that can be used to create or load data models, define type validation rules, and create indices for specific fields which enables them to be used for document filtering and sorting
      * different types of directives
        * Type validation directives
        * Directives for creating indices
          * how to: use @createIndex
          * When you use @documentReference to define a relation to another Stream, that field automatically gets indexed. There’s no need to add a separate @createIndex directive.
        * @createModel directive
          * accountRelation relates the profile to the author’s account. By default the @createmodel directive requires that every model must specify a relation to its author’s account. If SINGLE, that account can only have one instance of that MODEL. If LIST - it obvious. ONLY defines relation with AUTHOR.
        * @documentReference
          * defines a relation to another Stream/model
    * relations
      * NOTE: i think a model can have multiple types of relations
      * different types of relations
        * Account to Model
          * Happens by default i believe. It just means that every model instance is tied to the author that created the instance of that model
        * Model to Account
          * Very similar to Account to Model, except it's a field in the model that stores references to non-author accounts.
          * Is not involved with accountRelation keyword
          * When using this type of relation, you need to define a model field that stores an account (e.g. a DID), then add the @accountReference directive to make it queryable. example: recipient: DID! @accountReference
  * related
    * if you cant find something, check here: [[ceramic network]]