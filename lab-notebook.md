SOPHON Lab Notebook  
Important Links (todo allow access to everyone):

* [BOM](https://docs.google.com/spreadsheets/d/1Uu98sBQe1UVgy6LERJm_6FnM7hGbraojTXEiyiSHtSE/edit?usp=sharing)  
* [Assembly Guide (TODO)](https://docs.google.com/document/d/1KouWizE4vkPKuKhpX5GwkZoQQV8CltvG2VBpZg7XAYk/edit?usp=sharing)

---

03/22/26 \- Rakin

* ***BIG DAY\!***  
* Lab notebook: inaugural entry  
* Github Repo published, gathered all purchase orders for a clear and clean BOM  
* TODO:
 * assembly instructions
 * Publish STL+STEP+Onshape+3MF for 3D-Printed Parts
 * look into non-slip bumpers (tpu or similar) to avoid base slippage
 * Create schematic in KiCad
 * Consider culture recycling for V2 (saves water)
 * V2: slow down metabolism to slow down odor and decay of biomass?
 * V2: use Novus to clean acrylic vase?
 * **NOW: Add jumpers/dovetails so multiple SophonBoards can be chained together like real breadboards?**
 * Later: should V2 (2027) be about allowing people to make *more* smaller SOPHONs or focus efforts into a bigger (10-50L) version of SOPHON or both?
* ESP32 and DRV8871 were fried, ordered replacements  
* Went from Arduino Uno R3+ESP32 \-\> Uno R4 to simplify things. It was a clever hack for Rakin the designer, but it made life harder for Rakin+Jason+Arjun the builders. Given that the cost difference when buying a new ESP32 vs an 4 was only 5 dollars, the simplification was welcomed.  
* Start thinking about PCBs, still have to order the weights (see BOM) so tubing lines don’t float because of their desire to coil up  
* **Buy media \+ culture ASAP**  
* Quick FAQ guide for our favorite hypothetical ISEF judge: why we did what we did  
  * **Why use *Arthrospira platensis* specifically?**  
    * Grows like a weed, high pH environment reduces competition with bacteria, common and well documented  
  * **Why use dip tubes, where the stuff comes in from the top instead of drilling holes from the bottom?**  
    * We wanted to avoid drilling since it would have made it harder to reproduce for limited-access people, plus it introduces a further area of complexity where there isn’t any reason to have it  
  * **Isn’t the algae going to starve of carbon?**  
    * Yes, but that’s the *point*. The entire reason that SOPHON exists is to only use carbon from ambient air to be net carbon-*negative*. Though this isn’t true yet since it’s still powered on-grid and uses dissolved inorganic carbon, those are *cost* issues, not *design* flaws. Better a real proof-of-concept that’s slightly carbon-positive than an ideal carbon-negative bioreactor that doesn’t exist. Also: we bought RECs.    
* Added further rationale to the BOM for each component\!
* Create schematic in KiCad

---

03/28/26 \- Rakin
* Finally got turbidity sensor working
* I hate, hate, **HATE** loose wires with a **BURNING PASSION**
 * They made my turbidity sensor sometimes work fine, sometimes flop for no reason (what?)
 * I spent hours debugging it...
* Well, life experience learned
* Anyway, odd thing to check up on later: adjusting the pulldown resistor value (per the TST-10 schematic) from 4.7 kiloOhms decreases the max voltage.
* Feeling under the weather, so postponing work
* Also: chai works wonders for a sore throat. Use honey and ginger for best effect. Not SOPHON, but might save someone later

  ---

03/29/26 \- Rakin, Arjun, Jason
* Soldered MOSFET
* Almost done: just have to do firmware, hook up MOSFET
* I think of the circuitry as 3 "boxes"
    * Box 1: Wago Mess
        * Biggest fish, main 12V line, 5V line, pumps (peristaltic and air), LED light, basically anything that has a significant power draw
        * Connected to the other boxes through power lines (5V and GND) and motor driver
    * Box 2: UNO and Co.
        * Gets power (5V and GND from Box 1)
        * Microcontrollers, sensors, LCDs, controls, etc
        * Controls Box 3
    * Box 3: MOSFET
        * Controls light (on perfboard)
        * controlled by UNO and Co., gets power from Wago Mess
 ---

04/01/26 \- Rakin, Arjun, Jason
* First total test of all of SOPHON's parts _together_
 * Works well, but still have to figure out cable management + prevent wires from loosening + reduce EMI
 * Oddly, an air pump seems to both be powered by the system, but also acts as a power _source_ to the Arduino, albeit a very weak one. We're probably getting an ideal diode or Schottky to mitigate this.
 * I really, really hate wires. I am now trying to learn PCB design as fast as possible so that this demo **stays** a demo.
* Almost done: just have to do firmware, hook up MOSFET
* I think of the circuitry as 3 "boxes"
    * Box 1: Wago Mess
        * Biggest fish, main 12V line, 5V line, pumps (peristaltic and air), LED light, basically anything that has a significant power draw
        * Connected to the other boxes through power lines (5V and GND) and motor driver
    * Box 2: UNO and Co.
        * Gets power (5V and GND from Box 1)
        * Microcontrollers, sensors, LCDs, controls, etc
        * Controls Box 3
    * Box 3: MOSFET
        * Controls light (on perfboard)
        * controlled by UNO and Co., gets power from Wago Mess

 ---
 
04/02/26 \- Rakin
* Mainly just repo hygiene, adding CAD files
* Still have to print + verify distilled water and vessel top cap files

---

04/03/26 \- Rakin
* Finally turning the corner on the cold
* Redesigned top cap + distilled water caps; whether the redesigns actually _work_ are TBD 
* Bought ferrite beads + a bunch of ceramic capacitors in an effort to stop spooky EMI
* Also moving air pump to a seperate plug to avoid backfeeding into the Arduino
* Speaking about the 'Duino: tmrw, planning to meet up with Jason (+ maybe Arjun?) to HOT GLUE wires in, maybe transition breadboard to a perf strip (though that makes soldering harder)
* Also meeting w/ Arjun to do firmware

---

04/04/26 \- Rakin (+ Jason for 1.5 hours)
* So now it works. The problem is SOPHON is for classrooms. Classrooms with middle schoolers. Middle schoolers who, even with the best intentions, likely won't be as careful with my wires as I will be.
* SO: breadboard wire mess has to go onto perfboard; I wish Jason the best of luck with _that_!
* Speaking of imossible tasks, turns out my clever top cap design that has a PTFE membrane clamped by 3D-printed guides isn't so airtight after all. I had to use **HOT GLUE**
* Transitioning to using a sterile barbed filter and a "stack": bulkhead barb (inside vessel) -> barb (outside vessel) -> short tubing -> barb of filter -> filter membrane -> OUTPUT barb of filter
* Looks less clean, but hot glue isn't exactly clean either. Could use a really, really tall cap to hide it somewhat.
* Nervous, feeling time pressure
* Added dip tubes to all except distilled water

---

04/05/26 \- Rakin
  * Not doing a whole lot
  * Idea: sterilize harvest using flocculation (NaOH)
  * Harvest 30% on Monday since culture is getting denser on weekends
  * Really need to take more **PHOTOS**
  * Capsule filter: https://www.aliexpress.us/item/3256809638003121.html?gatewayAdapt=glo2usa4itemAdapt

---

04/06/26 \- Rakin, Arjun, Jason
  * Note: in air, the baseline turbidity sensor voltage is 3.14V using a 5.1k pulldown resistor.
  * Alright: so proabably buying capsule filter soon, but currently working on outreach/logo (Arjun), case design (Jason) and technical work (me). Probably should get the ideal diodes too if possible.
  * Making case look sleeker

---

04/13/26 \- Rakin, Jason (online)
  * Sorry for the lack of updates; SciOly has been really busy.
  * Good news: state comp just ended, so I can do more SOPHON
  * Working on: the new case, taking inspo from electronic project boxes
  * Making design into flat panels (think IKEA) instead of box for faster printing + better overhangs
  * Also makes it modular, key goal of SOPHON
  * Stops kids from touching too much
  * Maybe make V2's case (or V1.5 at earlist) out fo sheet metal, the panalizd design is basically begging for it but onshape hates sheet metal so we'll see how it goes
  * Jason the engineer who did load testing with cardboard (that's really cool btw), me the designer who wants it to look good on CAD in assembly and when finished, and the 3D printer with printer-problems like overhangs are all having a friendly fight
  * Trying to do the duino r4 firmware while jason does that 

---

04/16/26 \- Rakin, Jason (online)
* Life lifing
* Did print base partially
* Nixed the sheet metal idea: too much cost and time
* Trying to make schmatic
* Working on firmware wheile Jason handles printing and stuff

---

04/18/26 \- Rakin
* made significant headway on rudimentary HMI on LCD
* Still waiting on Arjun for printing
* Perosnally, I'm trying to mae sure the bottleneck doesn't fall on me.
* Maybe SOPHON V2 gets a Nextion or a purposebuilt HMI...that is energy-wasteful though.
* Need to code JSON/h-bridge/double-cehck code works.
* Need to code a website to recieve the POSTs

---

04/19/26 \- Rakin, Jason (Online)
* made even more headway on rudimentary HMI on LCD
* Redesigned some parts of enclosure for easier printing (reoriented for better layer strength)
* Maybe not a nextion, maybe an e-ink display or Nextion clone (brand name: DWIN), or maybe a Inkplate or MSPaper
* Idea: maybe use a prefilter on SOPHON V2
* jeez, i don't wwant to Osborne Effect SOPHON... wait, does that even apply to open-source stuff? I guess I don't want to scope creep.
* Reducing dead volume through software purging

---

04/20/26 - Rakin, Arjun (online), Jason (online)
* Printed 5/6 case parts, getting 6th tmrw
* Brief History of SOPHON: before I forget - > 3 main design iterations
  * **Design 1:** Overpolished Fossil
    * Oct-Nov '25, tried to integrate everything into 1 tiny, compact unit
    * Pros: compact, w/o supports
    * Cons: not modular *at all*, and ultimately a failure and waste of filament + time
  * **Design 2:** SophonBoard (Currently Published)  
    * Dec-Feb '26, went in the opposite direction: breadboard-like attachment grid + modules that attached via screws
    * Pros: super, duper modular: saved lots of filament, rapid testing of different arrangements
    * Cons: Didn't have space for wiring, lots of sprawl
  * **Design 3:** Custom Case  
    * Mar-Present '26, went in a middle direction, still had 1 case like V1 but it was built out of panels like an IKEA flat-pack
    * Pros: both modular, compact, and looked *great*
    * Cons: TBD (wish us luck!)

 ---
 
 04/21/26 - Rakin, Jason (online)
   * The deadline is nearing, started process for ordering algae and nutrients...
   * Must work on assembly guide
   * Finally finished assembly; now we verify and test.

---

 04/22/26 - Rakin
  * Happy Earth Day!
  * Also 1-month anniversary of this lab notebook
  * Anyway...
  * Maybe use an aquarium sponge as output prefilter? (prevents hydrophobic filter clogging due to high humidity air)
  * Use pill bottle/250mL wide mouth HDPE to act as a knockout pot, prevent algae from evaporation
  * ALGAE PRESERVATION: maybe use a dryer to dry the algae PASTE into little "flakes" OR 10% salt
  * SHORT TERM: allow oxygen exchange to minimize odor, decant/let settle + filter through 35 micorn mesh + squeeze to form paste

---
 04/25/26 - Rakin, Jason, Arjun
  * Changing fluid design from 3 (Distilled Water, Nutrients, Harvest) to 4 (Added salts water)
  * Compensated for dead volume in code
  * finished state machine code
  * Wired tubing
  * Program,spam capacitors and ferrites to banish EMI to the nether realm, and inoculate!!!
  * TODO:
    * Calibrate mL/sec for forward, reverse, and slower speed (nonlinear, so 85 duty cycle isn't 1/3rd the speed as 255) (maybe do through a helper sketch?)
    * prime stuff from tannks to manifold with their respective fluid
    * Comment Code
    * PUBLISH Code
    * Wait 4 days btwn inoculation and first harvest
    * Handle WiFi and POST request sending in code
    * Refill distilled water midway through (or switch to 500mL)

---

 04/26/26 - Rakin
   * Got the final case design from Jason
   * Actually tested code - menus finally work!
   * Hot glued wires in place, ensured nothing broke
   * TODO
     * Calibrate Pump (note, prime first!)
     * Add RC and LC filters to turibidity
     * Add ceramic caps everywhere

---

 04/28/26 - Rakin
   * **There's no way to sugarcoat this: SOPHON isn't doing too hot**
   * I'm scared: we tested the pump multiplexing with colored water, and the pump and prmots intermmittently failed
   * NTP sometimes failed too: shows 12 AM.

---

04/29/26 - Rakin
  * Alright, I'm outclassed: asked an aquaintance who knows Arduino more than I do
  * The weird NTP problems wwere fixed, but I think the safety features were too overzealous.

---

05/01/26 - Rakin
  * Fixed it myself! Turns out there's this [obscure Arduino bug](https://github.com/arduino/ArduinoCore-renesas/issues/58) where you cannot use analogWrite() and digitalWrite() at the same time
    * Fix: in applyMotor(), call pinMode([PIN_HERE], OUTPUT) before every digitalWrite() on that pin.
  * Anyway, still not all rainbows:
    * Need to add ferrites+securements so my turbidity sensor isn't a glorified random.org
    * Glue in arduino pins
    * Adjust PWM frequency to avoid annoying whine
    * Test with food coloring (at Jason's house), re-calibrate peristaltic pump (?)
    * Attach containers to barbs
    * Glue pump to SophonBoard
    * Glue LCD and joystick back on, cable management, soldering instead of breadboards NO MATTER WHAT!!!!
    * Comment code
  *  Documentation is... lacking
  *  idea for SOPHON V2: still use SophonBoard, but use slots as makeshift wire holes
  
---

05/04/26 - Rakin
  *Recalibrating peristaltic pump, bubbles seem to be a fact of life here
  * 6.05 ml/sec -> 4.6 ml/sec
  * Wait... my manifold is the leak point,, probably needs PTFE
  * Welp.

  * Hi this is Rakin 2 hours later, so it turns out bubbles are not a fact of life after all, resealing with PTFE did a LOT!!!!!
  * 6.05 was right after all for PWM 160, but interestingly reverse is faster at approx 7.1 ml/sec with watrer (adjusted to 6.75 since algae slurry thicker)
  * Still have to do a food coloring test, assembly guide, etc.
  * Poke hole in harvest for aerobic + pressure buildup reasons
  * Calculate dead volume one alst time, maybe add right angles to stop gravity from priming the liquids too far
