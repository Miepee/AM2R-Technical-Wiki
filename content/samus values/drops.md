---
title: Drop Values
---

Except for bosses and their projectiles, every enemy has the same drop spawning system, which is as follows:
TODO: Rewrite this to be cleaner
```
├─ Pickup Index is set to a number between flr(rnd(4))
│  ├─ If ("Pickup Index" is 0) then spawn "Small HP" if ("Player HP" is less than "Maximum HP" and "Small HP" count is less than "6")
│      ├─ Otherwise set "Pickup Index" to 2 (Missile Drop) 
│  ├─ If ("Pickup Index" is 1) then spawn "Big HP" if ("Player HP" is less than "Maximum HP" and "Big HP" count is less than "3")
│      ├─ Otherwise set "Pickup Index" to 2 (Missile Drop) 
│  ├─ If ("Pickup Index" is 2) then spawn "Missile Drop" if ("Player Missiles" is less than "Maximum Missiles", "Maximum Missiles" is greater than 0, and "Missile Drop" count is less than "8")
│  ├─ If ("Pickup Index" is 3) then spawn "Missile Drop" if ("Player Super Missiles" is less than "Maximum Super Missiles", "Maximum Super Missiles" is greater than 0, and "Super Missile Drop" count is less than "2")
```