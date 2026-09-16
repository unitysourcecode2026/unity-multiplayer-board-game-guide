# Client-Server vs P2P Multiplayer in Unity

Choosing the right networking architecture is an important decision when
building a multiplayer game in Unity.

Two common approaches are client-server and peer-to-peer (P2P) networking.
They organize communication and game authority differently, which can affect
security, reliability, scalability, latency, and development complexity.

For board games and turn-based multiplayer experiences, understanding these
differences helps developers design a network model that fits the game's rules
and expected player experience.

## Table of Contents

- [Client-Server Architecture](#client-server-architecture)
- [How Client-Server Works](#how-client-server-works)
- [Peer-to-Peer Architecture](#peer-to-peer-architecture)
- [How P2P Works](#how-p2p-works)
- [Client-Server vs P2P](#client-server-vs-p2p)
- [Game Authority](#game-authority)
- [Security Considerations](#security-considerations)
- [Latency and Reliability](#latency-and-reliability)
- [Board Game Example](#board-game-example)
- [Mobile Multiplayer Considerations](#mobile-multiplayer-considerations)
- [Architecture Decision Factors](#architecture-decision-factors)
- [Common Design Mistakes](#common-design-mistakes)
- [Related Documentation](#related-documentation)

---

## Client-Server Architecture

In a client-server architecture, players connect to a central server that
coordinates the multiplayer session.

A simplified structure looks like this:

```text
                 Game Server
                /     |     \
               /      |      \
              ▼       ▼       ▼
          Client 1 Client 2 Client 3
