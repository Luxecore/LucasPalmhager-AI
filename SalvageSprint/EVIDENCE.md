# Week 1 evidence

Keep this short. Bullet points, a small table and one diagram or code trace are enough. This is your checkpoint record, not an extra report. Replace the prompts as you work.

Name: Lucas Palmhager
Exact Unity version: 6000.3.26f1
Checkpoint commit / repository: baseline commit
Current stage and anything unfinished: stage 1

## Initial prediction

Three observations the rival needs, including one it might not have:

Seeing a pickup across a gap proves / does not prove reachability because: it depends on how the nav mesh is built in the project, if it allowes access over gaps or not.

One question about NPC behaviour: 

## One complete trace

Use one actual situation. Include the observation data, derived facts, selected task and reason, movement request/result, and how feedback affects a later decision. Identify the responsible code locations. A tiny state diagram can accompany this trace.

The AI have some issues with reachability when it has set its mind to 1 scrap and that one dissapears, for example: when the player picks up a scrap that the AI was going for it just stands there, when this happens he just stands there and keep making decisions but doesn't actually move.

Since the rival uses a linecast to find reachable scrap, so when it doesn't see a new scrap it doesn't know what to do. And even if scrap is in the range of the rival it doesn't go for them. 

This is because in PickupSensor.cs it adds candidates to the rival but it doesn't go for them because it doesnt physacly see them, and if an unvisuable scrap is closer than a visable, it just doesn't know what to do. And just stands there and keep making decisions.

## Scenario record

| Scenario | Predicted result | Observed result and short evidence / remaining issue |
|---|---|---|
| Normal loop and restart | | |
| Carrying cargo |walk back to base | prediciton was correct |
| Hidden / remembered pickup |walk to the remembered target if no other are in fov | prediciton was correct|
| Target taken |walk to second cargo in priority | prediciton was correct|
| Unreachable target |explore for new target or take the second target |prediciton was correct |
| No usable pickup |explore the map to maybe find hidden pick ups |prediciton was correct |

Supplied test result, with any added tests identified:
Live walkthrough checked by / recording link if used:

## One correction and one independent check

The original weakness and why it happened:
What I changed and why it addresses the cause:
My counterexample or experiment: prediction, observed result, and one limitation:

## Collaboration and help

People I discussed or playtested with:
Code, sources or substantive tools/AI assistance I used, and how I verified them:
If unfinished: what works, exact reproduction steps, and the help I need:
