# Decentralized Game Standard

**Protocols for Games That Endure as Open Rulesets, Not Fragile Products — Conceptual Framework, 2026-01-14**

Physical games have endured for centuries because they are fundamentally open rulesets played with neutral artifacts. Anyone can grab a ball and play soccer in a park—no permission needed from FIFA. Variants emerge freely: pickup games, backyard rules, niche leagues. Professional spectacles (World Cup, Premier League) add polish and scale as voluntary overlays, but they never own the game itself. Equipment makers, coaches, and local organizers build thriving ecosystems around the open core without gatekeeping play.

Digital games have taken the opposite path: built as proprietary products controlled by publishers who own the "ball," the rules, the field, and the scoreboard. This creates extraordinary short-term experiences but systemic fragility—games shut down, assets vanish, communities fracture, and innovation bottlenecks through gatekeepers.

The Decentralized Game Standard realigns digital play with its physical roots. It treats genres as eternal, open rulesets rather than disposable products. Persistent artifacts (items, characters) exist independently on Nostr. Composable engines interpret rules flexibly. Coordination flows peer-to-peer with instant settlement. The result: casual "pickup" games happen spontaneously, niche variants thrive without needing mass scale, and ambitious "pro league" experiences can emerge as voluntary services on top—competed against, forked, or ignored if they overreach.

This is not utopian purity demanding everything be fully decentralized. It is pragmatic freedom: a neutral, permissionless foundation that enables abundant play, with optional centralized layers for convenience and spectacle.

---

