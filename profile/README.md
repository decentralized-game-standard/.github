# Enduring Game Standard

**Protocols for Games That Endure — Patient Capital, Durable Substrate, Cumulative Craft**

The games that endured five millennia — chess, Go, the Olympic Games — all shared three structural conditions: patient capital to fund long-term stewardship, a durable substrate that persisted independently of any single owner, and cumulative craft that transmitted knowledge across generations. Physical games possess these conditions naturally. Anyone can grab a ball and play soccer in a park without permission from FIFA. Variants emerge freely: pickup games, backyard rules, niche leagues. Professional spectacles add polish and scale as voluntary overlays, but they never own the game itself.

Digital games haven't had these properties — yet. Built on proprietary infrastructure, they tie every experience to a single company's continued interest. Games shut down, assets vanish, communities fracture, and accumulated craft scatters.

The Enduring Game Standard restores all three conditions to digital play. It treats genres as open rulesets rather than disposable products. Persistent artifacts exist independently on Nostr, where they are discoverable and inheritable without any single party's permission. Composable execution engines interpret rules flexibly. Coordination flows peer-to-peer with instant settlement. Notation transmits design knowledge so craft compounds across generations.

Pragmatic freedom: a neutral, permissionless foundation enabling abundant play, with optional centralized layers for convenience and spectacle.

---

