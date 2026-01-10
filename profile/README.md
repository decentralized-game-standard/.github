# Decentralized Game Standard

**Protocols for Games That Endure Beyond Their Makers — Conceptual Framework, Version 0.2 — January 2026**

Games are among humanity's oldest cultural artifacts. Chess, go, mancala—played across centuries with the same core components, adapted endlessly by players who never sought permission. The pieces and board exist independently; rules are conventions interpreted anew by each generation. No single authority can revoke access, shut down the "servers," or demand a cut of every match.

Digital games have followed a different path. They are built as walled, server-dependent systems where publishers control the environment, the assets, and the flow of value. This architecture has produced extraordinary experiences but also systemic fragility: games die prematurely, communities lose their history, creators capture little of the value they generate, and innovation is bottlenecked through gatekeepers.

The Decentralized Game Standard is a set of minimal, interlocking protocols designed to realign digital play with its analog roots. By separating durable entities from interpretive rules, composing engines from swappable parts, and enabling direct coordination settled in sats, it aims to create games that can outlive companies, engines, and technological shifts.

## Structural Failures in the Current Model

The evidence is extensive and ongoing.

- **Preservation Crisis** — Online titles routinely vanish. Concussion (2022) shut down in 2023 after limited success. Knockout City (2021) ended official support in 2023, though a community version later emerged. The Crew (2014) was delisted and made unplayable in 2024 when Ubisoft revoked licenses. These are not outliers: hundreds of live-service games—Friday the 13th, Paragon, Battleborn—have followed the same trajectory, erasing player progress and purchased content.

- **Interoperability Absence** — Assets remain trapped. A Fortnite skin cannot travel to Roblox or another battle royale without corporate partnership (rare and selective). Engine lock-in compounds this: a Unity project rarely ports cleanly to Unreal, stifling experimentation.

- **Modding Precarity** — Mods sustain titles far beyond official support. Skyrim (2011) thrives in 2026 primarily through community content. Yet monetization attempts repeatedly fail under centralized models: Steam's 2015 paid mods backlash, Bethesda's Creation Club criticism for high prices and curation limits. Modders bear legal risk and receive inconsistent compensation.

- **Competitive Control** — Publishers can terminate esports ecosystems unilaterally. Heroes of the Storm's scene ended abruptly in 2018. Overwatch League scaled back dramatically. Tournament organizers face IP enforcement threats even when adding value.

- **Discovery and Value Capture** — Platforms extract 30% (or more) for distribution while algorithms bury most releases. Indie developers and community creators compete in opaque systems.

These issues stem from centralized architecture: single points of control, failure, and rent extraction.

## Core Premise: Decouple the Token from the Ruleset

A digital sword should exist as a persistent, neutral concept—definable once, interpretable variously—carrying its history across games and engines. Engines should compose from explicit, replaceable components. Coordination—funding servers, commissioning assets, running tournaments—should flow peer-to-peer with instant settlement.

Three protocols achieve this on existing open infrastructure:

| Protocol | Core Mechanism | Primary Failures Addressed |
|----------|----------------|---------------------------|
| **AEMS** | Nostr events defining universal Entities, game-specific Manifestations, mutable State, and optional ownership chains | Preservation, Interoperability |
| **GERS** | Data-flow engine architecture with uniform Records and stateless Processors | Modding fragility, Engine lock-in, Long-term maintenance |
| **WOSS** | Three-event coordination language settled via Lightning | Value capture, Competitive control, Discovery gatekeeping |

### AEMS: Durable Entities

AEMS structures game objects as layered Nostr events. A "health potion" is defined universally (Entity), interpreted per game (Manifestation), tracks instance changes (State), and optionally proves ownership through signed transfers (Asset). No blockchain required—Nostr's relay replication and cryptographic signing provide persistence and verifiability suited to social agreement, not financial double-spend prevention.

### GERS: Composable Engines

GERS applies data-oriented design: everything is a Record with Fields, transformed by small Processors wired into Networks. Renderers, physics, input—all swappable without systemic rewrite. Mods become native extensions. Obsolescence in one layer (e.g., a graphics API) affects only one component.

### WOSS: Permissionless Coordination

WOSS enables direct offers, fulfillments, and acknowledgments on Nostr, settled instantly via Lightning. Communities fund servers, modders earn directly, tournament pools form spontaneously—all without platform rents or approval.

## How the Protocols Interlock

A player discovers a rare artifact:
- Defined as an AEMS Entity by a community curator.
- Manifested differently by each GERS-based game engine.
- State updated through gameplay via Record Fields.
- A modder, funded via WOSS, adds a new Processor enhancing its visuals.
- Ownership transfers via AEMS when traded.
- If one game ends, the artifact persists on Nostr for another engine to import.

Value flows horizontally: creators, hosts, players coordinate directly.

## Technical Foundation

- **Nostr** — Signed, relay-replicated events for all persistent data (entities, state, offers).
- **Lightning** — Instant, low-cost settlement for coordination.
- No tokens, no consensus chains, no speculative assets.

## Status and Scope

These are conceptual specifications—minimal by design, inviting implementation and evolution. No reference engines or marketplaces exist yet. Each protocol includes incremental prototype steps from single Nostr events to small systems.

This is not a product or company. It is an open invitation to build games that compound cultural value across decades rather than resetting with corporate cycles.

Experiment. Critique. Extend.

**MIT License** — Free to implement, adapt, share.