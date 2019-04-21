---
layout: rpgs
title: Giantism in Fifth Edition Animals
game: Dungeons & Dragons Fifth Edition
subject: Creature Stats
tagline: Go Big or Go Home!
---
*Original post:* 4/13/2019

*Edit* 4/21/2019 Crab, Crocodile, and related Giant versions addded

I started this little exercise last week: statistics for converting creatures into giant versions.
As someone who works in the world of data science, I know that it isn't always easy to get your
datums all organized and cleaned, so even though there isn't too many giant creatures in the
*Monster Manual*{:.underlineTitle}, it is taking some time to get all of the data points that I 
want into the table format that I need, I will be updating this page as I add more data points.

The first thing I want to know is, what makes the creature giant? If we look at *Appendix A: Miscellaneous
Creatures* from the fifth edition *Monster Manual*{:.underlineTitle}, we can get a sense for that.

Since certain elements of a creature's stat block is based on *challenge rating*, and the *Dungeon 
Master's Guide*{:.underlineTitle} suggests picking CR first before creating or modifying a monster,
I think it is safe to assume that not all giant creatures in the *Monster Manual*{:.underlineTitle} 
will have been designed to scale up the same way. That is, a giant ape is not going to be proportional 
to an ape the same way that a giant frog is going to be proportional to a frog. I do think we can get 
a sense for how to convert a creature from one size to a larger size with some general rules.

Also, since certain elements of a creature's stat block is based on its size, like *hit dice*, 
*attack dice* and speed, I think we will find those elements to scale consistently based on size.

So, let's compare some statistical elements for creatures and their giant counterparts.

#### Size

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Ape   | Giant Ape   | size: medium to huge  | 2 sizes |
| Badger   | Giant Badger   | size: tiny to medium  | 2 sizes |
| Bat   | Giant Bat   | size: tiny to large  | 3 sizes |
| Boar  | Giant Boar  | size: medium to large  | 1 size  |
| Constrictor Snake  | Giant Constrictor Snake  | size: large to huge  | 1 size  |
| Crab   | Giant Crab   | size: tiny to medium  | 2 sizes |
| Crocodile   | Giant Crocodile   | size: large to huge  | 1 size |

#### Armor Class

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Ape   | Giant Ape   | Armor Class: 12  | no change |
| Badger   | Giant Badger   | Armor Class: 10  | no change |
| Bat   | Giant Bat   | Armor Class: 12 to 13  | 1 |
| Boar  | Giant Boar  | Armor Class: 11 to 12  | 1 |
| Constrictor Snake  | Giant Constrictor Snake  | Armor Class: 12  | no change |
| Crab   | Giant Crab   | Armor Class: 11 to 15  | 3 points |
| Crocodile   | Giant Crocodile   | Armor Class: 12 to 14  | 2 points |

#### Hit Dice

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Ape   | Giant Ape   | hit die: d8 to d12  | 2 standard dice |
| Badger   | Giant Badger   | hit die: d4 to d8  | 2 standard dice |
| Bat   | Giant Bat   | hit die: d4 to d10  | 3 standard dice |
| Boar  | Giant Boar  | hit die: d8 to d10  | 1 standard dice |
| Constrictor Snake  | Giant Constrictor Snake  | hit die: d10 to d12   | 1 standard dice |
| Crab   | Giant Crab   | hit die: d4 to d8  | 2 standard dice |
| Crocodile   | Giant Crocodile   | hit die: d10 to d12  | 2 standard dice |

#### Speed

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Ape   | Giant Ape   | speed: 30 ft. to 40 ft.  | 10 ft. |
| Badger   | Giant Badger   | speed: 20 ft. to 30 ft.  | 10 ft. |
| Badger   | Giant Badger   | speed: burrow 5 ft. to 10 ft.  | 5 ft. |
| Bat   | Giant Bat   | speed: 5 ft. to 10 ft.  | 5 ft. |
| Bat   | Giant Bat   | speed: fly 30 ft. to 60 ft.  | 30 ft. |
| Boar  | Giant Boar  | speed: 40 ft. to 40 ft.  | no change |
| Constrictor Snake  | Giant Constrictor Snake  | speed: 30 ft. to 30 ft.  | no change |
| Constrictor Snake  | Giant Constrictor Snake  | speed: swim 30 ft. to 30 ft.  | no change |
| Crab   | Giant Crab   | speed: 20 ft. to 30 ft.  | 10 ft. |
| Crab   | Giant Crab   | speed: swim 20 ft. to 30 ft.  | 10 ft. |
| Crocodile   | Giant Crocodile   | speed: 20 ft. to 30 ft.  | 10 ft. |
| Crocodile   | Giant Crocodile   | speed: swim 20 ft. to 50 ft.  | 30 ft. |

