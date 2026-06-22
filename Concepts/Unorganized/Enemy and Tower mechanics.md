Towers and enemies have health. When health is depleted, they die. Also, they should have a region around them that doesnt allow placing, like tds or redux

## Teams and Tags

Enemies and Towers can attack eachother, so enemies can attack towers, towers can attack towers, enemies can attack enemies…. the only real thing keeping them from killing each other is their “team”, or their “tag”… whatver

Towers have the “tower” tag, so they wont attack each other unless **changed**. (yes, dynamically changing), enemies have the “enemy” tag. Towers will attack enemies… etc.

TLDR; Tags define how one tag behaves to another. So enemies and towers are hostile towards eachother.

Later on, we can also add like “hidden”, which is ignored by all, or like “alien” (😭) which means that every team attacks each other. We can make some really chaotic and fun stuff

also **vocab check:**

- Tower = Tower Team
- Enemy = Enemy Team
- Unit = Either team, its valid for both

## Placing

I want alot of spawnable “freedom”? You know what i mean? so i as the dev can decide when where a tower or enemy should spawn. For example in the Story mission 2, where the turrets are, i want them to be placed as towers on game start.

Towers should also be able to “place” other towers (ex: Engineer Monkey BTD6), which then should be able to do stuff. Same with spawner towers obv. (ex. Magic monkey btd doesnt spawn them at the end of the road, but rather anywhere within its range. i also want to be able to set on which alpha of the road my entities spawn). **IMPORTANT: we NEED OnSpawn and OnDeath for both towers and enemies, both for visuals and for mechanics (ex: Engineer Monkey btd plasma turret explosion on death)**

I also want to add a tower which works similarly to the original Omniocolus tower. Remember that? The one that shields towers from entity abilities? we could have it work by summoning a shield (which would be a tower on the backend maybe) which gets attacked instead of the towers within. I have no clue how you will do that kio but i wish you much fun.

## Abilities

Also having passive or active abilities on towers in general would be cool. Stuff like commander buff tds, the passive dj buff obviously but maybe also a healer tower not attacking the enemies, but the towers (so like target mode first would get the closest towers, last the most far away one, weakest the one lowest on health and strongest the one highest on health). The omnioculus like tower ability could also be passive (casts itself every x seconds) or active (player can activate after a cooldown to shield towers in its range). I think though that if there are abilities like the omnioculus ability, that we should also be able to display the ability range with the tower range. Like in general, maybe having each attack have a set of prequisites such as which range from the tower to use, what faction to target and what to do with that target would be useful (yes towers with multiple ranges).

AOE Is kind of difficult, since balancing would be kind of hard without making them low on damage, but then again aoe is just fun. If we do decide to add aoe, id like: Circle AOE (ex. bombs, explosions), Range AOE (percentage of range, example: stomp), Cone aoe (ex. shotguns), Lane aoe (so like a straight line going from the tower to the end of the range. example: a rush attack, like a bull).

Damage **falloff** on range would be really cool aswell, so like if there is a falloff of 0.2, it means that the attack is 20% weaker on the edge of the range (scaling lineraly). Different types of **DOT** such as Fire, Poison, Corrosion and whatever we can think of would be cool too. Freezing (making slower or making the enemy stop moving/tower stop attacking) and Frostbite DOT (making slower and DOT, again i know this can be simplified on the backend to just be both DOT and freeze) would be cool too.

would be really cool if we could apply stuff like burn to towers aswell! so like a enemy can spit fire and its weaker the farther away a tower is from it (DOT and Falloff on a enemy!!)

Again i want to be able to put these whenever i want. so maybe having a effect by default for the entire game or just on some waves or like only for one team would be cool. Like having a underwater level where only the nanite towers will “corrode” or something like that.

## Summoners

Pretty self explanatory, however i wanna make clear that i want spawns to also be able to switch teams. so they should be enemies on team towers, attacking enemies, but when for example a ability triggers from an enemy or like its a “curse” (oma 2 heh) that they become enemies attacking your towers. Also, ranged and AOE attacks should be possible with spawns (would be cool if DOT too heh… and randomized spawns!!)

## Buffs, debuffs…

i want most if not all stats buffable. Since im not diamond, we dont need a super configuration for this, we can just have the buff system work by passing a dict with the stat and the buff/debuff to a certain amount of towers and the system just adding/removing that buff… So like i want to be able to buff cooldown, damage, health regen (which would be cool if we had self regen towers!), aoe, or even other stuff like summon health or cooldown! Again i think you can think of this waaaayyy better on backend kio, and if its not possible oh well, i can give you a list of all stats id like buffable. Obv buffs and debuffs should be easy for the player to read out and see. Also maybe being able to only buff or affect certain a “faction” (we talked about this, but basically a faction is like a type of tower or enemy, such as “nanite”, “human”, “monkey” or whatever) would be cool!

## More accurate projectiles!!

We can do either

