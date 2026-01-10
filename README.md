# Internal: Decentralized Game Standard Protocol Team

> [!CAUTION]
> **READ BEFORE CONTRIBUTING**
> This repository (`.github`) is the meta-layer for our organization. The public face is in [profile/README.md](profile/README.md). This document is for valid protocol contributors only.

## Architecture Guidelines

We are building protocols, not platforms. When proposing changes to AEMS, GERS, or WOSS, strict adherence to these rules is required:

1.  **No Rent-Seeking**: If your proposal adds a fee, token, or "governance" layer that extracts value without adding work, it will be rejected. 
2.  **Sats Only**: We settle in Bitcoin (Lightning). Do not propose new tokens for settlement.
3.  **Protocol Neutrality**: The protocol must not care if the user is a human, an AI, or a script. It must not care about the game genre.

## "Secret" Best Practices

We generally don't publish these rules widely to avoid bikeshedding, but they are enforced during code review:

*   **The "No-Code" Rule**: If a feature can be implemented by a 3rd party without changing the protocol, it belongs to the 3rd party. Do not bloat the standard.
*   **Documentation is Code**: In a standard, the README *is* the product. Clarity is as important as the JSON schema. Ambiguity leads to fragmentation.
*   **Ignore the Price**: We do not discuss the price of Bitcoin. We build rails for value, not speculation.

## Repository Structure

*   `/profile`: The public face. High-level manifesto.
*   `/gers`: The engine standard.
*   `/woss`: The labor standard.
*   `/aems`: The entity standard.

## Emergency Contacts

If a protocol flaw is discovered that risks user funds or creates infinite spam loops on Nostr relays:
1.  Open an issue tagged `CRITICAL-SECURITY` within the specific repo.
2.  Do not publicly disclose the exploit vector until patches are merged.

---

*This document is public but unadvertised. If you found it, you're looking deep enough to contribute.*