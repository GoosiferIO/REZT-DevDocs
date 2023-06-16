These functions don't appear to be part of a greater class structure at this time, and so will be defined here. 

Note: Global functions might not be an accurate name but in lieu of a better one, this will be fine for now.

## Cheat Function

- No name for this function has been given yet.
- By renaming a guest or staff member a given name defined by Blue Fang, certain cheats would fire off. 
- It turns out that there is a massive cheat function that acts as a switch board and listening device for these cheats, and it is located at `*(zoo.exe + 0x0044940B)`.
- All of the known cheats are in this switch board function. For a full list of cheats and names that trigger them, please see [ZT1 All Cheats and Easter Eggs](ZT1%20All%20Cheats%20and%20Easter%20Eggs.md).
- Every staff or guest name is explicitly defined as a string and a conditional in the switch statement, so we know they're not serialized anywhere and live inside of the main source code.
- The only cheat whose 'cheat name' *is not* explicitly defined inside of this structure is the [Jonathan Gilmour cheat.](../Mapped/ZTGameMgr.md) This function has not been completely studied, but will help reverse many other areas of the code.