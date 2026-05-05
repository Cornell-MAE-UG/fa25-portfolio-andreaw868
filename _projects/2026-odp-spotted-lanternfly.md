---
layout: project
title: Anti Spotted Lanternfly Device
description: For my introduction to mechanical design class, my team designed a device to aid grape vineyards with the spotted lanterfly invasion, preventing this invasive species from contaminating grape harvests.
technologies: Fusion 360, Laser Cutting, 3D Printing
image: 
---

For the Open Design Project, we were challenged to design a mechanical solution to the real world problem of the spotted lanternfly invasion of grape vineries. Our solution ended up utilizing compressed air to remove a target fly in the path of the harvester. I worked with a group of 4 other mechanical engineering students to develop a working prototype by the end of the semester. Throughout the process, we documented our brainstorming for our initial 
[Client Pitch](#client-pitch), 
[Functional Prototype](#functional-prototype), and 
[Final Client Report](#final-client-report).

## Project Milestones
- [Client Pitch](#client-pitch)
- [Functional Prototype](#functional-prototype)
- [Final Client Report](#final-client-report)

---

## Client Pitch

**Client(s):** *Cornell CALS Extension, E&J Gallo Winery, National Grape Coalition*

---

### **Problem Statement**
From August to November, spotted lanternflies (SLFs) mature into their adult form and migrate onto grape crops, with up to 400 insects per vine. During mechanical harvesting, SLFs cling to the grapes and enter the harvester.  

There is currently **no mechanism to prevent SLFs from entering the harvest stream**. Even *one or two SLFs* can contaminate an entire batch, rendering it unsellable—resulting in **wasted resources and increased production costs**.

---

### **Impact**
Our team focused on addressing SLFs *during the harvesting process*, where intervention is most effective and controlled.  

This approach:
- Minimizes disruption to existing workflows  
- Integrates directly with harvesting equipment  
- Avoids adding additional labor steps  

---

## **Concept A: SLF Vacuum**

**Description:**  
A vacuum system attached to the harvester removes SLFs from harvested grapes.

**How it would be used:**
- Attached to the collector system before the reservoir  
- SLFs are sucked up, juice filtered back, and SLFs deposited into a separate bin/out of harvester  

**Why it improves upon the status quo:**
- Remove the SLFs from the harvested grapes, so there are no SLFs in the final grape collection 
- Automatic sorting between SLFs and grapes, no need for manual differentiation

**End-of-semester proof-of-concept:**  
A tested vacuum system capable of removing SLFs while avoiding grapes.

**Key Risks:**
- Finding precise vacuum pressure to only pick up SLFs
- Smaller grapes and juice are at risk of being picked up

**Planned Testing:**
- Develop weight-accurate SLF and grape models  
- Systematically test vacuum selectivity  

---

## **Concept B: SLF Removal via Compressed Air**

**Description:**  
A front-mounted attachment that detects SLFs and deploys compressed air to remove them before harvesting begins.

**How it would be used:**
- Attach mechanism to front of harvester
- Approach grape vine, detect the presence of SLFs, stop and deploy compressed air until SLF is successfully removed and repeat 

**Why it improves upon the status quo:**
- Remove SLFs before grapes are harvested, but doesn’t require an extra process to do so (part of harvesting process) 
- Air is relatively cheap and reusable, compared to water

**End-of-semester proof-of-concept:**  
A mechanism capable of delivering targeted compressed air bursts, along with a mounting method for integration with a harvester.

**Key Risks:**
- Air may unintentionally remove grapes  
- Could slow down harvesting due to detection and actuation time  

**Planned Testing:**
- Perform 30+ trials to evaluate reliability  
- Optimize detection to avoid unnecessary firing  
- Ensure minimal interruption to harvesting speed  

---

## **Questions for the Client**
1. *What is the gripping force of SLFs on grape vines?*  
   → This determines required vacuum pressure and air force  

2. *Can we access common harvester models?*  
   → Enables seamless mechanical integration  

3. *Do SLFs maintain grip after death, and for how long?*  
   → Could inform alternative removal strategies (e.g., pesticides)  

## Functional Prototype
### CAD Model:

<div style="display: flex; gap: 16px; justify-content: center; flex-wrap: wrap;">
  <img src="/assets/images/ODPv1_FrontView.png" alt="Front View" style="width: 30%; border-radius: 8px;">
  <img src="/assets/images/ODPv1_IsometricView.png.png" alt="Isometric View" style="width: 30%; border-radius: 8px;">
  <img src="/assets/images/ODPv1_SideView.png" alt="Side View" style="width: 30%; border-radius: 8px;">
</div>

### **Design Documentation**

#### **Key Components**
- **Compressed Air Source:** 8 oz. disposable spray duster, from McMaster (7437K35, $19.13)
- **Rotational System:**  
  - Crank handle, from McMaster (6547N15, $24.87)  
  - 8 mm Steel shaft, from McMaster (6547N15, $24.87)
  - Flanged ball bearings x2, from McMaster (57155K496, $19.90) 
- **Custom Fabricated Parts:**  
  - 3D-printed shaft + trigger compressor  
  - 3D-printed housing and mounting bracket 

<figure style="text-align: center;">
  <img src="/assets/images/ODPv1_Components_Assembly_Sketch.jpg alt="Sketch of components" style="width: 100%; height: auto; border-radius: 8px;">
  <figcaption><em>Sketch of components and assembly</em></figcaption>
</figure>

*Note:* Due to fabrication delays, the housing ended up being prototyped using in-house wood scraps, assembled with wood glue, superglue, and epoxy.

---

#### **How to Assemble**
*Abbreviation: CAC = Compressed Air Can*

1. Insert ball bearings into the designated holes in the main housing and sideplate, securing with superglue. 
2. Assemble the main housing components using wood glue, leaving one sideplate off to allow for shaft insertion.
3. Slide the bracket onto the CAC from the top (the ridge at the bottom of the can prevents insertion from below). 
4. Place the CAC into the main housing and secure the bracket to the housing with superglue.
5. Insert the shaft into the bearing in the main housing. Then slide the sideplate with its bearing onto the shaft and attach the sideplate to the housing using wood glue.  
6. Attach the handle to the bracket using epoxy.

*Design choice:* Glue was decided as the adhesive/fastener for the first prototype to allow for adjustability in the process. We are planning to buy/design stronger fasteners for future prototypes once the design is in a more finalized state. 

---

### **Design Test**

#### **Test 1: Trigger Actuation Mechanism**
This is the primary mechanism that will be pushing down on the compressed air canister to shoot air at the SLFs. We needed to validate (1) whether the 3D printed part fits with the trigger of the compressed air canister and (2) when cranked, our mechanism can indeed produce enough force on the trigger.

- *Measured requirement:* **25–45 N** force needed for actuation, measured by using a spring scale to pull on the trigger. This helped establish a baseline for how much force our mechanism needs to be able to provide. For future electrical integration, this also informs the selection of how powerful the motor needs to be.
- **Result:** We realized that in our initial prototype, we assumed that we could press the trigger using a horizontal force. However, a downward force is also needed
- **Design pivot:**  
  → Switched from a rack and pinion mechanism (which would only provide horizontal force) to a **rotational crank + shaft system** for direct trigger compression  

- **Result (with updated rotational design):**
  - Successful trigger engagement of approximately 10 degrees of rotation for the initial pressing of the trigger, and 20 degrees for full strength.
  - Observed ~2–3 mm shaft deflection under load  

**Conclusion:**  
The mechanism works, but **shaft stiffness must be improved** since the deflection of the shaft made it difficult to rotate the handle. This can be addressed by thickening the shaft and making it more supported by having it wrap around in a full closed loop. 

---

#### **Test 2: Exterior Housing**
We need to ensure that the 3D printed bracket holding the duster can support the weight of a full duster without damage / deformation; i.e. the force exerted by the spray can cannot exceed the yield strength of our material

- Tested ability to hold ~*3.43 N load* (full can weight)  
- Observed ~*0.5 mm lateral movement* of the compressed air canister within the housing.

**Conclusion:**  
- Movement is acceptable for current function  
- Since the 3-D printed housing was not printed in time, and we needed to substitute with wood, we didn’t have the top or bottom of the housing to test but the next iteration will use laser-cut acrylic for improved rigidity and manufacturability.

---

#### **Test 3: SLF Removal Effectiveness**
**Goal:** Determine effective distance for removing SLFs using compressed air  

- Target: *0.5 m removal distance*  
- Method: Tested on ~*1 g SLF models*  

**Results:**
- Effective removal up to **~0.3 m (1 ft)**  
- Air stream sufficiently concentrated for targeted removal  

**Conclusion:**  
- Prototype is **functional but below target range**  
- Performance limited by:
  - Suboptimal nozzle orientation  
  - Incomplete trigger force due to shaft deformation  

**Next Improvements:**
- Reorient nozzle for horizontal targeting 
- Increase shaft strength to allow full-force actuation  

---

### **Success Criteria**

The prototype was evaluated against the following criteria:

- **[High Priority] Trigger Actuation**  
  Must reliably deliver *25–45 N* to activate compressed air  

- **[High Priority] SLF Removal**  
  Must dislodge SLF analogs (~1 g) at distances up to *0.5 m*  

- **[Mid Priority] Response Time**  
  Minimize delay between user input and air deployment (*target: ~10 seconds*)  

## Final Client Report
Placeholder for Final Client Report



