# Frankenstein's Bride

**Frankenstein's Bride** is a SillyTavern chat completion preset built on dptgreg's FF6 Micro. It adds a trimmed version of the Internal States tracker from Freaky Frankenstein 5.6, plus world mechanics and prose rules from Aria (Realistic Frankenstein 3.0).

I cut the FF5.6 and Aria mechanics that fired Chekhov bullets every few turns to a much rarer bullet system, and I also cut the ones that kept the world from ever hurting you.

Tested on Gemini 4 and GLM 5.3. This is the first public beta, and I need other people's chats to find what breaks.

**Download:** [Latest release](https://github.com/BSPiotr/Frankensteins-Bride/releases/latest)

**Sample Images:** [Real Chat](https://imgur.com/2RXbQBM) ([Card](https://chub.ai/characters/SecretApe/lacie-stuck-in-the-endless-dimension-c0b8d903b378)) ([Custom Lorebook](https://botbooru.com/lorebook/741))

> I'm still doing a final pass on this lorebook. Until I finish, if you think a room is important and want it to stay in context, type the room code in your next reply as: "Staying in Room [Code Here] for this turn"

**Mobile Mockup:** [Mobile Mockup](https://imgur.com/4Yv0ImN)

---

## What it does

**The world moves without you.** Two fate dice roll every turn and decide how much the world intrudes, from small background texture up to news that reaches a character by phone or letter. Combat and intimacy push the odds way down, so a fight or a love scene keeps its focus. Nobody knocks on the door unless an open thread or a scheduled appointment brings them.

**Dice decide risky acts.** Skilled or contested acts roll a d20 against a DC that gets locked before the roll. A miss stays a miss, and the prose shows the outcome as events with no numbers on the page.

**Setups pay off later.** Unpaid promises, secrets and odd objects get logged with an age. After four turns a fate roll can cash one in as a small cost or a reveal. An optional **Peril** toggle adds a rare major event in calm scenes, roughly once every 133 turns.

**The tracker lives in a folded 🎲 panel** at the end of each reply. You get your own card for status and items, and every NPC in the scene gets a card with what they know and what lies they've told. NPCs act only on what they saw or heard.

| Row | What it holds |
|:---|:---|
| Threads | Loose plans someone is pursuing |
| Goals | Your long aims, counted toward 5 |
| Quests | Card or accepted tasks with steps and deadlines |
| Setups | Open promises, secrets, threats |
| World | Offscreen events that reach you as news |
| Reminders | A GM notebook for promises, names, debts and scene rules |
| Changed | Lasting changes, carried forward every turn |
| Rolls | This turn's dice, or ∅ |

**It stays cheap.** Rules use the FF6 Micro telegraphic format. A Gate prompt at the very end prints this turn's dice and the prose reminders, so everything above it stays cached. The Context Saver regex strips trackers older than the last 2 turns from the prompt, and reply length follows the moment with no fixed target. The preset is ~3.5k tokens.

**The prose rules go after AI tells.** They ban contrast framing, three-item lists, participle tails and a long list of stock phrases. This README follows the same rules, so you can judge the style right here.

---

## Setup

1. Download the JSON from the [latest release](https://github.com/BSPiotr/Frankensteins-Bride/releases/latest) and import it in the chat completion preset panel. The regex suite comes bundled inside the preset, so check the Regex extension and confirm the preset's scripts are on.
2. Each divider header in the prompt list marks a group. Turn on one toggle per group and leave the headers off.
3. Start a chat and open the 🎲 panel after the first reply.

| Group | Default |
|:---|:---|
| Prose style | Cinematic Realism |
| POV | Hybrid (3rd person world, 2nd person for your senses) |
| NSFW | Realism Gemini NSFW |
| Echo | Anti-parrot and anti-echo |
| Internal States | DND Dice, Fate Dice, Setups, State Ledger |

Optional toggles include Peril, the Thoughts row, Colored Dialogue and Pop in Graphics.

**Recommended settings:** Temp 0.8, Top P 0.95. This tends to force the model to remember the tracker correctly, but you may have good results with higher temps if you don't care as much about fidelity (looking at you GLM).

> **Card fidelity is king**, because it gives the model the most creativity. THIS MEANS THAT SLOP CARDS GET SLOP OUTPUTS. You have been warned.

---

## Gemini and other models

The preset is tuned for Gemini, though it runs token hot on output because I'm using 'old faithful' from dptgreg, so consider another model if you can't afford the token cost.

On any other model, make these changes:

- Turn off **Gemini Money Shot** and **Gemini Chad Prompt**.
- In the Regex extension, turn on both **Gem Reverse** scripts.
- Swap the Gemini NSFW toggle for **Realism Mode** or **Freaky Mode**.
- Turn on **Scent Occasions**, which stops other models from smelling everything.

---

## Bugs and feedback

Accepting feedback for changes. Please use as much detail as you can, though I don't think I can fix fidelity issues as AI is just not playing nicely sometimes.

---

## Credits

Licensed GPL-3.0, the same as the works it's built from. Fork it freely and share your changes under the same license.

- **dptgreg**: Freaky Frankenstein 6.0 Micro (the base and the FrankenWIRE format), Freaky Frankenstein 5.4 and 5.6 Internal States, and the Hapuppy thought regex.
- **kinkyalt_02**: Aria's Realistic Intelligence Assistance 1.0, for the mechanics and prose rules, the gates, the fate roll ideas, and for letting me beta test ARIA
- **Rayansaki**: Shiro's Mixtape, the visual style behind the scene bar and tracker, and also some of the prose rules
- **Ok_Strategy_2420**: TRP-AO rules, which I explored during development and left out of this build

Assembled by BSPiotr.

---

## What this Preset Isn't

No current plans for a relationship tracker module. I find them clunky and they 'force' stale turns.

---

**TL;DR:** Do you like FF? Do you like internal states but found it bloated? Do you like Chekhov's gun but hated how it ALWAYS fired a bullet and caused the scene to go awry? Do you like RF prose rules but hate how the damn thing likes to pull fire alarms and heart attacks out the butt? Do you like the GM notebook but hate how it doesn't actually keep track of a scene? Do you want a preset that can do all of that in 3.5K tokens? Boy do I have it ready for a wider view.
