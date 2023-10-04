---
title: Midterm
has_children: false
nav_order: 3
has_toc: false
---

# Midterm Exam

The Midterm Exam is due at ***11:59PM*** on ***Saturday, October 7***. This deadline will be strictly enforced. Late submissions will not be accepted.

If you would like clarification on something, please make a ***private*** post on Piazza with your question.

## Exam Honor Statement

The USC SCampus Student Conduct Code states in section 11.13.A:

> Any use or attempted use of external assistance in the completion of an academic assignment and/or during an examination, or any behavior that defeats the intent of an examination or other classwork or assignment, shall be considered academically dishonest unless expressly permitted by the instructor. The following are examples of unacceptable behaviors: communicating with fellow students during an exam, copying or attempting to copy material from another student’s exam; allowing another student to copy from an exam or assignment; possession or use of unauthorized notes, calculator, or other materials during exams and/or unauthorized removal of exam materials.

### Exam Rules

You ***MAY NOT*** collaborate with anyone else on this exam. This means you cannot talk to anyone else about the content of this exam until the exam period is over. This is an ***individual*** take home exam, and you are expected to work on this individually. The goal of this exam is to see what you could do on your own, not what you could do with the help of other parties.

You ***ARE*** allowed to consult the following resources while working on the exam:

- Notes including any slides from the class
- The flipped classroom and lecture recordings
- Your own code/blueprints from the programming assignments and flipped classrooms
- The Unreal Engine documentation ([https://docs.unrealengine.com/5.2/en-US/](https://docs.unrealengine.com/5.2/en-US/))
- The course Piazza for the sole purpose of getting clarification on the exam

You ***MAY NOT*** consult other online resources (such as blogs, Discord channels, tutorials, ChatGPT, etc) while working on the exam.

### Affirmation

By submitting this exam, you affirm you have read the above excerpt from the Student Conduct Code as well as the exam rules and you will follow them. If you fail to abide by these rules, you will be reported to SJACS with a recommended sanction of an F in the course.

## Part 1 - Prone State (25 points)

In this part, you will add a "prone" state to the character in your TopDown game.

The requirements are:

- The `X` key should toggle the character between prone and standing. So for example, if the player is standing and you press `X`, the player will switch to prone. Then if you press `X` again, the player will go back to standing.
- When prone, any movement input should be ignored. Also, if the player is moving when they switch to prone, they should stop moving.
- For the purposes of the exam, you do not have to worry about transitions between prone and crouching.
- For the prone animations, you'll use three animations from the AnimStarterPack which should already be retargetted to the new mannequin and in your project's Content folder:
  - When transitioning from standing to prone, use `Stand_To_Prone` (Retargeted)
  - While prone, use `Prone_Idle` (Retargeted)
  - When transitioning from prone to standing, use `Prone_To_Stand` (Retargeted)
- Because the transition animations are fairly short, you may have to adjust the condition for when they'll transition so that the animations don't noticeably pop

*Hint*: There is no existing logic for a "prone" state in Character/CMC. You don't have to implement a custom CMC, and instead can just add necessary logic/variables to `ATopDownCharacter`.

*Note*: The transition from prone back to walking will look weird if you hold down a movement key, but you don't have to worry about fixing this.

Once implemented, switching to/from prone should look like this:

<video style="display:block; margin: 0 auto;" width="640" height="360" controls>
  <source src="assets/Midterm1.mp4" type="video/mp4">
</video>

### Submission Requirements

In your Google Drive, make a folder for `midterm` and then a `part1` sub-folder. Please submit the following:

- A video demonstrating that:
  - The player can transition to and from prone
  - Make sure at least once you show the player walking before switching to prone (to demonstrate the player stops moving)
  - Make sure you show the player facing in different directions when they go prone, don't always just show one
  - (Your video can be similar to the one above)
- A screenshot of the default animation graph, showing the high-level view of any new states added
- ***Any source files*** you modified to implement the prone logic. You don't need to submit any modified ini files, we just want the .h and .cpp files you changed.

Please double-check that you submitted the required files!

## Part 2 - Stealth Box Component (35 points)

For this part you will make a new C++ component and a blueprint actor which uses it, and place some in the level.

Create a StealthBoxComponent which inherits from BoxComponent in C++:

* It needs to detect both begin and and overlaps (in C++) and should only do anything if the overlap is an TopDownCharacter
* TopDownCharacter needs to track how many Stealth Box Components a player is in at any one time
* In TopDownHUD (in code), you should visibly display how many stealth triggers the player is in

*Hint*: For tracking, think about how we tracked the number blue triggers. For the overlapping, you may find referencing the FireComponent code.

Make a `StealthTrigger_BP` which inherits from `StaticMeshActor`:

* Its Static Mesh should be `Floor_400x400`
* It's Material should be M_Glass
* Add a Stealth Box Component and set its location to (200, 200, 0) and its Box Extents to (200, 200, 50)

Place two partially overlapping StealthTrigger_BPs in the level so that the player can stand in one or both at the same time. You may have to raise them slightly in the level so they do not z-fight (flicker) with the floor. It should look something like this:

<video style="display:block; margin: 0 auto;" width="640" height="360" controls>
  <source src="assets/Midterm2.mp4" type="video/mp4">
</video>

In your Google Drive, make a folder for `midterm` and then a `part1` sub-folder. Please submit the following:

- A video demonstrating that the stealth box count on the HUD increases and decreases as expected (as in the video)
- Your StealthBoxComponent.h/cpp files
- ***Any other source files*** you modified to implement the logic

## Part 3 - Stealth UI (35 points)

This part cannot be fully completed without implementing Parts 1/2, although though you can complete _most_ of it even if you don't implement Part 1.

In this part, you will add a stealth indicator to the UMG HUD which gives feedback to the player as to how stealthy they are. This indicator will show at the top middle of the screen as an asterisk `*` which will change colors based on your threat level.

The threat levels are from highest to lowest:

- Purple
- Red
- Yellow
- Blue
- Green

You need to update the threat level every frame. The threat level should be computed as follows:

- By default, the character's threat level is red
- If the character is currently moving ***OR*** moved within the last 0.5 seconds, the threat level should increase by one tier
- If the character is currently crouching, the threat level should decrease by one tier
- If the character is currently prone, the threat level should decrease by *two* tiers
- If the character is currently inside stealth triggers, the threat level should decrease by one tier if inside one trigger ***OR*** *two* tiers if inside *two or more* triggers.

This means that, for example, if the player is just walking around their threat level would be purple (+1 threat). On the other hand, if the player were crouched and motionless inside a single stealth trigger, their threat level would be blue (-2 threat).

You ***must*** implement this indicator using UMG (you can add it to the existing `HUDWidget`).

*Hint 1*: You can represent the threat level with an integer (although an `enum` is probably better quality code, you aren't required to use an `enum`).

*Hint 2*: You will need to check every frame whether the character is moving to do the "moving or within the last 0.5 seconds" logic.

*Hint 3*: Remember that if you set a gameplay timer with the same handle as a previously set one, it will reset the timer to the full duration.

Once implemented, this will look something like this:

<video style="display:block; margin: 0 auto;" width="640" height="360" controls>
  <source src="assets/Midterm3.mp4" type="video/mp4">
</video>


### Submission Requirements

In your grading `midterm` folder make a `part3` sub-folder. Please submit the following:

- A video demonstrating that the threat level on the stealth indicator correctly updates. Specifically, you should show that:
  - When ***NOT*** in a stealth trigger:
    - Standing still, the indicator is red
    - Moving while standing, and 0.5s after stopping moves, the indicator is purple
    - Crouching while still, the indicator is yellow
    - Moving while crouching, and 0.5s after stopping movement, the indicator is red
    - When prone, the indicator is blue
  - When ***IN ONE*** stealth trigger:
    - Standing still, the indicator is yellow
    - Moving while standing, and 0.5s after stopping movement, the indicator is red
    - Crouching while still, the indicator is blue
    - Moving while crouching, and 0.5s after stopping movement, the indicator is yellow
    - When prone, the indicator is green
  - When ***IN TWO*** stealth triggers:
    - Standing still, the indicator is blue
    - Moving while standing, and 0.5s after stopping movement, the indicator is yellow
    - Crouching while still, the indicator is green
    - Moving while crouching, and 0.5s after stopping movement, the indicator is blue
    - When prone, the indicator is green
- ***Any source files*** you modified to implement the stealth indicator logic. You don't need to submit any screenshots of blueprints, we just want the .h and .cpp files you changed.

Please double-check that you submitted the required files!

## Grading

The points breakdown is as follows:

### Part 1 (25 points)

- 10 points for basic changes to state machine
- 5 points for hooking up X to toggle on/off
- 5 points for making sure the player can't move when prone
- 5 points for making sure the animations don't pop when switching between standing/prone

### Part 2 (35 points)

* 15 points for correct StealthBoxComponent.h/cpp code
* 10 points for tracking number of stealth boxes active
* 10 points for StealthTrigger_BP functioning correctly

### Part 3 (35 points)

- 15 points for setting up changes to HUD widget to show and update the indicator
- 20 points for calculating the correct threat level

### Code Quality (5 points)

* While you won't lose points for nitpicky issues, if your code additions for the midterm flagrantly violate the Unreal Style Guide, we reserve the right to deduct these points.

Remember that the deadline is strictly enforced, and there are no resubmissions once the deadline is over. There will only be regrading in the event of a grading error.
