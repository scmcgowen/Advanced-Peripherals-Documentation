# Colony Integrator

!!! picture inline end
    ![Header](https://srendi.de/wp-content/uploads/2021/07/Colony-Integrator.png){ align=right }

The colony integrator can interact with a colony from MineColonies.

<br>

## Overview

| Peripheral Name | Interfaces with | Events | Introduced in |
| --------------- | --------------- | ------ | ------------- |
| colonyIntegrator| MineColonies    | No     | 0.7r        |

## Functions

Example:

```lua
local integrator = peripheral.find("colonyIntegrator") -- Finds the peripheral if one is connected

if integrator == nil then error("colonyIntegrator not found") end

if not integrator.isInColony then error("Block is not in a colony") end

print("Colony name:".. integrator.getColonyName())
print("Currently under attack?".. integrator.isUnderAttack())
for k, v in ipairs(integrator.getCitizens()) do
  print(k, v) -- Prints data of the citizens in the colony
end
```

| Function                        | Returns | Description                                                                |
| ------------------------------- | ------- | -------------------------------------------------------------------------- |
| isInColony()                    | boolean | Returns true if the block is in a colony.                                  |
| isWithin(table position)        | boolean | Returns true if the given coordinates are in a colony.                     |
| getCitizens()                   | table   | Returns a table with all citizens of the colony.                           |
| getColonyID()                   | int     | Returns the id of the colony.                                              |
| getColonyName()                 | string  | Returns the name of the colony.                                            |
| getColonyStyle()                | string  | Returns the style of the colony.                                           |
| isActive()                      | boolean | Returns true if the colony is active(Trusted players are online).          |
| getHappiness()                  | int     | Returns the overall happiness of the colony.                               |
| getLocation()                   | table   | Returns the position of the townhall.                                      |
| isUnderAttack()                 | boolean | Returns true if the colony is currently under attack.                      |
| amountOfCitizens()              | int     | Returns the amount of citizens.                                            |
| maxOfCitizens()                 | int     | Returns the possible max amount of citizens.                               |
| amountOfGraves()                | int     | Returns the amount of graves in the colony.                                |
| getVisitors()                   | table   | Returns a table with all visitors in your tavern of the colony.            |
| getBuildings()                  | table   | Returns a table with all buildings in your colony.                         |
| getWorkOrders()                 | table   | Returns a table with all work orders. Because MineColonies does not provide a good way to read the data of these orders, we return nbt values of the work order. |
| getResearch()                   | table   | Returns all possible researches, currently researches that is being worked on and research that has already been researched. |
| getWorkOrderResources(int id)   | table   | Returns a table with the resources of a work order. You can find out every order and its ID with getWorkOrders().                         |
| getRequests()                   | table   | Returns all requests in any kind of the colony. |
| getBuilderResources(table position) | table   | Returns all resources of the given builder's hut.                       |

## Changelog/Trivia

0.7r
Added the colony integrator