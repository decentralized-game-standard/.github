# Decentralized Game Standard

**Protocols for Games That Endure as Open Rulesets — Conceptual Framework, 2026-01-14**

📦 **[AEMS](https://github.com/decentralized-game-standard/aems-standard)** · 🔧 **[RUNS](https://github.com/decentralized-game-standard/runs-standard)** · 📖 **[RUNS Library](https://github.com/decentralized-game-standard/runs-standard-library)** · ⚡ **[WOCS](https://github.com/decentralized-game-standard/wocs-standard)** · 🎭 **[MAPS](https://github.com/decentralized-game-standard/ludic-notation-standard)** · ❓ **[FAQ](https://github.com/decentralized-game-standard/.github/blob/main/profile/FAQ.md)**

A child builds a LEGO castle on the living room floor. Three hundred bricks, eight hours of work, a drawbridge that actually opens. The castle is theirs. LEGO made the bricks, but the castle belongs to the child. If LEGO goes bankrupt tomorrow, the castle still stands on the floor. The child can add to it, take it apart, combine it with any other LEGO set ever manufactured. The bricks have a standard interface — the stud-and-tube coupling — that makes every brick compatible with every other brick across decades of production. No server keeps the castle alive. No subscription maintains it. No terms of service let anyone dissolve it remotely.

Now imagine a version of LEGO where the company retains ownership of every brick. The castle exists on LEGO's servers. You can look at it through an app, but you cannot hold it. When LEGO decides the product line is no longer profitable, every castle built from those bricks disappears. Your eight hours of work, the drawbridge mechanism you figured out, the satisfaction of seeing it on your shelf — gone. Not because the castle broke. Because the company that made the bricks decided to stop maintaining the system that let the bricks exist.

That is the current model of digital games.

## The Fusion Problem

In every digital game shipped today, four distinct concerns are welded into a single product: the game's rules, the engine that runs them, the servers that host them, and the platform that distributes them. When any one of these layers fails — the company loses interest, the engine is deprecated, the servers are shut down, the platform delists the title — the entire game dies. Not because the rules stopped being good. Because the rules were inseparable from infrastructure that someone else controlled.

This is the structural equivalent of a LEGO set where the bricks, the instructions, the table they sit on, and the store that sold them are all one fused object. Remove the store, and the bricks dissolve.

The question is whether the fusion is necessary. In every other medium where humans build things meant to last, the answer has been no.

## The Separation

In the 1880s, every factory in America that needed electric power ran its own generator. Edison's Pearl Street Station powered a few blocks of lower Manhattan through proprietary wiring. Each factory was a self-contained system: its own dynamo, its own wiring, its own voltage, its own maintenance crew. If the factory closed, the power system died with it. Nothing was reusable. Nothing was interchangeable. A motor built for one factory's voltage could not run on another factory's current.

The standardized electrical grid changed the equation by separating power generation from power consumption. Standard voltage. Standard outlets. Standard plugs. Now any appliance could draw power from any outlet. The factory that built your refrigerator could go bankrupt, and the refrigerator still worked. Power generation became competitive — gas, hydro, nuclear, solar — because the interface was shared. Innovation exploded on both sides of the plug because neither side owned the other.

DGS performs the same separation for digital games. Four protocols unbundle the four fused layers:

**AEMS** (Asset-Entity-Manifestation-State) separates game entities from the games that use them. A sword is a universal concept (Entity), given specific stats by each game (Manifestation), owned by a player's cryptographic key (Asset), with its own history (State). Signed Nostr events on open relays. The way a LEGO brick exists independently of any particular model you build with it.

**RUNS** (Record Update Network System) separates game logic from the engine that executes it. Data flows through stateless Processors wired into explicit Networks. Swap the renderer. Keep the physics. Replace the input system. The data shapes are standard. The way any appliance can plug into any outlet because the voltage is shared.

**WOCS** (Work Order Coordination Settlement) separates game coordination from platforms. Three Nostr events and a Lightning payment. Broadcast a need (Offer). A stranger fulfills it with proof (Fulfill). Settle instantly (Ack). Server hosting, anti-cheat, tournaments, mod creation — coordinated without a platform taking a cut. The way independent contractors show up at a job site without a staffing agency.

**MAPS** (Marks, Actions, Patterns, Scores) separates game rules from code. Four primitives — States, Verbs, Arcs, Marks — compose into reusable Patterns and complete Scores. Any engine can read a Score. Any designer can fork it. The way four DNA bases compose into genes that any cell can read and any organism can inherit.

Built on Nostr for resilient data and Lightning for instant settlement. No blockchains, tokens, or new consensus layers.

## What Play Looks Like

Imagine a MOBA genre where no company owns the ball.

A community defines the universal archetypes — heroes, items, creeps, towers — as AEMS Entities on Nostr. Different groups publish their own Manifestations: a "classic balance" pass, a "fast-paced beginner variant," an "underwater twist." The hero archetypes are shared across all of them; the stats and mechanics diverge.

Tuesday night. Someone posts a WOCS Offer: "500 sats buy-in, five-on-five MOBA, classic rules, lobby opens at 9pm." Nine other players see it on Nostr and join through any RUNS-compatible client. A community-hosted server runs the match. Items import automatically from each player's AEMS inventory. No accounts created. No platform logged into. The match happens the way a neighborhood basketball game happens: people showed up at the court.

A small group runs a weird variant every Thursday. Underwater MOBA, inverted controls. Five regular players. It stays cult forever, the way a Thursday-night poker game with friends stays cult forever. The costs are negligible because the protocols are lightweight and the server Offer is small.

Meanwhile, an ambitious organizer sees demand and builds on top. High-uptime servers, contracted anti-cheat, ranked matchmaking, streamed tournaments — all funded through recurring WOCS Offers. Thousands opt in for the polished experience. Third-party clients emerge with premium overlays, analytics, and social features. If the organizer becomes extractive, players drop to raw community lobbies. The foundation guarantees exit because no one owns the bricks.

Value flows to the people creating it. Modders earn for new Manifestations. Artists earn for asset creation. Hosts earn for reliability. Every transaction settles peer-to-peer. No store takes 30%.

## Authored Experiences

Genres-as-open-rulesets is the primary design target. But authored experiences — puzzle games where the solution is the treasure, mysteries where a single spoiler is fatal, interactive art where the creator's vision is the medium — also sit on the same foundation.

Attribution is cryptographic and unforgeable. Every creative act is signed. Copying a work is possible; falsely claiming authorship is mathematically prevented. Authors attach use expectations as legible social signals. Communities and reputation markets respect these through transparency, and the protocol enforces nothing beyond the signature. First-experience economics let creators monetize the curated revelation (paying for the journey), with content opening naturally after encounter.

Provenance over property. Covenants without enforcement. Markets for reputation funded via WOCS.

## Status

These are conceptual specifications. No reference implementations exist. No production games run on these protocols. The focus is the structural problem at the core of digital games: the fusion of rules, engine, server, and platform into a single killable product. The protocols separate those layers so that games can outlive the companies that built them, the way a LEGO castle outlives the store that sold the bricks.

Massive synchronous experiences may always involve voluntary centralized layers. The protocols guarantee those layers remain optional and replaceable.

**MIT License** — Free to implement, adapt, share.