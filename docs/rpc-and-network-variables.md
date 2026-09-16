# RPCs and Network Variables in Unity Multiplayer

RPCs and synchronized network variables are two important concepts in Unity
multiplayer development.

They solve different problems:

- **RPCs** can be used to communicate that an action or event should happen.
- **Network variables** can represent synchronized values that clients need to
  observe.

For multiplayer board games, understanding the difference helps developers
avoid unnecessary network traffic and keep game logic organized.

## Table of Contents

- [What Is an RPC?](#what-is-an-rpc)
- [What Is a Network Variable?](#what-is-a-network-variable)
- [RPC vs Network Variable](#rpc-vs-network-variable)
- [Client to Server Communication](#client-to-server-communication)
- [Server to Client Communication](#server-to-client-communication)
- [Example: Rolling a Dice](#example-rolling-a-dice)
- [Example: Synchronizing Player Position](#example-synchronizing-player-position)
- [Choosing Between RPCs and Variables](#choosing-between-rpcs-and-variables)
- [Avoiding Unnecessary Network Traffic](#avoiding-unnecessary-network-traffic)
- [Authority and Validation](#authority-and-validation)
- [Common Mistakes](#common-mistakes)
- [Related Documentation](#related-documentation)

---

## What Is an RPC?

RPC stands for **Remote Procedure Call**.

In multiplayer development, an RPC is a mechanism for requesting that a method
or action be executed on another network participant.

A conceptual flow looks like:

```text
Client
  │
  │ RPC Request
  ▼
Server
  │
  │ Execute / Validate
  ▼
Game Logic
