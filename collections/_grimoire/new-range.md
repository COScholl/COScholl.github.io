---
layout: grimoire
title: New Range
technologies: Javascript
subject: Converting one range of values to fit another range
tagline: What were those stats again?
---

*edit After laying down, I realized my math was wrong. I tried to divide* **v<sub>original n-1</sub> - v<sub>original 0</sub>**
*from both* **v<sub>new n-1</sub> - v<sub>new 0</sub>** *and* **v<sub>i</sub> - v<sub>0</sub>** *. We only need to divide* **v<sub>new n-1</sub> - v<sub>new 0</sub>** *one time.*

#### Use Case: 
Taking stats from one game and fitting them into the boundaries of another game's stats. As an example, I want to convert the first
edition *Advanced Dungeons & Dragons* ability scores into the new fifth edition *Dungeons & Dragons* ability scores. It is not explicitly stated that there is a minimum ability score threshold in AD&D. It is possible to lose ability score points in AD&D, though. Therefore, it is conceivable that a character could drop to 1 point in an ability score. Therefore the lower bound of ability scores in AD&D is 1.

In the book *Deities and Demigods*{:.underlineTitle}, it gives stats for the most powerful creatures in the game, and the maximum ability score described is 25. However, since "21+" for intelligence is describes as "Godlike" in the book, it could be reasonably surmised that 20 would be a cap for *player characters* and *creatures*. However, the hero Hiawatha has a strength ability score of 21. Being the outlier, since it seems that the heroes (that is non-divine creatures) in *Deities and Demigods*{:.underlineTitle} cap at 20, I would use 21 as the upper bound for non-divine AD&D characters, making their conversion to fifth edition slightly less powerful. The alternative is just to convert them as 1:1, but cap at 20, making 21 into 20.

In the fifth edition of Dungeons & Dragons, the *Player Handbook*{:.underlineTitle} is explicit that the minimum bound for an ability score is 1, and that the maximum is 30, though for a *PC*, the cap is 20. This means that player characters cannot become the most powerful creatures in the fifth edition universe. For the purpose of converting characters from first edition to fifth edition, this means that there will be two different ranges, one for player characters and races used for PC creation, and another for creatures that may have stats that go beyond the 20 point cap.

I frequently have to look up the formula for converting a stat from one range to another. I am going to offer a function that logs the converted range from the old values to the new values, which can then be used or altered to fit your own circumstances.

The function can be adapted for other purposes as well.

#### First Principles: 
* With a range of values in one system may have an upper bound and a lower bound that do not
  correspond with the upper bound and lower bound of another system.
* Consider a value *v* has a place in its system relative to the lower bound compared to the difference between the upper bound and the lower bound.
* All values in the range have an index between zero (*0*) and the index of the upper bound *n-1* such that the set of all values
  *v* with their index *i* fit into that range.
	*{v<sub>i</sub>}<sub>i=0</sub><sup>n-1</sup>*
* A value *v<sub>i</sub>* in its system shares the same minimum value *v<sub>0</sub>* as all other values in its system.
* For that reason, the difference between a value *v<sub>i</sub>* and the minimum value *v<sub>0</sub>* is used to create
  a ratio against the maximum value and the minimum value.
* The ratio *v<sub>i</sub> - v<sub>0</sub> / v<sub>n-1</sub> - v<sub>0</sub>* is the *min-max normalization* resulting in 
  the normalized value *v′*.
* The normalized value *v′* is within the range of 0 to 1, that is between  *v<sub>0</sub> - v<sub>0</sub> / v<sub>n-1</sub> - v<sub>0</sub>* and *v<sub>n-1</sub> - v<sub>0</sub> / v<sub>n-1</sub> - v<sub>0</sub>*.
* Therefore, the normalized value is a percentage of the difference between the value and the minimum and the range maxium and minimum.
* If one were to try to put a value from one range into a new system with a different upper bound
  and a different lower bound, the performance of that value in its new system will not be the same
  as it was in its original system.
* In order the guarantee that a value called *v<sub>original i</sub>* will perform the same role in a new system as it did in its
  original system, that value needs to be converted to a value *v<sub>new i</sub>* that carries the same weight in its
  new system as the original value carried in its old system.
* To convert the value, we need to take that percentage *v′* from the old system, and apply it to the range of the new system.

  *v′ ⋅ (v<sub>new n-1</sub> - v<sub>new 0</sub>)*
* The result is *v<sub>new i</sub> - v<sub>new 0</sub>*, which we'll call *Δv*. 
* At this point we have a value that equals the difference between the new system value and the new system minimum. In order to find 
  the new system value *v<sub>new i</sub>*, we need to add the minimum to the difference. So, the last step is 

  *Δv + v<sub>new 0</sub> = v<sub>new i</sub>*

#### Dungeons & Dragons Stats Then and Now
For the full range of stats:

```
/* 
  Note that for creature stat conversion, the following uses the full range of stats, and 
  rounds the decimals to the nearest integer	
 */
const oldMin = 1;
const oldMax = 25;
const newMin = 1;
const newMax = 30;

function NewValues(oldMin, oldMax, newMin, newMax) {
	for(let i = oldMin; i <= oldMax; i++) {
		console.log(
			`old value: ${i}, 
			 new value: ${
			 	Math.round(
			 		(((i - oldMin) * (newMax - newMin))/(oldMax - oldMin)) + newMin
			 	)
			 }`);
		}
}

NewValues(oldMin, oldMax, newMin, newMax)
```
For converting PCs and creature races if using AD&D upper bound of 21:
```
/ Alternately, just use a 1:1 conversion and make 21 a 20.
  
const oldMin = 1;
const oldMax = 21;
const newMin = 1;
const newMax = 20;

function NewValues(oldMin, oldMax, newMin, newMax) {
	for(let i = oldMin; i <= oldMax; i++) {
		console.log(
			`old value: ${i}, 
			 new value: ${
			 	Math.floor(
			 		(((i - oldMin) * (newMax - newMin))/(oldMax - oldMin)) + newMin
			 	)
			 }`);
		}
}

NewValues(oldMin, oldMax, newMin, newMax)
```
#### Why Did I Have To Learn This?
I have been interested in converting RPG creatures from one game to another since I started out playing *Dungeon Crawl Classics*.
I started to collect D&D books, as well as other RPG books and RPG websites, and I became more interested in different games and their flavor, storytelling, or mechanics. In building a campaign world for fifth edition, I am continuing to explore porting concepts and characters in to fifth edition, or from fifth edition to other games. I would like to write more code that takes various mechanics and weights the mechanics evenly.