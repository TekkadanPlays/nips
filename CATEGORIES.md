# NIP Categories

This document defines the categorical organization of Nostr Implementation Possibilities (NIPs).
Each category occupies a 100-number range, leaving room for future additions.

> **No protocol changes.** Event kinds, tags, and wire formats are unchanged.
> Only the NIP document numbering and organization has been restructured.

---

## 1xx — Core Protocol

Foundational protocol mechanics: event structure, wire format, encoding, threading, and base behaviors.

| New | Old | Title |
|-----|-----|-------|
| 100 | 01 | Basic protocol flow description |
| 101 | 10 | Conventions for `e` and `p` tags in text events |
| 102 | 19 | bech32-encoded entities |
| 103 | 21 | `nostr:` URI scheme |
| 104 | 13 | Proof of Work |
| 105 | 31 | Dealing with unknown event kinds |
| 106 | 40 | Expiration Timestamp |
| 107 | 70 | Protected Events |
| 108 | 03 | OpenTimestamps Attestations for Events |

## 2xx — Identity & Keys

User identity, profiles, key management, and social graph.

| New | Old | Title |
|-----|-----|-------|
| 200 | 02 | Follow List |
| 201 | 05 | Mapping Nostr keys to DNS-based internet identifiers |
| 202 | 06 | Basic key derivation from mnemonic seed phrase |
| 203 | 24 | Extra metadata fields and tags |
| 204 | 38 | User Statuses |
| 205 | 39 | External Identities in Profiles |
| 206 | 49 | Private Key Encryption |
| 207 | 51 | Lists |
| 208 | 58 | Badges |

## 3xx — Relay Infrastructure

Relay discovery, configuration, authentication, and capabilities.

| New | Old | Title |
|-----|-----|-------|
| 300 | 11 | Relay Information Document |
| 301 | 42 | Authentication of clients to relays |
| 302 | 45 | Event Counts |
| 303 | 50 | Search Capability |
| 304 | 65 | Relay List Metadata |
| 305 | 48 | Proxy Tags |

## 4xx — Signing & Encryption

Key signing interfaces, remote signing, encryption schemes, and message wrapping.

| New | Old | Title |
|-----|-----|-------|
| 400 | 07 | `window.nostr` capability for web browsers |
| 401 | 26 | Delegated Event Signing |
| 402 | 44 | Encrypted Payloads (Versioned) |
| 403 | 46 | Nostr Remote Signing |
| 404 | 55 | Android Signer Application |
| 405 | 59 | Gift Wrap |

## 5xx — Social & Content

Notes, reactions, reposts, long-form content, labeling, moderation, and media references.

| New | Old | Title |
|-----|-----|-------|
| 500 | 09 | Event Deletion Request |
| 501 | 14 | Subject tag in text events |
| 502 | 18 | Reposts |
| 503 | 23 | Long-form Content |
| 504 | 25 | Reactions |
| 505 | 27 | Text Note References |
| 506 | 30 | Custom Emoji |
| 507 | 32 | Labeling |
| 508 | 36 | Sensitive Content / Content Warning |
| 509 | 56 | Reporting |
| 510 | 84 | Highlights |
| 511 | 92 | Media Attachments |
| 512 | 73 | External Content IDs |

## 6xx — Messaging & Groups

Direct messages, public chat, and relay-based group communication.

| New | Old | Title |
|-----|-----|-------|
| 600 | 17 | Private Direct Messages |
| 601 | 28 | Public Chat |
| 602 | 29 | Relay-based Groups |
| 699 | 04 | Encrypted Direct Message *(deprecated → NIP-600)* |

## 7xx — Payments & Zaps

Lightning payments, wallet integrations, Cashu, and payment goals.

| New | Old | Title |
|-----|-----|-------|
| 700 | 57 | Lightning Zaps |
| 701 | 47 | Nostr Wallet Connect |
| 702 | 60 | Cashu Wallet |
| 703 | 61 | Nut Zaps |
| 704 | 75 | Zap Goals |

## 8xx — Media & Files

Video, file metadata, file storage, and HTTP authentication for media.

| New | Old | Title |
|-----|-----|-------|
| 800 | 71 | Video Events |
| 801 | 94 | File Metadata |
| 802 | 96 | HTTP File Storage Integration |
| 803 | 98 | HTTP Auth |

## 9xx — Applications & Specialized

Marketplaces, developer tools, calendars, communities, and domain-specific applications.

| New | Old | Title |
|-----|-----|-------|
| 900 | 15 | Nostr Marketplace |
| 901 | 34 | `git` stuff |
| 902 | 35 | Torrents |
| 903 | 52 | Calendar Events |
| 904 | 53 | Live Activities |
| 905 | 54 | Wiki |
| 906 | 64 | Chess (PGN) |
| 907 | 72 | Moderated Communities |
| 908 | 78 | Arbitrary custom app data |
| 909 | 82 | Medical Data |
| 910 | 89 | Recommended Application Handlers |
| 911 | 90 | Data Vending Machine |
| 912 | 99 | Classified Listings |

## Deprecated / Merged

These NIPs have been absorbed into other NIPs and exist only as redirect stubs.

| Old | Status | Redirect |
|-----|--------|----------|
| 08 | deprecated | → NIP-505 (was NIP-505, Text Note References) |
| 12 | merged | → NIP-100 (was NIP-100, Generic Tag Queries) |
| 16 | merged | → NIP-100 (was NIP-100, Event Treatment) |
| 20 | merged | → NIP-100 (was NIP-100, Command Results) |
| 33 | merged | → NIP-100 (was NIP-100, Parameterized Replaceable Events) |
