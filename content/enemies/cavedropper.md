---
title: Cavedropper
---

{{< columns >}}

- [Cavedropper nest image]
- Health: 10
TODO: invulnerable to a lot of things

<--->

TODO: speed is dependant of the difficulty!

- [Cavedropper image]
- Health: 5
- Damage: 6
- Can be X: TODO
- Can be EMP'd: No

{{< /columns >}}

The nests logic is relatively simple:  
After creation, it waits a frame, and then starts checking if Samus is in the 120 units target frame and spawn a cavedropper if thats the case. The next check will then be done after 120 frames.

Visual representation:
{{< mermaid class="text-center">}}
graph TB
    A[Creation] -->|Wait a frame| B{{Check if Samus is in target range}}
    B -->|Samus is not in target range| C[Wait 120 frames]
    B -->|Samus is in target range| D[Spawn Cavedropper]
    C --> B
    D --> C
{{< /mermaid >}}

TODO: cavedropper has a state 0 that seems unreachable. is that truly the case? check for instance creation code!

TODO: write cavedropper logic