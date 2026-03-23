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
* TODO: P
* Quick FAQ guide for our favorite hypothetical ISEF judge: why we did what we did  
  * **Why use *Arthrospira platensis* specifically?**  
    * Grows like a weed, high pH environment reduces competition with bacteria, common and well documented  
  * **Why use dip tubes, where the stuff comes in from the top instead of drilling holes from the bottom?**  
    * We wanted to avoid drilling since it would have made it harder to reproduce for limited-access people, plus it introduces a further area of complexity where there isn’t any reason to have it  
  * **Isn’t the algae going to starve of carbon?**  
    * Yes, but that’s the *point*. The entire reason that SOPHON exists is to only use carbon from ambient air to be net carbon-*negative*. Though this isn’t true yet since it’s still powered on-grid and uses dissolved inorganic carbon, those are *cost* issues, not *design* flaws. Better a real proof-of-concept that’s slightly carbon-positive than an ideal carbon-negative bioreactor that doesn’t exist. Also: we bought RECs.    
* Added further rationale to the BOM for each component\!
* Create schematic in KiCad
