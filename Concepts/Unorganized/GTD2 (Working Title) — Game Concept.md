## Game Overview & Worldbuilding

- **Working title:** GTD2 _(pending a new name that fits the narrative)_
- **Setting:** A well-functioning, rapidly advancing utopian society (not traditional post-apocalyptic).
- **The player:** An official Commander acting as part detective, part dispatcher—investigates threats and strategically deploys towers/units.
- **Lore (Nanites):** The world runs on Nanites—microscopic, self-replicating machines that can build cities in minutes and mimic any material. Because they can be weaponized or used to create infinite illegal substances, they’re heavily regulated by the government. Standard high-tech Nanites take about a month to clone.

---

## Game Structure & Progression Loop

- **Gacha-style progression:** Two distinct types of content:
    - **Main story campaign:** Longer quests with heavy narrative focus and high rewards. Level-locked to prevent players from rushing.
    - **Side quests & repeatable modes:** Shorter, replayable loops that players grind to level up and unlock the next main-story thresholds.

### Tower & Skin Systems (Proposal)

- **Goal:** Keep progression exciting while avoiding power creep; monetize primarily through cosmetics.

#### Tower acquisition options

- **Option A — Classic unlocks:** Unlock towers via currencies, quests, and event participation.

#### Skins (monetization without gameplay imbalance)

- **Achievement skins:** Earned by milestones/feats.
- **Quest skins:** Earned through specific missions/questlines.
- **RNG skins:** A portion comes from RNG (e.g., wheel-of-luck style) to support profitability.

---

## Core Gameplay & Backend Mechanics

- **Tower health system:** Towers aren’t invincible—each has a health pool and can be damaged or destroyed by enemy attacks, abilities, or rival turrets. (Either that or a lot of stunning and stuff…)
- **enemy / tower tags:** Entities (enemies, units, towers) can switch allegiances on the fly. Example: a boss can be re-tagged as an “ally” so player towers stop targeting them during a surrender sequence.
- **Game speed:** A system to drop the game’s timescale to zero, freezing the world mid-combat so characters can deliver important dialogue without the player getting overwhelmed—or the boss getting killed mid-sentence (maybe epic ability moment pause climax OMG).

---

## Enemy Design & Nanite Behaviors

The primary antagonists are factions illegally producing or modifying Nanites.

- **Standard illegal Nanites:** Variants such as fire-only susceptibility, or hybrid enemies with stunning/disabling abilities.
- **“Unstable” Nanites:** Heavily modified bootlegs that replicate in **1 minute** instead of a month.
    - **Visual engine feature:** Models are a jumble of parts/colors that randomly snap to different sizes and colors every minute when they attempt to replicate. Spawning them sequentially creates a wave-wide domino effect of morphing enemies.
    - **Mechanical RNG effect:** Upon taking damage _(or every minute)_, they trigger random effects:
        - Massive healing that severely slows movement
        - Minor healing that causes erratic/random attacking
        - Increased damage vulnerability
        - Self-stunning
