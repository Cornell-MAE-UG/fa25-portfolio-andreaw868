---
layout: project
title: Anti Spotted Lanternfly Device
description: For my introduction to mechanical design class, my team designed a device to aid grape vineyards with the spotted lanterfly invasion, preventing this invasive species from contaminating grape harvests.
technologies: Fusion 360, Laser Cutting, 3D Printing
image: /assets/images/ODP.jpg
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
  <img src="{{ site.baseurl }}/assets/images/ODPv1_FrontView.png" alt="Front View" style="width: 30%; border-radius: 8px;">
  <img src="{{ site.baseurl }}/assets/images/ODPv1_IsometricView.png" alt="Isometric View" style="width: 30%; border-radius: 8px;">
  <img src="{{ site.baseurl }}/assets/images/ODPv1_SideView.png" alt="Side View" style="width: 30%; border-radius: 8px;">
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
  <img src="{{ site.baseurl }}/assets/images/ODPv1_Components_Assembly_Sketch.jpg" alt="Sketch of components" style="width: 100%; height: auto; border-radius: 8px;">
  <figcaption><em>Sketch of components</em></figcaption>
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

---

## Final Client Report

---

## **Context and Problem Statement**
As grape crops are harvested, spotted lanternflies (SLFs) that cling to the crops also enter the harvesters. There is currently no reliable mechanism to stop SLFs from entering the harvester, and even one or two SLFs can contaminate a batch—making it unsellable and increasing production costs.

We focused on this stage of the process because it allows for the most control while minimizing disruption, since solutions can be directly attached to the harvester.

---

## **Design Summary**

<div style="display: flex; gap: 16px; justify-content: center; flex-wrap: wrap;">
  <img src="{{ site.baseurl }}/assets/images/ODP_FinalPrototype.jpg" alt="Fully assembled" style="width: 45%; border-radius: 8px;">
  <img src="{{ site.baseurl }}/assets/images/ODP_FinalPrototype_Interior.png" alt="Interior view" style="width: 45%; border-radius: 8px;">
</div>

*Left: Final prototype; Right: Interior view of compressed air canister mounted inside acrylic housing*

As pictured above, this is a mechanism that releases a concentrated stream of air and has the ability to aim with a two-axis gimbal and blow SLF off of grape plants from its mount on the harvester. The compressed air allows for both more accurate aiming as well as a higher force acting on the SLF’s, as previously attempted methods indicate that general wind/air is not a useful deterrent. The implementation of the gimbal was for the purpose of being able to cover a larger area, since the compressed air has such a small affected area, as well as to damp any vibrations or sudden movements from the harvester.

---

## **Conclusion and Recommendation**

Through testing and iteration, our prototype successfully:

1. Compressed the trigger on the air canister through a 3D printed shaft, actuated with a handle. 
2. Successfully blows off 3D printed “SLFs” weighing around 1 gram at distances of up to **2.5 ft**.
3. Is actuated quickly; i.e. the duration between when the user first interacts with our mechanism (i.e. touching the crank) to when the SLF is blown off in an average time of **5 seconds.** 
4. Has the ability to aim and is stabilized (from potential harvester vibrations) via a **two-axis gimbal**  

Additionally, the design is compact and can easily be integrated into a harvester without disrupting the harvesting process or integrated into other larger mechanisms. We believe our design is promising and can be utilized along with other solutions to reduce the SLFs in the fields. 

### **Remaining Challenges**
- Gimbal and trigger actuation are separate systems, making it difficult for both processes to proceed at the same time (i.e. rotating an axis while cranking the shaft)  
- Air canisters are not refillable and will require replacement
- Risk of unintentionally removing grapes requires more testing

### **Future Improvements**
- Automate with motors and electronics instead of a hand crank
- Replace disposable canister with refillable air system  
- Add SLF detection via software integration (i.e. cameras, sensors)  

---

## **Design Features**

### **Compressing Shaft**
<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/images/ODP_CompressingShaft.png" alt="Housing" style="width: 40%; border-radius: 8px;">
</div>
- **Material:** 3D Printed ABS  
- **Purpose:** The shaft compresses the trigger on the compressed air canister to trigger the release of air through actuation by a crank handle.

---

### **Outer Housing**
<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/images/ODP_OuterHousing.png" alt="Housing" style="width: 40%; border-radius: 8px;">
</div>

