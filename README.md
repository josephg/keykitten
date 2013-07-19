# Keykitten

Key kitten shares your public keys so you don't have to. Its like gravatar for public keys.

It will be hosted on keykitten.org, but its not there yet.

---

One of the reasons crypto isn't used more is usability. To use PGP there's like 6 scary steps you have to go through. First you have to install gpg, then make your keys (which requires typing some scary stuff and choosing your cypher..!?). Then you have to add your key to your keyring (??), and you should upload it to some random websites that nobody has ever heard of. And you'll still feel guilty because you didn't go to a key signing party. Even after you've done all of that, you need to store your private key somewhere safe so you don't lose it. And who do you trust with your private key?

And good gracious, I hope you don't use windows to do all of that!

Lets face it, my mum is never going to make a pgp key today, and my mum is GMail's target audience, not crypto neckbeards. Which makes message encryption impossible.

We have the same problem on the other side of the fence. If I want to send an encrypted message to jim@example.com, how can I get Jim's public key?

Well, in comes keykitten. The point of keykitten.org is gravatar for keys. Hash jim@example.com to c20266793..., then fetch https://keykitten.org/keys/c20266793d32b1b99e42438807fc7038f89bb326/pgp to get his pgp key. Or you can fetch /ssh to get jim's public ssh key.

The other half of the project is a simple web UI to sign in & upload your keys to the site. I want to make it usable by both my mum and security neckbeards. If you don't have a key, we'll generate you some using browser javascript. If you're worried you'll lose your private key, I'll store a copy of it (but only if you want me to). I'll use persona to sign users in, pin SSL certificates in chrome and firefox (and make the SSL cert widely published).

Neckbeards can go in and upload the pgp key they generated & got signed at key parties. My mum can click the 'figure it out for me' button. And finally, of course, the site should be federated so if you want jim@example.com's key, you should first check example.com/keys/... before looking on keykitten.com.

There's a few fun things you can do with a system like this. Once github knows my email address, they can just look up my ssh public keys to give me access. If I want to let my friend ssh in to my computer, I can add him from my contact book (I have his email address, after all). My computer will fetch his ssh key via keykitten, make an account and add his key via authorized_keys. And finally, it should be much easier to make things like encrypting browser extensions. All the extension needs to know is the recipient and it can figure out how to encrypt data for them.

