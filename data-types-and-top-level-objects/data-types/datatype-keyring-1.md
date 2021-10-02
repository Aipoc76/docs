# DataType:keyring

This datatype represents information about a keyring \(a.k.a. a collection of mounts, illusions, etc\)

## Members

| **Type** | **Member** | **Description** |
| :--- | :--- | :--- |
| [_int_](datatype-int.md) | **Count** | The number of items in this keyring |
| \_\_[_keyringitem_](datatype-keyring.md)\_\_ | **Stat** | The keyring item assigned as the stat item |

## Examples

If **Jungle Raptor Saddle** is set as your **Stat Mount**:

`/echo ${Mount.Stat}`  
Outputs: Jungle Raptor Saddle

If you have **3** items in your Mounts keyring:

`/echo ${Mount.Count}`  
Outputs: 3

