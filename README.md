![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/Maltodaxtrin/Portraits-for-Cowled-Menace?include_prereleases)
![Platform](https://img.shields.io/static/v1?label=platform&message=windows%20%7C%20macos%20%7C%20linux&color=informational)
![License](https://img.shields.io/static/v1?label=license&message=CC-BY-NC-4.0&color=green)

# DaxTweaks

Various minor tweaks I made for my game. See if they can be of use to you as well! Some of these tweaks were included in my mod Cowled Menace before, but were moved here for simplicity's sake instead. Although they were optional, a quest expansion mod bundling in tweaks as well wasn't ideal and not quite what people were expecting of a quest expansion mod.

## Content Index

- [Compatibility](#compatibility)
- [Installation](#installation)
- [Components](#components)
- [Tools Used in Creation](#tools-used-in-creation)
- [Copyright and Legal Information](#copyright-and-legal-information)
- [Version History](#version-history)

## Compatibility

Compatibility depends on the component, see each component below for more information.

## Installation

**Windows** </br> DaxTweaks is packaged and installed with WeiDU and is distributed as a self-extracting archive. To install, simply double-click the archive and follow the instructions on screen.

Alternatively the files can be extracted from the archive using WinRAR. If properly extracted, you should have a "**DaxTweaks**" folder and **setup-DaxTweaks.exe** in your BG2 folder. To install, double-click **setup-DaxTweaks.exe** and follow the instructions on screen.

Please run **setup-DaxTweaks.exe** in your BG2 folder to reinstall, uninstall, or otherwise change components.

## Components

**Properly change Imoen Avatar to Mage in BG2 - CDTweaks**

The Tweaks Anthology component that changes Imoen's Avatar to mage only changes her avatar for playable versions of Imoen. This component also replaces the missing 14 instances of Imoen used in cutscenes and dreams throughout the game with a mage avatar. For consistency purposes.

Compatibility: This component does not account for new versions of Imoen added by other mods.

**Replace the generic Lich in the "Spawn Undead" script (Install after SCS/Tactics if present)**

There are too many liches in this game in my opinion, and their overuse degrades the impact of their presence. Also, my mod Cowled Menace adds 2 liches due to the vastly increased involvement of the Twisted Rune (in sensible locations, to my defense; They are a cabal of liches after all...), so I felt I needed to reduce their numbers elsewhere to compensate. Also, lore-wise, liches shouldn't be as common, especially not in random places. Going from 12 to 8 liches in SoA in total I think is a nice improvement on vanilla worth installing this component for, and even down to 7 with the next component. Or in total with Cowled Menace installed: 9 liches, down from 14. Still too many, but more palatable.

What does this component do? Simple. It dynamically removes the 4 generic liches in the level-dependent undead spawn: If you're high level enough, 2 of them spawn in Temple Ruins (Umar Hills), 1 in Ghoul Town (Unseeing Eye), and 1 in Spellhold (Bodhi's Hunt Level 2), replacing them with one of two options: 

1. Replace with a custom and comparatively easier spellcasting Ancient Mummy
2. Replace with an Ancient Vampire (vanilla enemy)

The mummy is one that I created. More on that mummy in the component directly below. This way you can keep the hardest level-dependent spawns active in your game (for instance, with SCS you might want to always have the hardest spawns on for challenge purposes), except without any liches being present as they are so far and above the enemies of the other spawns in terms of challenge level, and them being there in the first place makes little sense in-universe.

Compatibility: This edit is done in an incredibly compatibility-friendly way (targeted REPLACE_TEXTUALLY on SPWNDEAD.BCS) and is compatible with SCS and Tactics in the sense that it will keep all of their changes, except the liches will be gone. It should be installed after SCS and Tactics Remix, otherwise they will undo my change since they replace the "SPWNDEAD" script entirely, deleting the changes this component makes. Note that for Tactics Remix, it's unintuitively the "Improved Undead" component that replaces the "SPWNDEAD" script, not the "Always Toughest Random Spawns in Dungeons" one, while for SCS it is the "Tie difficulty of level-dependent monster groupings to the difficulty slider" component that does it. Regardless, my component will work if installed after them, without breaking anything they have implemented. Obviously, this component works on a vanilla game, not just on SCS/Tactics installs.

**Replace the Lich in the City Gates Inn**

In very much the same vein as the component above, the goal of this component is to further reduce the number of liches in the game. Also, a lich was just chillin' there, waiting... really? What I offer instead is a dude being mummified and entombed there (perhaps against his will), which makes (somewhat) more sense in-universe due to the fact that mummies are a lot more common. Not that it makes any real sense to have this tomb there in the first place in the vanilla game, but we make do with what we have. 

Like the previous component, the options are either a custom spellcasting mummy (exactly the same as above) or a Greater Mummy (vanilla enemy)

Compatibility: Although the edit is done in the most compatibility-friendly way possible, it remains that SCS will not update the combat script of this custom mummy, so it won't benefit from the added difficulty of SCS. I have given the mummy a reasonably-competent AI that should make it at least a passable challenge. For a mummy anyway. Definitely don't expect a Lich-level challenge, but it could still surprise you if caught unprepared. 

I have accounted for Item Randomiser, so if it's installed, the Rod of Terror belonging to the Lich in the vanilla game won't be re-added back. The chest in the area is unaffected and will work fine with the randomisation. As this is a tweak mod, you should install Item Randomiser first before this mod. Any other mod that somehow requires the City Gates Inn Lich specifically for something precise, or adds items to this Lich, will be incompatible by virtue of these items being distributed to a creature that is no longer in the game. Obviously this component will break any mod that requires it to be, well, there. It's no longer there.

**Charisma Affects Store Prices More (klatu revised)**

This component widens the effect charisma has on store prices. So you'll start to see a (minimal, 2% discount) impact at 13 charisma, up to a massive 50% discount at 25 charisma. No change at 18 charisma.

Vanilla Charisma

```
  1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16  17  18  19  20  21  22  23  24  25
1 0 0 0 0 0 0 0 0 0 0  0  0  0  0  0  -5 -10 -15 -20 -25 -25 -25 -25 -25 -25
```

Modded Charisma

```
  1 2 3 4 5 6 7 8 9 10 11 12 13 14 15  16  17  18  19  20  21  22  23  24  25
1 0 0 0 0 0 0 0 0 0 0  0  0  -2 -4 -7 -10 -12 -15 -20 -25 -30 -35 -40 -45 -50
```

In contrast to vanilla, you get some small results earlier, and get rewarded for increasing charisma beyond 20. Hopefully this component makes charisma a stat worth considering sometimes instead of a pure dump stat. Sure, the ring can fix it for you by setting it at 18, but having 25 charisma (if you somehow manage to make it there), offers a massive difference in price now, so it might be worth checking out ways to increase it, instead of ignoring it entirely like in the base game. 

klatu made a similar tweak, but unfortunately it actually nerfs the impact of charisma from 19 to 21 compared to vanilla, which is most likely unintended as people don't install this type of component expecting a nerf to the effect of their charisma on store prices. Increasing charisma beyond 18 should see more benefits, not less.

Compatibility: Any other mod that changes how charisma affects store prices will be incompatible.

**Spellcasters cast Cacofiend and Gate far from themselves, so they don't end up fighting their own summoned demon (Useless with SCS)**

This component is aimed at vanilla (non-SCS) installs and is quite simple: casters able to cast Cacofiend and Gate (both Cleric and Wizard versions) will now do so far from themselves to reduce the chance that the demon will be their next target (truly genius AI). Summon Fiend would have been patched as well... if any vanilla spellcasters actually used it in combat (none do).

Compatibility: Shouldn't have any compatibility issues as it's very precise REPLACE_TEXTUALLY editing that I've done, compatibility-friendly to the max. As outlined above, this component is completely and utterly useless if you plan on installing SCS down the line. If you have already installed SCS Smarter Mages, this component will be skipped. Not sure if Tactics Remix Smarter Mages also makes it useless, but most likely it does as well.

**Use pre-EE Spell Deflection Globe** *(Requires EE)*

This component has 2 options to choose from: Either the old pre-EE globe is added only to Spell Trap and the Staff of the Magi (recommended, to help distinguish it since it's so powerful), or to all spells using that effect: Minor Spell Deflection, Spell Deflection, Spell Trap, etc., and their item versions.

![Visuals screenshot](https://media.invisioncic.com/u284679/monthly_2026_05/image.png.f7e920de1eb90ad427bf94dcdd16a37c.png)

As of May 5th 2026 (v2.0.1 of Cowled Menace), this component works as expected. If you installed it before that along with Cowled Menace, it is probably not working as intended (the effect doesn't expire). Sorry about that.

## Thanks and Acknowledgements

Special Thanks to Mike1072, Argent77, demivrgvs, Roxanne, kreso, klatu, DavidW, CamDawg, Nythrun & Miloch (area patching) and every helpful fellow on gibberlings3 forums!

### Tools Used in Creation

- [WeiDU](https://weidu.org/) by Wes Weimer and the bigg
- [DLTCEP](https://www.gibberlings3.net/files/file/900-dltcep/) by Avenger
- [Near Infinity](https://github.com/Argent77/NearInfinity/releases) by Jon Olav Hauglid and devSin, maintained by Argent77
- [IESDP](https://gibberlings3.github.io/iesdp/) maintained by igi

## Copyright and Legal Information

Copyright © 2026 Maltodaxtrin/Daxtreme

You are allowed to submit [maintenance updates](MAINTENANCE-NOTICE.md) for this mod. This mod is additionally licensed under [CC-BY-NC-4.0](https://creativecommons.org/licenses/by-nc/4.0/).

This Modification is unofficial Fan Content permitted under the Fan Content Policy. Not approved/endorsed by Wizards. Portions of the materials used are property of Wizards of the Coast. ©Wizards of the Coast LLC. This mod is also not developed, supported, or endorsed by BioWare, Black Isle Studios, Interplay Entertainment Corp., Overhaul Games or Beamdog. All other trademarks and copyrights are property of their respective owners.

## Version History

1.0 -- First release