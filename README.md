
#  Roblox Power System (Luau Scripter Submission)

### Author: @parizeryoutube
### Type: Single LocalScript with RemoteEvent + VFX
### Purpose: Submission for Luau Scripter role on Discord

---

##  Features

- **Dash (Q)**: Burst forward with blur and trail FX
- **Shield (R)**: Protective sphere with cooldown bar and visual aura
- **Fireball (E)**: Chargeable projectile with camera shake, VFX, and server-authoritative damage

---

##  Setup Instructions

1. Place this script inside:
   ```
   StarterPlayer > StarterPlayerScripts
   ```

2. In `ReplicatedStorage`, add:
   ```
   RemoteEvent named "RequestFireballHit"
   ```

3. In `ServerScriptService`, add a script to handle damage:
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local event = ReplicatedStorage:WaitForChild("RequestFireballHit")

event.OnServerEvent:Connect(function(player, hitPart)
	local target = hitPart:FindFirstAncestorWhichIsA("Model")
	if target and target:FindFirstChild("Humanoid") and not target:FindFirstChild("Shielded") then
		target.Humanoid:TakeDamage(25)
	end
end)
```

---

##  How to Use

| Key | Power     | Description |
|-----|-----------|-------------|
| Q   | Dash      | Short burst forward with blur and trail |
| R   | Shield    | Temporary protective bubble with cooldown bar |
| E   | Fireball  | Hold to charge, release to launch projectile |

---

##  API & Techniques Used

- `AssemblyLinearVelocity` (modern velocity control)
- `ContextActionService` for clean input handling
- `Debris` for memory-safe FX
- `TweenService` for GUI and shield bar
- `Trail`, `ParticleEmitter`, `PointLight`, `WeldConstraint`
- `RunService:BindToRenderStep` for camera shake
- `RemoteEvent` for server-authoritative fireball damage

---

##  Review Notes

- Over **200+ lines of executable Luau code**
- Modern API usage only (no deprecated components)
- Extensive VFX to showcase polish and functionality
- Safe for multiplayer; server handles damage logic

---

##  License

This project is made for submission purposes. Use or remix freely with credit.

