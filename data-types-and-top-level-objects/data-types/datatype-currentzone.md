# DataType:currentzone

Contains data about the current zone.

## Members

This type inherits members from [_zone_](datatype-zone.md).

| **Type** | **Member** | **Description** |
| :--- | :--- | :--- |
| [_bool_](datatype-bool.md) | **Dungeon** | Are we in a dungeon |
| [_float_](datatype-float.md) | **Gravity** | Gravity |
| [_int_](datatype-int.md) | **ID** | Zone ID |
| [_bool_](datatype-bool.md) | **Indoor** | Are we indoors? |
| [_float_](datatype-float.md) | **MaxClip** | Maximum clip plane allowed in zone |
| [_float_](datatype-float.md) | **MinClip** | Minimum clip plane allowed in zone |
| \_\_[_string_](datatype-string.md)\_\_ | **Name** | Full zone name |
| [_bool_](datatype-bool.md) | **NoBind** | Can we bind here? |
| [_bool_](datatype-bool.md) | **Outdoor** | Are we outdoors? |
| \_\_[_string_](datatype-string.md)\_\_ | **ShortName** | Short zone name |
| [_int_](datatype-int.md) | **SkyType** | Sky type |
| [_int_](datatype-int.md) | **Type** | Zone type:0=Indoor Dungeon 1=Outdoor 2=Outdoor City 3=Dungeon City 4=Indoor City 5=Outdoor Dungeon |
| [_int_](datatype-int.md) | **FogOnOff** | Is the fog on\|off |
| \_\_[_string_](datatype-string.md)\_\_ | **To String** | Same as **Name** |

## Example

A check in a condition or a macro to determine if the current zone is indoors:

```text
${Zone.Indoor}
```

