---
title: Wallfire
---

There are two types of Wallfires, the ones in Area 1 and the ones in Area 2. Besides health and spawning different projectiles, their behaviour is exactly the same.  
The internal names are `oWallfire` and `oWallfire2`, and for projectiles `oWallfireProj` and `oWallfireProj2` 

- [Wallfire1 image]
- Health: 11
- Damage: 4
- Can be X: No
- Can be EMP'd: Yes
---
- [Wallfire2 image]
- Health: 15
- Damage: 4
- Can be X: No
- Can be EMP'd: Yes
---

Wallfire has two timers: 

- initialTimer:
    |Easy|Normal|Hard
    |----|----|-----
    |120|80|70
- repeatedTimer:
    |Easy|Normal|Hard
    |----|----|-----
    |30+(timer*1.5)|20+timer|10+(timer*0.5) 

    The `timer` variable is unique to each Wallfire and is set in their instance creation code.

At creation, the Wallfire runs `initialTimer` to determine when to fire the first projectile. After the first projectile has been fired, it will use `repeatedTimer` to determine when to fire a projectile again.

Here's a visual representation of it:  

{{< mermaid class="text-center">}}
graph TB
    A[Creation] -->|Set InitializeTimer| B{Check InitializeTimer}
    B -->|Timer > 0| C[Decrease Timer]
    C --> B
    B -->|Timer == 0| D[Fire Projectile]
    D -->|Set RepeatedTimer| E{Check RepeatedTimer}
    E -->|Timer > 0| F[Decrease Timer]
    F --> E
    E -->|Timer == 0| D
{{< /mermaid >}}

TODO: note down `timer` for each wallfire.


---
Wallfire Projectiles

- [wallfireproj image]
- HPush: 5
- VPush: -3
- Damage: 3
- HSpeed: 3
- VSpeed: 0

- [wallfireproj2 image]
- HPush: 5
- VPush: -3
- Damage: 8
- HSpeed: 3.5
- VSpeed: 0