- Compute path duration on server (lag) and send the result to the client

or

- Compute path duration and path on client and send to server (not sure how secure that is)

or

- hardcode duration on server and make client come up with some bs way to make it look natural and not predefined

Maybe you know better solutions, but the point is that i want enemies to die when the projectile actually **hits** them, not before and not after (i mean if they had the health then obv not but ykwim!). This would make explosion vfx so much more satisfying, especially if we had OnDeath effects for the enemies! Obviously the same is for enemies killing/ attacking towers.

TLDR: damage and death should be looking good with the vfx on projectile based attacks for both towers and enemies

## Overall customizability

since i am a scripter, you obviously dont have to make everything neatly and nicely into a little config. If you want (or if you think its easier), having a main module which defines each and every attack and stat as a function and then making each tower/enemy need its own little module which returns its actual stats and its functionality as a attack function is fine. I have no issue with defining a tower as:

Attack = function(target)

task.wait(path_duration)

Mechanics.ApplyDamage(target, 30)

Mechanics.ApplyDOT(target, 2, 0.2, 10) — 2 damage every 0.2 seconds for 10 ticks or sum

end)

instead of

Tower = {

Damage = 3,

DOT_Damage = 2,

DOT_Tick = 0.2,

DOT_Count = 10,

}

or whatever… you know what i mean!

## Quick notice on numbers

i love funny numbers just as much as the next guy, but i think we should bring our number scaling down a bit, maybe similar to tds or btd (allthough BTD numbers escalate quickly)

## Enemies and stuff

wow alot of talk about towers, but what about enemies? I want enemies to be able to have:

- immunities (scalable in %, so takes x% less damage from y)
    - Fire
    - Ice
    - Electricity
    - Poison
    - Nanites
    - other stuff but yeah you get the gist
- Shield HP
    - Hp that is added on top of normal HP and that has to be broken in order to deal damage to the normal HP. Maybe adding this for towers too isnt a bad idea, would make the whole ominoculus like tower easier to maek….
    - Takes x% more damage from attacks that supports it!
- Summons
    - On death (can be random)
    - in intervalls
    - When a certain effect is applied (for example spawns small nanite units when attacked by a nanite attack (turns the nanites it got attacked with… evil?))
- Side swithcing
    - being able to take control of a certain type of towers in a set radius for x amount of time… aka making them into the enemy team
- Basic abilities
    - same as towers, should be able to perform the same kind of aoe, dot and other kinds of attacks (or supports! shielding/healing enemies nearby would be really cool!) on interval
    - should also be able to switch stats and abilities when below certain health (so like getting faster when low and being able to stun towers while it wasnt able to before, or losing the ability to do so!)

yap yap yap basically towers and enemies should function really similarly. Towers should also be able to gain immunites (and be impacted by the elemental effects for example)

## Elemental reactions

wow thats really juicy and im excited about that one.

basically, even though a enemy or tower can be immune to one element, it will still get a “stack” of that element applied on attack, and when a stack of another element is applied onto it, and the other element has a elemental reaction with the first element, the **reaction** will still have a effect on the enemy/tower.

This is again to debate how we should apply DOT/elementals, if it should be that for examples 10 stacks of burn means that there is damage applied every x seconds (removing a stack) until there are 0 stacks or if it should be 0 stacks with 10 stacks of burn building up, dealing damage with each additional stack. (maybe this could be scalable damage too)

before i explain how reactions should work, here is my element and reaction list so far (names up for change obv)

- Scorch (fire) — x amount of damage per stack, 1 stack per second
    - if we decide stacks should build up, the damage increases with each stack
        - x damage on stack 1, x + y damage on stack 2, x + 2y damage on stack 3 etc.
    - if we decide stacks should build down, the damage decreases with each stack
        - x damage on stack 1, x - y damage on stack 2, x - 2y damage on stack 3 etc.
- Venom (poison) — x amount of constant damage per stack, 1 stack per second
    - x damage on every stack
        - x damage on stack 1, x damage on stack 2, x damage on stack 3…
- Frosted (ice) — slows down firerate/walkspeed by x% per stack, 1 stack per second
    - if we decide stacks should buid up, x increases linearly (up to 100%)
    - If we decide stacks should build down, x decreases linearly (down to 0%)
- Shock (Electicity) — Stuns for x seconds and applies y damage based on stacks, instant stacks
    - if 3 stacks are applied, all 3 are consumed instantly and stun for 3_x seconds and deals 3_y damage
- Nanite Corrosion — x amount of constant damage per stack, getting faster with each stack
    - if we decide stacks should build up, the nanites will deal x amount of damage and get faster by z with each stack
        - so stack 1 (after 0 seconds, first stack is instant) deals x damage, stack 2 (after y seconds) deals x damage, stack 3 (after y / z²⁻¹ seconds) deals x damage, stack 4 (after y / z³⁻¹ seconds) deals x damage etc
    - If we decide stack should build down, the nanites will deal x amount of damage and get slower with each stack
        - so stack 1 (after 0 seconds, first stack is instant) deals x damage, stack 2 (after y seconds) deals x damage, stack 3 (after y * z²⁻¹ seconds) deals x damage, stack 4 (after y * z³⁻¹ seconds) deals x damage etc
    - yeah yeah i know this one is a bit more complicated

