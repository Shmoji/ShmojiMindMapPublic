  * what does it do?
    * A JSON Web Signature (JWS) verifies the authenticity of the sender of a message and the integrity of the message. It provides cryptographic evidence that the data was signed by the sender and has not been tampered with during transmission.
    * it does not make data private, ANYONE can still read it if not encrypted
  * Notes
    * JWE does exactly what JWS does, except it ALSO encrypts the data