# Authorial Provenance Standard (APS)

**A Voluntary Protocol Extension for Attribution, Covenants, and Creator Economics — Conceptual, January 2026**

---

The Decentralized Game Standard naturally serves games that resemble sports or folklore—commons by nature, where openness fuels longevity. But what of authored experiences? Puzzle games where the solution is the treasure. Mystery narratives where a single spoiler destroys the journey. Interactive art where the creator's intent is the experience itself.

These creations sit uneasily in purely open systems. The impulse is to reach for protection: DRM, enforcement, access control. Yet that path contradicts the abundance philosophy underlying everything else in DGS. It creates adversaries where there should be collaborators. It introduces friction for honest participants while failing to stop determined extractors.

There is another way. Instead of scarcity through enforcement, we propose **abundance through reciprocity**. Instead of treating information as property to be locked, we treat provenance as the primitive and attribution as the moral claim.

The result: authored experiences can thrive on the same open foundation as commons games—not by preventing copying (impossible and undesirable) but by making origin undeniable, creator expectations legible, and first-experience economics viable.

## The Moral Intuition Worth Preserving

Creators who invest deeply in their work often feel viscerally that wholesale extraction of their characters and story beats is *wrong*—even if they reject intellectual property law on principle. This intuition deserves a better framework than "information wants to be free" or "ideas are property."

What actually bothers authors isn't copying. It's:

- **Attribution erasure** — Someone passing off your creative act as theirs
- **Parasitic extraction** — Harvesting value you created without reciprocity
- **Context destruction** — Your characters meant something in your world; ripped out, they become hollow

These aren't property violations. They're **relational violations**—failures of honesty, reciprocity, and respect for creative labor.

IP law conflates these with property rights, which is philosophically incoherent. But dismissing IP doesn't require dismissing the underlying moral claims.

## The Distinction: Copying vs. Claiming

Consider a sealed letter. Anyone *can* open it before the intended time. But the seal *signals* "this was meant to be opened by X, at Y moment." Breaking the seal is socially understood to diminish the experience. The letter still exists if opened early—it's not destroyed.

Now consider two scenarios with your creative work:

**Scenario A: Copying**  
Someone reads your novel, loves a character, and writes fan fiction. They're extending *your* world, clearly derivative, often with attribution. The character lives beyond your pages. This is participation in a cultural commons you seeded—often flattering, sometimes transformative.

**Scenario B: Claiming**  
Someone takes your character wholesale, changes the name slightly, and publishes it as their original creation. They're *claiming* your creative act as theirs. This is fraud—a lie about origin.

The first is cultural propagation. The second is theft of credit.

IP law treats both as infringement. Your intuition correctly distinguishes them.

The Authorial Provenance Standard makes **claiming impossible** while allowing copying to flow naturally. Every creative act carries its author's cryptographic signature. Anyone can see who made it first. The math proves origin.

## Core Mechanisms

### 1. Unforgeable Attribution

Every AEMS Entity, RUNS Processor, or gamified element is a signed Nostr event with a timestamp. This is inherent to the protocol—no additional mechanism needed.

If someone rips your character and claims authorship, the provenance chain refutes them instantly. The original is timestamped and immutably attributed. You don't need courts or takedown requests. You need only point to the signature.

This is *stronger* than traditional IP in one sense: proof doesn't require lawyers or registration. The cryptography does it.

### 2. Voluntary Covenants

Authors can attach use expectations to their creations—not as locks, but as legible social signals.

```yaml
entity:
  # ... standard AEMS fields ...
  covenant:
    license: "CC-BY-NC"           # Standard or custom license
    attribution_required: true    # Signal preference
    commercial_contact: "..."     # How to negotiate commercial use
    covenant_text_cid: "ipfs://..." # Full covenant document if needed
```

These covenants are **purely social**. The protocol doesn't enforce them. But:

- Communities can filter, flag, or preference-rank based on covenant compliance
- Reputation aggregators (funded via WOCS) can track who honors vs. ignores covenants
- Social costs accrue to covenant violators—their npubs become associated with extraction

This mirrors how Creative Commons works in practice: rarely litigated, yet widely respected because reputation matters.

### 3. Market Coordination via WOCS

The protocol doesn't enforce covenants, but markets can emerge to provide verification, reputation, and dispute resolution services:

- **Attribution Verification** — Third parties offer services to prove/disprove authorship claims, compensated via WOCS offers
- **Covenant Compliance Tracking** — Aggregators maintain public records of who honors covenants
- **Reputation Markets** — Provenance chains become social capital; strong histories attract future commissions
- **Dispute Mediation** — Voluntary arbitration services for contested attribution

