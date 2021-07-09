# DataType:target

This is the type for your target, which has access to buff information. Inherits 

## Members

Inherits members from [_spawn_](datatype-spawn.md)_._

| **Type** | **Member** | **Description** |
| :--- | :--- | :--- |
| [_spell_](datatype-spell.md) | **Aego** | Returns the name of the Aego spell if the Target has one |
| [_spawn_](datatype-spawn.md) | **AggroHolder** | Returns the target's current target. |
| [_spell_](datatype-spell.md) | **Beneficial** | Returns the name of the Beneficial spell if the Target has one. This will skip "player" casted buffs, but will show NPC Casted buffs and some AA buffs. |
| [_spell_](datatype-spell.md) | **Buff\[**n**\]** | Returns the target's spell by buff index number. |
| [_spell_](datatype-spell.md) | **Buff\[**_name_**\]** | Returns the target's spell name, or the first buff if no Index is provided. |
| [_int_](datatype-int.md) | **BuffCount** | Returns the number of buffs on the target. |
| [_timestamp_](datatype-timestamp.md) | **BuffDuration\[**\#**\]** | Returns the duration remaining on this target buff by index number |
| [_timestamp_](datatype-timestamp.md) | **BuffDuration\[**_name_**\]** | Returns the duration remaining on this target buff by spell name |
| [_bool_](datatype-bool.md) | **BuffsPopulated** | Returns TRUE when the target's buffs are finished populating. |
| [_spell_](datatype-spell.md) | **Brells** | Returns the name of the Brells spell if the Target has one |
| [_spell_](datatype-spell.md) | **Charmed** | Returns the name of the Charmed spell if the Target has one |
| [_spell_](datatype-spell.md) | **Clarity** | Returns the name of the Clarity spell if the Target has one |
| [_spell_](datatype-spell.md) | **Corrupted** | Returns the name of any the Corruption spell if Target has one |
| [_spell_](datatype-spell.md) | **Cursed** | Returns the name of the Curse spell if Target has one |
| [_spell_](datatype-spell.md) | **Crippled** | Returns the name of the Cripple spell if the Target has one |
| [_string_]() | **Diseased** | Returns the name of a Disease spell if the Target has one |
| [_string_]() | **Dotted** | Returns the name of a DOT spell if the Target has one |
| [_spell_](datatype-spell.md) | **DSed** | Returns the name of the Damage Shield spell if the Target has one |
| [_spell_](datatype-spell.md) | **Focus** | Returns the name of the Focus spell if the Target has one |
| [_spell_](datatype-spell.md) | **Growth** | Returns the name of the Growth spell if the Target has one |
| [_spell_](datatype-spell.md) | **Hasted** | Returns the name of the Haste spell if the Target has one |
| [_spell_](datatype-spell.md) | **HybridHP** | Returns the name of the Hybrid HP spell if the Target has one |
| [_spell_](datatype-spell.md) | **Maloed** | Returns the name of the Malo spell if the Target has one |
| [_spell_](datatype-spell.md) | **Mezzed** | Returns the name of the Mez spell if the Target has one |
| [_string_]() | **Poisoned** | Returns the name of a Poison spell if the Target has one |
| [_spell_](datatype-spell.md) | **Pred** | Returns the name of the Predator spell if the Target has one |
| [_spell_](datatype-spell.md) | **Rooted** | Returns the name of the Rooted spell if the Target has one |
| [_spell_](datatype-spell.md) | **Regen** | Returns the name of the Regen spell if the Target has one |
| [_spell_](datatype-spell.md) | **RevDSed** | Returns the name of the Reverse Damage Shield spell if the Target has one |
| [_spell_](datatype-spell.md) | **SE** | Returns the name of the Spiritual Enlightenment spell if the Target has one |
| [_spell_](datatype-spell.md) | **Shining** | Returns the name of the Shining spell if the Target has one |
| [_spell_](datatype-spell.md) | **Skin** | Returns the name of the Skin spell if the Target has one |
| [_spell_](datatype-spell.md) | **Slowed** | Returns the name of the Slow spell if the Target has one |
| [_spell_](datatype-spell.md) | **Snared** | Returns the name of the Snare spell if the Target has one |
| [_spell_](datatype-spell.md) | **Strength** | Returns the name of the Strength spell if the Target has one |
| [_spell_](datatype-spell.md) | **SV** | Returns the name of the Spiritual Vitality spell if the Target has one |
| [_spell_](datatype-spell.md) | **Symbol** | Returns the name of the Symbol spell if the Target has one |
| [_spell_](datatype-spell.md) | **Tashed** | Returns the name of the Tash spell if the Target has one |
| \_\_[_string_]()\_\_ | **To String** | Same as **Name** |

### Examples

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Example</b>
      </th>
      <th style="text-align:left"><b>Output/Result</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><code>/target pet</code>
        </p>
        <p><code>/delay 5s ${Target.ID}==${Pet.ID} &amp;&amp; ${Target.BuffsPopulated}==TRUE</code>
        </p>
      </td>
      <td style="text-align:left">The Delay will stop when the pet is targeted...AND target buffs are populated,
        or 5 seconds.</td>
    </tr>
  </tbody>
</table>

