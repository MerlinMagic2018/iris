<img src="https://raw.githubusercontent.com/irislib/iris/master/brand/iris_logotype_rgb_small.png" alt="Iris" width="400">

Available at:
* [iris.to](https://iris.to)
* [iris.cx](https://iris.cx)
* [irislib.github.io](https://irislib.github.io)
* Browser extension: use Iris even if you are offline. In the future, can be used to sign in to websites.
  * [Chrome](https://chrome.google.com/webstore/detail/iris/oelmiikkaikgnmmjaonjlopkmpcahpgh)
  * [Firefox](https://addons.mozilla.org/en-US/firefox/addon/irisapp/)

Code:
- [iris-lib](https://github.com/irislib/iris-lib) Library for reading and writing Iris messages and indexes
- [iris-angular](https://github.com/irislib/iris-angular) Angular UI for web, browser extensions
- [iris-electron](https://github.com/irislib/iris-electron) Desktop application: wraps iris-angular and adds multicast capability
- [iris-mobile](https://github.com/irislib/iris-mobile) Mobile app (react native)

_Note: Iris is still **experimental** software._

<a href="https://opencollective.com/iris-social/donate" target="_blank"><img src="https://opencollective.com/iris-social/donate/button@2x.png?color=blue" width=200 /></a>

<p><sub>BTC donations: 3GopC1ijpZktaGLXHb7atugPj9zPGyQeST</sub></p>

---

**Want social media where _you_ decide what gets into your feed, not some obscure algorithm? Something that can't be censored by authoritarian governments? No big tech companies that decide what you can post, what gets visibility and who gets to have an account? Yet no harassing troll accounts, spam or ads? Something that works locally even if ISPs are unavailable in an emergency situation?**

Here comes Iris. Iris is a social networking application that stores and indexes everything on the devices of its users and connects directly with peers who run the application - no corporate gatekeepers needed.

## Public and private messaging
Interface-wise, Iris is not too different from some existing social media. You can post texts, photos, videos, audio or other types of files into your feed.

![Feed](https://github.com/irislib/iris/raw/master/img/feed.png)

You can also chat privately or participate in public group discussions.

## Web of trust
You can create new Iris accounts (technically: cryptographic keypairs) at will, without asking for anyone's permission, but only the users whose web of trust upvoted your account will see its posts.

When you upvote someone, they become your 1st degree contact. The accounts they upvoted become 2nd degree contacts. Then there are 3rd degree contacts and so on. This is the web of trust, which can be used to filter all content on Iris. Hiding users by downvoting is also possible.

**This way we can avoid spam and other unwanted content without giving power to central moderators.**

You can also add to your contacts list and rate people and organisations who are not yet on Iris.
A decentralised web of trust, unlike certain big brother systems, could be a strong positive social force as envisioned in the blog post [Learning to Trust Strangers](https://medium.com/@mmalmi/learning-to-trust-strangers-167b652a654f). (Iris is evolved from thereby mentioned Identifi.)

## Attestations (identity verifications)
Keep your contact details up-to-date and ask for attestations from peers or specialised verifiers trusted by your WoT.

Use your Iris account for online authentication or identification on services that support it (browser extension and mobile app in development).

Crypto wallets could use Iris to connect human-recognizable identities to payment addresses. Encrypted messaging apps like Signal could use Iris to look up users instead of telecom-bound phone numbers.

If you lose access to your account (keypair), just create a new one and link it to your existing identity by asking for verifications from your web of trust.

## Name service
Through WoT attestations, Iris maps human readable names to public keys and other identity attributes, providing an alternative to centrally managed identifiers such as domain names, CA certificates, email addresses, phone numbers or social media handles.

Iris name search is interface-wise similar to many existing social media: instead of having to know someone's unique username, you can type in their non-unique natural name and get a dropdown list of matching contacts ordered by distance in your web of trust.

You can also do reverse name lookup, such as looking up a name for an unknown number that is calling you. Or you could look up who owns a bitcoin address - as perceived by your web of trust.

## Importing content from existing sources
An Iris message is digitally signed by the entity that verified its origin. In other words: message author and signer can be different entities, and only the signer needs to be on Iris.

For example, a crawler can import and sign other people's messages from Twitter. Only the users who trust the crawler will see the messages.

![Feed](https://github.com/irislib/iris/raw/master/img/msg.png)
*A message imported from the bitcoin trading site bitcoin-otc.com by "Bitcoin-otc.com crawler".*

Importing content from existing sources helps overcome the network effect. It solves the chicken and egg problem, making Iris a useful medium even with no initial user base.

## Tech stack
The [browser application](https://github.com/irislib/iris-angular) runs on AngularJS. [Iris-electron](https://github.com/irislib/iris-electron) wraps it for desktop and adds peer sync over wifi (multicast).

[Iris-mobile](https://github.com/irislib/iris-mobile) is a React Native implementation (in development).

[Iris-lib](https://github.com/irislib/iris-lib) contains the core functionality of Iris that can be integrated to other applications. It is written in javascript for the browser and Node.js.

The task of data storage and networking is outsourced to [GUN](https://github.com/amark/gun), which manages the synchronization of data between different storages: RAM, localstorage, GUN websocket server, WebRTC peers, LAN multicast peers, IPFS (no adapter yet), S3 or others.

GUN enables subscription to data changes, so message feeds and identity profiles just update real-time without having to hit f5 or writing complex update logic.

[IPFS](https://ipfs.io) is used to store file attachments and message backups.

## Improving decentralisation
Currently the weak point of Iris's decentralisation is the list of initial peers, which could easily be blocked by governments or ISPs. By default, the application connects to IPFS default peers and a couple GUN peers. You can always add peers manually on the [settings page](https://irislib.github.io/#settings), but that is cumbersome for the average user.

[Iris-electron](https://github.com/irislib/iris-electron) and the upcoming mobile application can synchronize with peers on the same local area network. Bluetooth modules are not yet implemented, but will enable ad hoc networks of peers that need to meet each other only occasionally.

On the wide area network level, trusted contacts could exchange network addresses privately to avoid having them blocked or tracked. WebRTC's NAT traversal capabilities can enable direct connections between typical network endpoint users, but you still need a firewall-opened/port-forwarded rendez-vous node for them, and in some cases a relay node.

## How to help
**Donations** help keep the project going and are very much appreciated. You can donate via [Open Collective](https://opencollective.com/iris-social) or using bitcoin: 3GopC1ijpZktaGLXHb7atugPj9zPGyQeST

You can promote Iris by [creating an account](https://iris.to) and **sharing your profile link on your existing social networks**!

Currently the application is glitchy and slower than the technology allows, but it should give an idea of the intended functionality. Contributions to the [browser application](https://github.com/irislib/iris-angular) and the underlying [iris-lib](https://github.com/irislib/iris-lib) are very much appreciated.

If you want to integrate Iris with your product or service, please check out [iris-lib](https://github.com/irislib/iris-lib) and create Github issues if needed.

## License

Iris is released under the terms of the MIT license. See `COPYING` for more information or see http://opensource.org/licenses/MIT.

---

![The Greek goddess Iris](https://upload.wikimedia.org/wikipedia/commons/7/7b/Venus_supported_by_Iris%2C_complaining_to_Mars_1820.jpg)
*Iris (middle): Greek goddess of the rainbow and messenger of the gods. Iris of the eye is named after her, because of the many colours of the iris.*
