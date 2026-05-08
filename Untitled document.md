**SOPHON System Modeling**

Settings defaultSys \= {  
  .brightness      \= 128,  
  .dst             \= 1,  
  .magic           \= EEPROM\_MAGIC,  
  .tube\_salt\_mm    \= 1785.0,  
  .tube\_nutr\_mm    \= 1495.0,  
  .tube\_harvest\_mm \= 1785.0,  
  .tube\_clean\_mm   \= 1485.0   
//all these lengths are common trunk \+ branch \- common trunk is 1085mm  
};

**(V means convert that length of tubing to a volume)**

| Step: | Vreactor | Valgae | Vsalt | Vdistilled | Vnutrient | trunk | NutrBranch | HarvBranch | SaltBranch | DistBranch |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| Init | 2000mL ALGE | 0mL | 1500 SALT | 500mL DIST | 200mL NUTR | v(1085) DIST | v(410) NUTR | v(700) ALGE-OLD | v(700) SALT | v(400) DIST |
| Purge | 2000-v(1785) mL ALGE | v(700) mL ALGE-OLD+ v(1085) mL distilled | 1500 SALT | 500mL DIST | 200mL NUTR | v(1085) ALGE | v(410) NUTR | v(700) ALGE-NEW | v(700) SALT | v(400) DIST |
| Harvest (200mL) | 2000-v(1785)-200mL  ALGE | v(700) mL ALGE-OLD+ v(1085) mL distilled \+ 200mL ALGE | 1500 SALT | 500mL DIST | 200mL NUTR | v(1085) ALGE-newer | v(410) NUTR | v(700) ALGE-NEWer | v(700) SALT | v(400) DIST |
| Salt (**180**mL) | 2000-v(1785)-200mL+v(1085)mL algae \+ \[**180**\-v(1085) mL salt) ALGE+SALT | v(700) mL ALGE-OLD+ v(1085) mL distilled \+ 200mL ALGE | 1320 SALT | 500mL DIST | 200mL NUTR | v(1085) SALT | v(410) NUTR | v(700) ALGE-NEWer | v(700) SALT | v(400) DIST |
| Nutrients (20mL) | 2000-v(1785)-200mL+v(1085)mL algae \+ \[**180**\-v(1085) mL salt)+20mL salt ALGE+SALT | v(700) mL ALGE-OLD+ v(1085) mL distilled \+ 200mL ALGE | 1320 SALT | 500mL DIST | 180mL NUTR | \[v(1085)-20mL\] salt, 20mL Nutr | v(410) NUTR-new | v(700) ALGE-NEWer | v(700) SALT | v(400) DIST |
| Distilled (55mL, END\!) | 2000-v(1785)-200mL+v(1085)mL algae \+ \[**180**\-v(1085) mL salt)+20mL salt+\[v(1085)-20mL\] salt \+ 20mL Nutr+\[55-v(1085)\] mL DIST ALGE+SALT+DIST | v(700) mL ALGE-OLD+ v(1085) mL distilled \+ 200mL ALGE | 1320 SALT | 445mL DIST | 180mL NUTR | v(1085) DIST | v(410) NUTR-new | v(700) ALGE-NEWer | v(700) SALT | v(400) DIST |

**1800-22 ALGAE**

**180 SALT**

**20 NUTR**

**21 mL DIST**

**SALT should use 17 g/L culture salts per dilutions formula**

**NUTRIENT should be 1.5 to 1.75 mL ARS to 138 or enough to get 140mL total BUT mind the gap that the diptube can’t reach..**