These aren't protocol mandates—they're market opportunities. The No-Code Rule is preserved: if a feature can be implemented by a third party, it belongs to the third party.

## What APS Deliberately Excludes

APS provides attribution infrastructure, not enforcement mechanisms. Like copyright registration proves creation without preventing copying, APS proves provenance without controlling distribution:

| Excluded | Why | Where It Belongs |
|----------|-----|------------------|
| **DRM/access control** | Protocol is abundance, not scarcity | Client-side choices, business models |
| **Enforcement** | Protocol signals, not polices | Social pressure, reputation markets |
| **Takedowns** | Protocol is permissionless | Community moderation, legal systems |
| **Content verification** | Protocol proves origin, not quality | Curation services |
| **Licensing compliance** | Protocol publishes covenants, not audits | Third-party monitoring via WOCS |

APS makes provenance undeniable and expectations legible. Everything else is social coordination—enabled by the protocol, not embedded in it.

### 4. First-Experience Economics

For authored experiences (puzzles, mysteries, narrative games), the value is often in the *first encounter*. A mystery loses its magic once solved. A puzzle game's joy is the journey to solution.

This creates natural economics:

**Sealed Content Concept**
Authors can mark content as "sealed"—signaling that certain elements are revelation-dependent:

```yaml
experience:
  sealed_content:
    revelation_order: ["prologue", "act1", "twist", "finale"]
    sealed_elements:
      - id: "twist"
        reveal_condition: "act1_complete"
    experience_license: "unsealing-payment"
```

**The Economics**
- Players pay (via WOCS) for the *experience* of proper revelation—not for the "content" which could theoretically be spoiled
- Payment unlocks the author-intended sequence in compliant clients
- After completion, players have experienced what they paid for—whether content becomes "open" afterward is the author's choice

This is like paying for a theater ticket: you're paying for the *curated experience of first revelation*, not for exclusive ownership of the script.

**Implementation Note**: Sealed content mechanics are conceptual. Clients may implement any approach to revelation sequencing—honor-system based, payment-gated, or hybrid. The standard specifies *what* (sealed markers, revelation order) not *how* (enforcement mechanism).

## Alignment with DGS Philosophy

| DGS Tenet | APS Alignment |
|-----------|---------------|
| **No Rent-Seeking** | Covenants are purely social signals; no protocol-level fee extraction |
| **Sats Only** | First-experience payments and reputation services settle via Lightning |
| **Protocol Neutrality** | Works for human authors, AI-assisted creation, collaborative works |
| **No-Code Rule** | Enforcement/reputation markets are third-party services, not protocol-embedded |
| **Permissionless** | Anyone can publish; covenants don't prevent use, just signal expectations |

## What This Does NOT Do

Explicit anti-features:

- **Does NOT prevent copying** — Impossible in open systems and philosophically undesirable
- **Does NOT require trusted authorities** — No signers, lineages, or governance gatekeepers
- **Does NOT impose friction on honest users** — Attribution and provenance are zero-cost
- **Does NOT create adversarial dynamics** — No arms race between enforcers and evaders
- **Does NOT conflate copying with stealing** — Preserves the distinction your intuition recognizes

## Integration Points

**AEMS** — Covenant tags on Entities and Manifestations signal author expectations. Provenance is native to signed events.

**RUNS** — Sealed content markers in containers enable revelation-sequenced experiences. Clients choose how to respect them.

**WOCS** — Coordinates reputation markets, attribution verification, first-experience payments, and dispute mediation as voluntary third-party services.

## The Unified Vision

Authors of authored experiences and curators of commons games can coexist on the same foundation:

- A puzzle game publishes sealed content with covenants requesting first-play payment
- A folklore-like battle royale publishes fully open with "attribution appreciated"
- Both persist forever via Nostr
- Both benefit from WOCS-funded infrastructure
- Neither depends on corporate gatekeepers or enforcement mechanisms

The authored work's value is in the experience—captured at revelation, not locked forever. The commons work's value is in infinite variation—enabled by openness. Both are products of creative labor deserving attribution. Neither requires DRM.

Abundance through reciprocity. Provenance over property. Attribution without enforcement.

---

## Status and Invitation

This is a conceptual proposal for how authored experiences fit within the DGS philosophy. It invites experimentation:

- Publish an Entity with covenant tags
- Build a simple reputation aggregator service
- Design a client that respects sealed content markers
- Explore first-experience payment flows

Feedback welcomed on: covenant semantics, sealed content mechanics, reputation market design, and philosophical gaps.

**MIT License** — Open for implementation, adaptation, and critique.
