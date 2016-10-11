Action Tutorial:
http://joshualouderback.com/ActionFoundation/

Brief Overview:
# Action Managers

There are two Action managers sequences and groups. At the root of every Action is a sequence, meaning
whenever you want to play an Action it must be within a sequence. 

## What is a sequence?
It is simply a "horizontal list" of Actions, where they are completed in order and only runs one at a time.
By horizontal list I mean the flow of logic is from left to right.

Example:
Walk To Light Switch -> Turn Light Switch On -> Walk Away

In this sequence it will not do the "Turn Light Switch On" Action until the "Walk To Light Switch" Action 
is complete. Same goes for the "Walk Away" Action, it won't trigger until the light switch is turned on. 

## What is a group?
Just like a sequence, it is a list of Actions and completed in order, but this time it is represented 
with a "vertical list" and all the Actions run simultaneously. A sequence doesn't continue until all Actions
in a group are completed. By a vertical list, I mean the flow of logic is from top to bottom.

Example:
Walk To Light Switch         -> Turn Light Switch On -> Walk Away
Randomly Look Around In Fear
Randomly Shriek In Fear Once

Using the example sequence before, everything is the same instead the first Action has other Actions underneath of it.
What happens here is while they NPC walks towards the light, it will also randomly look around in fear and will eventually
shriek in fear before we reach the light switch. The NPC will move before it looks and looks before it shrieks, so if
you have any order dependencies groups will maintain it. Also when an Action in a group is completed it is removed, 
therefore if the NPC shrieks at the beginning, for the rest of the way it will never call that Action again. So 
all your Actions in a group don't have to complete at the same time.

#Actions
* ActionCall     -> Function Call (One Frame Logic)
* ActionRoutine  -> Coroutine Call (Multiple Frame Logic)
* ActionDelay    -> Wait For X Seconds
* ActionProperty -> Lerp Of A Value 
