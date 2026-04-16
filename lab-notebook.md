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