#### Ability Scores

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Ape   | Giant Ape   | strength: 16 to 23  | 7 |
| Ape   | Giant Ape   | dexterity: 14  | no change |
| Ape   | Giant Ape   | constitution: 14 to 18  | 4 |
| Ape   | Giant Ape   | intelligence: 6 to 7  | 1 |
| Ape   | Giant Ape   | wisdom: 12 | no change |
| Ape   | Giant Ape   | charisma: 7 | no change |
| Ape   | Giant Ape   | Ability Score bonus total 4 to 11 | 7 |
| Badger   | Giant Badger   | strength: 4 to 13  | 9 |
| Badger   | Giant Badger   | dexterity: 11 to 10 | -1 |
| Badger   | Giant Badger   | constitution: 12 to 15  | 3 |
| Badger   | Giant Badger   | intelligence: 2  | no change |
| Badger   | Giant Badger   | wisdom: 12 | no change |
| Badger   | Giant Badger   | charisma: 5 | no change |
| Badger   | Giant Badger   | Ability Score bonus total -8 to -3 | 5 |
| Bat   | Giant Bat   | strength: 2 to 15  | 13 |
| Bat   | Giant Bat   | dexterity: 15 to 16 | 1 |
| Bat   | Giant Bat   | constitution: 8 to 11  | 3 |
| Bat   | Giant Bat   | intelligence: 2  | no change |
| Bat   | Giant Bat   | wisdom: 12 | no change |
| Bat   | Giant Bat   | charisma: 4 to 6 | 2 |
| Bat   | Giant Bat   | Ability Score bonus total -9 to 0 | 9 |
| Boar   | Giant Boar   | strength: 13 to 17  | 4 |
| Boar   | Giant Boar   | dexterity: 11 to 10 | -1 |
| Boar   | Giant Boar   | constitution: 12 to 16  | 4 |
| Boar   | Giant Boar   | intelligence: 2  | no change |
| Boar   | Giant Boar   | wisdom: 9 to 7 | 2 |
| Boar   | Giant Boar   | charisma: 5 | no change |
| Boar   | Giant Boar   | Ability Score bonus total -5 to -1 | -4	 |
| Constrictor Snake   | Giant Constrictor Snake   | strength: 15 to 19  | 4 |
| Constrictor Snake   | Giant Constrictor Snake   | dexterity: 14 | no change |
| Constrictor Snake   | Giant Constrictor Snake   | constitution: 12  | no change |
| Constrictor Snake   | Giant Constrictor Snake   | intelligence: 1  | no change |
| Constrictor Snake   | Giant Constrictor Snake   | wisdom: 10 | no change |
| Constrictor Snake   | Giant Constrictor Snake   | charisma: 3 | no change |
| Constrictor Snake   | Giant Constrictor Snake   | Ability Score bonus total -3 to -1 | -2	 |
| Crab   | Giant Crab   | strength: 2 to 13  | 11 |
| Crab   | Giant Crab   | dexterity: 11 to 15  | 4 |
| Crab   | Giant Crab   | constitution: 10 to 11  | 4 |
| Crab   | Giant Crab   | intelligence: 1  | no change |
| Crab   | Giant Crab   | wisdom: 8 to 9 | 1 |
| Crab   | Giant Crab   | charisma: 2 to 3 | 1 |
| Crab   | Giant Crab   | Ability Score bonus total 12 to 17 | 5 |
| Crocodile   | Giant Crocodile   | strength: 15 to 21  | 6 |
| Crocodile   | Giant Crocodile   | dexterity: 10 to 9  | -1 |
| Crocodile   | Giant Crocodile   | constitution: 13 to 17  | 4 |
| Crocodile   | Giant Crocodile   | intelligence: 2  | no change |
| Crocodile   | Giant Crocodile   | wisdom: 10 | no change |
| Crocodile   | Giant Crocodile   | charisma: 5 to 7 | 2 |
| Crocodile   | Giant Crocodile   | Ability Score bonus total 18 to 22 | 4 |