📦 **[AEMS](https://github.com/enduring-game-standard/aems-schema)** · 🎯 **[AEMS Conventions](https://github.com/enduring-game-standard/aems-conventions)** · 🔧 **[RUNS](https://github.com/enduring-game-standard/runs-spec)** · 📖 **[RUNS Library](https://github.com/enduring-game-standard/runs-library)** · ⚡ **[WOCS](https://github.com/enduring-game-standard/wocs-protocol)** · 🎼 **[MAPS](https://github.com/enduring-game-standard/maps-notation)** · 🎶 **[MAPS Library](https://github.com/enduring-game-standard/maps-library)** · 🏫 **[Austin School](https://github.com/enduring-game-standard/austin-school)** · ❓ **[FAQ](https://github.com/enduring-game-standard/.github/blob/main/profile/FAQ.md)**

---

## What Digital Games Lost

Physical games are naturally durable. Digital games have been built on proprietary infrastructure — servers, asset validity, matchmaking, monetization all contingent on a single company's continued interest. The structural gap shows up as concrete costs:

- **Games should survive their creators** — yet live-service titles vanish routinely (The Crew delisted in 2024, Knockout City ended 2023, hundreds of others). Player progress and purchases evaporate.
- **Player artifacts should persist independently** — yet items rarely travel between games without corporate deals. Engine lock-in traps entire projects.
- **Modification should be native** — yet mods sustain classics like Skyrim while monetization efforts repeatedly fail under centralized curation and high rents.
- **Coordination should be permissionless** — yet esports scenes die unilaterally. Server hosting relies on unreliable donations. Discovery algorithms bury most creations while extracting 30%+.

These are downstream effects of building on depreciating foundations — where the financial pressure to extract value faster than it degrades makes long-term stewardship irrational. An open base layer with voluntary centralization closes the gap.

## Patient Capital

Open-source game engines, crowdfunding, cooperative studios, indie movements — each solved part of the problem. Open-source engines made tools accessible. Crowdfunding gave creators independence from publishers. Cooperatives aligned incentives. What none of them could reach was the structural cause underneath.

The structural cause is the relationship between money and time. When the currency a studio holds loses purchasing power year after year, the rational strategy is extraction: ship fast, monetize aggressively, move on. Long-term stewardship becomes irrational under depreciating money, regardless of the developers' intentions. This is why venture-funded studios optimize for exit, why live-service games maximize engagement over craft, and why accumulated design knowledge scatters when studios close.

Patient capital reverses this incentive. When money does not depreciate, holding it is costless and deploying it carries genuine opportunity cost. The rational strategy shifts from extraction to stewardship: fund carefully, build durably, maintain indefinitely. Sound money makes open infrastructure economically rational because the capital funding its development does not erode while the protocols mature.

The Enduring Game Standard assumes this condition. Its protocols become rational investments when the capital behind them holds value across decades.

## Core Premise: Genres as Sports, Not Products

A battle royale should function like soccer: core concepts (shrinking zone, looting, last-player-standing) are neutral and persistent. Anyone can host a quick match with friends or strangers. Items earned in one session carry forward. Niche variants (zombie mode, prop hunt) emerge without approval. Massive, polished tournaments with ranked ladders and streaming can exist as opt-in services — funded directly, competed against freely.

The standard achieves this by separating durable artifacts from interpretive rules and enabling frictionless coordination:

| Protocol | Core Mechanism | Primary Failures Addressed |
|----------|----------------|---------------------------|
| **AEMS** — the things | Nostr events defining universal Entities (named roles), game-specific Manifestations, player-owned Assets, and mutable State | Preservation, asset lock-in, interoperability |
| **RUNS** — the game | Composable execution: uniform Records transformed by stateless Processors wired into explicit Networks | Engine rigidity, mod fragility, long-term maintenance |
| **WOCS** — the coordination | Coordination primitive: broadcast needs, verify delivery, settle via Lightning — no platform, no escrow, no intermediary | Gatekept coordination, siloed communities, single points of failure |
| **MAPS** — the rules | Four primitives (State, Verb, Arc, Mark) describing game mechanics as readable, composable scores | Knowledge loss, design isolation, inability to study or build on prior work |

## The Discipline of Protocol Restraint

Long-lived protocols share a pattern: aggressive exclusion. They define minimal coordination primitives and deliberately refuse features that could be layered above.

| Protocol | What It Does | What It Deliberately Excludes |
|----------|--------------|-------------------------------|
| **TCP/IP** | Packet routing | Content, security, identity, application semantics |
| **SMTP** | Store-and-forward messages | Encryption, spam filtering, read receipts |
| **Bitcoin** | Timestamped transaction ordering | Smart contracts, identity, privacy, governance |
| **MIDI** | Note events | Sound synthesis, audio, timing guarantees |
| **Musical notation** | Pitch and duration | Timbre, dynamics, expression |

The end-to-end principle (Saltzer, Reed, Clark 1984) articulates why: *functionality belongs at endpoints, not in the network*. Protocols that try to solve every problem become complex, fragile, and capturable. Protocols that stay minimal become infrastructure — neutral substrates that outlive their creators.

EGS follows this discipline:

- **AEMS** defines entity structure, not databases or marketplaces
- **RUNS** defines execution substrate and data-flow patterns, not specific engines or frameworks
- **WOCS** defines minimal coordination primitives (offer/fulfill/ack), not escrow, reputation, or payment processing
- **MAPS** defines interactive grammar, not execution or timing

When you ask "why does EGS not handle X?" — dispute resolution, content moderation, identity verification, complex governance — the answer is the same answer TCP/IP gives: *because X is not the protocol's job*. Communities, markets, and applications handle X. The protocol is the neutral ground they coordinate on.

This restraint is not laziness or incompleteness. It is the design philosophy that lets protocols endure for decades while platforms rise and fall.

## The Protocols

### AEMS: The Things
Layered Nostr events make game artifacts independent and interpretable across any game that reads them.
- **Entity** — Named role: an IP-agnostic concept (e.g., "sword"), discoverable on the open commons.
- **Manifestation** — Game-specific implementation (e.g., +50 attack, fire enchantment). References one or more Entities.
- **Asset** — Player's unique instance of a Manifestation.
- **State** — Mutable stats of that specific Asset (durability, upgrades).

Items earned in one game persist for import elsewhere because they exist on Nostr, not on any single game's servers. Any game can read an Entity reference and decide what to do with it.

### RUNS: Composable Engines
Data-oriented design: everything is Records with Fields, transformed by stateless Processors wired into Networks.
- Swap renderers, physics, or input without rewriting core logic.
- Mods are native Processor additions, not fragile hooks into proprietary engines.
- Naturally supports parallelism and explicit data flow.

RUNS runtimes reference AEMS Entities for content definitions and apply selected Manifestations. The [RUNS Library](https://github.com/enduring-game-standard/runs-library) provides semantic agreement on fundamental schemas (`runs:time`, `runs:transform`, `runs:input`).

### WOCS: Permissionless Coordination
A minimal coordination primitive built on Nostr: three events (Offer, Fulfill, Ack) with Lightning settlement.
- Broadcast a need with committed settlement amount (Offer).
- Prove delivery and request payment (Fulfill).
- Acknowledge completion with payment proof (Ack).

Open signals enabling strangers to coordinate server hosting, anti-cheat services, asset creation, tournament pooling, and any other ecosystem service — directly, with instant settlement.

### MAPS: The Rules
A neutral, implementation-agnostic system for describing game mechanics as readable, composable scores.
- **State** — Observable condition or situation.
- **Verb** — Available action or affordance.
- **Arc** — Directed transition or requirement linking States through Verbs.
- **Mark** — Token or quantifiable resource tracking progress, inventory, or score.

MAPS integrates directly with the composable infrastructure: States become RUNS Records, Verbs become Processors, Arcs become Networks. A designer who sketches a combat system in notation is writing the skeleton that the execution layer reads.

## Cumulative Craft

Durable substrate preserves games. Patient capital funds their development. But neither explains how the *knowledge of how to make games well* survives across generations. Physical game traditions solved this through apprenticeship and notation — chess theory accumulated in books, musical craft compounded through scores that any trained musician could read.

MAPS Notation provides this transmission layer for interactive design. When mechanics are written as readable scores rather than buried in proprietary code, designers can study, fork, and extend each other's work. The [MAPS Library](https://github.com/enduring-game-standard/maps-library) establishes semantic agreement on fundamental patterns — resource acquisition, locked transitions, basic exchanges — so common structures are composable rather than reinvented.

The [Austin School](https://github.com/enduring-game-standard/austin-school) complements notation with institutional memory: an open-source commons for game design knowledge that combines curated resources, community practice, and apprenticeship. Together, notation and institution provide the cumulative-craft pillar — the condition that lets game design compound across decades the way architectural, musical, and mathematical knowledge has compounded across centuries.

## Substrate Requirements

The standard requires two structural properties from its underlying infrastructure:

1. **Persistent signed broadcast with permissionless replication.** Every artifact — entity definitions, execution components, coordination offers, notation scores — must be signed by its creator, stored redundantly without any single operator's cooperation, and discoverable by anyone without permission. This is the structural requirement for cumulative craft: if artifacts depend on a single host, they die with that host.

2. **Instant settlement finality in a non-depreciating unit.** Coordination payments must complete atomically — either settled or not, with no intermediate state. Instant finality eliminates credit risk. Without credit risk, there is no need for escrow. Without escrow, there is no need for a trusted intermediary. Settlement in a non-depreciating unit ensures that the patient-capital incentive extends to coordination itself.

These requirements are substrate-independent. Any infrastructure that satisfies them is a valid foundation for the standard.

### Current Implementation: Nostr and Lightning

Nostr provides exactly the first property: cryptographic provenance (every event is signed by its creator), relay-based persistence (content survives on any relay that stores it), and permissionless discoverability (anyone can find and build on published work). Where a centralized database introduces a single point of failure and a blockchain introduces consensus overhead, Nostr provides a neutral commons with zero coordination cost.

Lightning provides the second: near-zero-fee settlement in bitcoin — instant finality without tokens, without intermediaries, and without the consensus overhead of on-chain transactions.

If either substrate were superseded, migration would be mechanical: convert the existing events to the new format and republish. The standard's value lives in its structural abstractions (entity hierarchies, data-flow composition, coordination primitives, interactive grammar), not in the specific event kinds or invoice formats that currently carry them.

## How It Works in Practice

Imagine "MOBA" as a genre like basketball:

- A community defines universal Entities (heroes, items, creeps) via AEMS. Each Entity is a signed Nostr event, discoverable by any client.
- Different groups publish Manifestations: "classic Dota-style," "fast-paced beginner variant," "underwater twist." Each references the same Entities but interprets them differently.
- Players own Assets — instances with history and state that persist on Nostr.

Casual play: Someone posts a WOCS Offer — "500 sats for a quick MOBA lobby tonight, classic rules." Others accept via any RUNS-compatible client. A community-hosted server runs the match. Items are recognized via Entity references — the receiving game decides what to do with them. Accounts and platforms are optional.

Niche play: A small group runs their own variant weekly. It stays niche indefinitely — a standing game among friends, sustained without scale.

Pro-layer play: A popular organizer funds high-uptime servers, anti-cheat services, and ranked matchmaking via recurring WOCS Offers. Thousands opt in for the polished experience. Third-party clients emerge with discovery feeds, analytics, or premium overlays. If the organizer gets extractive, players fork the ruleset or drop to raw pickup lobbies. The open foundation guarantees exit.

Value flows horizontally: modders earn directly for new Manifestations, artists for assets, hosts for reliability, streamers for casting. Ecosystems grow around the open ruleset without anyone owning the game itself.

## Scope: Commons and Authored Experiences

This standard optimizes for games that benefit from longevity and community evolution — genres that function like sports or folklore. But what of puzzle games where the solution is the treasure? Mystery narratives where a single spoiler destroys the journey? Interactive art where the creator's intent *is* the experience?

These authored experiences fit the same foundation through a philosophy of **abundance through reciprocity** rather than scarcity through enforcement:

- **Unforgeable Attribution** — Every creative act is cryptographically signed. Origin is mathematically provable without courts or takedowns. Copying is fine; *claiming* (fraud about authorship) is impossible.
- **Voluntary Covenants** — Authors attach use expectations as legible social signals ("attribution required," "commercial license needed"). Communities and reputation markets respect these through transparency, not enforcement.
- **First-Experience Economics** — Authored works monetize the *curated revelation* (paying for the puzzle-solving journey, not the solution itself). After encounter, content may open naturally.

Attribution and openness reinforce each other. Authors retain provenance and earn from first experiences. Copiers participate in cultural propagation. Both share the same open foundation.

The [Authorial Provenance Standard (APS)](https://github.com/enduring-game-standard/.github/blob/main/profile/APS.md) details this approach — provenance over property, covenants without enforcement, and markets for reputation and verification funded via WOCS.

## Convergence

Permissionless forking is a feature — backyard rules, regional styles, experimental variants. But cumulative craft also requires shared canon: enough agreement that designers can build on each other's work rather than speaking parallel dialects. The standard provides convergence through layered mechanisms rather than central authority:

- **Shared vocabularies** — The [MAPS Library](https://github.com/enduring-game-standard/maps-library) and [RUNS Library](https://github.com/enduring-game-standard/runs-library) establish semantic agreement on fundamental patterns and data shapes. A designer who imports `maps:locked-transition` composes with every other designer who targets the same pattern. A developer who targets `runs:transform` interoperates with every Processor that reads the same field.
- **Namespacing conventions** — The `std:` prefix in [AEMS Conventions](https://github.com/enduring-game-standard/aems-conventions) marks community-ratified universals. The `runs:` and `maps:` prefixes reserve protocol-level vocabulary. Third-party namespaces coexist freely.
- **Provenance chains** — Every artifact on Nostr carries its author's signature and references its predecessors. Forks are traceable. Lineage is discoverable. A future scholar can reconstruct which variant descended from which original, the way musicologists trace manuscript lineages.
- **Institutional memory** — The [Austin School](https://github.com/enduring-game-standard/austin-school) provides the cultural complement: curation, scholarship, and apprenticeship that select for quality the way academies and journals do in other fields.
- **Economic curation** — [WOCS](https://github.com/enduring-game-standard/wocs-protocol) coordinates funding for library contributions, curation, and audits. Communities can fund the convergence work they value.
- **RFC processes** — Breaking changes to shared vocabularies require community review (already established in the [RUNS Library](https://github.com/enduring-game-standard/runs-library)).

This mirrors how every durable standard has converged historically. Musical notation converged through conservatories, publisher conventions, and shared pedagogy — not through a standards body that dictated note shapes. Chess notation converged through tournament practice and published analysis — not through a central registry. The standard provides the structural conditions for convergence and trusts the surrounding craft to supply the cultural layer.

## Protocol Stability

The protocol primitives — MAPS's four elements (State, Verb, Arc, Mark), AEMS's four layers (Entity, Manifestation, Asset, State), RUNS's four components (Record, Field, Processor, Network), and WOCS's three events (Offer, Fulfill, Ack) — are designed to be stable across generations. They are minimal enough that evolution is primarily additive: new library patterns, new conventions, new ecosystem packages. The primitives themselves change only when genuinely new concepts emerge — an event expected to be rare, analogous to musical notation adding dynamic markings centuries after establishing the staff.

Evolution happens at the library and convention layers, which version independently. MAPS Patterns carry explicit version numbers. RUNS Library changes follow an RFC process. AEMS Conventions are separate from the core protocol and explicitly invite forking. This separation protects the protocol's role as neutral infrastructure while allowing the surrounding vocabulary to grow freely.

## Status

These are conceptual specifications — minimal, open, and language-agnostic — inviting experimentation. No reference implementations yet exist. The standard describes game structure and composition; execution is the job of runtimes, which may be centralized, distributed, or hybrid at any scale. A high-performance centralized server farm running a RUNS Network is a fully compliant implementation. The standard ensures that centralized layers remain voluntary overlays rather than locked-in dependencies.

This is an invitation to build games that endure — on substrate open enough to outlast the people who built them.

**MIT License** — Free to implement, adapt, share.