- **Material:** Laser-cut acrylic  
- **Purpose:**  Housing protects the compressed air canister while operation of the prototype and holds the air canister in place through a bracket. Features puzzle piece edges that allow for quick assembly, maintenance and iteration. 

---

### **Gimbal System**
<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/images/ODP_Gimbal.png" alt="Gimbal" style="width: 40%; border-radius: 8px;">
</div>

- **Material:** 3D Printed ABS  
- **Purpose:**  Allows the prototype to aim and rotate about two axes and stabilizes the air canister when mounted on the harvester. 

---

## **Testing and Validation**

### **Test 1: Removal Distance**
<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/images/ODP_DistanceTest.jpg" alt="Distance test" style="width: 80%; border-radius: 8px;">
</div>

**Test Process**: We created modelled SLFs with masking tape, weighing ~1g each and used the compressed air canister to blow them.  SLFs weigh an average of 0.3g, but have grip strength so we included a safety factor of 3​. 
**Results**: Prototype successfully blows off 3D printed “SLFs” weighing around 1 gram at distances of up to 2.5 ft. This showed that our design can be successful while mounted on a harvester where it will target the infested grapevines from a distance.

---

### **Test 2: Trigger Force**
<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/images/ODP_Force_Test.jpg" alt="Force test" style="width: 50%; border-radius: 8px;">
</div>

**Test Process**: The purpose of this test is to verify what the necessary force is to ensure accurate selection of electrical actuation for future prototypes. We first utilized spring scale to measure the force that the 3D printed shaft must exert on the trigger. To release a small stream of air, ~25 N of force is needed. To fully depress the trigger, ~45 N of force is necessary. With our prototype, we measured the amount of force the 3D printed shaft exerted on the trigger of the compressed air canister. 
**Results**: The 3D printed shaft successfully compresses the air canister with a force of 45N, successfully reaching our target compressive force. 

---

### **Test 3: Response Time**
**Test Process**: We staged 5 trials of SLFs placed at a distance of 2.5 feet (the maximum range of the compressed air canister). For each trial, the time between the compression of the shaft and the SLFs being disrupted from their place was taken.
**Results**: The average time for displacement of SLFs was 5.49 seconds. Compared to our target time of 10 seconds, this showed that our prototype was sufficiently efficient. Further improvements can be made to the efficiency with the implementation of electronics and SLF detection. 

---

## **Bill of Materials**

| Source | Item | Description | Cost | Qty |
|--------|------|------------|------|-----|
| McMaster (7437K35) | Spray Duster | Compressed air source | $19.13 | 1 |
| McMaster (5972K91) | Ball Bearings | Shaft + gimbal rotation | $2.95 | 8 |
| McMaster (6547N15) | Crank Handle | Actuation | $24.87 | 1 |
| McMaster (4634T34) | Aluminum Rod | Gimbal structure | $2.16 | 4 |
| McMaster (6056N16) | Set Screw Collar | Shaft retention | $2.25 | 4 |
| Cornell RPL | 3D Printed Shaft | Trigger system | $0.96 | 1 |
| Cornell RPL | Acrylic Housing | Outer casing | $8.50 | 1 |
| Cornell RPL | Gimbal Rings | Rotation system | $9.00 | 2 |
| Cornell RPL | Gimbal Spacers | Stabilization | $0.05 | 4 |

**Total Cost:** **$112.86**

---

## References

Barringer, Lawrence, and Claire M Ciafré. “Worldwide Feeding Host Plants of Spotted Lanternfly, with Significant Additions from North America.” *Environmental Entomology*, vol. 49, no. 5, 14 Aug. 2020, pp. 999–1011, https://doi.org/10.1093/ee/nvaa093.

Ladin, Zachary S., et al. “Human-Mediated Dispersal Drives the Spread of the Spotted Lanternfly (Lycorma Delicatula).” *Scientific Reports*, vol. 13, no. 1, 19 Jan. 2023, p. 1098, www.nature.com/articles/s41598-022-25989-3, https://doi.org/10.1038/s41598-022-25989-3.

“Spotted Lanternfly Management in Vineyards.” *Penn State Extension*, 10 Apr. 2025, extension.psu.edu/spotted-lanternfly-management-in-vineyards.

