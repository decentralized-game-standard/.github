## Frequently Asked Questions: Decentralized Game Standard

### General Questions

**What is the Decentralized Game Standard?**  
Three interlocking protocols—AEMS, GERS, and WOSS—that enable games to exist outside corporate servers. Built on Nostr for decentralized data and Lightning for instant settlement. The goal: games that last centuries, players who truly own their assets, and creators who build on shared foundations.

**Why should I care?**  
Digital games are fragile. When servers shut down, worlds vanish, progress evaporates, and assets become worthless. This standard addresses that structural problem—not by fighting the industry, but by defining open protocols anyone can build on.

**Is this ready to use?**  
No. These are conceptual standards (Version 0.2, January 2026). No reference implementations exist. Each standard includes prototype paths for hands-on exploration. This is a decade-long effort, not a product launch.

---

### For Developers

**What benefits could developers see?**  
Over time:
- Reusable entities via AEMS—define once, interpret across games
- Modular engine composition via GERS—swap processors without rewrites
- Direct compensation via WOSS—earn sats for contributions without platform fees

**What's the current state of the technology?**  
Nostr relay networks vary in reliability. Lightning routing has improved but isn't perfect. These are real trade-offs. The standards work within current limitations while anticipating improvements.

**How can developers engage now?**  
- Review the protocol specs in each standard's README
- Try the Tier 1 prototype paths (no code required)
- Open issues with questions or ideas
- Build minimal implementations

**Will this integrate with Unity, Unreal, Godot?**  
Future goal. GERS is designed to be engine-agnostic—existing engines could implement the Record/Processor pattern. No SDKs exist yet.

---

### For Studios

**What could studios gain?**  
- Reduced redundancy by building on shared entity definitions
- Revenue from player-driven economies that outlive individual titles
- Flexibility in monetization without platform constraints
- Games that don't die when you stop maintaining them

**Is this scalable?**  
Untested at scale. Decentralized systems currently trade some latency for censorship resistance. Better suited to turn-based, async, or smaller-scale projects initially. Performance research is ongoing.

**How do we prevent fragmentation?**  
AEMS defines a core schema structure. The Entity → Manifestation → State → Asset model ensures games can interpret shared entities differently without breaking the underlying standard.

**Can we participate without full commitment?**  
Yes. Monitor development, provide input on requirements, or build internal proofs-of-concept. No production adoption is expected at this stage.

---

### For Gamers

**What long-term benefits might I see?**  
- Own your in-game assets via cryptographic keys—no server required
- Games that persist beyond studio closures
- Earn sats for contributions like modding, hosting, or testing via WOSS
- A portable identity (your Nostr keypair) across games

**Could this affect gameplay quality?**  
Early implementations may have performance trade-offs. Decentralized data fetching adds latency compared to centralized servers. Caching and optimization strategies are being explored.

**How can gamers contribute?**  
- Test prototypes when available
- Join discussions and offer feedback
- Share your perspective on what matters in game longevity

---

### Technical Questions

**How does identity work?**  
Your Nostr keypair is your identity. No separate identity protocol is needed—Nostr profiles already provide usernames, avatars, and social graphs. Games interpret the same pubkey as the player.

**How does multiplayer coordination work?**  
WOSS can coordinate any offer-response pattern, including matchmaking and lobby formation. Third-party services build game-specific implementations on top, but the protocol provides the coordination language.

**What about cheating and verification?**  
WOSS enables verification services—third parties can attest to gameplay sessions, achievement legitimacy, or entity provenance. The protocol doesn't enforce verification; it enables markets for trust.

**What about mods and extensions?**  
GERS Processors are inherently modular. Third-party processors can be distributed and compensated via WOSS. No separate mod protocol is needed—the existing standards handle it.

**How do the three standards connect?**  
1. **AEMS** defines entities (the *what*)
2. **GERS** runs processors that read/write entity state (the *how*)
3. **WOSS** compensates creators and contributors (the *why*)

A level designer creates an AEMS entity, a GERS processor renders it, and WOSS ensures the designer gets paid when someone uses it.

---

### Long-term Vision

**What's the 10+ year goal?**  
An ecosystem where:
- Game assets function as interoperable concepts across titles
- Players retain items and progress indefinitely
- Developers build on shared, open foundations
- Games can run for centuries—maintained by communities, not corporations

**What if major studios don't adopt this?**  
Adoption will likely start with independent developers demonstrating viability. Studios may follow as player demand and economic incentives align. Or they may not—open protocols don't require permission.

**How will decentralization be sustained?**  
Open protocols don't need ongoing maintenance once solidified. Like TCP/IP or HTTP, the standards themselves are stable; implementations evolve. Governance will shift from initial contributors to the implementing community.

---

### Practical Steps

**What's the simplest thing I can do today?**

Each standard has a Tier 1 action requiring no code:

- **AEMS**: Post a Nostr note with `{ "name": "Iron Sword", "type": "item" }`—you've created a decentralized entity
- **WOSS**: Post a `kind:32001` event with `["sats", "100"]`—you've broadcast a work offer
- **GERS**: Sketch a network on paper—boxes (processors) connected by arrows (data flow)

See each standard's README for deeper prototype paths.

**What constitutes the first milestone?**

A proof-of-concept demonstrating:
- Two games sharing an AEMS-defined entity
- A WOSS transaction compensating a contributor
- A GERS processor powering a basic game feature

This marks the shift from theory to prototype.

---

### Final Thoughts

**Why should this matter now?**  
The gaming industry loses cultural capital to short-lived, platform-bound models. This standard offers a path to games that endure—open, resilient, community-owned. It's an investment in a future where gaming thrives for centuries.

**What if this effort fails?**  
Even failure plants seeds. The ideas may inspire alternatives or shift industry perspectives. The greater risk is inaction—perpetuating systems where games die with their servers. This is a calculated step toward something better.
