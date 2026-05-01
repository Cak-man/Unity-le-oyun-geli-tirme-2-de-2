# Unity Advanced Horror & Stealth Mechanics

This repository contains advanced game systems and scripts based on the book **"Unity'le Oyunlar Tasarlama"** (Series: 2/2) by **Yiğit Çakman**. This module focuses on professional single-player horror mechanics, AI behaviors, and 3D environment interaction[cite: 2].

## 🛠 Advanced Features

### 1. Artificial Intelligence (Enemy AI)
A complete NavMesh-based enemy system featuring:
*   **Patrol & Idle:** Randomly moves between waypoints with configurable wait times[cite: 2].
*   **Detection (Raycasting):** Uses field-of-view raycasting to detect the player[cite: 2].
*   **Chase & Jumpscare:** Switches to high-speed chasing upon detection and triggers a jumpscare animation/scene transition on contact[cite: 2].
*   **Footstep System:** Dynamic audio feedback for walking and sprinting states[cite: 2].

### 2. Stealth & Hiding System
A dual-script system (`hidingPlace.cs` & `roomDetector.cs`) for immersive stealth:
*   **Proximity Logic:** Uses a "Room Detector" to ensure the player can only hide when inside the designated area[cite: 2].
*   **Interactive Hiding:** Switches between the normal player and a "hiding camera" view (e.g., inside a locker)[cite: 2].
*   **AI Integration:** Automatically forces the AI to stop chasing if the player hides while at a safe distance[cite: 2].

### 3. Interaction & Inventory System
*   **Advanced Pickup/Drop:** Raycast-based system to pick up items, parent them to the player's hand, and disable physics while held[cite: 2].
*   **Locked Door Mechanics:** Key-to-door name matching using `static` variables for data persistence[cite: 2].
*   **Flashlight Logic:** Automatically toggles the light component on/off based on whether the object is held by the player[cite: 2].

### 4. Technical Optimizations
*   **Automatic Backup System:** Includes a `.bat` script and a Unity Editor script that prompts to backup the project every time you quit[cite: 2].
*   **Texture Applier:** An `ExecuteInEditMode` script to quickly adjust texture tiling (X/Y repeat) directly in the Inspector[cite: 2].
*   **Smooth Transitions:** Uses `Quaternion.Slerp` for natural door opening and character rotation[cite: 2].

## 📂 Core Scripts Overview

| Script | Description |
| :--- | :--- |
| **`EnemyAI.cs`** | Manages AI states: Patrol, Chase, Idle, and Jumpscare[cite: 2]. |
| **`hidingPlace.cs`** | Handles player concealment and enemy "lose" logic[cite: 2]. |
| **`RaycastPickupDrop.cs`** | Standard 3D interaction for collecting and dropping items[cite: 2]. |
| **`Door.cs`** | Controls smooth door rotation and audio effects[cite: 2]. |
| **`TextureApplier.cs`** | Utility to scale textures for large environmental objects[cite: 2]. |
| **`AutoBackupOnQuit.cs`** | (Editor Script) Automates project backups via Batch files[cite: 2]. |

## 🕹 Setup Instructions

1.  **AI Setup:** Bake a **NavMesh** in your scene. Attach `EnemyAI.cs` to your monster and assign the player and patrol points in the Inspector[cite: 2].
2.  **Hiding Points:** Place a trigger collider on a closet/under-bed area. Assign the `hidingPlace` and `roomDetector` scripts. Ensure your Player has the `Player` tag[cite: 2].
3.  **Interaction:** Assign `RaycastPickupDrop.cs` to your Main Camera. Set the `TargetPosition` (where the item sits in the hand)[cite: 2].
4.  **UI:** Import **TextMeshPro** for the on-screen prompts ("Press E to Hide", "Item Collected")[cite: 2].

## 🛡 Backup Safety
To prevent data loss (as suggested in the book), use the provided `.bat` logic to sync your `Assets`, `ProjectSettings`, and `Packages` folders to a secure directory or cloud storage[cite: 2].

---
*Reference: Based on the educational series "Unity'le Oyunlar Tasarlama" by Yiğit Çakman.*[cite: 2]
