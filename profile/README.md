# Decentralized Game Standard

**January 2026 — Conceptual Standards, Version 0.2**

What if digital games could endure like chess or poker—not as relics, but as living protocols? The Decentralized Game Standard defines how games can exist outside corporate servers, how players can truly own what they earn, and how creators can build on shared foundations.

---

## The Current State of Play

We are witnessing a structural failure in the gaming industry. It's not just about servers turning off—it's about a fundamental mismatch between the value players/creators generate and the architecture that captures it.

### 1. The Modding Dead End
Modding keeps games alive for decades, yet it remains a legal grey area with zero reliable monetization.
*   **The Skyrim "Paid Mods" Fiasco**: Previous attempts to monetize mods failed because they relied on centralized marketplaces taking 75% cuts, incentivizing low-effort theft.
*   **The Reality**: A modder who fixes *Cyberpunk 2077* or creates *Defense of the Ancients* creates billions in value but relies on donations or precarious "grey market" Patreon subs.
*   **The Fix**: Monetization must be peer-to-peer and protocol-native, not a store feature.

### 2. The Esports Chokehold
Esports is a sport where one company owns the ball, the field, and the rules.
*   **Publisher Dictatorship**: Blizzard killed the *Heroes of the Storm* pro scene overnight. Nintendo routinely shuts down *Smash Bros* tournaments.
*   **Licensing Hell**: Third-party organizers live in fear of IP takedowns. Sponsorships are gatekept by publishers.
*   ** The Fix**: Competitive layers must be decoupled from the game client. A tournament should be a permissionless layer on top of the game, not a marketing expense for the publisher.

### 3. The Preservation Crisis
The "Server Shutdown" is just the symptom. The disease is the lack of a "Game End-of-Life" protocol.
*   **The "Grey Market" of History**: *World of Warcraft* private servers saved the game's history when Blizzard wouldn't. They were legally persecuted for doing the preservation work the industry refused to do.
*   **Legal vs Technical**: There is no technical reason a server binary cannot be released when a game sunsets. It is a business decision to force players onto the next sequel.
*   **The Fix**: A standard for decentralized, community-hosted backends effectively "immortalizes" online games by design.

### 4. The Interoperability Lie
"Metaverse" hype promised interoperability but delivered walled gardens with different skins.
*   **Engine Lock-in**: A Unity asset doesn't work in Unreal. This is a hard technical hurdle, often cited as why "shared items" are impossible.
*   **The Business Incentive**: Even if technical hurdles were solved, *Fortnite* has zero incentive to let you use a skin you bought in *Call of Duty*.
*   **The Fix**: We stop asking permission. We standardize the *concept* (Entity) separate from the *implementation* (Manifestation). A "Dragon Sword" exists as data; *Fortnite* and *CoD* can interpret it (or ignore it) as they wish, but they no longer own the concept.

### 5. The Discoverability Algorithm
Indie devs are dying in the noise.
*   **The 30% Tax**: Steam takes 30% not just for hosting, but for *access* to users.
*   **The Algorithm Trap**: If you don't spike metrics on Day 1, the algorithm buries you. You are renting your audience from the platform.
*   **The Fix**: An open order book for games, assets, and services (WOSS). Discoverability becomes a query, not a black box algorithm.

This isn't just about "web3" or "crypto." It's about fixing the broken architecture that turns creators into serfs and players into renters.

---

## The Core Insight

A chess piece doesn't know the rules of chess. The piece just *is*. The rules interpret it. You can use that same piece in Fischer Random, in a variant you invented, or as a paperweight. It exists independently.

A Pokémon card in your drawer doesn't vanish when the company folds. You can still battle your grandson in 80 years with house rules.

Digital games trap everything inside servers. When the server dies, so does your sword, your character, your world. We can change this.

---

## What We're Building

Three interlocking standards that directly address the structural failures above:

