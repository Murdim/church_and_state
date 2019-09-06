# Church and State: Lay and Pluralist Religions

A game mod for Crusader Kings II. Only includes text files; the full version must be downloaded on the [Steam Workshop][Steam]. Feel free to [contribute](#modding)!

[Steam]: https://steamcommunity.com/sharedfiles/filedetails/?id=1850863172


## Features

For a more general overview, check the mod description on [Steam], which can also be found in the file [workshop.md](workshop.md).

### Non-Clerical Doctrine

The following religions are [flagged as clergyless](common/scripted_effects/CNS_maintenance_effects.txt) at the beginning of a campaign, unless religious features have been randomized: Lollard, Waldensian, Paulician, Jewish and Karaite. The Paulician Patriarchate is also destroyed and disabled under these same conditions; this is a separate effect.

Non-clericalism affects religious heads in the following ways:

 - Reformed with Non-Clerical: if combined with Autocephalous, "true" RH title is disabled. No change otherwise.
 - Randomized with Non-Clerical: RH title is destroyed and disabled if held by a theocracy. No change otherwise.
 - Tagged as clergyless: no change, the RH title must be destroyed and/or disabled manually if needed.

### Non-Clerical Governments

These governments use a separate compatibility mechanic from vanilla, defined with [scripted triggers](common/scripted_triggers/CNS_government_opinion_triggers.txt) and refreshed every 30 days. They are accepted by non-Order feudal vassals, and tribal vassals of the same culture, but not theocracies.

Infidel taxes prevent Cosmopolitan religions from using Secular (instead of Pious) Feudal. They still have access to the "true" Pluralist governments.

Baron-tier temple holders not from a significant dynasty (Count+ or patrician head) are not treated as "proper" feudal lords (yet). They actually use a separate version of Pious Feudal, made to look almost identical to the playable one:

 - Uses special titles, like Pastor or Rabbi.
 - Open Elective succession, tweaked to only include scripturally learned courtiers. Gender law based on religion.
 - Randomly generated rulers are lowborn, with the Guardian of Scripture trait if available.

### Pluralist Governments

Pluralist Feudal uses the same compatibility mechanic as Pious and Secular Feudal, with the same rules as vanilla Feudal.

The additional "Imperial" features are: no wrong government penalty, can hold Cities, free vassal retraction, +10 vassal limit, +15 court size (up from +10), +1 piety/month, can change capital every 200 months (down from 600).

Adopting Pluralist Imperialism is fairly easy if the primary title has been Pluralist Imperial within the past 100 years. Otherwise, it has both administrative (tied to Prestige) and religious (tied to Piety) prerequisites.

It can also be obtained by inheritance; if the heir is not already Cosmopolitan, they will be asked to convert.

In all three cases, ALL held empires will be flagged as pluralist, as well as any obtained after that.

The Roman, Persian and Indian empires are flagged as "historically pluralist" at the beginning of a campaign, making the decision somewhat easier to take with them as primary title.

### Non-Clerical Advisor

Requires Conclave and Holy Fury (for the doctrine), available to Duke+ feudal or republican rulers. This bonus advisor is intended to compensate for the inability to keep a powerful vassal placated as Court Chaplain. As such, it does not depend on the ruler himself using a non-clerical government type.

To be considered "authoritative", a character must be an adult of the right sex and rule a theocracy OR have a Learning-based education or lifestyle or Hafiz/Guardian. Ascetics and "special spirituals" bypass these restrictions.

 - Delegate (Cosmopolitan): authoritative and/or landed adult + different religion. Can be recruited by decision. TODO
 - Peacemaker (Peaceful): authoritative + same religion. TODO
 - Propagandist (Warmongering or Proselytizing): authoritative + same religion. TODO
 - Censor (Unyielding or Dogmatic): authoritative + same religion. TODO

### Guardians of Scripture

If the feature is active, in addition to the standard +5 Muslim opinion, the Hafiz/Guardian trait also grants +2 Learning, +5 same religion opinion, and:

 - For Muslims, +0.5 piety/month
 - For Christians and Israelites, +5 religion group opinion
 - For others, including all random-named religions, +10 religion opinion (up frop +5)

All versions use the vanilla Hafiz trait. The new effects are implemented with hidden modifiers.

The trait and modifiers are removed and re-applied on title gain and game load, when the game actually checks for the trait's "potential" trigger and remove it from non-Muslims. There might be other occasions where it does so; please warn me if you notice someone losing the trait for no apparent reason (a reload SHOULD fix it).


## Compatibility

This mod was developed for Crusader Kings 2 v3.2.1, and should remain compatible with future versions.

It should also be compatible with most other mods, with the following caveats:

 - Mods that rely on landed priests may work poorly with Non-Clerical religions. Follow the instructions in [this file](common/scripted_triggers/CNS_religion_feature_triggers.txt) to avoid incompatible doctrine choices.
 - New government types may conflict with those from this mod. This should be fixed with a compatibility patch to the government maintenance [events](events/CNS_maintenance_events) and [effects](common/scripted_effects/CNS_maintenance_effects).

### CK2 Overrides

* `localisation/v2_00b.csv` + `v2_15.csv` (partial): Israelite theocratic titles.
* `localisation/v1_06.csv` + `v2_30.csv` (partial): Hafiz trait name and description.

### Notable Dependencies

* `common/scripted_triggers/00_scripted_triggers.txt`


## Modding

The source code of this mod is publicly available for anyone to fork, reuse, or take inspiration from it. Bug reports, suggestions and pull requests are all very much welcome.

The playable version also includes image files, some of which have been derived from artwork found in the base game. In order to run the mod from this repository, you will need to extract the "gfx" directory from the Steam version, or else use some kind of placeholder.

Finally, do not forget to copy the .mod file to the root of your "mod" directory.
