# Macros for WoW Classic

## Show/Hide Player Names

This macro toggles among 3 modes: showing NPCs' names, showing friendly players' names, and showing neither.

I typically turn on NPCs' names in the wild to look out for mobs, and turn it off in town if I don't have to find a specific NPC. But occasionally I need to turn on players' names to quickly find someone nearby.

```
/run local a,b=GetCVarBool("UnitNameNPC"),GetCVarBool("UnitNameFriendlyPlayerName");SetCVar("UnitNameNPC",(not a and not b) and 1 or 0);SetCVar("UnitNameFriendlyPlayerName",(a and not b) and 1 or 0)
```

Original:

```lua
local npcNameVisible = GetCVarBool("UnitNameNPC")
local playerNameVisible = GetCVarBool("UnitNameFriendlyPlayerName")

SetCVar("UnitNameNPC",
    (not npcNameVisible and not playerNameVisible) and 1 or 0)

SetCVar("UnitNameFriendlyPlayerName",
    (npcNameVisible and not playerNameVisible) and 1 or 0)
```
