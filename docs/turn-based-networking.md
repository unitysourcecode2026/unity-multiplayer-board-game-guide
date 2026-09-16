# Turn-Based Networking in Unity

Turn-based multiplayer games have a different networking model from fast
real-time games. Instead of constantly synchronizing rapid movement and
continuous actions, the network mainly needs to keep turn ownership, player
actions, and important game state consistent.

Board games, card games, strategy games, and tactical games can all benefit from
a clear turn-based networking design.

## Table of Contents

- [What Is Turn-Based Networking?](#what-is-turn-based-networking)
- [Basic Turn Flow](#basic-turn-flow)
- [Turn Ownership](#turn-ownership)
- [Turn Validation](#turn-validation)
- [Turn State Machine](#turn-state-machine)
- [Processing a Player Action](#processing-a-player-action)
- [Changing the Turn](#changing-the-turn)
- [Turn Timers](#turn-timers)
- [Handling Invalid Actions](#handling-invalid-actions)
- [Disconnected Players](#disconnected-players)
- [Late Joining](#late-joining)
- [Simultaneous Actions](#simultaneous-actions)
- [Example Turn Manager](#example-turn-manager)
- [Testing Turn-Based Networking](#testing-turn-based-networking)
- [Related Documentation](#related-documentation)

---

## What Is Turn-Based Networking?

Turn-based networking is a multiplayer design where players perform actions
according to a defined turn order.

A simple four-player game might use:

```text
Player 1
   ↓
Player 2
   ↓
Player 3
   ↓
Player 4
   ↓
Player 1
