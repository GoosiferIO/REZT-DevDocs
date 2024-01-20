Return to [start here](app://obsidian.md/start%20here.md) / [Mapped Code](app://obsidian.md/General/Mapped%20Code.md)

# `ZTAIMgr`

Not much known about how this class works yet, but as its namesake suggests, it is dealing with the game AI. We know its name because we have been able to map symbols with their pointers using a function that calls [[BFRegistry]].

The class constructor is at `0x0063536C`.

# Table of Contents

[[#Structure]]
   [[#Member Functions]]

# Structure
## Data Members

The following offsets are added to the `*(0x638048)` pointer.

| Member |  Offset | Data Type | Member Type | Description | 
| ------- | --------------- | ---------| -----| ---- |
| mbr_0 | `0x0`  | vtable | vtable | Point to class cls_0x635324|
| mbr_8 | `0x8`  | vtable | vtable | Point to class cls_0x635324|

## Member Functions

These are the only known functions part of this structure at this time.

| Member | Location | Ret Type | Calling Conv. | Description |
| ---- | ---- | ---- | ---- | ---- |
|  | `*(00638098) + 8` | void |  | It's possible that this is a virtual function. Not much info given by Ghidra, will need other tools to verify. Seems to point to OOAnalyzer::cls_0x62de40::virt_meth_0x59da9f |
| initAIParams | `0052599F` | `uint` | \__thiscall |  |
| ZTAIMgr::virt_meth_0x434AA2 | `00434AA2` | void | \__thiscall | Virtual function. |
