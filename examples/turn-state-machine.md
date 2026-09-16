# Turn State Machine Example for Unity Multiplayer

A turn state machine provides a structured way to control the different stages of a turn-based multiplayer game.

Instead of allowing actions at any time, the game can move through predefined states such as waiting for a player, rolling the dice, selecting an action, processing the action, and ending the turn.

---

## 📑 Table of Contents

- [What Is a Turn State Machine?](#what-is-a-turn-state-machine)
- [Why Use a State Machine?](#why-use-a-state-machine)
- [Basic Turn Flow](#basic-turn-flow)
- [Turn States](#turn-states)
- [State Transition](#state-transition)
- [Example TurnState Enum](#example-turnstate-enum)
- [Example Turn Manager](#example-turn-manager)
- [Validating Player Actions](#validating-player-actions)
- [Handling Invalid Actions](#handling-invalid-actions)
- [Handling Disconnections](#handling-disconnections)
- [Turn Timer](#turn-timer)
- [Multiplayer Synchronization](#multiplayer-synchronization)
- [Testing the Turn State Machine](#testing-the-turn-state-machine)
- [Related Documentation](#related-documentation)
- [Conclusion](#conclusion)

---

## What Is a Turn State Machine?

A turn state machine divides gameplay into clearly defined states.

For example:

```text
WaitingForPlayer
       |
       v
StartTurn
       |
       v
RollDice
       |
       v
ChooseAction
       |
       v
ProcessAction
       |
       v
EndTurn
       |
       v
StartTurn
