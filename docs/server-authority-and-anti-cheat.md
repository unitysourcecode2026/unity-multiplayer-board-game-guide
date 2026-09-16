# Server Authority and Anti-Cheat in Unity Multiplayer Games

Server authority is an important part of designing reliable and secure multiplayer games. In a multiplayer board game, the server should control important game rules and validate actions before changing the shared game state.

This guide explains server authority, client validation, common multiplayer cheating risks, and practical approaches for Unity multiplayer projects.

---

## 📑 Table of Contents

- [What Is Server Authority?](#what-is-server-authority)
- [Why Server Authority Matters](#why-server-authority-matters)
- [Client vs Server Responsibilities](#client-vs-server-responsibilities)
- [Authoritative Game State](#authoritative-game-state)
- [Validating Player Actions](#validating-player-actions)
- [Common Multiplayer Cheating Risks](#common-multiplayer-cheating-risks)
- [Server-Side Validation](#server-side-validation)
- [Dice Roll Example](#dice-roll-example)
- [Turn Validation](#turn-validation)
- [Preventing Invalid Movement](#preventing-invalid-movement)
- [Protecting Game Economy Data](#protecting-game-economy-data)
- [Client-Side vs Server-Side Logic](#client-side-vs-server-side-logic)
- [Handling Suspicious Requests](#handling-suspicious-requests)
- [Security Considerations](#security-considerations)
- [Testing Server Authority](#testing-server-authority)
- [Server Authority Checklist](#server-authority-checklist)
- [Related Documentation](#related-documentation)
- [Conclusion](#conclusion)

---

## What Is Server Authority?

Server authority means that the server is responsible for controlling important multiplayer game rules and the official game state.

Instead of allowing each client to decide whether an action is valid, the client sends a request to the server.

The server then:

1. Receives the request.
2. Identifies the player.
3. Checks the current game state.
4. Validates the requested action.
5. Applies the action if it is valid.
6. Updates the shared game state.
7. Sends the resulting state to connected players.

A simplified flow looks like this:

```text
Player
   |
   v
Client Request
   |
   v
Game Server
   |
   v
Validate Action
   |
   +---- Invalid ----> Reject
   |
   +---- Valid ------> Update Game State
                         |
                         v
                    Other Players