So now the reactions (WHEN i talk about stacks i mean consumable stacks, so if there are for example 4 stacks of frosted and 1 stack of scorch, thats 1 consumable stack):  
Make this into specific tower passives

- Scorch + Venom = Exothermal Reaction
    - Consumes as much stacks as possible instantly
    - makes enemy explode in a radius (scaled by stacks) and deal damage (scaled by stacks)
    - other enemies who had either Scorch or Venom will also explode, however with one stack less than the original exploded one
- Scorch + Frosted = Will o’ Wisp
    - Consumes as much stacks as possible per second
    - Slows and Deals damage (as discussed with scorch above) depending on consumable stacks
- Scorch + Shock = Arc Flash
    - Consumes as much stacks as possible instantly
    - deals damage to a set amount of enemies (in row, think electroshocker tds) based on stacks
        - We can either have it be it can hit a max of like 10 enemies at 10 stacks of shock, if they are all less than a set amount of studs apart of each other
        - Or we can make it infinite enemies but they have to be like really close to eachother
- Scorch + Nanite = Nothing… yet 🤔
- Venom + Frosted = nothing… yet 🤔
- Venom + Shock = Nerve Toxin
    - Based on stacks and health of the target, makes target join the other team for a short time
        - so ok, example: if we make it scale by 100, it means that if the enemy has 100 health left, you need at least 1 stack of nerve toxin to put them in your team for the short amount of time
            - if we do decide to have 3 teams, it would be really difficult to implement and track which stack came from where, so we should definetly look into this again…
- Venom + Nanite Corrosion = Plague
    - Basically the same as nanite corrosion, but the DAMAGE also increases/decreases with each stack
        - ex: 3 stacks of plague available, after that the unit has 2 stacks of nanite corrosion left.
        - this means that the plague will get faster/slower for 3 stacks and deal more/less damage
        - and the nanite corrosion then starts from ONE again, so it will get faster/slower for 2 stacks
- Frosted + Shock = Nothing… yet?
- Frosted + Nanite = Nothing… yet?
- Shock + Nanite = nothing…yet?

i mean i guess you get the gist, and tbh i think my explanation is kind of bad since it is really difficult… maybe we should change like all of these if they are too hard

oh yeah and on a sidenote, adding a new stack of a element after a unit already has a stack, it just gets decreased/added to the queue. However, if there is a elemental reaction (maybe we should rename this to just “reaction” or like “synergy”) already ongoing, its just going to be added as a new elemental stack. once the reaction is finished, if the stacks are there, a new one will start. this prevents super long scalable op elemental reactions

No matter how, a elemental reaction would immediately once the one element for the reaction is added be triggered and consume the **maximum amount** of stacks for the reaction.

i think its a bit hard to imagine so here is a example:

- This is bob → 👱
- bob has 14 stacks of scorch on him
- now a tower attacks and puts another 3 stacks of Frosted on him
- the moment that happens, a **reaction** occurs. Instead of being affected by both the scorch and the frosted, it now only gets affected by the resulting reaction of both, so the **maximum amount**, aka 3 gets consumed over the course of 3 seconds. Then he will just continue burning like normal
- If during these three seconds another stack of frosted were to be laid on him, he would still only burn through will o wisp for 3 stacks. the new stack would simply be added on top and wait its turn. then, after will o wisp is done, the new reaction (now with just one stack) is started.
- during the will o wisp reaction, as said, the other stacks will wait. Also for simplicity purposes, there can only be one reaction occuring at a time, maybe having them play out like a stack is a option
- another option is just removing all other stacks on/during reaction

Yeah whow that was a lot of stacking

here is a cute cat picture to calm you down

![image.png](attachment:12045572-1c51-4078-bc83-21d0db831edf:image.png)

Now lets continue

## Optimization

obviously we want allat to be optimized, id say about 4000 to 5000 should be able to exsist comfortably in my 60fps on a average machine, if you can do even better, go for it. Nothing is stopping you

## Final notes

keep in mind that these are **Concepts.**

Im not diamond, so im not going to eat your head for not liking or expressing your opinion on one of them. If you think something is too difficult to implement or should be changed, be my guest, suggest, change (pls with like a little note that you changed it), propose, discuss!

99% of ideas never make the final cut, but thats what makes projects good. Filtering out all the clutter for just the best of the best.

# New „Stacks“ (elemtns?)

- Weakness
    - Increases the damage dealt to the affected enemy/unit
    - Increases by how much its increased based on stacks
    - Stacks decay over time
    - NO ELEMENTAL REACTIONS