#### Skills

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Ape   | Giant Ape   | skills: Athletics +5 to +9 | 4 |
| Ape   | Giant Ape   | skills: Perception +3 to +4 | 1 |
| Crab   | Giant Crab   | skills: Stealth +2 to +4 | 2 |
| Crab   | Giant Crab   | skills: Perception +3 to +4 | 1 |
| Crocodile   | Giant Crocodile   | skills: Stealth +2 to +5 | 3 |

#### Senses

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Ape   | Giant Ape   | Senses: passive Perception 13 to 14 | 1 |
| Badger   | Giant Badger   | Senses: darkvision 30 ft. | no change |
| Badger   | Giant Badger   | Senses: passive Perception 11 | no change |
| Bat   | Giant Bat   | Senses: blindsight 60 ft. | no change |
| Bat   | Giant Bat   | Senses: passive Perception 11 | no change |
| Boar  | Giant Boar  | Senses: passive Perception 9 to 8  | -1  |
| Constrictor Snake  | Giant Constrictor Snake  | Senses: blindsight 10 ft.  | no change  |
| Constrictor Snake  | Giant Constrictor Snake  | Senses: passive Perception 10 to 12  | 2  |
| Crab   | Giant Crab   | Senses: passive Perception 9 | none |
| Crab   | Giant Crab   | blindsight 30 ft. | none |
| Crocodile   | Giant Crocodile   | Senses: passive Perception 10 | none |

#### Challenge Rating

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Ape   | Giant Ape   | Challenge: 1/4 to 7 | 8 levels of CR |
| Badger   | Giant Badger   | Challenge: 0 to 1/4 | 2 levels of CR |
| Bat   | Giant Bat   | Challenge: 0 to 1/4 | 2 levels of CR |
| Boar  | Giant Boar  | Challenge: 1/4 to 2 | 3 levels of CR  |
| Constrictor Snake  | Giant Constrictor Snake  | Challenge: 1/4 to 2 | 3 levels of CR  |
| Crab   | Giant Crab   | Challenge: 0 to 1/8 | 1 level of CR |
| Crocodile   | Giant Crocodile   | Challenge: 1/2 to 5 | 5 levels of CR |


#### Attributes

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Badger   | Giant Badger   | Attribute: *Keen Smell* | no change |
| Bat   | Giant Bat   | Attribute: *Echolocation* | no change |
| Bat   | Giant Bat   | Attribute: *Keen Hearing* | no change |
| Boar  | Giant Boar  | Attribute: *Charge* and *Relentless*  | no change  |
| Crab   | Giant Crab   | Attribute: *Amphibious* | no change |
| Crocodile   | Giant Crocodile   | Attribute: *Hold Breath* | no change |

#### Actions

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Ape   | Giant Ape   | Actions: *Multiattack*: 2 | no change |
| Badger   | Giant Badger   | Actions: *Multiattack*: Giant Badger only | 1 |
| Bat  | Giant Bat   | Actions: one attack | no change |
| Boar  | Giant Boar  | Actions: one attack  | no change  |
| Constrictor Snake  | Giant Constrictor Snake  | Actions: one attack  | no change  |
| Crab   | Giant Crab   | Actions: 1 | no change |
| Crocodile   | Giant Crocodile   | Actions: 1 to Multiattack | 1 attack |

#### Attack Bonus

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Ape   | Giant Ape   | attack bonus: +5 to +9 | 4 |
| Badger   | Giant Badger   | attack bonus: +2 to +3 | 1 |
| Bat   | Giant Bat   | attack bonus: +0 to +4 | 4 |
| Boar  | Giant Boar  | attack bonus: +3 to +5  | 1  |
| Constrictor Snake  | Giant Constrictor Snake  | attack bonus: +4 to +6  | 2  |
| Crab   | Giant Crab   | attack bonus: +0 to +3 | 3 |
| Crocodile   | Giant Crocodile   | attack bonus: +4 to +8 | 4 |

