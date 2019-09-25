# Macros for WoW Classic

## Toggle Friendly Units' Names and Nameplates

This macro toggles among 3 modes: showing nameplates of all friendly units, showing only names (instead of nameplates) of NPCs, and showing neither.

```
/run local a,b=GetCVarBool("nameplateShowFriends"),GetCVarBool("UnitNameNPC");SetCVar("nameplateShowFriends",(not a and not b) and 1 or 0);SetCVar("UnitNameNPC",(a and not b) and 1 or 0)
```

Original:

```lua
local nameplateShowFriends = GetCVarBool("nameplateShowFriends")
local UnitNameNPC = GetCVarBool("UnitNameNPC")

SetCVar("nameplateShowFriends",
    (not nameplateShowFriends and not UnitNameNPC) and 1 or 0)

SetCVar("UnitNameNPC",
    (nameplateShowFriends and not UnitNameNPC) and 1 or 0)
```

## Toggle Click To Move

```
/run SetCVar("autoInteract",GetCVarBool("autoInteract") and 0 or 1)
```

Original:

```lua
local autoInteract = GetCVarBool("autoInteract")
SetCVar("autoInteract", autoInteract and 0 or 1)
```
