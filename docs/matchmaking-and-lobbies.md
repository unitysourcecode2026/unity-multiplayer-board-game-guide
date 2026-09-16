# Matchmaking and Lobbies in Unity Multiplayer

Matchmaking and lobby systems provide the connection between finding players
and starting a multiplayer game.

A lobby can allow players to gather, see who has joined, select settings, and
prepare for a match. Matchmaking can help connect players based on the rules
defined by the game.

For multiplayer board games, a clear lobby flow can make the transition from
the main menu to an active match easier to manage.

## Table of Contents

- [What Is a Multiplayer Lobby?](#what-is-a-multiplayer-lobby)
- [What Is Matchmaking?](#what-is-matchmaking)
- [Lobby vs Matchmaking](#lobby-vs-matchmaking)
- [Basic Multiplayer Flow](#basic-multiplayer-flow)
- [Creating a Lobby](#creating-a-lobby)
- [Joining a Lobby](#joining-a-lobby)
- [Lobby State](#lobby-state)
- [Player Ready System](#player-ready-system)
- [Starting the Match](#starting-the-match)
- [Private and Public Lobbies](#private-and-public-lobbies)
- [Player Limits](#player-limits)
- [Leaving a Lobby](#leaving-a-lobby)
- [Connection Problems](#connection-problems)
- [Mobile Considerations](#mobile-considerations)
- [Example Lobby State](#example-lobby-state)
- [Testing Matchmaking and Lobbies](#testing-matchmaking-and-lobbies)
- [Related Documentation](#related-documentation)

---

## What Is a Multiplayer Lobby?

A lobby is a temporary multiplayer space where players can gather before a
match begins.

A simple four-player board-game lobby might look like:

```text
┌─────────────────────────────┐
│       Game Lobby            │
│                             │
│ Player 1     Ready           │
│ Player 2     Ready           │
│ Player 3     Not Ready       │
│ Player 4     Ready           │
│                             │
│       Start Match           │
└─────────────────────────────┘
