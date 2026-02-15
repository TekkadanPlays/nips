# NIPs

NIPs stand for **Nostr Implementation Possibilities**.

They exist to document what may be implemented by [Nostr](https://github.com/nostr-protocol/nostr)-compatible _relay_ and _client_ software.

---

- [List](#list)
- [Event Kinds](#event-kinds)
- [Message Types](#message-types)
  - [Client to Relay](#client-to-relay)
  - [Relay to Client](#relay-to-client)
- [Standardized Tags](#standardized-tags)
- [Criteria for acceptance of NIPs](#criteria-for-acceptance-of-nips)
- [Is this repository a centralizing factor?](#is-this-repository-a-centralizing-factor)
- [How this repository works](#how-this-repository-works)
- [Breaking Changes](#breaking-changes)
- [License](#license)

---

## List

> See [CATEGORIES.md](CATEGORIES.md) for the full category map and [LEGACY-MAP.md](LEGACY-MAP.md) for old→new number lookup.

### 1xx — Core Protocol

- [NIP-100: Basic protocol flow description](100.md)
- [NIP-101: Conventions for `e` and `p` tags in text events](101.md)
- [NIP-102: bech32-encoded entities](102.md)
- [NIP-103: `nostr:` URI scheme](103.md)
- [NIP-104: Proof of Work](104.md)
- [NIP-105: Dealing with unknown event kinds](105.md)
- [NIP-106: Expiration Timestamp](106.md)
- [NIP-107: Protected Events](107.md)
- [NIP-108: OpenTimestamps Attestations for Events](108.md)

### 2xx — Identity & Keys

- [NIP-200: Follow List](200.md)
- [NIP-201: Mapping Nostr keys to DNS-based internet identifiers](201.md)
- [NIP-202: Basic key derivation from mnemonic seed phrase](202.md)
- [NIP-203: Extra metadata fields and tags](203.md)
- [NIP-204: User Statuses](204.md)
- [NIP-205: External Identities in Profiles](205.md)
- [NIP-206: Private Key Encryption](206.md)
- [NIP-207: Lists](207.md)
- [NIP-208: Badges](208.md)

### 3xx — Relay Infrastructure

- [NIP-300: Relay Information Document](300.md)
- [NIP-301: Authentication of clients to relays](301.md)
- [NIP-302: Event Counts](302.md)
- [NIP-303: Search Capability](303.md)
- [NIP-304: Relay List Metadata](304.md)
- [NIP-305: Proxy Tags](305.md)

### 4xx — Signing & Encryption

- [NIP-400: `window.nostr` capability for web browsers](400.md)
- [NIP-401: Delegated Event Signing](401.md)
- [NIP-402: Encrypted Payloads (Versioned)](402.md)
- [NIP-403: Nostr Remote Signing](403.md)
- [NIP-404: Android Signer Application](404.md)
- [NIP-405: Gift Wrap](405.md)

### 5xx — Social & Content

- [NIP-500: Event Deletion Request](500.md)
- [NIP-501: Subject tag in text events](501.md)
- [NIP-502: Reposts](502.md)
- [NIP-503: Long-form Content](503.md)
- [NIP-504: Reactions](504.md)
- [NIP-505: Text Note References](505.md)
- [NIP-506: Custom Emoji](506.md)
- [NIP-507: Labeling](507.md)
- [NIP-508: Sensitive Content / Content Warning](508.md)
- [NIP-509: Reporting](509.md)
- [NIP-510: Highlights](510.md)
- [NIP-511: Media Attachments](511.md)
- [NIP-512: External Content IDs](512.md)

### 6xx — Messaging & Groups

- [NIP-600: Private Direct Messages](600.md)
- [NIP-601: Public Chat](601.md)
- [NIP-602: Relay-based Groups](602.md)
- [NIP-699: Encrypted Direct Message](699.md) --- **unrecommended**: deprecated in favor of [NIP-600](600.md)

### 7xx — Payments & Zaps

- [NIP-700: Lightning Zaps](700.md)
- [NIP-701: Nostr Wallet Connect](701.md)
- [NIP-702: Cashu Wallet](702.md)
- [NIP-703: Nut Zaps](703.md)
- [NIP-704: Zap Goals](704.md)

### 8xx — Media & Files

- [NIP-800: Video Events](800.md)
- [NIP-801: File Metadata](801.md)
- [NIP-802: HTTP File Storage Integration](802.md)
- [NIP-803: HTTP Auth](803.md)

### 9xx — Applications & Specialized

- [NIP-900: Nostr Marketplace](900.md)
- [NIP-901: `git` stuff](901.md)
- [NIP-902: Torrents](902.md)
- [NIP-903: Calendar Events](903.md)
- [NIP-904: Live Activities](904.md)
- [NIP-905: Wiki](905.md)
- [NIP-906: Chess (PGN)](906.md)
- [NIP-907: Moderated Communities](907.md)
- [NIP-908: Arbitrary custom app data](908.md)
- [NIP-909: Medical Data](909.md)
- [NIP-910: Recommended Application Handlers](910.md)
- [NIP-911: Data Vending Machine](911.md)
- [NIP-912: Classified Listings](912.md)

### Deprecated

- [NIP-08: Handling Mentions](08.md) --- merged into [NIP-505](505.md)
- [NIP-12: Generic Tag Queries](12.md) --- merged into [NIP-100](100.md)
- [NIP-16: Event Treatment](16.md) --- merged into [NIP-100](100.md)
- [NIP-20: Command Results](20.md) --- merged into [NIP-100](100.md)
- [NIP-33: Parameterized Replaceable Events](33.md) --- merged into [NIP-100](100.md)

## Event Kinds

| kind          | description                     | NIP                                    |
| ------------- | ------------------------------- | -------------------------------------- |
| `0`           | User Metadata                   | [100](100.md)                            |
| `1`           | Short Text Note                 | [100](100.md)                            |
| `2`           | Recommend Relay                 | 100 (deprecated)                       |
| `3`           | Follows                         | [200](200.md)                            |
| `4`           | Encrypted Direct Messages       | [699](699.md)                            |
| `5`           | Event Deletion Request          | [500](500.md)                            |
| `6`           | Repost                          | [502](502.md)                            |
| `7`           | Reaction                        | [504](504.md)                            |
| `8`           | Badge Award                     | [208](208.md)                            |
| `9`           | Group Chat Message              | [602](602.md)                            |
| `10`          | Group Chat Threaded Reply       | [602](602.md)                            |
| `11`          | Group Thread                    | [602](602.md)                            |
| `12`          | Group Thread Reply              | [602](602.md)                            |
| `13`          | Seal                            | [405](405.md)                            |
| `14`          | Direct Message                  | [600](600.md)                            |
| `16`          | Generic Repost                  | [502](502.md)                            |
| `17`          | Reaction to a website           | [504](504.md)                            |
| `40`          | Channel Creation                | [601](601.md)                            |
| `41`          | Channel Metadata                | [601](601.md)                            |
| `42`          | Channel Message                 | [601](601.md)                            |
| `43`          | Channel Hide Message            | [601](601.md)                            |
| `44`          | Channel Mute User               | [601](601.md)                            |
| `64`          | Chess (PGN)                     | [906](906.md)                            |
| `818`         | Merge Requests                  | [905](905.md)                            |
| `1021`        | Bid                             | [900](900.md)                            |
| `1022`        | Bid confirmation                | [900](900.md)                            |
| `1040`        | OpenTimestamps                  | [108](108.md)                            |
| `1059`        | Gift Wrap                       | [405](405.md)                            |
| `1063`        | File Metadata                   | [801](801.md)                            |
| `1311`        | Live Chat Message               | [904](904.md)                            |
| `1617`        | Patches                         | [901](901.md)                            |
| `1621`        | Issues                          | [901](901.md)                            |
| `1622`        | Replies                         | [901](901.md)                            |
| `1630`-`1633` | Status                          | [901](901.md)                            |
| `1971`        | Problem Tracker                 | [nostrocket][nostrocket]               |
| `1984`        | Reporting                       | [509](509.md)                            |
| `1985`        | Label                           | [507](507.md)                            |
| `1986`        | Relay reviews                   |                                        |
| `1987`        | AI Embeddings / Vector lists    | [NKBIP-02]                             |
| `2003`        | Torrent                         | [902](902.md)                            |
| `2004`        | Torrent Comment                 | [902](902.md)                            |
| `2022`        | Coinjoin Pool                   | [joinstr][joinstr]                     |
| `4550`        | Community Post Approval         | [907](907.md)                            |
| `5000`-`5999` | Job Request                     | [911](911.md)                            |
| `6000`-`6999` | Job Result                      | [911](911.md)                            |
| `7000`        | Job Feedback                    | [911](911.md)                            |
| `7374`        | Reserved Cashu Wallet Tokens    | [702](702.md)                            |
| `7375`        | Cashu Wallet Tokens             | [702](702.md)                            |
| `7376`        | Cashu Wallet History            | [702](702.md)                            |
| `9000`-`9030` | Group Control Events            | [602](602.md)                            |
| `9041`        | Zap Goal                        | [704](704.md)                            |
| `9321`        | Nutzap                          | [703](703.md)                            |
| `9467`        | Tidal login                     | [Tidal-nostr]                          |
| `9734`        | Zap Request                     | [700](700.md)                            |
| `9735`        | Zap                             | [700](700.md)                            |
| `9802`        | Highlights                      | [510](510.md)                            |
| `10000`       | Mute list                       | [207](207.md)                            |
| `10001`       | Pin list                        | [207](207.md)                            |
| `10002`       | Relay List Metadata             | [304](304.md)                            |
| `10003`       | Bookmark list                   | [207](207.md)                            |
| `10004`       | Communities list                | [207](207.md)                            |
| `10005`       | Public chats list               | [207](207.md)                            |
| `10006`       | Blocked relays list             | [207](207.md)                            |
| `10007`       | Search relays list              | [207](207.md)                            |
| `10009`       | User groups                     | [207](207.md), [602](602.md)               |
| `10015`       | Interests list                  | [207](207.md)                            |
| `10019`       | Nutzap Mint Recommendation      | [703](703.md)                            |
| `10030`       | User emoji list                 | [207](207.md)                            |
| `10050`       | Relay list to receive DMs       | [207](207.md), [600](600.md)               |
| `10063`       | User server list                | [Blossom][blossom]                     |
| `10096`       | File storage server list        | [802](802.md)                            |
| `13194`       | Wallet Info                     | [701](701.md)                            |
| `21000`       | Lightning Pub RPC               | [Lightning.Pub][lnpub]                 |
| `22242`       | Client Authentication           | [301](301.md)                            |
| `23194`       | Wallet Request                  | [701](701.md)                            |
| `23195`       | Wallet Response                 | [701](701.md)                            |
| `24133`       | Nostr Connect                   | [403](403.md)                            |
| `24242`       | Blobs stored on mediaservers    | [Blossom][blossom]                     |
| `27235`       | HTTP Auth                       | [803](803.md)                            |
| `30000`       | Follow sets                     | [207](207.md)                            |
| `30001`       | Generic lists                   | [207](207.md)                            |
| `30002`       | Relay sets                      | [207](207.md)                            |
| `30003`       | Bookmark sets                   | [207](207.md)                            |
| `30004`       | Curation sets                   | [207](207.md)                            |
| `30005`       | Video sets                      | [207](207.md)                            |
| `30007`       | Kind mute sets                  | [207](207.md)                            |
| `30008`       | Profile Badges                  | [208](208.md)                            |
| `30009`       | Badge Definition                | [208](208.md)                            |
| `30015`       | Interest sets                   | [207](207.md)                            |
| `30017`       | Create or update a stall        | [900](900.md)                            |
| `30018`       | Create or update a product      | [900](900.md)                            |
| `30019`       | Marketplace UI/UX               | [900](900.md)                            |
| `30020`       | Product sold as an auction      | [900](900.md)                            |
| `30023`       | Long-form Content               | [503](503.md)                            |
| `30024`       | Draft Long-form Content         | [503](503.md)                            |
| `30030`       | Emoji sets                      | [207](207.md)                            |
| `30040`       | Modular Article Header          | [NKBIP-01]                             |
| `30041`       | Modular Article Content         | [NKBIP-01]                             |
| `30063`       | Release artifact sets           | [207](207.md)                            |
| `30078`       | Application-specific Data       | [908](908.md)                            |
| `30311`       | Live Event                      | [904](904.md)                            |
| `30315`       | User Statuses                   | [204](204.md)                            |
| `30388`       | Slide Set                       | [Corny Chat][cornychat-slideset]       |
| `30402`       | Classified Listing              | [912](912.md)                            |
| `30403`       | Draft Classified Listing        | [912](912.md)                            |
| `30617`       | Repository announcements        | [901](901.md)                            |
| `30618`       | Repository state announcements  | [901](901.md)                            |
| `30818`       | Wiki article                    | [905](905.md)                            |
| `30819`       | Redirects                       | [905](905.md)                            |
| `31388`       | Link Set                        | [Corny Chat][cornychat-linkset]        |
| `31890`       | Feed                            | [NUD: Custom Feeds][NUD: Custom Feeds] |
| `31922`       | Date-Based Calendar Event       | [903](903.md)                            |
| `31923`       | Time-Based Calendar Event       | [903](903.md)                            |
| `31924`       | Calendar                        | [903](903.md)                            |
| `31925`       | Calendar Event RSVP             | [903](903.md)                            |
| `31989`       | Handler recommendation          | [910](910.md)                            |
| `31990`       | Handler information             | [910](910.md)                            |
| `34235`       | Video Event                     | [800](800.md)                            |
| `34236`       | Short-form Portrait Video Event | [800](800.md)                            |
| `34550`       | Community Definition            | [907](907.md)                            |
| `37375`       | Cashu Wallet Event              | [702](702.md)                            |
| `39000-9`     | Group metadata events           | [602](602.md)                            |

[NUD: Custom Feeds]: https://wikifreedia.xyz/cip-01/
[nostrocket]: https://github.com/nostrocket/NIPS/blob/main/Problems.md
[lnpub]: https://github.com/shocknet/Lightning.Pub/blob/master/proto/autogenerated/client.md
[cornychat-slideset]: https://cornychat.com/datatypes#kind30388slideset
[cornychat-linkset]: https://cornychat.com/datatypes#kind31388linkset
[joinstr]: https://gitlab.com/1440000bytes/joinstr/-/blob/main/NIP.md
[NKBIP-01]: https://wikistr.com/nkbip-01
[NKBIP-02]: https://wikistr.com/nkbip-02
[blossom]: https://github.com/hzrd149/blossom
[Tidal-nostr]: https://wikistr.com/tidal-nostr

## Message types

### Client to Relay

| type    | description                                         | NIP         |
| ------- | --------------------------------------------------- | ----------- |
| `EVENT` | used to publish events                              | [100](100.md) |
| `REQ`   | used to request events and subscribe to new updates | [100](100.md) |
| `CLOSE` | used to stop previous subscriptions                 | [100](100.md) |
| `AUTH`  | used to send authentication events                  | [301](301.md) |
| `COUNT` | used to request event counts                        | [302](302.md) |

### Relay to Client

| type     | description                                             | NIP         |
| -------- | ------------------------------------------------------- | ----------- |
| `EOSE`   | used to notify clients all stored events have been sent | [100](100.md) |
| `EVENT`  | used to send events requested to clients                | [100](100.md) |
| `NOTICE` | used to send human-readable messages to clients         | [100](100.md) |
| `OK`     | used to notify clients if an EVENT was successful       | [100](100.md) |
| `CLOSED` | used to notify clients that a REQ was ended and why     | [100](100.md) |
| `AUTH`   | used to send authentication challenges                  | [301](301.md) |
| `COUNT`  | used to send requested event counts to clients          | [302](302.md) |

## Standardized Tags

| name              | value                                | other parameters                | NIP                                                |
| ----------------- | ------------------------------------ | ------------------------------- | -------------------------------------------------- |
| `e`               | event id (hex)                       | relay URL, marker, pubkey (hex) | [100](100.md), [101](101.md)                           |
| `p`               | pubkey (hex)                         | relay URL, petname              | [100](100.md), [200](200.md)                           |
| `a`               | coordinates to an event              | relay URL                       | [100](100.md)                                        |
| `d`               | identifier                           | --                              | [100](100.md)                                        |
| `-`               | --                                   | --                              | [107](107.md)                                        |
| `g`               | geohash                              | --                              | [903](903.md)                                        |
| `h`               | group id                             | --                              | [602](602.md)                                        |
| `i`               | external identity                    | proof, url hint                 | [205](205.md), [512](512.md)                           |
| `k`               | kind                                 | --                              | [502](502.md), [504](504.md), [907](907.md), [512](512.md) |
| `l`               | label, label namespace               | --                              | [507](507.md)                                        |
| `L`               | label namespace                      | --                              | [507](507.md)                                        |
| `m`               | MIME type                            | --                              | [801](801.md)                                        |
| `q`               | event id (hex)                       | relay URL, pubkey (hex)         | [502](502.md)                                        |
| `r`               | a reference (URL, etc)               | --                              | [203](203.md), [504](504.md)                           |
| `r`               | relay url                            | marker                          | [304](304.md)                                        |
| `t`               | hashtag                              | --                              | [203](203.md), [901](901.md)                           |
| `alt`             | summary                              | --                              | [105](105.md)                                        |
| `amount`          | millisatoshis, stringified           | --                              | [700](700.md)                                        |
| `bolt11`          | `bolt11` invoice                     | --                              | [700](700.md)                                        |
| `challenge`       | challenge string                     | --                              | [301](301.md)                                        |
| `client`          | name, address                        | relay URL                       | [910](910.md)                                        |
| `clone`           | git clone URL                        | --                              | [901](901.md)                                        |
| `content-warning` | reason                               | --                              | [508](508.md)                                        |
| `delegation`      | pubkey, conditions, delegation token | --                              | [401](401.md)                                        |
| `description`     | description                          | --                              | [901](901.md), [700](700.md), [208](208.md)              |
| `emoji`           | shortcode, image URL                 | --                              | [506](506.md)                                        |
| `encrypted`       | --                                   | --                              | [911](911.md)                                        |
| `expiration`      | unix timestamp (string)              | --                              | [106](106.md)                                        |
| `goal`            | event id (hex)                       | relay URL                       | [704](704.md)                                        |
| `image`           | image URL                            | dimensions in pixels            | [503](503.md), [903](903.md), [208](208.md)              |
| `imeta`           | inline metadata                      | --                              | [511](511.md)                                        |
| `lnurl`           | `bech32` encoded `lnurl`             | --                              | [700](700.md)                                        |
| `location`        | location string                      | --                              | [903](903.md), [912](912.md)                           |
| `name`            | name                                 | --                              | [901](901.md), [208](208.md), [907](907.md)              |
| `nonce`           | random                               | difficulty                      | [104](104.md)                                        |
| `preimage`        | hash of `bolt11` invoice             | --                              | [700](700.md)                                        |
| `price`           | price                                | currency, frequency             | [912](912.md)                                        |
| `proxy`           | external ID                          | protocol                        | [305](305.md)                                        |
| `published_at`    | unix timestamp (string)              | --                              | [503](503.md)                                        |
| `relay`           | relay url                            | --                              | [301](301.md), [600](600.md)                           |
| `relays`          | relay list                           | --                              | [700](700.md)                                        |
| `server`          | file storage server url              | --                              | [802](802.md)                                        |
| `subject`         | subject                              | --                              | [501](501.md), [600](600.md), [901](901.md)              |
| `summary`         | summary                              | --                              | [503](503.md), [903](903.md)                           |
| `thumb`           | badge thumbnail                      | dimensions in pixels            | [208](208.md)                                        |
| `title`           | article title                        | --                              | [503](503.md)                                        |
| `web`             | webpage URL                          | --                              | [901](901.md)                                        |
| `zap`             | pubkey (hex), relay URL              | weight                          | [700](700.md)                                        |

Please update these lists when proposing new NIPs.

## Criteria for acceptance of NIPs

1. They should be fully implemented in at least two clients and one relay -- when applicable.
2. They should make sense.
3. They should be optional and backwards-compatible: care must be taken such that clients and relays that choose to not implement them do not stop working when interacting with the ones that choose to.
4. There should be no more than one way of doing the same thing.
5. Other rules will be made up when necessary.

## Is this repository a centralizing factor?

To promote interoperability, we standards that everybody can follow, and we need them to define a **single way of doing each thing** without ever hurting **backwards-compatibility**, and for that purpose there is no way around getting everybody to agree on the same thing and keep a centralized index of these standards. However the fact that such index exists doesn't hurt the decentralization of Nostr. _At any point the central index can be challenged if it is failing to fulfill the needs of the protocol_ and it can migrate to other places and be maintained by other people.

It can even fork into multiple and then some clients would go one way, others would go another way, and some clients would adhere to both competing standards. This would hurt the simplicity, openness and interoperability of Nostr a little, but everything would still work in the short term.

There is a list of notable Nostr software developers who have commit access to this repository, but that exists mostly for practical reasons, as by the nature of the thing we're dealing with the repository owner can revoke membership and rewrite history as they want -- and if these actions are unjustified or perceived as bad or evil the community must react.

## How this repository works

Standards may emerge in two ways: the first way is that someone starts doing something, then others copy it; the second way is that someone has an idea of a new standard that could benefit multiple clients and the protocol in general without breaking **backwards-compatibility** and the principle of having **a single way of doing things**, then they write that idea and submit it to this repository, other interested parties read it and give their feedback, then once most people reasonably agree we codify that in a NIP which client and relay developers that are interested in the feature can proceed to implement.

These two ways of standardizing things are supported by this repository. Although the second is preferred, an effort will be made to codify standards emerged outside this repository into NIPs that can be later referenced and easily understood and implemented by others -- but obviously as in any human system discretion may be applied when standards are considered harmful.

## Breaking Changes

[Breaking Changes](BREAKING.md)

## License

All NIPs are public domain.

## Contributors

<a align="center" href="https://github.com/nostr-protocol/nips/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=nostr-protocol/nips" />
</a>
