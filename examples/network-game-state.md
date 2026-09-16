# Network Game State Example for Unity Multiplayer

A multiplayer game needs a shared game state that represents the current condition of the match.

In a Unity board game, this can include players, turns, board positions, scores, dice results, match status, and other values required to continue the game.

This example shows how a simple network game state can be structured and synchronized in a multiplayer project.

---

## 📑 Table of Contents

- [What Is Game State?](#what-is-game-state)
- [Why Game State Matters](#why-game-state-matters)
- [Typical Multiplayer Game State](#typical-multiplayer-game-state)
- [Example Game State Model](#example-game-state-model)
- [Player State](#player-state)
- [Turn State](#turn-state)
- [Board State](#board-state)
- [Match State](#match-state)
- [Updating Game State](#updating-game-state)
- [Server-Authoritative State](#server-authoritative-state)
- [Synchronizing Clients](#synchronizing-clients)
- [Late Join State](#late-join-state)
- [Reconnect State](#reconnect-state)
- [Example Network Flow](#example-network-flow)
- [Testing Network Game State](#testing-network-game-state)
- [Network Game State Checklist](#network-game-state-checklist)
- [Related Documentation](#related-documentation)
- [Conclusion](#conclusion)

---

## What Is Game State?

Game state is the collection of information that describes the current condition of a multiplayer match.

For example:

```text
Game State
├── Match Status
├── Current Turn
├── Players
├── Board
├── Dice Result
├── Scores
└── Winner
