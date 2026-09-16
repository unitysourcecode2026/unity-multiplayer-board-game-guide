# Reconnect System in Unity Multiplayer

Network disconnections are common in multiplayer games, especially on mobile
devices where players can switch between Wi-Fi and mobile data or temporarily
lose connectivity.

A reconnect system allows a multiplayer game to detect a disconnected player,
preserve the appropriate game state, and restore the player's session when the
connection becomes available again.

For turn-based board games, reconnect support is particularly useful because a
match may continue for several minutes while players are taking turns.

## Table of Contents

- [What Is a Reconnect System?](#what-is-a-reconnect-system)
- [Why Reconnection Matters](#why-reconnection-matters)
- [Disconnect Detection](#disconnect-detection)
- [Basic Reconnect Flow](#basic-reconnect-flow)
- [Preserving Player State](#preserving-player-state)
- [Identifying the Reconnecting Player](#identifying-the-reconnecting-player)
- [Restoring Game State](#restoring-game-state)
- [Reconnecting During a Turn](#reconnecting-during-a-turn)
- [Reconnect Timeout](#reconnect-timeout)
- [Mobile Network Switching](#mobile-network-switching)
- [Late Reconnection](#late-reconnection)
- [Handling Reconnect Failures](#handling-reconnect-failures)
- [Example Reconnect State](#example-reconnect-state)
- [Testing Reconnection](#testing-reconnection)
- [Related Documentation](#related-documentation)

---

## What Is a Reconnect System?

A reconnect system defines what happens when a player's network connection is
lost and the player attempts to return to the same multiplayer session.

A basic flow is:

```text
Player Connected
      │
      ▼
Network Connection Lost
      │
      ▼
Player Marked Disconnected
      │
      ▼
Reconnect Attempt
      │
      ▼
Player Identified
      │
      ▼
Game State Restored
      │
      ▼
Player Continues Match
