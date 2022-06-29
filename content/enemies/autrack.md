---
title: Autrack
---

{{< columns >}}

- [Autrack image]
- Health: 25
- Damage: 8
- Can be X: No
- Can be EMP'd: Yes

<--->

TODO: speed is dependant of the difficulty!

- [autrackproj image]
- HPush: 5
- VPush: -3
- Damage: 9
- HSpeed: 3.5
- VSpeed: 0

{{< /columns >}}

Autrack's logic is like this:  
If Samus is in the 90 units target range, start the winding up animation and wait a little. Then, fire a projectile, go to the winding down animation, wait a little again and start checking if Samus is in range again.

Here's a visual representation:

{{< mermaid class="text-center">}}
graph TB
    A[Creation] --> B{{Check if Samus is in target range}}
    B -->|Samus is not in target range| B
    B -->|Samus is in target range| C[Windup animation]
    C -->|After 20 frames happened| D[Attack animation]
    D -->|After 12 frames happened| E[Fire projectile]
    E -->|After 4 frames happened| F[Winddown animation]
    F -->|After 10 frames happened| B
{{< /mermaid >}}

Source: [`oAutrack`](https://github.com/AM2R-Community-Developers/AM2R-Community-Updates/blob/main/objects/oAutrack.object.gmx), [`oAutrackProj`](https://github.com/AM2R-Community-Developers/AM2R-Community-Updates/blob/main/objects/oAutrackProj.object.gmx)