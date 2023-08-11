Return to [[start here]] / [[Mapped Code]]

# `ZTWorldMgr`

Not much known about how this class works yet. We know its name because we have been able to map symbols with their pointers using a function that calls [[BFRegistry]].

The class constructor is at `0x00630CAC`.

# Table of Contents

[[#Structure]]
   [[#Data Members]]
   [[#Member Functions]]

# Structure

## Data Members

The following offsets are added to the `*(0x630CAC)` pointer.

|Member|Offset|Data Type|Member Type|Description|
|---|---|---|---|---|
|`MapX`|`0x34`|int|Variable|Size of currently loaded map in the X dimension|
|`MapY`|`0x38`|int|Variable|Size of currently loaded map in the Y dimension|
|`EntityArray`|`0x80`|ZT Array|Member Variable|Array of all entities in the map|


## Member Functions

These are the only known functions part of this structure at this time.

|Member|Location|Ret Type|Member Type|Description|
|---|---|---|---|---|
||`*(00638040) + 50`|void|virtual function|It's possible that this is a virtual function pointer.|