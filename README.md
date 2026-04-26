# Crystal Collector – Observer Pattern (UE5)

## Overview
This project is a simple third-person prototype built in Unreal Engine 5 to demonstrate the **Observer design pattern** using Event Dispatchers. The player collects crystals in a small level. Each crystal notifies the GameMode when it is collected, and the GameMode updates the score and checks for a win condition.

---

## Design Pattern Used

### Observer Pattern
- **Publisher (Subject):** BP_Crystal  
- **Observer (Listener):** BP_GameMode  
- **Communication:** Event Dispatcher (OnCrystalCollected)

When a crystal is collected, it broadcasts an event. The GameMode listens for this event and updates the score accordingly. This removes direct dependencies between objects and improves modularity.

---

## How It Works

1. Game starts
2. GameMode finds all crystals in the level
3. GameMode binds to each crystal’s OnCrystalCollected event
4. Player collects a crystal
5. Crystal broadcasts event
6. GameMode receives event → increases score
7. When all crystals are collected → "YOU WIN" is triggered

---

## Controls

- **WASD** – Move
- **Mouse** – Look around
- **Spacebar** – Jump

---

## How to Run

1. Open the project in Unreal Engine 5
2. Open the main level (e.g., `Lvl_ThirdPerson`)
3. Click **Play**
4. Collect all crystals to win

---

## Project Structure

- **BP_Crystal**
  - Handles overlap detection
  - Broadcasts OnCrystalCollected event
  - Destroys itself after collection

- **BP_GameMode**
  - Tracks Score and TotalCrystals
  - Subscribes to crystal events
  - Handles win condition
