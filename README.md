The **-t** snippet analyzes the targets in combat to determine whether they have any status effects that should apply advantage, disadvantage, critical hits, or miss entirely. On our servers that typically run between 6-10 combatants, this snippet saves us from missed statuses frequently and seldom required bypass or counter arguments (attacker using adv or dis to cancel out automated adv or dis).

**Optional Arguments:**
**close** - Adding close to your attack informs the snippet that you are within 5'.  This is necessary for determining adv/dis on prone targets as well as critical hits on unconscious or paralyzed trgets.
**bypass** - Used to bypass the -t snippet on a single attack.

Currently Supported Status Effects:
**Prone** - **adv** with **close** argument otherwise **dis**
**Paralyzed** - **adv**, with **close** argument also **crit**
**Blinded** - **adv**
**Invisible** - **dis** (If you can see invisible, use **adv** to cancel **dis**.  If you have advantage use **adv** and **bypass**)
**Restraiend** - **adv**
**Stunned** - **adv**
**Unconscious** - **adv**, with **close** argument also **crit**
**Guiding Bolt** - first attack **adv** then effect removed
**Marked (Faerie Fire)** - **adv**
**Distracted** - **adv**
**Blurred** - **dis**
**Attacked Recklessly** - **adv**
**Dodging** - **dis**
**Sanctuary** - Reminder only
**Mirror Image** - Will force attack to **miss** if duplicate targeted (based on number of duplicates) and prompt to determine whether mirror image hit. Provides AC of duplicate.

**Limitations & Known Issues:**
You may not attribute adv/dis individually.  Ex. -t target1|adv -t target2|dis will not work.  Instead use the spell or attack on all targets which have advance and then all targets which have disadvantage.  Ex. !i cast fireball -t target1 -t target2 sadv and then !i cast fireball -i -t target3 -t target4 sdis. This generally only comes up with spell casting.  Attacks (i.e. d20 rolls) that hit multiple targets seldom need individual modifiers because -t picks up on their status.

Do not name your NPCs or PCs the same name as a snippet.  Since the targeted names are still passed, they will execute any snippets with the same name.  Ex. !a sword -t john will run the targeting assist, but will also execute any snippet named john.  We've never actually had a snippet with the same name as an creature or pc, but it is a possibility and should be avoided.

Probably other stuff.  My hope is that someone with more coding skill improves upon this.

Example: !a dag -t aur
https://cdn.discordapp.com/attachments/1079189782254600264/1080544008415232040/image.png
