# Multiplayer Architecture in Unity

Designing a multiplayer game in Unity starts with choosing an architecture that
can keep players synchronized while maintaining reliable and predictable game
logic.

For board games, turn-based games, card games, and similar multiplayer
experiences, the architecture should clearly separate player input, game rules,
network communication, and shared game state.

## Table of Contents

- [What Is Multiplayer Architecture?](#what-is-multiplayer-architecture)
- [Core Components](#core-components)
- [Client-Server Architecture](#client-server-architecture)
- [How a Multiplayer Turn Works](#how-a-multiplayer-turn-works)
- [Game State](#game-state)
- [Network Messages](#network-messages)
- [Server Authority](#server-authority)
- [Handling Disconnections](#handling-disconnections)
- [Choosing an Architecture](#choosing-an-architecture)
- [Recommended Project Structure](#recommended-project-structure)
- [Performance Considerations](#performance-considerations)
- [Testing Multiplayer Architecture](#testing-multiplayer-architecture)
- [Related Resources](#related-resources)

---

## What Is Multiplayer Architecture?

Multiplayer architecture describes how players, game clients, servers, and game
data communicate with each other.

A typical multiplayer Unity game contains:

```text
Player
   │
   ▼
Unity Client
   │
   │ Network Messages
   ▼
Game Server
   │
   ├── Game Rules
   ├── Match State
   ├── Player State
   └── Turn State
   │
   ▼
Other Players
