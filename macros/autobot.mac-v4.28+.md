## Description

[AutoBot.mac](https://macroquest2.com/phpBB3/viewtopic.php?t=12712) by A_Druid_00 is a versatile
[macro](../documentation/macroquest2-macros.md) for automating a lot of tasks for your character in group, raid and solo
situations.

This wiki includes many updates/changes done by Gomer,gSe7eN,trevyn,Warlock45,and others.

## Requirements

[AutoBot.mac](https://macroquest2.com/phpBB3/viewtopic.php?t=12712) does not run on a default [MQ2
compilation](../documentation/macroquest2-compiling.md), it has a few extra dependencies. Some of the below items are
[Plugins](../commands/plugin.md) and need to be compiled, just like MacroQuest2. Please read the appropriate documentation
for each plugin. The Include files should be added to the same directory that AutoBot will be run from.

[Plugins](../commands/plugin.md):

-   [MQ2MoveUtils](https://macroquest2.com/phpBB3/viewtopic.php?t=11732) by Outlander  
    This is so the macro knows about stick, /makecamp, and /moveto. Check out the
    [wiki](https://macroquest2.com/wiki/index.php/MQ2MoveUtils).  
-   [MQ2Exchange](https://macroquest2.com/phpBB3/viewtopic.php?t=7603) by Wassup  
    This is so that item swapping, casting, and swapping back will work  
-   [MQ2Debuffs](https://macroquest2.com/phpBB3/viewtopic.php?t=13495) by pinkfloydx33  
    This is so the macro can keep track of your debuff counters.  
-   [MQ2Melee](https://macroquest2.com/phpBB3/viewtopic.php?t=12779) by s0rcier  
    So as to properly configure melee/ranged combat and various options thereof, check out the
    [wiki](https://macroquest2.com/wiki/index.php/MQ2Melee).  
    \*Optional: [MQ2AutoLogin](https://macroquest2.com/phpBB3/viewtopic.php?f=50&t=16427&hilit=MQ2Autologin)  
    to change to your trader

Includes Files:

-   [Wait4Rez.inc](wait4rez.inc.md) Handles pre-rez situations.  
-   [spell_routines.inc](spell-routines.inc.md) Handles spell casting, from gems, items and AAs.  
-   QuickBeg2.inc Handles buff begging.  
-   [Ninjadvloot.inc](ninjadvloot.inc.md) Handles looting.  
-   [Defense.inc](defense.inc.md) Handles automatic engagement of defensive disc/aa/items for tanks.  
-   [AAPurchase.incHandles](aapurchase.inc.md) automatic purchase of AA based on INI entries.  

## Getting Started

Pointers for AutoBot stuffs. (We should make a multi-boxing wiki sometime, we could link it here...)

In addition to the documentation for the various plugins used directly by AutoBot (see links in
[Requirements](https://macroquest2.com/wiki/index.php/AutoBot.mac#Requirements)) The following is useful info on
other plugins you can use to enhance your AutoBot experience.

[MQ2Clip](https://macroquest2.com/phpBB3/viewtopic.php?t=7692) by Vaft, Cr4zyb4rd, et al.  
Manages the clip plane of backgrounded sessions. Your CPU will thank you.

[MQ2FPS](https://macroquest2.com/phpBB3/viewtopic.php?t=8346) by Lax.  
Helps manage framerates of EQ sessions, greatly helps multi-botting... Check out the
[wiki](https://macroquest2.com/wiki/index.php/MQ2FPS)

[MQ2Eqbc](https://macroquest2.com/phpBB3/viewtopic.php?t=12147) by Omnictrl  
Is an alternative way to communicate with your bots.  
Configure your EQBC.ini with the following:  
\[Last Connect\]  
Server=192.168.1.101 (This must be edited to match the ip and port you have the server listening to)  
Port=2112  
\[Settings\]  
AutoConnect=1  
AllowControl=1  
  
You will also need to change the channel setting in your AutoBot.ini from "i say" to "bc" to use it for bot to bot
communication. Don't forget that if you are getting identify spam that you check loot.ini and QB2Settings.ini for any i
say or i msg commands. QB2Settings.ini defaults to i msg and needs to be changed if using EQBC. Recommend
[MQ2NetBots](https://macroquest2.com/phpBB3/viewtopic.php?t=12186),
[MQ2NetStat](https://macroquest2.com/phpBB3/viewtopic.php?t=12186), and
[MQ2NetHeal](https://macroquest2.com/phpBB3/viewtopic.php?t=12312&highlight=mq2netheal) to go along with this. More
information available on [Page
59](https://macroquest2.com/phpBB3/viewtopic.php?t=11619&postdays=0&postorder=asc&highlight=eqbc+autobot&start=870) of
the original AutoBot thread.

## Using AutoBot.mac

1\) The main macro file, 'yyy.mac' (called 'RaidDruid.mac' in the .zip file) can be named to 'AutoBot.mac' or
'AnythingYouWant.mac'.  
2) To start the macro in EverQuest with MQ2 running; type '/macro yyy.mac  
Note: The first time you run the macro, it will generate an ini file called RD_xxx.ini  
3) Configure your RD_xxx.ini, where 'xxx' is your character name.  
3a) Peruse through [RDCommon.ini](rdcommon.ini.md) and add in any mobs you might want to have certains spells
ignore. I tend to put Guild Lobby and PoK NPCs as immune to mez, makes life simpler when walking around and I forget to
pause my bots. You will also find the MasterList here.  
4)Restart Autobot after configuring RD_xxx.ini.  
5) Enjoy the show.  

## Bot Commands

There are a few non-alias (no / required) commands available to Autobot. These commands will cause the bots to respond
to a few general status/movement commands without the obvious /alias, for easy use in a group setting. Bots will only
respond to commands sent by someone in the MasterList  
**buffqueue**  
This command has your bot respond in your ChatChannel with the # of buffs left in his "buff queue". Handy for deciding
whether to continue pulling/crawling after a group wipe. Keep in mind that some longer cast spells such as Night's Dark
Terror for enchanters have extremely long recast times, and so can sit in the queue for a while.  
**break**  
This will make your bots visible (they will click off all invisibility or IVU buffs).  
**camp here**  
This command will cause any other toons using Autobot to utilize MQ2Moveutil's "make camp" function, using he location
coordinates you are standing on when issuing the command.  
**follow**  
This command will have your bots /stick to you. They will sit to med if needed and within your LeashLength. They will
also break off to attack if /domelee is turned on and the MA is fighting something. They will also service buff requests
and do debuffing if applicable and they are not moving.  
**guard here**  
Those toons you have the Guard function turned on will utilize MQ2MoveUtils camp function to set up a tightly controlled
camp radius where that character is currently standing.  
**mana**  
All bots with a mana pool bigger than 0 will report their current % mana in your /chatchannel.  
**medtime**  
All bots with a mana pool bigger than 0 will report their currently estimated time to full mana based on their current
Mana Regen divided by their mana level.  
**move up**  
This command tells your bots to move up to your current location. If they are set to /makecamp, they will reset their
camp X and Y loc to your current position. If they are following, they will resume following once they reach your
position (This is handy for positioning your bots in front of doors/bridges before moving through/across them)  
**stop**  
This command tells the bots to stop following wherever they happen to be standing.  
**use keyword XXX YYY**  
This command will cause the toon to say the keyword XXX to target YYY. Example: "use keyword when gribble"  
**who has XXXX**  
This command will have the toon check their inventory for the item. It will announce in the chat channel if it is in
your bank, bags, top level inventory, or a worn item. If the item is an augment and mounted, it will say what item the
augments is in.

------------------------------------------------------------------------------------------------------------------------

**Send me to XXXXX**  
This will cause a listening wizard or druid to cast zehphyr/translocate XXX on the requester, uses same keywords as
portto  
**portto XXXXX**  
This will cause your wizard or druid bot to port using their group port spells, provided they have them in their
spellbook. Current accepted keywords are:  
Druid

`alra`  
`arcstone`  
`barindu`  
`blightfire`  
`brell`  
`buriedsea`  
`butcher`  
`cobalt`  
`commons`  
`combine`  
`dawnshroud`  
`direwild`  
`domain`  
`east (karana)`  
`emerald (jungle)`  
`feerrott`  
`greatdivide`  
`grimling`  
`grounds`  
`karana (north)`  
`iceclad`  
`lavastorm`  
`Lceanium `  
`loping`  
`misty`  
`moors`  
`natimbi`  
`nexus`  
`pok`  
`ro`  
`shards`  
`skyfire`  
`south (emerald jungle)`  
`steamfont`  
`steppes`  
`stonebrunt`  
`succor`  
`surefall`  
`tempest`  
`time`  
`tox`  
`twilight`  
`undershore`  
`wakening`

Wizard:

`alra`  
`arcstone`  
`barindu`  
`bloodfield`  
`brell`  
`cazic`  
`cobalt`  
`combine|dreadlands`  
`commons`  
`dawnshroud`  
`dragonscale`  
`ej|emerald (emerald jungle)`  
`gfay (greater faydark)`  
`gd|greatdivide`  
`grimling`  
`grounds`  
`karana (north)`  
`katta`  
`iceclad`  
`icefall`  
`Lceanium `  
`moors (blightfire moors)`  
`natimbi`  
`nek`  
`nexus`  
`nro`  
`pok|knowledge`  
`sarith`  
`skyfire`  
`shards`  
`slaughter`  
`sro`  
`sunderock`  
`time`  
`tox`  
`twilight`  
`twk|west karana (ethernere tainted west karana)`  
`undershore`  
`wakening`  
`wkarna`  
`succor`

## Slash Commands

[AutoBot.mac](https://macroquest2.com/phpBB3/viewtopic.php?t=11619) comes with a great set of predefined [Slash
Commands](../commands/slash-commands.md) for easy and fast in-game configuration.  
Uber macro pause/unpause hotkey (bound to \\ for me, unlike normal EQ hotkeys 1-10, it works even while casting) Add the
following lines to [MQ2CustomBinds](https://macroquest2.com/wiki/index.php/MQ2CustomBinds).txt:

` name=StartPauseDB`  
` down=/docommand ${If[!${Macro.Name.Equal[RaidDruid.mac]}, /mac RaidDruid.mac, /varset RDPause ${If[${RDPause}==1,0,1]}]}`  
` up=`

Then in game type */bind StartPauseDB \\* to bind that to your *\\* key. When pressed your *\\* key will start AutoBot
if it's not already started. If it's already running it will toggle the pause on the macro.

Here's a full list, divided into sub-sections for each category of [Slash Commands](../commands/slash-commands.md) there are
(Each toggle alias works by itself, or will take an argument of ON/OFF, TRUE/FALSE, or 1/0):

  

### Melee

-   **/dodefense**  
    Toggles usage of the defensive measures in Defense.inc (currently only works for SK,PAL, and WAR)
-   **/domelee**  
    Toggles automatic engaging of the MA's target in melee.(Must have the plugin
    [MQ2Melee](https://macroquest2.com/phpBB3/viewtopic.php?t=12221) configured properly)
-   **/domercassist**  
    Toggles whether you want the macro to engage mercenaries (so you can better control when they engage)
-   **/domercstance**  
    Toggles automatic changing of the bot's mercenary stance based on if the MA's target is named (or higher level) or
    mercenary's aggro
-   **/doranged**  
    Toggles automatic engaging of /autofire if MA's target is with in NPCradius and beyond range distance
-   **/mercengagehps**  
    Set the HP% you want the macro to engage your mercenaries, if you have /domercassist on
-   **/guard**  
    Toggles the guard function on\|off
-   **/rangedist XXX**  
    set the minimum distance away from mob before engaging /autofire. The EQ minumum is 30.
-   **/reportdefense**  
    Toggles reporting for Defense.inc events
-   **/status**  
    This will toggle the group "status" checking part of the guard function, allowing the guard toon to pause for group
    members below 50mana or 30endurance, for 60 second per check.
-   **/stickarg XXX**  
    sets melee arguments for stick during fights

### General

-   **/addalert ${Target.CleanName}**  
    Adds targetted NPC to the list which will be ignored in the RDCommon.ini and will perform normally when near these
    npc's not treating them as hostile. ${Target.CleanName} can also be replaced with the name of the mob typed out or
    the ini file can be manually edited.
-   **/assistdelay**  
    Sets the amount of time the bot will wait between MA assists. (Ex. /assistdelay 5s)
-   **/assistma**  
    Toggles assisting of your designated MA1, MA2, and MA3. Turning this off essentially disables Melee, Nuking, DoTing,
    and Debuffing
-   **/autoninja**  
    Toggles auto looting of the nearest corpse after each XP gained message. Will only loot droppable items. Must have
    the plugin [MQ2MoveUtils](https://macroquest2.com/phpBB3/viewtopic.php?t=11732) for this to work.
-   **/autosit**  
    Toggles auto sitting to med. Not much to say here.
-   **/changetank**  
    Toggles automatic changing to MA2 or MA3 when MA1 dies (need to have /usegroupassist and /useraidassist both off,
    still testing)
-   **/chatchannel**  
    Sets the chat channel the bot reports to, (Ex. /chatchannel "i say"�)
-   **/docanni**  
    Toggles auto casting of your cannibalization spell when below your MedPct and above your CanniHPs. Also works for
    wizard harvest, mana robe, and necromancer Lich spells.
-   **/doports**Toggles whether your druid or wizard bot will respond to portto comands
-   **/doyaulp**  
    Toggles auto casting of your yaulp spell when below your MedPct and there are NPCs within your NPCRadius.
-   **/engagehps**  
    Sets the % of the mobs HPs you want to start melee/debuffing/dotting/nuking (Ex. /engagehps 95)
-   **/ma1**  
    Assigns a PC as Main Assist 1. (Ex. /ma1 BoDuke)
-   **/ma2**  
    Assigns a PC as Main Assist 2. (Ex. /ma2 LukeDuke)
-   **/ma3**  
    Assigns a PC as Main Assist 3. (Ex. /ma3 DaisyDuke)
-   **/leashlength**  
    Sets the distance your bot will allow itself to get from his follow target before resuming follow (Ex.
    /leashlength 25)
-   **/listspells**  
    Returns a list of all configured Spell Sets in your ini.
-   **/loadini "IniFileName"**  
    Loads a pre-configured ini file.
-   **/medpct**  
    Sets the % of Mana you want to sit or summon your horse at. (Ex. /medpct 50)
-   **/npcradchk**  
    Sets the Radius (in feet) around you that defines how close mobs are allow before you stop buffing to avoid aggro
    (Ex. /npcradchk 100)
-   **/npcradius**  
    Sets the Radius (in feet) around you that you want to watch NPCs using Assist healing and Assisting the MA (Ex.
    /npcradius 200)
-   **/npczradius**  
    Sets the Radius (in feet) above/below you that you want to watch NPCs using Assist healing and Assisting the MA (Ex.
    /npczradius 200)
-   **/rdpause**  
    Toggles AutoBot's active functions on and off.
-   **/relaytells**  
    Toggles automatic reporting of tells sent to the bot in your configured /chatchannel
-   **/reportevents**  
    Toggles automatic reporting of your bot's status messages such as low food/drink, stunned/unstunned, encumbered,
    etc.
-   **/reportmana**  
    Toggles automatic reporting of your mana status if you get below the medpct, only reports once before going above
    the medpct.
-   **/reportmanapct**  
    Defines the point at which you want to start reporting your mana status to your chat channel.
-   **/reporttoggles**  
    Toggles automatic reporting of your toggle status of any /commands you send your bot in the ChatChannel.
-   **/reportwow**  
    Toggles automatic reporting of Wrath of the Wild on the MA
-   **/saveini "IniFileName"**  
    Creates an ini file named "IniFileName"
-   **/sitdelay**  
    Sets the amount of time you want to wait before sitting after casting any spell that might be considered aggro. (Ex.
    /sitdelay 5s)
-   **/stophps**  
    Sets the % of the mob's HPs you want to stop nuking and debuffing. (Ex. /stophps 10)
-   **/targetlock**  
    Toggles using non-assist target lock
-   **/useepic**  
    Toggles automatic use of epic
-   **/usegroupassist**  
    Toggles automatic assigning of the group's main assist as MA1
-   **/usegroupma**  
    Toggles automatic assigning of the gorup's main assist as MA1
-   **/usegrouptank**  
    Toggles automatic assigning of the group's main tank as MA1
-   **/usemount**  
    Toggles automatic mount summoning at your /medpct, if this is off and /autosit is on, it will sit to med instead of
    summoning a mount.
-   **/useraidassist**  
    Toggles using the raid's main assist (assist 1) as MA1
-   **/useraidma**  
    Toggles using the raid's main assist (assist 1) as MA1

### Healing

-   **/aeheal**  
    Toggles on AE Healing. This creates an array of every PC within PCRadius, and cycles through every one of them,
    checking their HPs against your defined HealPct, and casts heals if appropriate. Super handy on mobs with AE Rampage
    or AE Damage effects.
-   **/assistheal**  
    Toggles on Assist Healing. This creates an array of every NPC within NPCRadius, and assists them to find the target
    of their aggression, and heals that target if necessary. Super handy for general clearing on raids before getting to
    named. Also causes target to constantly ping-pong wildly all over the place trying to find a target to heal
-   **/cancelpct**  
    Set this to the percentage of HPs you want AutoBot to cancel heals at. (Ex. /cancelpct 90)
-   **/checkgroup**  
    Sets the number of seconds you'd like to wait between HP evaluations
-   **/delayedhealpct XX**  
    Sets the percentage of HPs to cast delayed heal on MA1
-   **/divarbhps**  
    Sets the % HPs you want to cast Divine Arbitration at if a groupmember gets below it (Ex. /divarbhps 25)
-   **/dointerrupting**  
    Toggles interrupting debuffs/nukes/dots to heal group members. Some people like to just let their group members die
    instead of ducking a nuke to heal them. This is for those people!
-   **/doretort**  
    Toggles automatic casting of the listed Retort spell on MA1
-   **/doward**  
    Toggles automatic casting of the listed Ward spell on MA1
-   **/healchannel**  
    Sets the channel your bots use to report heals when they are cast.
-   **/healfd**  
    Toggles healing of FD classes (SK, Necro, Monk) only while they are FD (Ex. /healfd ON will only heal if they are
    FD)
-   **/healgroup**  
    Toggles healing of your group. With this on, it will heal groupmembers that are below HealPct
-   **/healmefirst**  
    Toggles healing of yourself over any group members. If you are mid-cast to heal someone else and your HPs fall below
    the HealPct, you will cancel it and heal yourself first. Self preservation at its finest.
-   **/healpct**  
    Sets the % of HPs you want to heal other PCs at. (ex. /healpct 70)
-   **/healpets**  
    Toggles healing of any pets in the group if they are below the PetHealPct
-   **/healramp**  
    Toggles automatic healing of your Rampage tank anytime a RAMPAGE message is detected.
-   **/healxtarget**  
    Toggles activation of healing PC and pets on the extended target window.
-   **/pcradius**  
    Sets the Radius (in feet) around you that you want to watch PC HPs using AE healing (Ex. /pcradius 200)
-   **/pczradius**  
    Sets the Radius (in feet) above and below you that you want to watch PC HPs using AE healing (Ex. /pczradius 50)
-   **/pethealpct**  
    Sets the % of HPs you will heal pets at. (Ex. /pethealpct 40)
-   **/ramptank**  
    Sets the Rampage Tank that you check whenever a RAMPAGE message is seen with /healramp on. (Ex. /ramptank
    UncleJesse)
-   **/reportheals**  
    Toggles automatic reporting of heals in the ChatChannel
-   **/reportinterrupts**  
    Toggles automatic reporting of interrupts to heal in the ChatChannel
-   **/reportsotw**  
    Toggles automatic reporting of Spirit of the Wood in the ChatChannel
-   **/sotw**  
    Toggle auto casting of Spirit of the Wood
-   **/sotwpct**  
    Set this to the average group HP percentage you want it to auto cast Spirit of the Wood at. (Ex. /sotwpct 75)
-   **/tankhealpct**  
    Sets the % you start Chealing. Due to some predictive logic the Cheal may start earlier. Set this to the abslute
    floor you want to start CH at.
-   **/usech**  
    Toggles using your Cheal spell on MA1 on or off. It will monitor the tank's HPs and if he's taking enough damage to
    be dead in less than 20 seconds, it will duck out of whatever RD is currently doing and start a CH. If the tank's
    HPs stop falling and level off above the TankHealPct, it will cancel CH and wait until the tank's HPs fall again.
-   **/usedelayed**  
    Toggles casting the listed Delayed Heal on MA1
-   **/usedivarb**  
    Toggles using your divine arbitration or cleric epic 1.5 (if you have it) when a group member falls below the
    DivArbHPs.
-   **/usetankhot**  
    Toggles casting the listed Heal over Time spell on MA1
-   **/waittocancel**  
    Toggle. When turned on, this will wait until your heals have less than .5 seconds left before making the decison to
    cancel the heal.

### Buffing

AutoBot queues buff requests and casts them when appropriate. It will not cast buffs unless there are no mobs within 20
feet of the bot, it's not in combat, and it's not moving. It will hold onto those buff requests until you are no longer
moving, not in combat, and there are no mobs within 20 feet. If you zone, all stored buffs are flushed, and you have to
beg again.  
By default the bot only listens for /tells and IRC chat for buffing. If you want him to listen in other channels, you
need to add **#chat group** to listen in group, or **#chat chat** to listen in EQ's chat channels; to the RaidDruid.mac
file under the **#chat tell** line right near the top of the macro. More information on the #chat function can be found
in the MacroQuest [manual](https://macroquest2.com/includes/wassup/manual.php).

**Aliases:**

-   **/buff "Spell Name/Alias" \[Name \| Group\]**  
    Use this alias to send a buff command to your bot, will also accept buff aliases. You can use this to cast items and
    AAs as well as spells. If you specify Group instead of a name, it will buff your whole group with that spell, if it
    is a single target spell. In addition, you can cast it on any spawn including NPCs, Pets, Corpses, etc. (Ex. /buff
    "Steeloak Skin"� Bob, or /buff Oak Bob if oak is an alias for steeloak skin). If the /buff command utilizes a DoBuff
    alias, the buff request is queued and will not be performed during combat. If the Spell/AA/item name itself is used
    in the /buff command it is cast immediately. (Ex. /buff "Exodus" would fire right away, while /buff "Evac" would
    not). **WARNING: YOUR BOTS WILL NOT WATCH THE GROUP'S HPS OR ANYTHING ELSE WHILE EXECUTING A /BUFF COMMAND, USE IT
    WHEN YOU KNOW YOU DON'T NEED TO BE DOING ANYTHING ELSE IMPORTANT LIKE HEALING**
-   **/dobuffs**  
    Toggles automatic casting of buff requests made via /tell
-   **/dobufftells**  
    Toggles sending automatic replies to buff requests made via /tell
-   **/refreshbuffs**  
    Toggles automatic refreshing of buffs. Only buffs that are set to refresh in the ini will be refreshed.
-   **/reportdobuffs**  
    Toggles automatic reporting of buffs in the ChatChannel
-   **/reportselfbuffs**  
    Toggles automatic reporting of self buffs in the ChatChannel
-   **/selfbuff**  
    Toggles Self Buffing. Useful if you happen to be in an environment where having all your self buffs up puts you over
    the limit
-   **/wow**  
    Toggles automatic casting of Wrath of the Wild on your designated MA. I figure an extra 650 damage every 4 minutes
    cant hurt, since its mana free and all.

### Debuffing

-   **/debuff**  
    Toggles Auto debuffing. Pretty much all there is to say about that
-   **/debuffchannel**  
    Sets the channel your bots will use to report debuffs
-   **/dot**  
    Toggle Auto DoTing of mobs
-   **/mez**  
    Toggles Auto mezzing for those places where mez==bad
-   **/reportdebuffs**  
    Toggles reporting of debuffs in the ChatChannel
-   **/reportdots**  
    Toggles automatic report of DoTs in the ChatChannel
-   **/reportmez**  
    Toggles automatic report of Mezzes in the ChatChannel
-   **/usehott**  
    Toggles using the Health of Target's Target Leadership ability to determine a mob's aggro.

### Nuking

-   **/domancy**  
    Toggles Auto use of wizard's Pyromancy, Cryomancr, and Arcomany AA before casting spell nukes.
-   **/nuke**  
    Toggles Auto Nuking the MA's target.
-   **/nukedelay**  
    Sets the delay between chain nuking. If your tank sucks, or are in a kite group raise this delay to prevent agro.
-   **/nukeset #**  
    Sets the spellset to cast Nuke/Debuff/DoTs. If no number is given, returns the current spell set # you are nuking
    from.

### Pet

-   **/petbuff**  
    Toggles automatic buffing of your pet
-   **/usepet**  
    Toggles automatic summoning and sending in of pet to melee.

### Curing

This portion of the macro requires the [MQ2Debuffs](https://macroquest2.com/phpBB3/viewtopic.php?t=13495) plugin by
pinkfloydx33. See the [requirements](https://macroquest2.com/wiki/index.php/AutoBot.mac#Requirements).

-   **/docures**  
    Toggles auto-curing on and off.
-   **/reportcures**  
    Toggles auto-cure reporting on and off.

### Stuff

This macro has been updated to utilize a programmable rest, combat, and named script checks and commands similar to
MQ2Melee's holy/down shits.

-   **/docombat**  
    Toggles useage of the Combat scripts.
-   **/donamed**  
    Toggles useage of the Named scripts.
-   **/dorest**  
    Toggles usage of the Rest scripts.

### Bard

This portion of the macro makes use of the [MQ2Twist](https://macroquest2.com/phpBB3/viewtopic.php?t=8895) (See
[MQ2Twist wiki](https://macroquest2.com/wiki/index.php/MQ2Twist)) and
[MQ2BardSwap](https://macroquest2.com/phpBB3/viewtopic.php?t=9178) plugins.

-   **/addcombatsong <Alias>\|"<Song Name>"**  
    Adds the Alias or Song Name to the combat twist if a slot is available.
-   **/addrestsong <Alias>\|"<Song Name>"**  
    Adds the Alias or Song Name to the rest twist if a slot is available.
-   **/autorestoff**  
    When turned on it watches with each loop to see if any npc's are within the radius defined and will switch off rest
    songs if any are detected
-   **/autorestradius**  
    Sets the radius at which your bard will stop twisting when NPCs are present
-   **/combatsongs on\|off**  
    Enables or Disables automatically twisting the combat twist temporarily.
-   **/delcombatsong <Alias>\|"<Song Name>"**  
    Removes the Alias or Song Name from the combat twist present.
-   **/delrestsong <Alias>\|"<Song Name>"**  
    Removes the Alias or Song Name from the rest twist if present.
-   **/listsongs combat\|rest\|all**  
    Lists the songs set to be twisted for the given twist type.
-   **/songalias <alias> "Song Name"**  
    Creates an alias for the given song name (must be in quotes if it has a space).

## INI entries

.ini files will be automatically created and populated with default values if they do not exist.

### \[MeleeStuff\]

**DoMelee=1** *(Set by /domelee)*  
**DoRanged=1** *(0=Don't use ranged attacks, 1=Use Ranged attacks)*  
**DoMercAssist=TRUE** *(TRUE\|1\|FALSE\|0) - If you want the macro to engage mercenaries so you can better control when
they engage*  
**DoMercStance=FALSE** *(TRUE\|1\|FALSE\|0) - Toggles use of automatic mercenary stance changes based on aggro*  
**MercEngageHPs=98** *At what hp% you want the MATarget to be at before engaging*  
**StanceChange=50** *(Amount off aggro to change DPS mercs from burn to balance)*  
**Guard=TRUE** *(TRUE\|1\|FALSE\|0 - Toggles the guard function)*  
**StickArgs=10 pin** *(Set by /stickargs)*  
**DiscTotal=1** *(Set this to the total number of melee disciplines you have defined)*  
**UseDiscs=1** *(0=Don't Disc, 1=Use Discs)*  
**DiscName1=Furious Discipline** *(Set this to the name of the Discipline you want to use)*  
**DiscType1=0** *(0=Defensive, 1=Offensive)*  
**DiscEndurance1=10** *(Set this to the % endurance you want to be above when triggering this disc)*  
**DiscMinHPs1=10** *(Set this to the min HPs of the mob or yourself that you want to trigger this disc at.)*  
**DiscMaxHPs1=90** *(Set this to the max HPs of the mob or yourself that you want to trigger this disc at.)*  
**DiscSpawnCount1=2** *(Set this to the # of mobs you want to have in melee range before triggering this disc.)*  

### \[Settings\]

**AABuy=FALSE** *TRUE\|1\|FALSE\|0 - Toggles whether to automatically buy AA*  
**ASRadius=20** *(Set to radius to check for mobs before sitting)*  
**ASZRadius=50** *(Set to Z radius to check for mobs before sitting)*  
**AutoNinja=0** *(Set by /autoninja, 0=off and 1=on)*  
**AutoSit=1** *(Set by /autosit, 0=off and 1=on)*  
**DrinkGem=gem1** *(Set this to gem#, item, or alt; as applicable to summon food)*  
**DrinkSpell=Abundant Drink** *(Set this to the name of the spell/item/alt you use to summon drink)*  
**DoShrink=FALSE** *(TRUE\|1\|FALSE\|0 - Toggles whether to automatically shrink)*  
**EndMedPct=80** *Endurance % to med at?* **FoodGem=gem1** *(Set this to gem#, item, or alt; as applicable to summon
food)*  
**FoodSpell=Abundant Food** *(Set this to the name of the spell/item/alt you use to summon food)*  
**GatherPct=10** *(Set this to the % mana you want to use your Gather Mana)*  
**IRCAddress=** *IRC Server URL*  
**IRCPort=6667** *(set to the port you want MQ2IRC to use)*  
**IRCChannel=#Name** *(Set to the name of the channel you want MQ2IRC to utilize, remember to put a # sign in front)*  
**LeashLength=25** *(Set by /leashlength)*  
**MedPct=50** *(Set by /medpct)*  
**MountItem=Black Rope Bridle** *(This is the item you use to summon your mount)*  
**MoveUpJitter=10** *(Amount of distance before "jittering", to look more natual)*  
**NPCRadChk=100** *(Set by /npcradchk)*  
**NPCRadius=75** *(Set by /npcradius)*  
**NPCZRadius=100** *(Set by /npczradius)*  
**PCRadius=200** *(Set by /pcradius)*  
**PCZRadius=100** *(Set by /pczradius)*  
**ShrinkGem=** *(Set to item or gemNumber or alt for your shrink spell)*  
**ShrinkSelfOnly=TRUE** *(TRUE\|1\|FALSE\|0 - Toggles whether to automatically use shrink on yourself)*  
**ShrinkSpell=** *(Put the name of your shrink spell or item here)*  
**SitDelay=5s** *(Set by /sitdelay)*  
**UseIRC=FALSE** *(TRUE\|1\|FALSE\|0 - Toggles whether to utilize MQ2IRC)*  
**UseMount=1** *(Set by /usemount, 0=off and 1=on)*  
**UseRods=0** *(Set by /userods)*  
**RodMana=50** *(Set this to the % mana you want to be below before clicking your mod rods)*  
**RodSpell=Rod of Mystical Transvergance** *(Set this to the spell you use to summon mod rods)*  
**RodGem=gem1** *(Set this to gem you want to cast this from, or put item for items, alt for AAs)*  

### \[GeneralStuff\]

**AssistDelay=5s** *(Set by /assistdelay)*  
**AssistMA=1** *(Set by /assistma, 0=off and 1=on)*  
**CalmSpell=** *Put the name of your calm spell or item here*  
**CalmGem=** *Put gem# for spells, or item for items*  
**CanniGem1=gem6** *(Set this to spell gem you want to cast your canni spell from, or put alt if an AA, or item if its
an item)*  
**CanniHPs1=0** *(Set this to the % HPs you want to stop using your canni AA at)*  
**CanniSpell1=Harvest** *(Set this to the name of your canni aa/item/spell. This section also works for Lich and any
other Canni type spells that have a buff icon)*  
**CanniTotal=1** *(Set this to the total cannibalization/harvest AAs/items/spells you want to check and cast)*  
**ChangeTank=FALSE** *(TRUE\|1\|FALSE\|0 - Toggles automatic changing to MA2 or MA3 when MA1 dies)*  
**ChatChannel=i say** *(Set by /chatchannel)*  
**DoCanni=1** *(Set this to 1 if you want to use your Canni AAs/items/spells when you fall below your medpct)*  
**DoWoW=1** *(Set by /wow, 0=off and 1=on)*  
**DoYaulp=1** *(Set this to 1 if you want to use Yaulp when mobs are close by instead of sitting)*  
**EngageHPs=95** *(Set by /engagehps)*  
**InvisibilitySpell=** *Put the name of your invis spell or item here*  
**InvisibilityGem=** *Put gem# for spells, or item for items*  
**MA1=HappyGilmore** *(Set by /ma1)*  
**MA2=BillyMadison** *(Set by /ma2)*  
**MA3=MrDeeds** *(Set by /ma3)*  
**MaxMezLvl=93** *(Set this to the maximum level your Mez spell can effect)*  
**MaxCharmLvl=89** *(Set this to the Max level your Charm spell can effect)*  
**MaxCalmLvl=90** *(Set this to the Max level your Calm spell can effect)*  
**Mezbroke=FALSE** *(TRUE\|1\|FALSE\|0 - Toggles announcement of who broke Mez)*  
**RelayTells=1** *(Set by /relaytells)*  
**ReportEvents=1** *(Set by /reportevents)*  
**ReportMana=1** *(Set by /reportmana)*  
**ReportManaPct=50** *(Set by /reportmanapct)*  
**ReportToggles=1** *(Set by /reporttoggles)*  
**ReportWoW=1** *(Set by /reportwow)*  
**SpellSet1=SomeSpellSetName** *(Put the name of the Spell Set you want to memorize when you die while using this spell
set here. Needs to match the name of the spell set you have saved in EQ to work properly)*  
**SpellSetTotal=1** *(Set this to the # of unique spell sets you have defined for nukes/debuffs)*  
**StopHPs=20** *(Set by /stophps)*  
**TargetLock=FALSE** *TRUE\|1\|FALSE\|0 - Toggles whether to lock target when not using a MA*  
**TraderName=Traderdude01** *(Set this to name of your account's Trader in order to use MQ2AutoLogin's toon switching
feature via "go to trader" )*  
**UseEpic=1** *(TRUE\|1\|FALSE\|0 - Toggles automatic use of Epic on MA1's target*  
**UseGroupMA=TRUE** *(TRUE\|1\|FALSE\|0 - Toggles whether to automatically assign the group's main assist as MA1 )*  
**UseGroupTank=FALSE** *(TRUE\|1\|FALSE\|0 - Toggles whether to automatically assign the group's main tank as MA1)*  
**UseRaidMA=FALSE** *(TRUE\|1\|FALSE\|0 - Toggles whether to automatically assign the raid's main assist (assist1) as
MA1)*  
**YaulpGem1=gem6** *(Set this to spell gem you want to cast your Yaulp spell from)*  
**YaulpSpell1=Yaulp VII** *(Set this to the name of your Yaulp spell)*  

### \[HealStuff\]

**AEHealing=0** *(Set by /aeheal, 0=off and 1=on)*  
**AutoInterrupt=1** *(Set by /interrupt, 0=off and 1=on)*  
**AssistHealing=0** *(Set by /assistheal, 0=off and 1=on)*  
**BegFrantic=FALSE** *(TRUE\|1\|FALSE\|0 - Toggle auto begging for frantic heals when below the BegFranticPCT)  
**BegFranticPct=35*** (Sets the amount of HP below which your toon will beg for a Frantic Heal)  
**BegFranticChannel=BC** *(Sets the channel your toon will beg for Frantic Heals in)  
**CancelPct=90***(Set by /cancelpct)*  
**CheckGroupInterval=3***(Set by /checkgroup, and sets how often you check group HP levels for healing)*  
**DelayedHeal=Promised Rehabilitation***(This is your Delayed Heal spell)*  
**DelayedHealGem=Gem4***(This is the gem you will be casting the Delayed Heal from)*  
**DelayedHealPct=95***(Sets the HP% below which your toon will cast the Delayed Heal on MA1, use "/delayedhealpct
##")*  
**DoRetort=TRUE***(TRUE\|1\|FALSE\|0 - Toggles use of automatically casting Retort on MA1 during combat)*  
**UseDelayedHeal=TRUE***(TRUE\|1\|FALSE\|0 - Toggles whether to automatically cast the Delayed Heal, use "/usedelayed"
)*  
**DivArbHPs=20***(Set by /divarbhps)*  
**DoSotW=1***(Set by /sotw, 0=off and 1=on, Toggles casting of "Spirit of the Wood" or other listed spell/AA)*  
**FastHeal=Chlorotrope***(This is your fast healing spell)*  
**FastHealGem=gem2***(This is the gem you cast your Fast Heal from if it's not memmed already)*  
**FranticHeal=Fifteenth Emblem*** (Sets which heal your toon will cast in response to a Frantic Heal call)  
**FranticHealGem=Gem6** *(Sets the gem number to memorize the Frantic Heal spell)  
**GroupHealing=1***(Set by /healgroup, 0=off and 1=on)*  
**HealChannel=echo***(Set by /healchannel)*  
**HealFD=0***(Set by /healFD, 1 only heals FD classes while FD, 0 heals normally)*  
**HealMeFirst=1***(Set by /healmefirst)*  
**HealPct=30***(Set by /healpct)*  
**HealXTarget=TRUE***(TRUE\|1\|FALSE\|0 - Toggles healing of PC and Pets on the Extended Target Window)*  
**PetHeal=Karana's Renewal***(Put the name of the spell you wish to use to heal your group's pets here)*  
**PetHealGem=gem1***(Put the gem you wish to cast your pet heal from if its not memmed)*  
**PetHealing=1***(Set by /healpets)*  
**PetHealPct=50***(Set by /pethealpct)*  
**QM=TRUE***(TRUE\|1\|FALSE\|0 - Toggles automatic use of Quiet Miracle on group members whose mana is below 40m)*  
**RampHealing=0***(Set by /healramp, 0=off and 1=on)*  
**RampTank=BigDaddy***(Set by /ramptank)*  
**ReportHeals=1***(Set by /reportheals)*  
**ReportInterrupts=1***(Set by /reportinterrupts)*  
**ReportSotW=1***(Set by /reportsotw)*  
**RetortSpell=Olsif's Retort***(This is your Retort spell)*  
**RetortGem=Gem9***(This is the gem you want to cast the Retort spell from)*  
**SotWAA=Spirit of the Wood***(This is the Actual Alt ability you have, set it to whichever one you have)*  
**SotWPct=80***(Set by /sotwpct)*  
**TankHeal=Karana's Renewal***(Heal spell to use on the tank... usually your Cheal) **MUST** be defined and a different
spell than FastHeal, even if not used.*  
**TankHealGem=gem8***(Spell slot for your tank heal spell)*  
**TankHealPct=70***(This is the % you heal MA1 at)*  
**UseBDA=0***(Set this to 1 if you want to cast Bestow Divine Aura on groupmembers when Divine Arbitration is not up)*  
**UseCH=1***(Use Chealing... or not, 1 for on, 0 for not)*  
**UseDivArb=0***(Set by /usedivarb)*  
**UseFranticHeal=TRUE***(TRUE\|1\|FALSE\|0 - Toggles whether to respond to calls for Frantic Heals)*  
**WaitToCancel=1***(Set by /waittocancel)''  

### \[CureStuff\]

**CureTotal=1** *(Put your total number of cure spells here)*  
**DoCures=0** *(0=Don't Cure, 1=Cure)*  
**ReportCures=0** *(0=Don't Report, 1=Report)*  
**CureSpell1=Resplendent Cure** *(Put the name of the item, alt, or spell you use to cure with here)*  
**CureGem1=alt** *(Put item for item, alt for AA, or the gem# you want to use to cure with here)*  
**CurseCounters1=50** *(Set this to the # of curse counters you want this to react to (For example if the spell cures 25
curse counters and you want it to only cure if it can do it in 2 casts or less, set it to 50))*  
**DiseaseCounters1=50** *(Set this to the # of Disease counters you want this to react to (For example if the spell
cures 25 Disease counters and you want it to only cure if it can do it in 2 casts or less, set it to 50))*  
**PoisonCounters1=50** *(Set this to the # of Poison counters you want this to react to (For example if the spell cures
25 Poison counters and you want it to only cure if it can do it in 2 casts or less, set it to 50))*  

### \[SelfBuffStuff\]

**SelfBuffTotal=9** *(Put your total number of self buffs here)*  
**SelfBuffs=1** *(Set by /selfbuff, 0=off and 1=on)*  
**ReportSelfBuffs=1** *(Set by /reportselfbuffs)*  
**SelfBuffRecheck=10s** *(Sets how often you check to see if your self buffs are going to fade)*  
**SelfBuff1=Shrunken Goblin Skull Earring** *(This is the name of the item or spell you use for self buff 1)*  
**SelfBuffIcon1=Grim Aura** *(This is the name of self buff 1 as it shows up in your buff window)*  
**SelfBuffGem1=item** *(This is the gem you cast self buff 1 from, if it's an item put item, if it's an AA put alt)*  
**SelfBuffCount1=14** *(Put the number of buffs you would like to stop casting this buff after, i.e if you want to leave
a couple buff slots open, set your self buffs up so that the could is never equal to your max number of buff slots)*  

### \[DoBuffStuff\]

**DoBuffTotal=10** *(Put the total number of DoBuff entries you have here)*  
**DoBuffs=1** *(Set by /dobuffs, 0=off and 1=on)*  
**ReportDoBuffs=1** *(Set by /reportdobuffs)*  
**DoBuffTells=0** *(Set by /dobufftells)*  
**RefreshBuffs=1** *(Set by /refreshbuffs)*  
**DoBuff1=Woven Grass Boots** *(Put the name of the item, aa, or spell you cast this buff with here)*  
**DoBuffIcon1=Spirit of Wolf** *(This is the name of dobuff 1 as it would show up in your buff window)*  
**DoBuffGem1=item** *(This is the gem you cast dobuff 1 from, if it's an item put item, if it's an AA put alt)*  
**DoBuffMana1=0** *(Set this to the % mana you'd like to be above before handling this buff request)*  
**DoBuffAliases1=SoW\|Spirit\|** *(This is the string of different buff messages you want the druid bot to respond to,
separated by the \|. Make sure to have a \| for each buff, as it needs to count them to find out how many buff request
strings to check for. Also be mindful of spaces, as the buff request will not be registered without the preceding and
trailing spaces defined in the alias. Ex: If the alias were set up as \| Rune \|. "I could use a Rune right about now"
would trigger the request while "Rune" alone would not, unless the alias is actually defined with no spaces as
\|Rune\|).*  
**DoBuffRefresh1=1** *(Set this to 1 if you want to refresh this buff when it wears off)*  
**BattleBuff1=FALSE** *(Set this to TRUE if you would like to cast this buff with mobs nearby and/or in Combat.)*  
**RezBuff1=FALSE** *(This allows the buff to be cast on a corpse, IE set rez spells to TRUE, all else FALSE)*  
**BuffGem=gem3** *(Set this to the spell gem you want to cast your /buff commands from)*  

### \[DebuffStuff\]

**DebuffTotal=3** *(Put the total number of Debuff entries you have here)*  
**DoDebuffs=1** *(Set by /debuff, 0=off and 1=on)*  
**DoDoTs=1** *(Set by /dot, 0=off and 1=on)*  
**DoMez=1** *(Set by /mez, 0=off and 1=on)*  
**DoManaTaps=1** *(0=off and 1=on)*  
**ReportDebuffs=1** *(Set by /reportdebuffs)*  
**ReportDoTs=1** *(Set by /reportdots)*  
**ReportMez=1** *(Set by /reportmez)*  
**DebuffChannel=echo** *(Set by /debuffchannel)*  
**UseHoTT=1** *(0=off and 1=on)*  
**MaxMobs=1** *(Set this to the maximum number of mobs you would like AutoBot to keep track of)*  
**AllDebuffsFirst=1** *(Set this to 1 if you want to land all your debuffs on each mob before moving on to debuff the
next)*  
**DebuffMAFirst=1** *(Set this to 1 if you want to land all your debuffs on the MA's target before moving on to any
adds)*  
**DebuffSpell1=Hand of Ro** *(Put the name of the item, aa, or spell you cast this debuff with here)*  
**DebuffIcon1=Hand of Ro** *(This is the name of debuff 1 as it would show up in your buff window)*  
**DebuffGem1=gem5** *(This is the gem you cast debuff 1 from, if it's an item put item, if it's an AA put alt)*  
**DebuffMana1=1** *(Set this is to the % mana you would like to stop casting this debuff at.)*  
**DebuffHPs1=1** *(Set this is to the % HPs you would like to start casting this debuff at.)*  
**DebuffStopHPs1=1** *(Set this is to the % HPs you would like to stop casting this debuff at.)*  
**DebuffRecast1=3** *(Set by /debuffrecast)*  
**DebuffSpellSet1=1** *(This is the spell set you want to cast this debuff with. 0=all spell sets, 1=spell set #1,
etc.)*  
**DebuffMAOnly1=1** *(Set this is to 1 if you want to land this debuff on the MA's target only, and exclude adds.)*  
**DebuffNamedOnly1=1** *(Set this is to 1 if you want to land this debuff on named targets only, and not normal XP
mobs.)*  
**DebuffMessage1=%Target Debuffed by %Spell** *(This is your custom debuff message when you successfully land a debuff.
Use %Target to report the target's name, %Spell to report the spell name, and %Duration to report the duration of the
spell you just landed) Or set to None for no message.*  
**SpellType1=1** *(Set this is to 0 for debuffs, 1 for DoTs, 2 for Mez, 3 for Mana Tap spells, 4 for AE Mez, and 5 for
Charm.)*  
**DebuffCondition1=TRUE** *(Code conditions can be put here such as "{Target.Body.Name.Equal\[Undead\]} or
!{Target.Buff\[Turgur's Swarm\].ID} Default is TRUE )*  

### \[NukeStuff\]

**NukeTotal=1** *(Set this to the number of nukes you have defined)*  
**DoNukes=1** *(Set by /nuke, 0=off and 1=on)*  
**Domancy=TRUE** *(Set by /domancy, FALSE=off and TRUE=on) determines if wizards will use "mancy" AA before casting
spell*  
**NukeDelay=1** *(Sets the delay in re-casting nukes, usefull when you have sucky tanks with low agro. Format for a 10
second delay is either 10s or 100)*  
**WhichNuke=1** *(Sets which nuke to use 1=SpellSet #1, etc.)*  
**Nuke1=Solstice Strike** *(Set this to the name of the Nuke you want to cast)*  
**NukeGem1=gem7** *(Set this to gem#, # being the gem you want to mem this nuke in)*  
**NukeSpellSet1=1** *(Set this to the spell set you want to be using to cast this nuke)*  
**NukeStartHPs1=100** *(Set this to the % of the mob's HPs you want to start dropping bombs on it. Some classes might
want to use a smaller nuke when a mob gets under say 30% HPs, in order to prevent wasting mana)*  
**NukeStopHPs1=30** *(Set this to the % HPs you want to stop nuking with this spell at)*  
**NukeMaxMana1=30** *(The highest % mana you want to be when using this nuke. Most of us will want this at 100%, but
some classes (such as wizards) might want to switch out to a small nuke when under 50m, and use a bigger one when over
50m.)*  
**NukeMinMana1=30** *(Set this to the lowest % mana you want to be before you stop nuking. Essentially this is where
most of us set our mana reserve for other duties such as healing, debuffing, etc. For wizards though, this provides the
ability to stop nuking with one spell, and start nuking with another spell below this % using the same % for MaxMana)*  
**GoMNuke1=0** *(Set this to 0 if you don't want to cast this Nuke when Gift of Mana is up. Set it to 1, and it will use
this nuke when GoM is up. Another addition mainly for wizards, it provides them the opportunity to get a 1 mana cost
monster nuke off, instead of wasting it on a crappy lure or something. If set to 1, it will stop debuffing in favor of
nuking while Gift of Mana is up. If you want to get your debuffing done over all else, then leave this at 0. Your bots
will still heal and mez normally if set to 1, but debuffs are ignored as long as the buff is up)*  
**DoConcussion=1** *(0=Don't Concussion, 1=Do Concussion)*  
**ConcussionSpell=Concussion** *(Set this to the name of the Item, Alt, or Spell you use for Concussion)*  
**ConcussionGem=gem1** *(Set this to Item for items, Alt for AAs, or gem# for Spells)*  
**DoMancy=TRUE"** *(WIZ only, causes macro to change the "pyromancy, ect" buff according to the nuke it is about to
cast)*  

### \[PetStuff\]

**UsePet=1** *(Set by /usepet)*  
**PetMana=10** *(Set this to the % mana you'd like to be above before casting your pet.)*  
**KillFlappy1=1** *(0=Keep your familiar, 1=Kill your Familiar)*  
**PetFocus=Some focus item** *(Set this to the item you want to equip before casting your pet)*  
**PetSpell=Nature Walkers Behest** *(Set this to your Pet spell)*  
**PetGem=gem4** *(Set this to the gem you want to cast your pet from)*  
**PetBuffTotal=1** *(Set this to the total number of pet buffs you want to cast)*  
**DoPetBuffs=1** *(1=pet buffing on, 0= pet buffing off)*  
**ReportPetBuffs=1** *(1=pet buffing reporting on, 0= pet buffing reporting off)*  
**PetBuffRecheck=10s** *(Set this to how often you'd like to re-check your pet's buffs for wearing off)*  
**PetBuff1=Pet Buff Item/Spell name**  
**PetBuffIcon1=Pet Buff Item/Spell Icon name**  
**PetBuffGem1=Pet Buff Item/Spell Gem name**  
**PetShrink=1** *(1=pet shrinking on, 0=pet shrinking off)*  
**PetShrinkSpell=Tiny Companion** *(Set this to the Name of the spell/aa/item you use to shrink your pet)*  
**PetShrinkGem=gem4** *(Set this to the gem you want to shrink your pet from)*  
**PetItemTotal=1** *( Your total number of pet item buffs. If you have 2 weapons you want to summon, you currently have
to define the same weapon twice, so set this accordingly)*  
**PetItemSpell1=Blazing Stone of Demise** *( The name of the spell/aa/item you want to summon with)*  
**PetItemGem1=item** *(gem# for spells, item for items, alt for AAs.)*  
**PettHealing=** *(Mage Specific- TRUE/FALSE use "self pet heals")*  
**SelfPetHealPct=** *(Mage Specific- what perctage of pet HP to heal pet)*  
**SelfPetHeal=** *(Mage Specific- what pet only heal to use)*  
**SelfPetHealGem=** *(Mage Specific- what gem to use pet only heal from)*  
**PetDelayedHealing=** *(Mage Specific- TRUE/FALSE use Pet Delayed Heal)*  
**PetDelayedHealPct=** *(Mage Specific- What Hit Point percentage to cast the Pet Delayed Heal)*  
**PetDelayedHeal=** *(Mage Specific- What Delayed Pet Heal spell to use)*  
**PetDelayedHealGem=** *(Mage Specific- What gem to use Delayed Pet Heal)*  

### \[HolyShit\]

**TotalShit=1** *(Set this to the total number of HolyShit Abilities you have defined)*  
**DoHolyShit=1** *(1=On, 0=Off)*  
**HolyShit1=Oaken Guard** *(Name of Item/AA/Spell/disc to use)*  
**HolyShitGem1=gem9** *(Put the HolyShit Gem#, alt, item, or skill)*  
**HolyShitHp1=70** *(HP level you want to be below before triggering this ability)*  
**HolyShitType1=0** *(0=Just cast, 1=Target yourself, 2=Target the mob hitting you, 3=Ability like "Lay Hands")*  
**HolyShitRUN1=0** *(1=Attempt to run away from the mob towards the MA after casting this spell. 0=stand there and do
nothing after casting)*  

### \[CombatStuff\]

`(This section is only accessed when you are in a combat state)`

**CombatTotal=7** *(Set this to the total number of Combat commands you have defined)*  
**DoCombatStuff=TRUE** *(TRUE\|1\|FALSE\|0)*  
**CombatStuffRecheck=5s** *(Sets the amount of time between checking Combat scripts)*  
**CombatCommand1=/casting "Mindless Hatred" ALT** *(The command/script to do it all the conditions are met)*  
**CombatCondition1={Me.AltAbilityReady\[Mindless Hatred\]} && {Target.Distance}\<=50 && {Me.PctAggro}\<100**
*(Conditions to meet before doing the command/script)*  

### \[NamedStuff\]

`(This section is only access when your target is a named, the MA's target is more then 2 levels over you,`  
`or you have more then 2 mobs on your extended target window.`  
`If you wish to change this, search/look for "/call named" in the main loop)`

**NamedTotal=1** *(Set this to the total number of Named scripts you have defined*  
**DoNamedStuff=TRUE** *(on\|off\|TRUE\|FALSE)*  
**NamedStuffRecheck=5s** *(Sets the amount of time between checking Named scripts)*  
**NamedCommand1=/call Cast "Fury of Ro" ALT** *(The command/script to do if the conditions are met)*  
**NamedCondition1={Me.PctAggro}\<80 && {Me.AltAbilityReady\[Fury of Ro\]}** *(Conditions to meet before doing
command/script)*  

### \[RestStuff\]

`(This section is called when you are not in combat)`

**RestTotal=1** *(Set this to the total number of Rest commands you have defined)*  
**DoRestStuff=TRUE** *(TRUE\|1\|FALSE\|0)*  
**RestStuffRecheck=5s** *(Sets the amount of time between checking Rest scripts)*  
**RestCommand1=/useitem "Huntsman's Ethereal Quiver"** *(The command/script to do if all conditions are met)*  
**RestCondition1={FindItemCount\[Ethereal Arrow\]}\<100** *(The conditions to meet before doing the command/script)*  

### \[Bard\]

**DoBardSwap=False** *(Enables [Bardswap plugin](https://macroquest2.com/phpBB3/viewtopic.php?t=9178) automatically on
startup if set to True)*  
**DoBardMeleeSwap=False** *(Enables [Bardswap](https://macroquest2.com/phpBB3/viewtopic.php?t=9178) to swap in melee
weapons as well automatically on startup if set to True)*  
**AutoRestOff=0** *(Set with /autorestoff)*  
**AutoRestRadius=125** *(Set with /autorestradius)*  

### \[Bard-Combat\]

**SongsArray1-8=Song Name** *(Set via /addcombatsong <songname>\|<alias>. Removed with /delcombatsong
<songname>\|<alias>. Add in extra entries as you gain spell gems.)*  

### \[Bard-Rest\]

**SongsArray9-18=Song Name** *(Set via /addrestsong <songname>\|<alias>. Removed with /delrestsong
<songname>\|<alias>.*  

### \[Bard-Aliases\]

**aliasname=songname** *(Set via /songalias <aliasname> "song name").* Songalias is basically to make it easier to
change your combat/rest lineup on the fly with /addrestsong alias.

## Troubleshooting/FAQ

-   **On "where is my master list?!?**  

The master list was moved to the RDCommon.ini file to avoid having to maintain a list on 50 different profile ini's.
Open RDCommon.ini and use find "MastereList" to easily find where to put additional names.

`(A new command was added, in the channel your toon is listening to send "add to masterlist newtoonname" to have the macro add the new name to the list)`

-   **On I set my ini to service XXXX skill/spell/AA/item but its not working**  

Got something spelled wrong or not filled out properly. Check the examples again. Very rarely EQ has odd spaces in some
names. I find it best to look up the spell/skill/item/AA off of Allakhazam.com and copy+paste to insure accurate
spelling when troubleshooting problem INI's.

-   **On Dots/Debuffs that don't work, but (possibly) used to**  

If in a group/raid with HoTT leadership skill set UseHoTT=1 in the ini file. If HoTT is not avialable you must set
UseHoTT=0. Check to see the MaxMobs=5 is appropraite to the number of NPC's around you. Monsters that are green or
sitting/laying down will never be debuffed/dotted.

-   **On Buff requests not being serviced**  

Unless you indicate that you want the buff executed in combat the bot will not service the buff if there are NPC's
nearby. You can have the macro ignore certain npcs that we know for certain arnt kos by adding their names in the
RDCommon.ini .Alternatly the NPC check radius is adjustable in the ini. Also make sure that the buff name is spelled
correctly just how it looks in the info window. Lastly make sure that the alias's are correct. in the example ini's it
looks like this "\| convicton \| viction \| convic \|", however if you have it set up like that, the buff requester for
all intents and purposes needs to put that word in a sentence. if you have the ini looking like this
"\|convicton\|viction\|convic\|" with no spaces in between the " \| " then the bot will reconize and ackowlege any tell
that has any of the word alias's it sees.

-   **On Bot will assist but wont engage when set to**  

The bigest thing you do to fix that is increase the NPCRadius=120, Also, consider verifiying, and tweaking the following
as well. NPCZRadius=120, AssistMA=TRUE, , DoMelee=TRUE, AssistDelay=0s, MA1=Chuck_Norris, EngageHPs=101. aso remember
that other options may be fighting for servicing. looting, selfbuffing, debuffing, buffing, etc.. so if melee is
priority, turn everything but assisting off. also make sure that mq2melee is set up right. type /melee to bring up its
console and see whats set and whats not. same thing goes. if your not a pet class turn off all that other stuff to
prevent any chance of conflicts.

-   **On Cant load selo's into the ini**  

Selos uses a "\`\`\`\`\`\`\`\`\`\`\`\`" located to the left of the 1 key.

-   **On incorrectly mezed Targets (also known as: Oh why does my chanter mez my MA's target?)**  

You need to properly set the target for the BOT by the Leader AA, or /varset MATarget ${Target.ID} as explained in "On
target acquisition"

-   **On automatically mezzing NPCs when you don't want to**  

Set /rdpause on the BOT you want to stop auto debuffing (rdpause stops all automatic activity), type "/rdpause on"
(minus quotes) into your command channel to stop auto-activity on multiple BOT's at once, or add the NPC you wish to not
mez to the immune/ignore list in RDCommon.ini. You will need to know the spell ID for the spell you wish not to cast and
this can be found by ${Spell\[My Mez Spell Name Here\].ID} (Use /echo in front of ${Spell\[My Mez Spell Name Here\].ID}
if your typing it in EQ)

-   **On Target acquisition**  

AutoBot acquires the Main Assist's (MA) target in a number of ways.

1\) By setting the MA in the bot's ini file and the assist delay, the macro will attempt to acquire the target of the MA
after the set time.

2\) By assigning the role Main Assist to someone in your group, the bot will acquire the MA's target that way. (if
/udegroupassist or /usegroupma is on)

3\) By assigning the role Main Tank to someone in your group, the bot will aquire the MT's target. (if /usegrouptank is
on)

4\) By manually setting the MA's target using /varset MATarget ${Target.ID} in whatever channel your bots listen to
commands in.

5\) By using "/useraidassist" or "/useraidma" (remember to turn off /usegroupma and /usegrouptank if you do this) the
macro will aquire a target assist the raids main assist (Raid Assist 1)

-   **On non-working clickies**  

If you have a clicky with no recast timer that isn't working. (Such as Time's Antithesis, Veil of Lost Hopes, et al...)
The odds are you have an old version of MQ2. As of the 20th of Dec Zip, these issues have been fixed. if you don't know
what version of the zip you have, try simply running /echo ${FindItem\[item name\].Timer} and seeing what value it
returns. Anything other than zero is Bad(tm) and denotes an out-of-date zip file. Update, update, update! Also your last
inventory slot must NOT be a bag. Clickies usable from inventory, even if usable in other slots, will be used from base
inventory slot 8.

-   **On chain-casting clickies or buffs**  

Often times this is due to misspelling something in the INI file, or it can be the resulting buff icon differs from the
spell icon in some manner. You will note there is now an "Icon" entry for buffs. Carefully double check the actual name
of the buff ingame and match the INI to it.

-   **On out-of-date alias lists**  

If you are attempting to reload your alias to your macroquest.ini. You must remove the Version=X.XX from RD_common.ini.
Doing this will make the Version mismatch appear and reload all the alias's

-   **On healing not working**  
-   **On heals that never cancel even though target's health goes above CancelPct**  

Tankheal must be defined as a valid spell and different than FastHeal=, even if you are not using Tankheals (UseCH
setting).

-   **On Green (non-XP) corpses that are not auto looted**  

These are not looted automatically. To trigger looting, at any time, send your bot "You gain party experience!" in
whatever channel it is set to monitor.

-   **On late/not reliable buffs**  

Bots will not buff in combat. Also it will not sit to memorize buffs if a NPC is within a certain range, although using
a horse remedies this.

-   **On non-refreshing buffs on bots themselves**  

Buffs from the \[DoBuffStuff\] or buff command are not rebuffed on the same bot that cast them, because you dont get a
buff wear off message when they wear off yourself. If you want certain buffs kept up on your bot, you should use
\[SelfBuffStuff\] section.

-   **On bots that keep targeting some npc, even though it hasn't been told it to assist and kill it**  

Your MA could have a corpse close, and that is being assisted to get a target. Or you could be using an old version of
autobot.

-   **On non-following bots**  

Target someone and type /stick. If that doesnt work you have issues with
[MQ2MoveUtils](https://macroquest2.com/phpBB3/viewtopic.php?t=11732).  

-   **On Clerics that spam Complete Heals and interrupt them all**  

Make sure you have UseDivArb set to 0 if you dont have that AA. // There's more to this than just the DivArb setting...
but this might be one issue\\\\

-   **On non-attacking pets/bots**  

Check your MQ2Melee settings(the wiki for it is [here](https://macroquest2.com/wiki/index.php/MQ2Melee)). You need a
properly configured MQ2Melee for your pets/bots to attack and do other various melee-related tasks.

-   **On items being identified**  

You aren't using the IRC plugin. By default /i is mapped to /identify.  

-   **No slash commands work or error: "DoCommand - Couldn't parse '/...' "**

This usually happens when you update MQ2 and overwrite the macroquest.ini file. This file contains all the aliases (ie.
the slash commands). To fix, delete the Version=X.XX line in RD_Common.ini, which will write all the aliases back to the
macroquest.ini file when you restart Autobot. In general, you do not need to overwrite the Macroquest.ini file when
updating MQ2.

-   **When your bot doesn't mem spells**  

Your ini is set up wrong. Your XXXXGem#= entry needs to read "gem#", not just #. At least, 9 times out of 10 that's the
problem. Check one of the sample ini files for an example.

-   **On My bots dont aquire targets when everything is set up properly**  

Each toon needs a breastplate, it has to do with the way autobot checks deaths and runs the auto accept rez feature, it
also disables assisting, for a good reason...


