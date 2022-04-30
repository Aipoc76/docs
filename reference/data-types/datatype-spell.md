# DataType:spell

This is the type used for spell information.

## Members

|                                      |                              |                                                                                                                                |
| ------------------------------------ | ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Type**                             | **Member**                   | **Description**                                                                                                                |
| [_float_](datatype-float.md)         | **AERange**                  | AE range (group spells use this for their range)                                                                               |
| [_string_](datatype-string.md)__     | **CastOnAnother**            | Message when cast on others                                                                                                    |
| [_string_](datatype-string.md)__     | **CastOnYou**                | Message when cast on yourself                                                                                                  |
| [_timestamp_](datatype-timestamp.md) | **CastTime**                 | Cast time (unadjusted)                                                                                                         |
| [_string_](datatype-string.md)__     | **CounterType**              | The resist counter. Will be one of "Disease", "Poison", "Curse" or "Corruption"                                                |
| [_int_](datatype-int.md)             | **CounterNumber**            | The number of counters that the spell adds                                                                                     |
| [_ticks_](datatype-ticks.md)         | **Duration**                 | Duration of the spell (if any)                                                                                                 |
| [_ticks_](datatype-ticks.md)         | **DurationValue1**           | Duration of the spell (if any)                                                                                                 |
| [_timestamp_](datatype-timestamp.md) | **FizzleTime**               | Time to recover after fizzle                                                                                                   |
| [_int_](datatype-int.md)             | **GemIcon**                  | Icon number of the spell. Example ${Spell\[blah].GemIcon}                                                                      |
| [_int_](datatype-int.md)             | **HastePct**                 | Percentage of haste, example of use ${Me.Hasted.HastePct} or ${Spell\[Speed of Milyex].HastePct}                               |
| [_int_](datatype-int.md)             | **ID**                       | Spell ID                                                                                                                       |
| [_bool_](datatype-bool.md)           | **IsSkill**                  | is this spell a skill?                                                                                                         |
| [_bool_](datatype-bool.md)           | **IsSwarmSpell**             | Is this spell a Swarm spell?                                                                                                   |
| [_int_](datatype-int.md)             | **Level**                    | Level                                                                                                                          |
| [_int_](datatype-int.md)             | **Location**                 | Appears to be max distance                                                                                                     |
| [_int_](datatype-int.md)             | **Mana**                     | Mana cost (unadjusted)                                                                                                         |
| [_timestamp_](datatype-timestamp.md) | **MyCastTime**               | Adjusted cast time                                                                                                             |
| [_float_](datatype-float.md)         | **MyRange**                  | Adjusted spell range, including focus effects, etc.                                                                            |
| [_string_](datatype-string.md)__     | **Name**                     | Spell Name                                                                                                                     |
| [_float_](datatype-float.md)         | **PushBack**                 | Push back amount                                                                                                               |
| [_float_](datatype-float.md)         | **Range**                    | Maximum range to target (use **AERange** for AE and group spells)                                                              |
| [_int_](datatype-int.md)             | **Rank**                     | Returns either 1, 2 or 3 for spells and 4-30 for clickables and potions.                                                       |
| [_string_](datatype-string.md)__     | **RankName**                 | Returns the spell/combat ability name rank character has.                                                                      |
| [_float_](datatype-float.md)         | **RecastTime**               | Time to recast after successful cast                                                                                           |
| [_timestamp_](datatype-timestamp.md) | **RecoveryTime**             | Same as **FizzleTime**                                                                                                         |
| [_int_](datatype-int.md)             | **ResistAdj**                | Resist adjustment                                                                                                              |
| [_string_](datatype-string.md)__     | **ResistType**               | See below for Resist Types                                                                                                     |
| [_string_](datatype-string.md)__     | **Skill**                    | See below for Skill Types                                                                                                      |
| [_int_](datatype-int.md)             | **SlowPct**                  | Percentage of slow, example of use ${Target.Slowed.SlowPct} or ${Spell\[Slowing Helix].SlowPct}                                |
| [_int_](datatype-int.md)             | **SpellIcon**                | Icon number of the spell. Exmaple ${Spell\[blah].SpellIcon}                                                                    |
| [_string_](datatype-string.md)__     | **SpellType**                | "Beneficial(Group)", "Beneficial", "Detrimental" or "Unknown"                                                                  |
| [_bool_](datatype-bool.md)           | **Stacks\[**duration**]**    | Does the selected spell stack with your current buffs (duration is in ticks)                                                   |
| [_bool_](datatype-bool.md)           | **StacksPet\[**duration**]** | Does the selected spell stack with your pet's current buffs (duration is in ticks)                                             |
| [_bool_](datatype-bool.md)           | **StacksTarget**             | Does the selected spell stack with your target's current buffs                                                                 |
| [_bool_](datatype-bool.md)           | **StacksWith\[**name**]**    | alias for .WillStack - see entry for more details                                                                              |
| [_string_](datatype-string.md)__     | **TargetType**               | See below for Target Types                                                                                                     |
| [_string_](datatype-string.md)__     | **WearOff**                  | The "wear off" message                                                                                                         |
| [_bool_](datatype-bool.md)           | **WillStack\[**name**]**     | Does the selected spell stack with the specific SPELL _name_ DOES NOT work with AAs.                                           |
| [_int_](datatype-int.md)             | **WillLand**                 | This is like stacks but without the duration check.  It's a clean: "Will this spell land."  Returns the slot it would land in. |
| [_int_](datatype-int.md)             | **WillLandPet**              | Same as WillLand, but for your pet.                                                                                            |
| [_string_](datatype-string.md)__     | **To String**                | Same as **Name**                                                                                                               |