| Standard | Purpose | Solves Problem # |
|----------|---------|------------------|
| **[AEMS](../../aems/README.md)** | **Asset-Entity-Manifestation-State**<br>Standardizes entities outside of any game client. | **#3 Preservation & #4 Interoperability**<br>Ensures assets survive server death and can be interpreted by multiple engines. |
| **[GERS](../../gers/README.md)** | **Game Engine Record Standard**<br>Composes engines from modular, swappable processors. | **#1 Modding & #3 Preservation**<br>Allows mods to be "processors" that slot in cleanly. Decouples logic from proprietary engines. |
| **[WOSS](../../woss/README.md)** | **Work-Offer Settlement Standard**<br>Coordination language settled in sats. | **#1 Modding, #2 Esports, #5 Discoverability**<br>Peer-to-peer payments for modders, permissionless tournament pools, and an open order book for discovery. |

### AEMS: The "Object Permanence" Layer
*Solves: The Interoperability Lie (#4) & The Preservation Crisis (#3)*

AEMS standardizes the *concept* of an item (Entity) separate from its *code* (Manifestation). A "Health Potion" is defined universally on Nostr.
*   **Fixes Lock-in**: If Unity changes pricing, your asset definitions are safe.
*   **Fixes Preservation**: Even if the *server* dies, the *Entity* and its *State* (who owns it) persist on the network, ready for a community server to pick up.

### GERS: The "Modular Engine" Layer
*Solves: The Modding Dead End (#1) & The Preservation Crisis (#3)*

GERS applies the "Unix Philosophy" to game engines. Instead of a monolithic binary, a game is a pipeline of small Processors reading Records.
*   **Fixes Modding**: A mod isn't a hack; it's just another Processor. Adding a "Damage Meter" or "New Physics Model" is natively supported.
*   **Fixes Preservation**: You can swap out a defunct "DirectX 11 Renderer Processor" for a "Vulkan Renderer Processor" without rewriting the game logic.

### WOSS: The "Open Bazaar" Layer
*Solves: The Esports Chokehold (#2), The Discoverability Algorithm (#5), & The Modding Dead End (#1)*

WOSS is a language for "I want this" (OFFER) and "I did this" (FULFILL), settled instantly in sats.
*   **Fixes Esports**: A tournament organizer posts an OFFER for a prize pool. Players FULFILL it by winning. The smart contract is the protocol; no publisher permission needed.
*   **Fixes Discoverability**: No black box algorithm. You query the network for "RPG Level Design" or "Co-op Session."
*   **Fixes Modding**: Modders get paid directly by users who want their features, with no store taking 30%.

---

## How They Work Together

**Scenario**: A level designer creates a dungeon map for a game.

1. **AEMS**: The dungeon is an Entity with Fields (layout, difficulty, lore). Any game can create a Manifestation of it.

2. **WOSS**: The designer posts an OFFER: "1000 sats for playtesting my dungeon." A player FULFILLs it with feedback. The designer pays, posts ACK with Lightning preimage.

3. **GERS**: A game engine composed of Processors (renderer, physics, AI) reads the dungeon Record and runs it. The runtime schedules everything—swap in a different renderer if needed.

4. **Ownership**: The dungeon's creator is tracked via AEMS chain-of-custody. If the game shuts down, the dungeon still exists on Nostr. Another game can interpret it.

---

## Tech Layer

**Nostr** — AEMS and WOSS are Nostr-native: entities, ownership, and work offers are all signed Nostr events. GERS is architecture-agnostic—processor definitions *can* live on Nostr for discoverability, but the runtime pattern works anywhere.

**Lightning** — Sats move instantly via Lightning invoices. Universal settlement. No banking relationship required.

---

## What This Is (And Isn't)

| This Is | This Is NOT |
|---------|-------------|
| Conceptual standards (v0.2) | Production-ready code |
| A decade-long vision | A quick fix |
| Open protocols anyone can implement | A product or company |
| Real decentralization (Nostr, Lightning) | Crypto hype or token schemes |

No reference implementations exist yet. Each standard includes a "Prototype Path" with hands-on steps from posting a Nostr event to building a minimal system.

---

## Shape It

This needs you:

- **Question**: What holds? What's missing?
- **Prototype**: Build something minimal using the standards
- **Discuss**: Open an issue, start a conversation

No rush. It's a foundation for games that last centuries.

---

## FAQ

See the [Frequently Asked Questions](FAQ.md) for deeper dives.

---

## License

[MIT License](../LICENSE) — Use it, extend it, keep it free.
