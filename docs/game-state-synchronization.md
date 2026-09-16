# Game State Synchronization in Unity Multiplayer

Game state synchronization is one of the most important parts of a multiplayer
Unity game. Every connected player should receive the information required to
display the current match correctly.

In a multiplayer board game, this can include player positions, turns, scores,
dice results, cards, timers, and match status.

The goal is not necessarily to send every visual event over the network. Instead,
the networking system should keep the important shared state consistent while
allowing each client to handle presentation locally.

## Table of Contents

- [What Is Game State Synchronization?](#what-is-game-state-synchronization)
- [What Belongs in Game State?](#what-belongs-in-game-state)
- [Authoritative Game State](#authoritative-game-state)
- [State Update Flow](#state-update-flow)
- [Full State vs Incremental Updates](#full-state-vs-incremental-updates)
- [Synchronizing Player State](#synchronizing-player-state)
- [Synchronizing Turn State](#synchronizing-turn-state)
- [Synchronizing Board State](#synchronizing-board-state)
- [Handling Conflicting Updates](#handling-conflicting-updates)
- [Late Joining Players](#late-joining-players)
- [Reconnection and State Recovery](#reconnection-and-state-recovery)
- [Reducing Network Traffic](#reducing-network-traffic)
- [Example State Model](#example-state-model)
- [Synchronization Checklist](#synchronization-checklist)
- [Related Documentation](#related-documentation)

---

## What Is Game State Synchronization?

Game state synchronization is the process of keeping important multiplayer
game data consistent between the systems participating in a match.

For example:

```text
Player 1 Position = 8
Player 2 Position = 13
Current Turn = Player 3
Round = 4
