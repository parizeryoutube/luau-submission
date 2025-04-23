# 🔥 Roblox Power System – Dash, Shield & Fireball (with Camera FX)

A fully modular, client-side power system for Roblox games that adds immersive combat mechanics through fluid motion, visual feedback, and user-friendly controls.

---

## ✨ Features

- **Dash Ability** — Instant forward movement with trail, blur, and sound effects.
- **Shield Ability** — Temporary immunity with force-field visual and animated cooldown GUI.
- **Fireball Ability** — Charge-based projectile with speed scaling, raycasting hit detection, particle effects, and server damage sync.
- **Camera Effects** — Includes shake on explosion and walking head sway for realism.
- **Advanced Input Handling** — Robust keybindings via `UserInputService`.
- **Clean Architecture** — Fully documented with performance-focused logic and modular design.

---

## 🧠 How It Works

### Client-Side LocalScript
All logic is handled locally for responsive user input and visual effects. Key interactions:

- **Dash** applies a velocity burst and visual feedback.
- **Shield** welds a visual force field to the player and sets a `Shielded` tag (for use by NPCs, enemy projectiles, etc.).
- **Fireball** uses `RaycastParams` each frame to detect precise hits, avoiding false positives.

### Server Communication
- Uses `RemoteEvent` (`RequestFireballHit`) to inform the server when a damageable target is hit by a fireball.

### GUI
- Displays a dynamic cooldown bar for the Shield ability.

---

## 🔧 Installation

1. **Copy the script** into a LocalScript inside `StarterPlayerScripts`.
2. **Add a RemoteEvent** to `ReplicatedStorage` named:  
3. **(Optional)**: Tag enemies with `CollectionService:AddTag(object, "Damageable")` for fireball targeting.

---

## ⌨️ Controls

| Key | Ability      | Description                              |
|-----|--------------|------------------------------------------|
| Q   | Dash         | Quick forward dash                       |
| R   | Shield       | Activates shield + cooldown UI           |
| E   | Fireball     | Hold to charge, release to fire          |

---

## 🛠️ Customization

- **Cooldowns**: Change in `cooldowns` table (top of script).
- **Dash Speed**: Modify `root.AssemblyLinearVelocity`.
- **Fireball Speed Curve**: Tweak `math.clamp()` inside `fireFireball()` function.
- **GUI Colors/Sizes**: Adjust `shieldBar` and `shieldFill`.

---

## ✅ Best Practices Used

- 🚀 Performance-aware: all temporary objects auto-cleaned with `Debris`.
- 🔒 Safe input handling: ignores input during UI/gameProcessed events.
- 🔁 Modular design: each ability encapsulated with separate logic and clean side effects.
- 📘 Comments: every part of the code is documented with **how**, **why**, and **what**.

---

## 🧪 To Do (Optional Enhancements)

- Add `ContextActionService` for mobile/controller support.
- Add sound toggle and audio profiles per ability.
- Add cooldown icons or number-based GUI feedback.
- Integrate server-side validation for anti-cheat measures.

---

## 💬 Credits

**Author:** [parizeryoutube]  
**Enhanced by:** ChatGPT (OpenAI) – Full documentation and optimization

---

## 📌 License

This project is open to use and modification for personal or commercial Roblox games. Credit is appreciated but not required.


