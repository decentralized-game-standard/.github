# Frequently Asked Questions: Decentralized Game Standard

🏠 **[Overview](https://github.com/decentralized-game-standard)** · 📦 **[AEMS](https://github.com/decentralized-game-standard/aems-standard)** · 🔧 **[GERS](https://github.com/decentralized-game-standard/gers-standard)** · ⚡ **[WOSS](https://github.com/decentralized-game-standard/woss-standard)** · ✍️ **[APS](https://github.com/decentralized-game-standard/decentralized-game-protection)** · 📜 **[Ludic](https://github.com/decentralized-game-standard/ludic-standard)**

---

## Overview

**What is the Decentralized Game Standard?**  
A set of three minimal, interlocking protocols—AEMS (Asset-Entity-Manifestation-State), GERS (Game Engine Record Standard), and WOSS (Work-Offer Settlement Standard)—designed to make digital games more resilient, interoperable, and community-driven. Built entirely on existing open infrastructure (Nostr for persistent data and Lightning for settlement), they separate durable game objects from interpretive rules, enable modular engine construction, and facilitate direct peer-to-peer coordination. The aim is to create games that can persist for generations, much like chess or go, without depending on any single company or server.

**Why does this matter?**  
Most digital games are architecturally fragile: they rely on centralized servers that can be switched off, revocable licenses that can be taken away, and proprietary engines that lock in assets and progress. The result is cultural loss—entire worlds, inventories, and communities disappear when support ends. This standard proposes an alternative path where players retain meaningful control, creators earn directly, and games can evolve indefinitely through open contribution.

**Is this production-ready?**  
Not yet. These are conceptual specifications (2026-01-14) with no reference implementations. The focus is on clear, minimal protocols that anyone can experiment with today. Each includes incremental prototype steps starting from single Nostr events. This is a long-term architectural proposal, not a finished product.

## For Players

**What could change for me as a player?**  
Over time, you might:
- Carry items, characters, or progress across different games via shared AEMS entities
- Retain ownership of assets through cryptographic keys, independent of any studio
- Earn sats for contributions (hosting servers, testing, or creating content) via WOSS
- Play games that survive studio closures, maintained by communities

**Will gameplay feel different?**  
Early experiments may involve trade-offs—decentralized data fetching can introduce latency compared to optimized central servers. Caching, local prediction, and hybrid approaches are possible mitigations. The standards prioritize correctness and longevity over peak performance in every scenario.

**How can I get involved now?**  
- Follow development discussions
- Try the no-code Tier 1 prototypes (e.g., posting an entity definition on Nostr)
- Share feedback on what features matter most for longevity and ownership

## For Developers and Modders

**What advantages could this offer developers?**  
- AEMS allows defining entities once and reusing them across projects
- GERS enables truly modular engines—replace renderers, physics, or input systems without breaking everything
- WOSS provides direct, instant payment for features, fixes, or assets—no platform cuts

**How realistic is adoption for indie or solo developers?**  
The protocols are deliberately lightweight. A solo developer could start by importing AEMS entities into a simple GERS-style pipeline and accepting WOSS payments for custom work. No large team or funding required to experiment.

**What are the current technical limitations?**  
Nostr relay availability varies; some events may require multiple relays for reliable retrieval. Lightning payments work well for micro-transactions but routing can occasionally fail. These are known constraints of the underlying infrastructure, not the standards themselves.

**How do I start building?**  
Each protocol includes a stepped prototype path:
- Step 1: No-code actions (post events, sketch networks)
- Steps 2–5: Gradually add reading, writing, and scheduling logic
Review the individual READMEs and experiment freely.

## For Studios and Larger Teams

**What strategic benefits might studios see?**  
- Reduced duplication of effort through shared entity definitions
- New revenue models from persistent, player-owned economies
- Flexibility to pivot technology stacks without losing core content
- Games that continue generating value long after active development ends

**Does this require abandoning existing engines?**  
No. GERS patterns can be incrementally adopted within existing codebases. AEMS entities can be imported alongside proprietary assets. Studios can participate selectively—monitoring, contributing feedback, or running internal experiments.

**How do we maintain creative control?**  
Games retain full authority over their Manifestations (AEMS) and Processor selection (GERS). Shared entities are optional; proprietary ones remain possible. The standards enable interoperability without mandating it.

**Is this suitable for high-performance, real-time games?**  
Untested at AAA scale. Decentralized data introduces challenges for sub-millisecond synchronization. Turn-based, asynchronous, or smaller-scale titles are more natural starting points. Performance optimizations are an open research area.

## Technical Deep Dive

**How is identity handled?**  
Your Nostr keypair serves as your universal identity—no additional system needed. The same pubkey signs entity ownership, state updates, work offers, and game actions. Profiles (name, avatar, bio) come from standard Nostr NIP-05/NIP-57 features.

**How does multiplayer work?**  
The standards are transport-agnostic. WOSS can coordinate matchmaking offers ("hosting a lobby for X game") and session funding. Actual networking can use WebRTC, dedicated relays, or hybrid approaches built on top.

**What about anti-cheat and trust?**  
No built-in enforcement—the protocol enables markets for verification. Third parties can offer signed attestations, replay analysis, or reputation aggregation, compensated via WOSS. Games choose their trust model.

**How do mods fit in?**  
GERS treats mods as additional Processors that slot into the network. Distribution and compensation happen naturally through WOSS and AEMS provenance.

**How do the protocols connect in practice?**  
- AEMS provides the persistent "what" (entities and state)
- GERS provides the runtime "how" (Processors transforming Records)
- WOSS provides the economic "why" (incentives for creation and maintenance)

Example flow: A community defines an AEMS sword → multiple games manifest it differently in their GERS engines → a modder adds a new visual Processor and gets paid via WOSS → ownership transfers remain valid across all implementations.

## Authored Experiences and Provenance

**Does this standard only work for "sports-like" games? What about puzzle games, mysteries, or narrative experiences?**  
The core protocols (AEMS, GERS, WOSS) naturally serve commons-style games—those that benefit from open variation like folklore or sports. But authored experiences (puzzles, mysteries, artistic visions) fit the same foundation through the Authorial Provenance Standard (APS).

**How can authored works exist in an open system without being "spoiled"?**  
The key insight is that authored experiences monetize the *first encounter*, not eternal exclusivity. A puzzle game's value is in the journey of solving it—once solved, the solution naturally becomes known. APS enables:
- **Sealed content markers** — Authors signal which elements are revelation-dependent
- **First-experience payments** — Players pay (via WOSS) for the curated experience of proper revelation
- **Post-encounter openness** — Content may open naturally after the experience, contributing to cultural commons

This is like paying for a theater ticket: you pay for the experience of first revelation, not perpetual ownership of the script.

**What about someone copying my characters or story beats?**  
APS distinguishes between *copying* (cultural participation) and *claiming* (fraud about authorship). Every creative act is cryptographically signed with your Nostr keypair—origin is mathematically provable. Someone can riff on your work, but they cannot claim to have created it. The provenance chain proves you made it first.

**Can I set terms for how my work is used?**  
Yes, through voluntary covenants—metadata attached to your creations signaling your expectations ("attribution required," "commercial use needs license," etc.). These are purely social signals; the protocol doesn't enforce them. But communities and reputation markets (funded via WOSS) can track who respects vs. ignores covenants, creating social costs for violators.

**Isn't this just trusting people to be good?**  
Partly—but with transparency. Covenants are legible. Provenance is unforgeable. Reputation aggregators can surface who consistently honors vs. exploits creator expectations. The protocol enables markets for verification and dispute mediation, compensated via WOSS. Enforcement isn't baked in, but coordination tools can emerge.


## Long-Term Perspective

**What is the multi-decade vision?**  
An ecosystem of games that compound cultural value: assets that travel between titles, engines that evolve without breaking old content, communities that self-fund preservation and innovation. Games as living protocols, not disposable products.

**What if major publishers ignore this?**  
Open standards don't require permission. Viability can be proven by independents first, creating player demand that larger studios eventually respond to—or not. The protocols remain available either way.

**How will the standards evolve?**  
Through open discussion and implementation feedback. Once proven patterns emerge, the specifications can stabilize like other internet protocols. No central governance—just community consensus via adoption.

## Immediate Next Steps

**What is the easiest way to engage today?**  
Try a Tier 1 prototype—no coding required:
- **AEMS**: Publish a kind 30001 event defining a simple item
- **GERS**: Draw a data-flow diagram for a basic game loop
- **WOSS**: Broadcast a kind 32001 offer for a small task

These actions demonstrate the core ideas in minutes.

**What would count as a meaningful milestone?**  
A working demo where:
- An AEMS entity is shared between two independent game prototypes
- A GERS processor is added and compensated via WOSS
- Ownership/state persists across sessions

This would shift the project from speculation to tangible proof-of-concept.

## Closing Note

The gaming medium deserves architectures that match its cultural significance. Centralized models have delivered incredible experiences but at the cost of premature obsolescence and captured value. This standard offers a different foundation—one rooted in openness, resilience, and direct human coordination. Whether it succeeds broadly or inspires better alternatives, the conversation itself moves the industry forward.

Experiment, question, build. The protocols are here for anyone to use.

**MIT License** — All specifications are free to implement and extend.