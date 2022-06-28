---
title: Damage Values
---

## Beam Stats
Power Beam has the following base stats:
| Name     | Damage     | Cooldown (in frames)  | Speed (TODO: probably pixels per frame) |
| -------- | ---------- | --------------------- | ----- |
| Power	   | 5.0  	    | 5		 	            | 6.4	|

Every other beam then applies attributes on top, except for speed, in this order:  
TODO: double check charge cooldown: charge_beam_fire
TODO: apparently multipliers are applied multiple times? https://github.com/AM2R-Community-Developers/AM2R-Community-Updates/blob/df6576c1064881a711d96b825042eae5bab3fbb1/scripts/chStepFire.gml#L59

| Name     | Damage (Multiplier to base) | Cooldown (in adition to base)  | Speed |
| -------- | --------------------------- | ------------------------------ | ----- |
| Wave	   | 1.5                         | 2	 	                      | 9	  |
| Ice	   | 1.5                         | 2	 	                      | 6.4	  |
| Spazer   | 0.8                         | 2	 	                      | 6.4	  |
| Plasma   | 1.2                         | 3	 	                      | 6.4	  |
| Charge   | 3.0 / 1.8*                  | 16                             | 12    |

*Charge Beam will have a multiplier of 1.8, if Samus has Wave Beam but not Spazer equipped. Otherwise, it has a multiplier of 3.0 . 

TODO: does plasma deal damage per frame? AFAIK yes, but cant find it rn in shoot method

It is also worth noting that:
- Spazer creates 3 beam projectiles that can do damage
- Charged Wave without Spazer creates two beam projectiles that can do damage

Source: [`scripts/shoot_beam.gml`](https://github.com/AM2R-Community-Developers/AM2R-Community-Updates/blob/main/scripts/shoot_beam.gml)


## Missile Stats
Missiles are fairly straight forward:  
TODO: double check speed, as I'm certain SMs move faster 
| Name              | Damage     | Cooldown (in frames)  | Speed |
| ----------------- | ---------- | --------------------- | ----- |
| Normal            | 20 	     | 10		 	         | 6.4	 |
| Super	            | 100	     | 20		 	         | 6.4	 |
| Normal Explosion  | 5	  	     | 10		 	         | N/A	 |
| Super	Explosion   | 25         | 20		 	         | N/A	 |

Source: [`scripts/shoot_missile.gml`](https://github.com/AM2R-Community-Developers/AM2R-Community-Updates/blob/main/scripts/shoot_missile.gml), [`oMissile.UserEvent0`](https://github.com/AM2R-Community-Developers/AM2R-Community-Updates/blob/main/objects/oMissile.object.gmx)

## Bombs Stats
TODO: find source and double check
| Name     | Damage     | Cooldown (in frames)  | Speed |
| -------- | ---------- | --------------------- | ----- |
| Normal   | 6	  	    | 10	 	            | 6.4	|
| Power	   | 20	    	| 20	 	            | 6.4	|
