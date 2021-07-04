## Description

Used to get information on MQ2Data types.

## Forms

-   *[type](../data-types/datatype-type.md)* **Type\[**name**\]**

## Access to Types

-   *[type](../data-types/datatype-type.md)* **type**

## Examples

`/echo ${Type[spawn].Member[ID]}`

Determines if a member of a type exists

`/for n 1 to 100`  
`  /echo ${Type[spawn].Member[${n}]}`  
`/next n`

Enumerate members of a type using a loop

## See Also

-   [Top-Level Objects](top-level-objects.md)
-   [type](../data-types/datatype-type.md)
-   [Data Types](../data-types/data-types.md)


