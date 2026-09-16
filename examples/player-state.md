# Player State Example for Unity Multiplayer

Player state represents the information associated with each player during a multiplayer match.

A well-structured player state helps the server track players and allows clients to display the correct information without mixing gameplay data with visual presentation.

This example demonstrates a simple player-state structure for a Unity multiplayer board game.

---

## 📑 Table of Contents

- [What Is Player State?](#what-is-player-state)
- [Why Player State Matters](#why-player-state-matters)
- [Typical Player State Data](#typical-player-state-data)
- [Example Player State](#example-player-state)
- [Player State Lifecycle](#player-state-lifecycle)
- [Player Joining](#player-joining)
- [Player Ready State](#player-ready-state)
- [Player Turn State](#player-turn-state)
- [Player Movement](#player-movement)
- [Player Score](#player-score)
- [Player Disconnection](#player-disconnection)
- [Player Reconnection](#player-reconnection)
- [Server Authority](#server-authority)
- [Synchronizing Player State](#synchronizing-player-state)
- [Example State Flow](#example-state-flow)
- [Testing Player State](#testing-player-state)
- [Player State Checklist](#player-state-checklist)
- [Related Documentation](#related-documentation)
- [Conclusion](#conclusion)

---

## What Is Player State?

Player state is a collection of values describing a player's current status in a multiplayer game.

For example:

```text
Player State
├── Player ID
├── Player Name
├── Position
├── Score
├── Ready State
├── Turn State
└── Connection State