## Example

`/echo I have the ${Spell[Certitude].RankName} version of Certitude. - Spell`\
`Outputs:[MQ2] I have the Certitude Rk. II version of Ceritude.`

`/cast "${Spell[Vinespur].RankName}" in your macro will cast it, since its going to be resolved as /cast "Vinespur Rk. II"`

`/echo My version of Rest is: ${Spell[Rest].RankName} - Combat ability`\
`Outputs: [MQ2] My version of Rest is: Rest Rk. II`

## Resist Types

**ResistType** will be one of the following:

| <p>:* Chromatic</p><p>:* Corruption</p><p>:* Cold</p><p>:* Disease</p><p>:* Fire</p> | <p>:* Magic</p><p>:* Poison</p><p>:* Unknown</p><p>:* Unresistable</p><p>:* Prismatic</p> |
| ------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |

## Target Types

**TargetType** will be one of the following:

| <p>:* AE PC v1</p><p>:* AE PC v2</p><p>:* AE Summoned</p><p>:* AE Undead</p><p>:* Animal</p> | <p>:* Corpse</p><p>:* Group v1</p><p>:* Group v2</p><p>:* LifeTap</p><p>:* Line of Sight</p> | <p>:* PB AE</p><p>:* Pet</p><p>:* Plant</p><p>:* Self</p><p>:* Single</p> | <p>:* Summoned</p><p>:* Targeted AE</p><p>:* Targeted AE Tap</p><p>:* Uber Dragons</p><p>:* Uber Giants</p> | <p>:* Undead</p><p>:* Unknown</p> |
| -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------- |

## Skill Types

**Skill** will be one of the following:

:\* Abjuration

:\* Alteration

:\* Conjuration

:\* Divination

:\* Evocation

## MyDuration

MyDuration is a custom mod located [here](https://macroquest.org/phpBB3/viewtopic.php?t=13007). It is not supported by the developers, nor included in the zip release.

|                              |                |                            |
| ---------------------------- | -------------- | -------------------------- |
| **Type**                     | **Member**     | **Description**            |
| [_ticks_](datatype-ticks.md) | **MyDuration** | Adjusted Duration (if any) |

## Data Dump as of 07/31/20

* ID
* Address
* AERange
* Attrib
* AutoCast
* Base
* Base2
* BaseName
* Beneficial
* BookIcon
* Calc
* CalcIndex
* CanMGB
* CastByMe
* CastByOther
* Caster
* CastOnAnother
* CastOnYou
* CastTime
* Category
* CounterNumber
* CounterType
* Deletable
* Description
* Duration
* DurationValue1
* DurationWindow
* EnduranceCost
* EQSpellDuration
* Extra
* FizzleTime
* GemIcon
* HasSPA
* HastePct
* IllusionOkWhenMounted
* IsActiveAA
* IsSkill
* IsSwarmSpell
* Level
* Location
* Mana
* Max
* MaxLevel
* MyCastTime
* MyDuration
* MyRange
* Name
* NewStacks
* NewStacksWith
* NoExpendReagentID
* NumEffects
* PushBack
* Range
* Rank
* RankName
* ReagentCount
* ReagentID
* RecastTime
* RecastTimerID
* RecoveryTime
* ResistAdj
* ResistType
* Restrictions
* Skill
* SlowPct
* SPA
* SpellGroup
* SpellIcon
* SpellType
* Stacks
* StacksPet
* StacksSpawn
* StacksTarget
* StacksWith
* StacksWithDiscs
* Subcategory
* SubSpellGroup
* Target
* TargetType
* TimeOfDay
* Trigger
* WearOff
* WillStack
