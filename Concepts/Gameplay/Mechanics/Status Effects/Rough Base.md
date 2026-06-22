The way stacks work is that the „applied stacks“ are applied instantly, and then slowly get ticked off. So, when i say tower applies 3 stacks of scorch, affected enemies get 3 stacks of scorch applied to them, and after 1 second the first stack depletes and deals damage to the enemy.

## Scorch

- Deals x amount of damage per consumed stack
- Consumes 1.5 stack/s (point is it should be faster than venom)
- Max 10

## Venom

- Deals x amount of damage per consumed stack
- Consumes 1 stack/s
- Max 10

## Freeze

- Slows down firerate/walkspeed by x% per stack
- Consumes 1 stack/s
- Max 10 (100% freeze)

## Arc

- Stuns while stacks are applied (stun stops aprubtly once all stacks are depleted)
- Consumes 3 stacks/s

## Nanite Corrosion

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