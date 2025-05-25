  * tracking thoughts
    * tracking what other people say it's trying to do
      * [[2024-03-07]]
        * Peter van Hardenberg: we dont want places and we dont want things.
    * tracking thoughts on actual functionality
      * [[2024-04-26]]
        * i think at least for text docs, it records and version controls every single character - no idea how it works for other types of data tho. Quote from them: "**History:** Automerge never deletes anything. It stores every change made to a document with efficient compression. This enables features like [dynamic history](https://www.inkandswitch.com/patchwork/notebook/03/) that rely on a complete log of changes."

  * what is it?
    * on their blog:
      * a JSON data storage and synchronization library developed here at Ink & Switch
    * their site:
      * data-structure for building local-first applications
      * Automerge is a library of data structures for building collaborative applications
      * Automerge is a [[Conflict-Free Replicated Data Type (CRDT)]], which allows concurrent changes on different devices to be merged automatically without requiring any central server.
  * questions
    * what is it for?
      * their blog: Automerge was designed to support local-first software and uses a [CRDT](https://crdt.tech/) sync algorithm to merge together edits made on different devices, without the need for a central authority server. This internal machinery is also a good fit for version control interfaces:
        * **History:** Automerge never deletes anything. It stores every change made to a document with efficient compression. This enables features like [dynamic history](https://www.inkandswitch.com/patchwork/notebook/03/) that rely on a complete log of changes.
        * **Diffs:** Automerge can compute an exact difference between two points in history of a document. It doesn’t need to resort to heuristics because the full edit history is tracked. This enables features like [diff visualizations](https://www.inkandswitch.com/patchwork/notebook/04/). For text in particular, Automerge gives each character has its own ID, so it’s easy to show precisely which characters were deleted or inserted.
        * **Branching and merging:** Automerge supports cloning documents and then merging them back together in reasonable ways using the CRDT algorithm, even if there have been concurrent edits on both copies. This is the underlying capability that supports our [simple branching](https://www.inkandswitch.com/patchwork/notebook/06/).