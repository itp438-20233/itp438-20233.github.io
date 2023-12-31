---
title: Weekly Breakdown
parent: Syllabus
has_children: false
nav_order: 2
---

# Weekly Breakdown

## Where to Get Slides / Other Materials

All course materials not on the website including slides are available on the course Google Drive [here](https://drive.google.com/drive/folders/1--W2QL9GMyJUnwbgcPUX20SVJoydcuKB?usp=sharing). This drive will be updated as the semester progresses, so you should keep it favorited. For convenience, a link is included in the top toolbar on this website.

---

## Week 1

### Monday

***Lecture***: Course Intro; Unreal Basics

### Before Wednesday's Class

Complete [Assignment Setup](00.html)

### Wednesday

***Flipped Classroom***:<br/>[Using Perforce](https://youtu.be/vXFahMeKx4s) (11:24)<br/>[Navigating Code in Visual Studio](https://youtu.be/YteaoiB66ew) (5:46)<br/>[Debugging in Visual Studio](https://www.youtube.com/watch?v=lvOnHyxr_xo) (13:00)<br/>
Start [Assignment 1: Unreal Basics](01.html)

### Upcoming Dates

* The final version of Assignment 1 is due Wednesday of Week 2

---

## Week 2

### Monday

***Lecture***: Blueprints; C++ in Unreal<br/>

### Wednesday

***Flipped Classroom***: [Live Coding - Blueprints](https://www.youtube.com/watch?v=dQfpbnChFwk) (39:07)<br/>**Corrections**:

* The player blueprint is now called `BP_TopDownCharacter`
* The player material is now in Content>Characters>Mannequins>M_Mannequin
* The body color parameter is now called `Tint`
* The original color is now `(1, 1, 1)`
* In code, set the `DefaultColor` to `FLinearColor::White`
* In code, set `BodyColorParameter` to `FName(TEXT("Tint"))`

Start [Assignment 2: Puzzles](02.html)<br/>Assignment 1 is **DUE** at 11:59PM

### Upcoming Dates

* Grades for Assignment 1 are out on Saturday
* Regrade requests for Assignment 1 are due Tuesday of Week 3
* The final version of Assignment 2 is due Wednesday of Week 3

---

## Week 3

### Monday

***Labor Day (No class)***

### Tuesday

Assignment 1 regrade requests **DUE** at 11:59PM

### Wednesday

***Flipped Classroom***: [Live Coding - Interact System](https://youtu.be/K1g0VY6EAII) (43:04)<br/>**Corrections**:

* Select "Cascade Particle System" as the component for the torch

Start [Assignment 3: Interaction and More Puzzles](03.html)<br/>Assignment 2 is **DUE** at 11:59PM

### Upcoming Dates

* Grades for Assignment 2 are out on Saturday
* Regrade requests for Assignment 2 are due Tuesday of Week 4
* The final version of Assignment 3 is due Wednesday of Week 4

---

## Week 4

### Monday

***Lecture***: More C++ in Unreal; Physics Basics

### Tuesday

Assignment 2 regrade requests **DUE** at 11:59PM

### Wednesday

***Flipped Classroom***: [Live Coding - Physics and Sequencer](https://www.youtube.com/watch?v=ZEqmo9Xyru0) (30:48)<br/>**Corrections**:

* With the default physics settings of the Crate_BP, you may notice it's a little tough to push onto the pressure plate. To fix this, in Crate_BP, under "Physics" check the "Mass (kg)" box which will set the mass to 100. That seems to make it be a lot easier to push around and onto the plate
* You may notice the pressure plate flickers the puzzle output a bit when you're standing on the edge of it, but this is expected
* Sequences are now under Cinematics>Level Sequence
* For the keyframe at frame 60, set the z position to 0 as the ground is at 0
* You may notice that jumping off the pressure plate when as the player may not always reset the pressure plate. This is expected, but you can try to tweak physics settings if it bothers you

Start [Assignment 4: Physics Puzzles](04.html)<br/>Assignment 3 is **DUE** at 11:59PM

### Upcoming Dates

* Grades for Assignment 3 are out on Saturday
* Regrade requests for Assignment 3 are due Tuesday of Week 5
* The final version of Assignment 4 is due Wednesday of Week 5

---

## Week 5

### Monday

***Lecture***: Animations; Character Movement

### Tuesday

Assignment 3 regrade requests **DUE** at 11:59PM

### Wednesday

***Flipped Classroom***: [Live Coding - Animations](https://www.youtube.com/watch?v=wN-SUEirhsc) (30:01)<br/>**Corrections**:

* The retargeted animations will not have `_Retargeted` at the end of them by default, so for example when you want to play `Stand_to_Crouch_Rifle_Hip_Retargeted`, it will just be `Stand_to_Crouch_Rifle_Hip`

Start [Assignment 5: Dashing and Damage](05.html)<br/>Assignment 4 is **DUE** at 11:59PM

### Upcoming Dates

* Grades for Assignment 4 are out on Saturday
* Regrade requests for Assignment 4 are due Tuesday of Week 6
* The final version of Assignment 5 is due Wednesday of Week 6

---

## Week 6

### Monday

***Lecture***: Unreal Motion Graphics UI

### Tuesday

Assignment 4 regrade requests **DUE** at 11:59PM

### Wednesday

***Flipped Classroom***: [Live Coding - UMG](https://youtu.be/juhZqqejLzo) (34:37)<br/>**Corrections**:

* When you create HUDWidget_BP, and it asks you for the class you want to subclass, just click the "User Widget" button
* Widgets no longer automatically start with a Canvas Panel, so you will need to add one. To add one, select "Canvas Panel" under "Panels" from the Palette and drag it onto the Hierarchy
* "Enable Fill Animation" is already unchecked by default on Progress Bar

Start [Assignment 6: UI](06.html)<br/>Assignment 5 is **DUE** at 11:59PM

### Upcoming Dates

* Grades for Assignment 5 are out on Saturday
* Midterm is during Week 7!
* Due to the midterm in Week 7, regrade requests for Assignment 5 are due Tuesday of ***Week 8***
* Due to the midterm in Week 7, the final version of Assignment 6 is due Wednesday of ***Week 8***

---

## Week 7

### Monday

***Lecture***: Materials and Rendering

### Wednesday

***Midterm Exam (programming; in-person) during class period***

### Upcoming Dates

* Regrade requests for Assignment 5 are due Tuesday of Week 8
* The final version of Assignment 6 is due Wednesday of Week 8

---

## Week 8

### Monday

***Lecture***: Nav Mesh; AI Controllers; Behavior Trees

### Tuesday

Assignment 5 regrade requests **DUE** at 11:59PM

### Wednesday

***Flipped Classroom***: [Live Coding - Behavior Trees](https://www.youtube.com/watch?v=RfnoFN_kxns) (38:27)<br/>**Corrections**:

* The existing Top Down Character Blueprint is BP_TopDownCharacter under Content/TopDown/Blueprints
* For the AI character, change the anim blueprint to ABP_Manny and the skeletal mesh to SKM_Manny (so it looks different than our player!)
* When you reparent now, it seems like it now automatically fixes the AI Controller Class and Auto Possess AI properties, so you shouldn't have to change them (though check just in case)

Start [Assignment 7: Behavior Trees](07.html)<br/>Assignment 6 is **DUE** at 11:59PM

### Upcoming Dates

* Grades for Assignment 6 are out on Saturday
* Regrade requests for Assignment 6 are due Tuesday of Week 9
* The final version of Assignment 7 is due Wednesday of Week 9

---

## Week 9

### Monday

***Lecture***: Networked Multiplayer Basics

### Tuesday

Assignment 6 regrade requests **DUE** at 11:59PM

### Wednesday

***Flipped Classroom***: [Live Coding - Networking](https://youtu.be/NCYrZy_5GOg) (40:53)<br/>
Start [Assignment 8: Networking 1](08.html)<br/>Assignment 7 is **DUE** at 11:59PM

### Upcoming Dates

* Grades for Assignment 7 are out on Saturday
* Regrade requests for Assignment 7 are due Tuesday of Week 10
* The final version of Assignment 8 is due Wednesday of Week 10

---

## Week 10

### Monday

***Lecture***: More Networking

### Tuesday

Assignment 7 regrade requests **DUE** at 11:59PM

### Wednesday

***Flipped Classroom***: [Live Coding - Networking, Part 2](https://www.youtube.com/watch?v=tvNnOADCPFI) (40:10)<br/>**Corrections**:

* For setting the color for the spawn areas, you can duplicate the MI_PrototypeGrid_TopDark twice and make one MI_PrototypeGrid_Blue and one MI_PrototypeGrid_Red, setting the SurfaceColor and TopSurfaceColor parameters to the colors you want. Then use that on some of the geometry in those spawn areas

Start [Assignment 9: Networking 2](09.html)<br/>Assignment 8 is **DUE** at 11:59PM

### Upcoming Dates

* Grades for Assignment 8 are out on Saturday
* Regrade requests for Assignment 8 are due Tuesday of Week 11
* The final version of Assignment 9 is due Wednesday of Week 11

---

## Week 11

### Monday

***Lecture***: 

### Tuesday

Assignment 8 regrade requests **DUE** at 11:59PM

### Wednesday

***Flipped Classroom***: [Live Coding - Aim Offsets](https://youtu.be/bZAph-2M724) (34:15)<br/>**Corrections**:

* When updating the Horizontal/Vertical axis in the aim offset asset, also check "Snap to Grid" as it makes it easier to place the aim offset animations where you want to.
* Use Ctrl+Click to drag the preview point in the aim offset, not Shift+Click

Start [Assignment 10: Networking 3](10.html)<br/>Assignment 9 is **DUE** at 11:59PM

### Upcoming Dates

* Grades for Assignment 9 are out on Saturday
* Regrade requests for Assignment 9 are due Tuesday of Week 12
* The final version of Assignment 10 is due Wednesday of Week 12

---

## Week 12

### Monday

***Lecture***: Online Subsystems and Steam

### Tuesday

Assignment 9 regrade requests **DUE** at 11:59PM

### Wednesday

***Flipped Classroom***: [Live Coding - Listen Server and Main Menu](https://youtu.be/h6yqIuBkCfY) (31:31)<br/>Start [Assignment 11: Steam](11.html)<br/>Assignment 10 is **DUE** at 11:59PM

### Upcoming Dates

* Regrade requests for Assignment 10 are due Tuesday of Week 13
* The final version of Assignment 11 is due Wednesday of Week 13

---

## Week 13

### Monday

***Lecture***: Cooking; Serialization; Save/Load

### Tuesday

Assignment 10 regrade requests **DUE** at 11:59PM

### Wednesday

***Flipped Classroom***: [Live Coding - Decal Tags](https://youtu.be/7TU10-Q8CGo) (46:20)<br/>Start [Assignment 12: Tags and Save/Load](12.html)<br/>Assignment 11 is **DUE** at 11:59PM

### Upcoming Dates

* Grades for Assignment 10 are out on Saturday
* Regrade requests for Assignment 10 are due Tuesday of Week 14
* The final version of Assignment 11 is due Wednesday of Week 14

---

## Week 14

### Monday

***Lecture***: Gameplay Ability System; Plugins

### Tuesday

Assignment 11 regrade requests **DUE** at 11:59PM

### Wednesday

***Thanksgiving (No class)***

### Upcoming Dates

* Regrade requests for Assignment 11 are due Tuesday of Week 15
* The final version of Assignment 12 is due Wednesday of Week 15

---

## Week 15

### Monday

***Lecture***: Guest Lecture

### Wednesday

***Lecture***: New Gameplay Features in Unreal 5<br/>Assignment 12 is **DUE** at 11:59PM

### Upcoming Dates

* The final exam is [scheduled based on your section](Schedule.html#final-exam-schedule)
