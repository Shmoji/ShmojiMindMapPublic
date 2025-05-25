  * what is it?
    * Gordon in mix of mine and his words:
      * you want to start with the project/art and work towards the tech (not the other way where you start with some decentralized tech). Taking the shortest path to market by doing things that don’t scale. This lets you iterate toward something that people actually want.
      * But there’s a dilemma: when you don’t start by thinking through decentralization, you can accidentally build a system that is difficult or impossible to decentralize later.
      * It would be great if we could use the momentum of the traditional app stack to get to product, then slingshot toward something decentralized. How do we avoid avoid painting ourselves into a corner
      * decentralizable is an app that isnt locked in to centralization and can still be decentralized later
  * questions
    * What is the minimum set of mechanisms we need to make software decentralizable?
      * Gordon from Noosphere:
        * Some answers will vary from project-to-project, but I see some common patterns:
          * Immutable data
            * Decentralized software is a kind of is a distributed system. That means resources may exist in many different places, and in multiple places at once. Each place has a different subjective view of the state of the system. There is, by definition, no central source of truth, no shared state. I edit something in one place, the other may not know about it until much later, if ever. I may change something in both places, or many places at once. Who wins?
            * In a decentralized system, conflicts arise. Things fall out of sync, or rather, they were never in sync to begin with. So, we often need mechanisms to resolve conflicting understandings of the world.
            * We can accomplish this by changing the way we think about the problem. Instead of trying to modify a single shared state, just pass messages. Each message is immutable—it doesn’t change after being sent. That means the message can be sent to many different places and these places don’t need to coordinate to find out if the message has changed. It won’t.
            * How do you represent change? Multiple messages can tell a story about how something changes. This is how Git, CRDTs, Nostr, and Noosphere model changes.
            * With immutable data and the right merge semantics, different parts of a system can receive messages at different times, and in different orders, and become eventually consistent as they gather messages.
          * Universal identifiers
            * Decentralized means data can be stored in many different places. At some point you’re going to want to be able to identify some data independent of where it lives.
            * So, we need an identifier that does not depend upon location. We also want to avoid the need for a centralized registration authority. Usually, we want to avoid having to coordinate on IDs at all. That rules out domain names. What we want is something universally unique, something that will not collide with any other IDs, anywhere.
            * There are two easy ways to accomplish this:
            * 1) Content hashes
            * 2) UUID4
            * Content hashes say: to identify something, just hash it. This gives you an ID that corresponds 1:1 with the content. If the content changes, the hash changes—exactly what you want for immutable messages. Git, IPFS, Nostr, and BitTorrent use content hashes in this way.
            * Hashes have a wonderful additional property: they’re self-verifying. When you retrieve content by its hash, don’t need to trust the node or server it’s coming from. Just hash the content and check if the hashes match. If they do, you’ve got your data.
            * Because they have a 1:1 correspondence with content, and are self-verifying, content hashes are a good choice for identifying immutable data.
            * UUID4 is essentially a long random number. It is so unlikely to collide, you can treat it as universally unique. This is a good choice for entities that conceptually change over time, but need a stable identifier.
          * User-controlled keys
            * Networked software is an adversarial environment. There are bad guys out there, and your computer is connected to them, just like it’s connected to everyone else. That means we need to consider security, privacy, and trust.
            * This is where cryptography comes in. Cryptographic keys let us guarantee security and trust through signing, and privacy through end-to-end encryption.
            * Cryptography is a tool for turning lots of different problems into key management problems. (Dr. Lea Kissner, Head of Privacy Eng and CISO at Twitter)
            * Just like in real life, cryptographic keys let you open a lock. They let you lock others out, too. Who owns the keys owns the data.
            * Now, the web solves for trust using centralized authorities. Apps work the same way. The server owns the keys, owns your data, owns your account. This security model is fundamentally feudal. It places a castle wall around the server. To get inside the castle, you cross over a drawbridge (“sign in”). This castle protects your data, but also keeps you trapped inside. That’s why they call it a moat.
            * Those who build walls are their own prisoners. (Ursula K. Le Guin)
            * Castle-wall doesn’t cut it. It centralizes power in the hands of the server and creates the conditions for lock-in. For software to be decentralizable, we need a trustless security model. In other words, we need to rebuild trust around people.
            * How? Sign everything with user-controlled keys.
            * The user controls one or more public keys.
            * They sign messages with their key.
            * Every client validates these signatures.
            * This gets us to the minimal definition of user agency.
        * If you have all three, you have a fair shot at building first, decentralizing later. Let’s unpack.