Return to [start here](app://obsidian.md/start%20here.md) / [Mapped Code](app://obsidian.md/General/Mapped%20Code.md)

ZTHabitatMgr

Not much known about how this class works yet. We know its name because we have been able to map symbols with their pointers using a function that calls [[BFRegistry]].

The class constructor is at `0x0063805C.

# Table of Contents

[[#Structure]]
   [[#Data Members]]
   [[#Member Functions]]
   [[#Other Functions]]

# Related Classes

|Address|Name|Class Type|Description|
|---|---|---|---|
|`0x463737`|ZTHabitatMgr|Base class| |
|`0x632100`| |Potential Parent|Several methods from this classes VTable are called on ZTHabitatMgr |
|`0x6355C8`||Potential parent|First member at runtime points to this VTable|
|`0x6355C0`||Potential Parent|Constructor(?) sets first member to this VTable, however class seems to only contain one virtual deletor|



# Structure

## Data Members

The following offsets are added to the `*(0x63805C)` pointer.

|Member|Offset|Data Type|Member Type|Description|
|---|---|---|---|---|
|`MapX`|`0x08`|int|Variable|Size of currently loaded map in the X dimension|
|`MapY`|`0x0C`|int|Variable|Size of currently loaded map in the Y dimension|
|`ZooEntranceX`|`0x10`|int|Variable|X coord of the zoo entrance object|
|`ZooEntranceY`|`0x14`|int|Variable|Y coord of the zoo entrance object|
|`ExhibitArray`|`0x1c`|ZTArray|Variable|Array of exhibits




## Member Functions

These are the only known functions part of this structure at this time.

|Member|Location|Ret Type|Member Type|Description|
|---|---|---|---|---|
||`0x463737`|vftable_6355c8||Unsure if constructor or destructor; ghidra says destructor but usage suggest constructor|

## Other Functions

Other related functions, `thiscall` or otherwise

|Name|Location|Class|Ret Type|Description|
|---|---|---|---|---|
|WriteExhibitsToFile|`0x479a54`|`0x632100`|uint|Saves ZTHabitatMgr to savefile|
||`0x410d04`|`0x632100`|int|Returns Zoo Gate object|
|WriteExhibitToFile|`0x479b73`|`0x632100`|int|Saves exhibit to savefile|