#### Attacks

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Ape   | Giant Ape   | attack die, natural weapon *fist*: d6 to d10 | 2 standard dice |
| Ape   | Giant Ape   | number of attack dice, natural weapon *fist*: 1 to 3 | 2 dice |
| Ape   | Giant Ape   | damage output, natural weapon *fist*: 6 to 22 | 16 |
| Ape   | Giant Ape   | attack die, weapon *rock*: d6 | no change |
| Ape   | Giant Ape   | number of attack dice, weapon *rock*: 1 to 7 | 6 |
| Ape   | Giant Ape   | damage output, natural weapon *rock*: 6 to 30 | 24 |
| Badger   | Giant Badger   | attack die, natural weapon *bite*: (no die) to d6 | 2 standard dice |
| Badger   | Giant Badger   | number of attack dice, natural weapon *bite*: (no dice) to 1 | 1 die |
| Badger   | Giant Badger   | damage output, natural weapon *bite*: 1 to 4 | 3 |
| Badger   | Giant Badger   | attack die, natural weapon *claw*: (Giant Badger only) d4 | 1 standard dice |
| Badger   | Giant Badger   | number of attack dice, natural weapon *claw*: (Giant Badger only) 2 | 2 die |
| Badger   | Giant Badger   | damage output, natural weapon *claw*: (Giant Badger only) | 6 |
| Bat   | Giant Bat   | attack die, natural weapon *bite*: (no die) to d6 | 2 standard dice |
| Bat   | Giant Bat   | number of attack dice, natural weapon *bite*: (no dice) to 1 | 1 die |
| Bat   | Giant Bat   | damage output, natural weapon *bite*: 1 to 5 | 4 |
| Boar   | Giant Boar   | attack die, natural weapon *tusk*: d6 | no change |
| Boar   | Giant Boar   | number of attack dice, natural weapon *tusk*: 1 to 2 | 2 dice |
| Boar   | Giant Boar   | damage output, natural weapon *tusk*: 4 to 10 | 6 |
| Constrictor Snake   | Giant Constrictor Snake   | attack die, natural weapon *bite*: d6 | no change |
| Constrictor Snake   | Giant Constrictor Snake   | number of attack dice, natural weapon *bite*: 1 to 2 | 2 dice |
| Constrictor Snake   | Giant Constrictor Snake   | damage output, natural weapon *bite*: 5 to 11 | 6 |
| Constrictor Snake   | Giant Constrictor Snake   | attack die, natural weapon *constrict*: d6 | no change |
| Constrictor Snake   | Giant Constrictor Snake   | number of attack dice, natural weapon *constrict*: 1 to 2 | 2 dice |
| Constrictor Snake   | Giant Constrictor Snake   | damage output, natural weapon *constrict*: 6 to 13 | 7 |
| Crab   | Giant Crab   | attack die, natural weapon *claw*: none to d6 | 2 standard dice |
| Crab   | Giant Crab   | number of attack dice, natural weapon *claw*: none to 1 | 1 die |
| Crab   | Giant Crab   | damage output, natural weapon *claw*: 1 to 4 | 3 |
| Crocodile   | Giant Crocodile   | attack die, natural weapon *bite*: d10 | no change |
| Crocodile   | Giant Crocodile   | number of attack dice, natural weapon *bite*: 1 to 2 | 2 die |
| Crocodile   | Giant Crocodile   | damage output, natural weapon *bite*: 7 to 21 | 14 |
| Crocodile   | Giant Crocodile   | attack die, natural weapon *tail*: none to d8 | 3 standard dice |
| Crocodile   | Giant Crocodile   | number of attack dice, natural weapon *tail*: none to 2 | 2 die |
| Crocodile   | Giant Crocodile   | damage output, natural weapon *tail*: 0 to 13 | 13 |

#### Damage Per Round

| Creature | Giant Creature | Stat Element | Difference |
|:--------:|:-------:|:--------|:--------|
| Ape   | Giant Ape   | damage output, per round max: 12 to 60 | 48 |
| Badger   | Giant Badger   | damage output, per round max: 1 to 10 | 9 |
| Bat   | Giant Bat   | damage output, per round max: 1 to 5 | 4 |
| Boar  | Giant Boar  | damage output, per round max:  7 to 17 | 10 |
| Constrictor Snake  | Giant Constrictor Snake  | damage output, per round max:  6 to 13 | 7 |
| Crab   | Giant Crab   | damage output, per round max: 1 to 4 | 3 |
| Crocodile   | Giant Crocodile   | damage output, per round max: 7 to 34 | 27 |
