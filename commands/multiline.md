## Syntax

**<span style="color:red">/multiline</span> *<span style="color:blue">delimiter</span> command* \[
*<span style="color:blue">delimiter</span> command* \[...\] \]**

## Description

Executes multiple commands using a single line separated by the delimiter.  
  
**Notes**

-   This is useful for keybinds
-   There **must** be a space before and after the defined delimiter. e.g. **/multiline ; command**
-   You do not need to put a space before and after the delimiter separating the individual commands
-   The delimiter is 1 parameter, and the list of commands is 1 parameter, ergo you need a space separating the
    delimiter from the list of commands
-   /call, /return and /delay are line based and their use on a /multiline line is unpredictable.

## Examples

    /if ( ${Target.ID} && ${Target.Type.Equal[NPC]} && !${Me.Combat} ) {
           /multiline ; /echo Attacking ${Target.DisplayName}; /attack on
    }

[Return to Slash Commands](slash-commands.md)


