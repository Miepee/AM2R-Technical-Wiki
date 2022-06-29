---
title: Wallfire
---

There are two types of Wallfires, the ones in Area 1 and the ones in Area 2. Besides health and spawning different projectiles, their behaviour is exactly the same.  
The internal names are `oWallfire` and `oWallfire2`, and for projectiles `oWallfireProj` and `oWallfireProj2`. 

{{< columns >}}

- [Wallfire1 image]
- Health: 11
- Damage: 4
- Can be X: No
- Can be EMP'd: Yes

<--->

TODO: speed is dependant of the difficulty!

- [wallfireproj image]
- HPush: 5
- VPush: -3
- Damage: 3
- HSpeed: 3
- VSpeed: 0

{{</ columns >}}

{{< columns >}}

- [Wallfire2 image]
- Health: 15
- Damage: 4
- Can be X: No
- Can be EMP'd: Yes

<--->

- [wallfireproj2 image]
- HPush: 5
- VPush: -3
- Damage: 8
- HSpeed: 3.5
- VSpeed: 0

{{< /columns >}}

Wallfire has two timers (units in frames): 

- initialTimer:
    |Easy|Normal|Hard
    |----|----|-----
    |120|80|70
- repeatedTimer:
    |Easy|Normal|Hard
    |----|----|-----
    |30+(`timer`*1.5)|20+`timer`|10+(`timer`*0.5) 

    The `timer` variable is unique to each Wallfire and is set in their instance creation code.

At creation, the Wallfire runs `initialTimer` to determine when to fire the first projectile. After the first projectile has been fired, it will use `repeatedTimer` to determine when to fire a projectile again.

Here's a visual representation of it:  

{{< mermaid class="text-center" >}}
graph TB
    A[Creation] -->|Set initialTimer| B{{Check initialTimer}}
    B -->|initialTimer > 0| C[Decrease initialTimer]
    C --> B
    B -->|initialTimer == 0| D[Fire Projectile]
    D -->|Set repeatedTimer| E{{Check repeatedTimer}}
    E -->|repeatedTimer > 0| F[Decrease repeatedTimer]
    F --> E
    E -->|repeatedTimer == 0| D
{{< /mermaid >}}

TODO: note down `timer` for each wallfire.

Source: [`oWallfire`](https://github.com/AM2R-Community-Developers/AM2R-Community-Updates/blob/main/objects/oWallfire.object.gmx), [`oWallFire2`](https://github.com/AM2R-Community-Developers/AM2R-Community-Updates/blob/main/objects/oWallfire2.object.gmx), [`oWallfireProj`](https://github.com/AM2R-Community-Developers/AM2R-Community-Updates/blob/main/objects/oWallfireProj.object.gmx), [`oWallfireProj2`](https://github.com/AM2R-Community-Developers/AM2R-Community-Updates/blob/main/objects/oWallfireProj2.object.gmx)