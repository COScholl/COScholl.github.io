---
layout: rpgs
title: Ability Scores of Lesser Deities
game: Dungeons & Dragons Fifth Edition
subject: Creature Stats
tagline: Rosetta Stone from First Edition
---
*This is a fresh start for this section of my site*

### New Initiative for RPG Posts
For a few months, I have been slowly converting raw text from the first edition Advanced Dungeons & Dragons book <u>Deities & Demigods</u> into JavaScript objects. This is the start of my fifth edition deities project. My ultimate goal for this project is to gather statistics from all of the deity stat blocks from first edition, and to create a deity generator that takes into account how James M. Ward and Robert J. Kuntz devised the concepts of deities to be in that edition. I will be compiling data by divine level of deity (demigod, lesser god, greater god), and then filtering that data to fit with the limits of bounded accuracy, and to create a spiritual successor for <u>Deities & Demigods</u> for fifth edition, not as a book of deities, but as a framework for generating deities based on that work.

I know the very idea of gods in play and with statistics to boot has been somewhat controversial throughout the history of D&D, but I think it is a fun exercise. I became a software developer without formal education, and as part of rounding out my computer science knowledge, I think this project will help me get a more complete understanding of data analysis and statistics. All of my source material will be private, since I am working with proprietary materials that I have purchased that are not licensed under fifth edition's SRD, but I will be creating a public repository for the project once I start producing my statistics.

### Process
I have a template JavaScript object for deity stat blocks, and I will be adding certain data points as a sprint of work, and then I will generate statistics for these first edition deities at the end of each of these sprints. Each sprint will have the following data collections as focus:

- name, domains, divine rank, ability scores
- armor class
- HD, hp, size, movement
- class levels
- special abilities
- special attacks
- special defenses
- magic items/weapons

Whatever stats are generated will be by divine rank and abstracted into generic templates and statistic analysis. I will then filter those results through my _Fifth Edition Rosetta Stone_, that is, ten published fifth edition creatures that are considered to be _lesser deities_ in first edition. These ten creatures will serve as my baseline for what a lesser deity _might_ look like. It could be argued that these ten creatures are not really considered lesser deities in fifth edition, but I think its the best place to start.

There will be some other ways that I can reinforce my process, and I have been playing with what religion means to me for D&D, and what is outlined in the DMG, pp 9 - 13. I hope that I can expand on this systematically, and that I can come up with something that is altogether unique, useful, and fun.

### Fifth Edition Rosetta Stone
This is the lens through which first edition deities will be filtered. The data set is not large, but it is concrete. Based on CR alone, the _Monster Statistics by Challenge Rating_ table from the DMG, p. 274 can be used to generate another collection of statistics.

#### 5e Lesser Deity Statistics Rough Draft Based on Ten 1e Lesser Deities

|Category|Average|Standard Deviation|Maximum|Minimum |
|--------|-------|------------------|-------|--------|
|Armor Class|19.818181818181817|2.3284088136119445|25|17|
|Hit Points|386.7|101.22850389094961|615|283|
|Ability Scores|20.933333333333334|5.1732216482789735|30|10|
|Proficiency Bonus|7.1|0.9433981132056604|9|6|
|Number of Skills|1.3|1.1874342087037917|3|0|
Skill  Scores (When Present)|14.23076923076923|4.387987906754357|26|9|
Number of Damage Resistances|1.7|1.1874342087037917|3|0|
|Number of Damage Vulnerabilities|0.3|0.9|3|0|
|Number of Damage Immunities|2.7|1.2688577540449522|6|1|
|Number of Condition Immunities|6.2|2.6|13|4|
|Challenge Rating|22.6|3.7735924528226414|30|18|
|Number of Special Traits|5.8|0.8717797887081347|7|5|
|Number of Actions**|3.7|0.6403124237432849|5|3|
|Attack Bonus|15.2|2.5612496949731396|19|11|
|Number of Attacks|2.3|0.45825756949558405|3|2|
|Save DC|20.8|2.4819347291981715|26|17|
|Attack Damage Per Round|117.67999999999999|38.46649971078731|213|71.5|
|Number of Legendary Actions|3.1|0.7|5|2|
|Number of Legendary Action Options|3.2|0.9797958971132713|6|2|
|Number of Lair Action Options|2.6|0.9165151389911681|3|0|
|Number of Regional Effect Options|3.1|1.1357816691600549|4|0|

### Conclusion
The above statistics are a starting point for translating deities from first edition to fifth edition. As is noted often in many how-to guides for converting creatures between editions, this is really more of an art than a science. Much about the statistics above can not be set in stone as standards, but it gives an idea and a jumping off point.
