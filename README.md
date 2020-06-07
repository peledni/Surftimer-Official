# Surftimer-olokos for CS:GO

<sup>I have renamed the repository to Surftimer-olokos just to make it obvious, that we're entering a new chapter in CS:GO surf community, a milestone.</sup>


## Project Goals

*As you probably all know there are quite some bugs in all open-source versions of cksurf or surftimer.*

*Our main goal with this project to have a bug-free, properly optimized surf timer that would work as we all expect it to, across all configurations.*

*Because of this, we will be putting new features and additions on the side, as they can potentially introduce new, unknown issues and there's plenty of those already.*

#### Does it mean this version is buggy?

>Yes, but not any more than other projects currently and for past years.

**Pull requests and any contributions are welcome and encouraged!**
**Our [discord](https://discord.gg/5dsFHeR) is a good place for dev talk and help!**

## Issue Rules

**We are only helping with timer related bugs, any host related issue will be closed immediately.**

**If any of the rules listed below are not followed, you must expect the issue to be closed immediately.**

- Prerequisites:
	- Ensure your timer version is up to date with the [latest release](https://github.com/olokos/Surftimer-olokos/releases/latest)
	- [SourceMod](https://www.sourcemod.net/downloads.php?branch=stable) and [Metamod](https://www.sourcemm.net/downloads.php/?branch=stable) are up to date (support only for latest stable)
	- Ensure [includes](https://github.com/olokos/Surftimer-olokos#Optional) for compilation are up to date
	- Stock timer without any additional changes
- Follow the template
	- That means you won't delete any pre-entered questions!
- Give clear and as precise information as you can
	- If applicable include related logs / configs (posted to [pastebin](https://pastebin.com/))
- Don't edit issues 
	- Always write a new comment below!
	
	
## Installation

#### Requirements

* [SourceMod 1.10](https://www.sourcemod.net/downloads.php?branch=stable)
* [Metamod 1.10](https://www.sourcemm.net/downloads.php/?branch=stable)
* [DHooks](https://forums.alliedmods.net/showpost.php?p=2588686&postcount=589)
* [SMJansson](https://github.com/JoinedSenses/SMJansson)
* [SteamWorks](https://forums.alliedmods.net/showthread.php?t=229556)
* [Sourcemod-Discord API](https://github.com/Deathknife/sourcemod-discord)
* [Precompiled Surftimer + Discord-API](https://github.com/olokos/Surftimer-olokos/releases/latest)
* A MySQL Database (MySQL 5.7 / 8+ / MariaDB supported)

#### Optional

* [SMLib](https://github.com/bcserv/smlib/tree/transitional_syntax)
* [ColorLib](https://github.com/c0rp3n/colorlib-sm/blob/master/addons/sourcemod/scripting/include/colorlib.inc) (colorlib.inc only)
* [AutoExecConfig](https://github.com/Impact123/AutoExecConfig/)
* [Cleaner](https://github.com/Accelerator74/Cleaner)
* [Stripper](https://forums.alliedmods.net/showthread.php?t=39439) (recommended filter included)

*(All optional are required to compile it manually!)*

#### Installation guide

*   Download [Requirements](https://github.com/olokos/Surftimer-olokos#Requirements) & [Optional](https://github.com/olokos/Surftimer-olokos#Optional)
*   Add a entry in `csgo/addons/sourcemod/configs/databases.cfg` called `surftimer` (create a new mysql user)
*   (Opt.) Run `csgo/scripts/mysql-files/ck_maptier.sql` & `csgo/scripts/mysql-files/ck_zones.sql` in your surftimer database (if you want to use the premade zones & maptiers)
*   Move unwanted plugins in `csgo/addons/sourcemod/plugins` to `csgo/addons/sourcemod/plugins/disabled`
*   Upload all files into your `csgo` folder
*   (If [fastDL](https://www.youtube.com/watch?v=a77mZKlDoic):) Upload `csgo/sound` folder
*   Edit .cfg in `csgo/addons/sourcemod/configs/surftimer` & `csgo/addons/sourcemod/configs/discord.cfg`
*   Configure a [mapgroup](https://beta.configcreator.com/create/csgo/gamemodes_server.txt) OR Set workshop [collection](https://www.bisecthosting.com/clients/knowledgebase/94/How-to-create-a-Steam-Workshop-collection.html) (inc. all [start parameters](https://developer.valvesoftware.com/wiki/Counter-Strike:_Global_Offensive_Dedicated_Servers#Starting_the_Server))
*   Update `csgo/mapcycle.txt` & `csgo/maplist.txt` & `csgo/cfg/server.cfg`
*   Start the server
*   Stop the server
*   Edit the autogenerated `csgo/cfg/sourcemod/surftimer.cfg` (+ maybe some other .cfg from other plugins)
*   Check `csgo/addons/sourcemod/logs` for issues and fix them
*   Start the server
*   Connect and [zone](https://youtu.be/YIpKIAqtDp4) the maps (Use !hookzone first) & set map settings
*   Continue this for all maps
*   Done !

#### Notes regarding Discord

If you choose to use the various discord features, please make sure of the followings:

*   If you setup a mentions other that @here or @everyone, you use the ID of the role, and not just @rolename. To get the id of the role, you have to type "\@rolename" in a discord channel and copy the output.
*   If you want to use custom thumbnails/images, make sure they have the exact same name as the map in question, and that they are in the .jpg format. Furthermore, don't forget to add "/" at the end of the url, without the "".
*   To edit the color of the embeds, use the hexadecimal color format, you can generate it at [this adress](https://www.color-hex.com/color-palette/25362).
	
## Upgrading

#### Upgrade from pre v.285 checkpoints

*   Follow [installation](https://github.com/olokos/Surftimer-olokos#Installation)
*   Run `CSGOFOLDER/scripts/mysql-files/checkpoints-upgrade.sql` in your surftimer database

#### Upgrade from SurfTimer ([fluffys](https://github.com/fluffyst/Surftimer))

*   Run the upgrade script `CSGOFOLDER/scripts/upgrade_scripts/upgrade-fluffy.sh` (edit the defined path)
*   Follow [installation](https://github.com/olokos/Surftimer-olokos#Installation)
*   Edit configs (maybe c/p some rank names from old configs)
*   Run `CSGOFOLDER/scripts/mysql-files/upgrade-fluffy.sql` in your surftimer database
*   Run `CSGOFOLDER/scripts/mysql-files/checkpoints-upgrade.sql` in your surftimer database

#### Upgrade from ckSurf ([nikooo777](https://github.com/nikooo777/ckSurf))

*   Run the upgrade script `CSGOFOLDER/scripts/upgrade_scripts/upgrade-nikooo.sh` (edit the defined path)
*   Follow [installation](https://github.com/olokos/Surftimer-olokos#Installation)
*   Edit configs (maybe c/p some rank names from old configs)
*   Run `CSGOFOLDER/scripts/mysql-files/upgrade-niko.sql` in your surftimer database
*   Run `CSGOFOLDER/scripts/mysql-files/checkpoints-upgrade.sql` in your surftimer database


## Point System
<details>
  <summary>Explanation</summary> 
  
The points system has seen a massive overhaul from the original ckSurf; it is now a percentile tiered system. Points are now distributed in two ways: (1) map completion, and (2) map ranking. Map completion points will be given to all players who complete a specific and are dependent on the tier.
* Tier 1: 25
* Tier 2: 50
* Tier 3: 100
* Tier 4: 200
* Tier 5: 400
* Tier 6: 600
* Tier 7: 800
* Tier 8: 1000

Map ranking points are dependent upon the individuals ranking on the map. This is done firstly by calculation of the WR points for the map. WR points per tier are calculated as follows:
* Tier 1: WR = MAX(250, (58.5 + (1.75 * Number of Completes) / 6))
* Tier 2: WR = MAX(500, (82.15 + (2.8 * Number of Completes) / 5))
* Tier 3: WR = MAX(750, (117 + (3.5 * Number of Completes) / 4))
* Tier 4: WR = MAX(1000, (164.25 + (5.74 * Number of Completes) / 4))
* Tier 5: WR = MAX(1250, (234 + (7 * Number of Completes) / 4))
* Tier 6: WR = MAX(1500, (328 + (14 * Number of Completes) / 4))
* Tier 7: WR = MAX(1750, (420 + (21 * Number of Completes) / 4))
* Tier 8: WR = MAX(2000, (560 + (30 * Number of Completes) / 4))

Once the WR points are calculated the top 10 are points are calculated by multiplying the WR points by a factor. These factors are:
* Rank 2 = WR * 0.8
* Rank 3 = WR * 0.75
* Rank 4 = WR * 0.7
* Rank 5 = WR * 0.65
* Rank 6 = WR * 0.6
* Rank 7 = WR * 0.55
* Rank 8 = WR * 0.5
* Rank 9 = WR * 0.45
* Rank 10 = WR * 0.4

Players who are not in the top 10 but are above the 50th percentile in map ranking will be sorted into 5 groups – with each higher group giving proportionally more points. These groups and their point distribution are as follows:
* Group 1 (top 3.125%) = WR * 0.25
* Group 2 (top 6.25%) = (Group 1) / 1.5
* Group 3 (top 12.5%) = (Group 2) / 1.5
* Group 4 (top 25%) = (Group 3) / 1.5
* Group 5 (top 50%) = (Group 4) / 1.5

Take surf_aircontrol_nbv for example: (You can use sm_mi to see this menu)
<img src="http://puu.sh/ykaR8/7520a6b0d6.jpg" width="372" height="469" />

###### Credit to NDiamond for theory crafting this point system, I just implemented his idea
  
</details>


## Credits

*   [Jonitaikaponi](https://github.com/jonitaikaponi) - Original ckSurf creator
*   [sneaK](https://github.com/sneak-it)
*   [nikooo777](https://github.com/nikooo777)
*   [fluffys](https://github.com/fluffyst)
*   [Jakeey802](https://github.com/Jakeey802)
*   Grandpa Goose
*   [Ace](https://github.com/13ace37) [xace.ch](https://xace.ch)
*   [olokos](https://github.com/olokos) [Steam](https://steamcommunity.com/id/olokos/) [My server (running dev version)](https://kiepownica.pl/)
*   And many, many more who contributed to the project!