📦 **[AEMS](https://github.com/decentralized-game-standard/aems-standard)** · 🔧 **[RUNS](https://github.com/decentralized-game-standard/runs-standard)** · ⚡ **[WOCS](https://github.com/decentralized-game-standard/wocs-standard)** · ❓ **[FAQ](https://github.com/decentralized-game-standard/.github/blob/main/profile/FAQ.md)**

---

## The Product Paradigm and Its Failings

Digital games became products because abundance was channeled into artificial scarcity. Publishers control servers, asset validity, matchmaking, and monetization—making every experience contingent on their continued interest.

Real-world evidence shows the cost:

- **Preservation Crisis** — Live-service titles vanish routinely (The Crew delisted in 2024, Knockout City ended 2023, hundreds of others). Player progress and purchases evaporate.
- **Locked Assets** — Items rarely travel between games without corporate deals. Engine lock-in traps entire projects.
- **Modding and Community Fragility** — Mods sustain classics like Skyrim, yet monetization efforts repeatedly fail under centralized curation and high rents.
- **Gatekept Coordination** — Esports scenes die unilaterally. Server hosting relies on unreliable donations. Discovery algorithms bury most creations while extracting 30%+.

These stem from forced centralization at the foundation. The alternative is not anarchy—it's an open base layer with voluntary centralization where useful.

## The Discipline of Protocol Restraint

Long-lived protocols share a pattern: aggressive exclusion. They define minimal coordination primitives and deliberately refuse features that could be layered above.

| Protocol | What It Does | What It Deliberately Excludes |
|----------|--------------|-------------------------------|
| **TCP/IP** | Packet routing | Content, security, identity, application semantics |
| **SMTP** | Store-and-forward messages | Encryption, spam filtering, read receipts |
| **Bitcoin** | Timestamped transaction ordering | Smart contracts, identity, privacy, governance |
| **MIDI** | Note events | Sound synthesis, audio, timing guarantees |
| **Musical notation** | Pitch and duration | Timbre, dynamics, expression |

The end-to-end principle (Saltzer, Reed, Clark 1984) articulates why: *functionality belongs at endpoints, not in the network*. Protocols that try to solve every problem become complex, fragile, and capturable. Protocols that stay minimal become infrastructure—neutral substrates that outlive their creators.

DGS follows this discipline:

- **AEMS** defines entity structure, not databases or marketplaces
- **RUNS** defines data-flow primitives, not engines or frameworks
- **WOCS** defines offer/fulfill/ack, not escrow or reputation systems
- **Ludic Structures** defines notation, not execution

When you ask "why doesn't DGS handle X?"—dispute resolution, content moderation, identity verification, complex governance—the answer is the same answer TCP/IP gives: *because X is not the protocol's job*. Communities, markets, and applications handle X. The protocol is the neutral ground they coordinate on.

This restraint is not laziness or incompleteness. It is the design philosophy that lets protocols endure for decades while platforms rise and fall.

## Core Premise: Genres as Sports, Not Products

A battle royale should feel like soccer: core concepts (shrinking zone, looting, last-player-standing) are neutral and persistent. Anyone can host a quick match with friends or strangers. Items earned in one session carry forward. Niche variants (zombie mode, prop hunt) emerge without approval. Massive, polished tournaments with ranked ladders and streaming can exist as opt-in services—funded directly, competed against freely.

The standard achieves this by separating durable artifacts from interpretive rules and enabling frictionless coordination:

| Protocol | Core Mechanism | Primary Failures Addressed |
|----------|----------------|---------------------------|
| **AEMS** (Asset-Entity-Manifestation-State) | Nostr events defining universal Entities, game-specific Manifestations, mutable State, and optional ownership | Preservation, asset lock-in, interoperability |
| **RUNS** (Record Update Network Processor) | Data-flow engine architecture with uniform Records and stateless Processors | Engine rigidity, mod fragility, long-term maintenance |
| **WOCS** (Work Order Coordination Settlement) | Three-event coordination language settled via Lightning | Gatekept value flow, centralized coordination, discovery rents |

Built on mature primitives—Nostr for resilient data, Lightning for instant micropayments—no blockchains, tokens, or new consensus layers.

## How It Works in Practice

Imagine "MOBA" as a genre like basketball:

- A community defines universal Entities (heroes, items, creeps) via AEMS.
- Different groups publish Manifestations: "classic Dota-style," "fast-paced beginner variant," "underwater twist."
- Players own instances with history and state that persist on Nostr.

Casual play: Someone posts a WOCS offer—"500 sats buy-in for a quick MOBA lobby tonight, classic rules." Others join via any RUNS-compatible client. A community-hosted server (or P2P mesh) runs the match. Items import automatically. No accounts, no platform—just play.

Niche play: A small group runs their weird variant weekly. It stays cult forever, like church-league softball.

Pro-layer play: A popular organizer bounties high-uptime servers, anti-cheat Processors, and ranked matchmaking via recurring WOCS offers. Thousands opt in for polished experience and streamed tournaments. Third-party clients emerge with slick UI, discovery feeds, or premium overlays. If the organizer gets extractive, players fork the ruleset or drop to raw pickup lobbies—the foundation guarantees exit.

Value flows horizontally: modders earn directly for new Manifestations, artists for assets, hosts for reliability, streamers for casting. Ecosystems grow around the open ruleset (client apps, analytics tools, "equipment" like custom renderers) without anyone owning the game itself.

Single-player adventures (Zelda-likes) fit too: worlds as shared Entity collections, mods as new Manifestations/Processors, persistence beyond any one engine.

## Scope: Commons and Authored Experiences

This standard optimizes for games that benefit from longevity and community evolution—like sports or folklore genres. But what of puzzle games where the solution is the treasure? Mystery narratives where a single spoiler destroys the journey? Interactive art where the creator's intent *is* the experience?

These authored experiences fit the same foundation through a philosophy of **abundance through reciprocity** rather than scarcity through enforcement:

- **Unforgeable Attribution** — Every creative act is cryptographically signed. Origin is mathematically provable without courts or takedowns. Copying is fine; *claiming* (fraud about authorship) is impossible.
- **Voluntary Covenants** — Authors attach use expectations as legible social signals ("attribution required," "commercial license needed"). Communities and reputation markets respect these—not through enforcement, but through transparency.
- **First-Experience Economics** — Authored works monetize the *curated revelation* (paying for the puzzle-solving journey, not the solution itself). After encounter, content may open naturally.

This rejects the false choice between "fully open commons" and "DRM-protected products." Authors retain attribution and can earn from first experiences. Copiers participate in cultural propagation. Neither requires enforcement mechanisms that contradict the open foundation.

The Authorial Provenance Standard (APS) details this approach—provenance over property, covenants without enforcement, and markets for reputation and verification funded via WOCS.

## The Protocols

### AEMS: Durable Entities
Layered Nostr events make artifacts independent and interpretable.
- Universal Entity (e.g., "sword that deals damage").
- Game-specific Manifestation (e.g., +50 attack, fire enchantment).
- Mutable State (durability, upgrades).
- Optional signed ownership chain.

Items earned in one game persist for import elsewhere.

### RUNS: Composable Engines
### WOCS: Permissionless Coordination
- A modder (funded via WOCS) adds visual flair Processor.
Data-oriented design: everything is Records with Fields, transformed by stateless Processors wired into Networks.
- Swap renderers, physics, or input without rewriting core.
- Mods are native Processor additions.
- Naturally supports parallelism and explicit data flow.

Engines import AEMS Entities as Records and apply selected Manifestations.

### WOCS: Permissionless Coordination
- A modder (funded via WOCS) adds visual flair Processor.
Three Nostr events (Offer, Fulfill, Ack) settled via Lightning.
- Fund servers, bounty assets, pay modders, pool tournament prizes.
- Direct, instant, no rake.

Communities coordinate at any scale without gatekeepers.

## Technical Foundation

- **Nostr** — Signed, relay-replicated events for all persistent data.
- **Lightning** — Near-zero-fee settlement for commitments.
- Minimal by design: no speculative assets, no consensus overhead.

## Example Emergence

A player discovers a rare shield:
- Defined universally via AEMS Entity.
- Manifested differently across games.
- State tracks battle history.
- A modder (funded via WOCS) adds visual flair Processor.
- Ownership transfers permissionlessly.
- One hosted game ends—the shield lives on for the next pickup match or pro tournament.

## Status and Scope

These are conceptual specifications—minimal, open, and language-agnostic—inviting experimentation. No reference implementations yet exist. The focus is the hardest problems: preservation, permissionless play, and open ecosystems. Massive synchronous experiences may always involve voluntary centralized layers; the standard guarantees they remain optional.

This is an invitation to build games that compound cultural value across decades, like chess or soccer, rather than resetting with corporate cycles.

Experiment. Host a pickup game. Define an Entity. Watch ecosystems emerge.

**MIT License** — Free to implement, adapt, share.