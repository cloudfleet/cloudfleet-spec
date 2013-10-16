A short reminder on the https handshake,
[explained by Jeff Moser](http://www.moserware.com/2009/06/first-few-milliseconds-of-https.html).

Seems like js-sequence-diagrams
[aren't really working that well](https://github.com/bramp/js-sequence-diagrams/issues/52).

TODO: maybe contribute a proper grunt task to build js-sequence-diagrams.

Until then, here is the poor man's version:

HTTPS handshake
---------------
Frodo is trying to start a conversation with Gandalf securely using their
palantíri (without Sauron knowing what they're talking about). He types in
`https://www.gandalf.mde` and starts talking on port 443...

Frodo -> Gandalf: Good greetings!

Note right of Gandalf: Gandalf fumbles for his certificate (containing his name
and public RSA key) signed by Elrond, whom everybody trusts.

Gandalf -> Frodo: Hello, Frodo. Take this certificate.

Note left of Frodo: Frodo calculates the SHA-1 hash sum of Gandalf's certificate
and compares it to the signature Elrond added and signed by his private key
(which can be verified using Elrond's public key,
which everyone has and trusts).

Frodo -> Gandalf: Oh Gandalf, it is you! OK, let's exchange symmetric keys using
your public RSA key, which I now know is yours and trust.